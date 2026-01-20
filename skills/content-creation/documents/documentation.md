Reference the writing standards in ../writing-standards.md, then create professional documentation following these specifications:

## Documentation Specifications

### Structure Requirements
- **Title**: Clear, descriptive topic in 3-8 words
- **Length**: Varies by type (see below)
- **Format**:
  - Overview/introduction
  - Prerequisites (if applicable)
  - Main content with clear headings
  - Examples and code snippets
  - Troubleshooting (if applicable)
  - Related resources
- **Tone**: Clear and instructional

### Documentation Types

**Technical Documentation** (500-1500 words):
- Purpose: Explain how something works
- Overview (what it is, why it exists)
- Architecture or structure
- Key components and their roles
- How components interact
- Configuration options
- Technical constraints
- Code examples
- References to related documentation

**How-To Guide** (300-800 words):
- Purpose: Walk through a specific task
- What you'll accomplish (outcome)
- Prerequisites (knowledge, access, tools needed)
- Step-by-step instructions (numbered)
- Code snippets or screenshots
- Verification steps (how to confirm it worked)
- Troubleshooting common issues
- Next steps or related guides

**API Documentation** (per endpoint):
- Endpoint description (what it does)
- HTTP method and path
- Authentication requirements
- Request parameters (path, query, body)
- Request examples (with sample code)
- Response format
- Response codes and meanings
- Error handling
- Rate limits or usage notes
- Related endpoints

**Process Documentation** (400-1000 words):
- Purpose: Document a repeatable process
- Process overview (what and why)
- When to use this process
- Roles and responsibilities
- Prerequisites or requirements
- Detailed steps (with decision points)
- Tools or systems involved
- Quality checks or validation
- Exception handling
- Related processes

**Runbook** (300-700 words per scenario):
- Purpose: Operational guide for specific scenarios
- Scenario description (when to use this runbook)
- Symptoms or triggers
- Immediate actions (first 5 minutes)
- Diagnostic steps
- Resolution procedures
- Escalation criteria
- Post-incident tasks
- Prevention measures

### Content Elements
- **Task-Focused**: Written from user's perspective ("you will...")
- **Scannable**: Headings, bullets, short paragraphs
- **Examples**: Show, don't just tell
- **Current**: Review and update regularly
- **Tested**: Steps actually work as written
- **Complete**: No assumed knowledge beyond stated prerequisites

## Prompt for Documentation Creation

Before creating the documentation, gather this information:

1. **Documentation Type**: Technical, How-To, API, Process, Runbook, or Other?

2. **Audience**:
   - Who will use this? (Developers, operators, end users)
   - What's their skill level?
   - What do they already know?

3. **Purpose**: What will readers accomplish or understand?

4. **Scope**: What's included and what's not?

5. **Prerequisites**: What must readers have or know first?

6. **Key Information**:
   - What are the main concepts or steps?
   - What are common pitfalls or confusion points?

7. **Examples Needed**: What should be illustrated with code or screenshots?

8. **Related Documentation**: What should readers reference for more info?

9. **Update Frequency**: How often will this need updating?

## Output Format

I will provide:

1. **Title** (clear and searchable)
2. **Introduction** (overview and audience)
3. **Main Content** with proper structure:
   - Logical sections with clear headings
   - Code examples (if applicable)
   - Visual aids (if applicable)
   - Troubleshooting section
4. **Related Resources**
5. **Brief notes** on maintenance and updates

## Quality Checks Applied

Before delivering, I verify:
- ✓ Clear title that indicates topic
- ✓ Audience and purpose stated upfront
- ✓ Prerequisites listed clearly
- ✓ Steps are numbered and actionable
- ✓ Code examples are complete and tested
- ✓ Screenshots or diagrams referenced where helpful
- ✓ Troubleshooting section included
- ✓ Active voice ("click the button" not "the button should be clicked")
- ✓ Consistent terminology throughout
- ✓ No jargon without explanation
- ✓ Related resources linked

## Example Outputs

### Example: How-To Guide

**Title**: How to Deploy a New Service to Production

**Overview**

This guide walks you through deploying a new service to production using our CI/CD pipeline. You'll set up the deployment configuration, validate it in staging, and promote it to production with zero downtime.

**Time Required**: 30-45 minutes
**Difficulty**: Intermediate

**Prerequisites**

Before starting, ensure you have:
- [ ] Service passing all tests in CI
- [ ] Code merged to `main` branch
- [ ] Production deployment approval from tech lead
- [ ] Access to GitHub Actions and AWS console
- [ ] Familiarity with Docker and our deployment process

**What You'll Need**

- Service repository checked out locally
- Access to `#deployments` Slack channel
- AWS CLI configured with production credentials

**Steps**

**1. Create Deployment Configuration**

Navigate to your service directory and create `deploy/production.yaml`:

```yaml
service:
  name: user-service
  version: ${GIT_SHA}
  replicas: 3

resources:
  cpu: 1000m
  memory: 2Gi

environment:
  - name: DATABASE_URL
    valueFrom: aws-secrets-manager://prod/user-service/db
  - name: LOG_LEVEL
    value: info
```

**2. Validate Configuration**

Run the validation script:

```bash
./scripts/validate-config.sh deploy/production.yaml
```

Expected output:
```
✓ Configuration valid
✓ All required secrets exist
✓ Resource limits within bounds
```

If you see errors, check:
- Secret names match AWS Secrets Manager
- Resource requests don't exceed node capacity
- Environment variables don't contain hardcoded secrets

**3. Deploy to Staging**

Test the deployment in staging first:

```bash
./scripts/deploy.sh staging
```

Monitor the deployment:
```bash
kubectl get pods -n staging -w
```

Wait for all pods to show `Running` status (typically 2-3 minutes).

**4. Run Smoke Tests**

Verify staging deployment:

```bash
./scripts/smoke-test.sh https://staging.example.com
```

Expected output:
```
✓ Health check passed
✓ API endpoints responding
✓ Database connectivity confirmed
✓ All smoke tests passed
```

**5. Announce Deployment**

Post in `#deployments` Slack channel:
```
Deploying user-service v2.1.0 to production
ETA: 10 minutes
Monitoring: https://datadog.com/dashboard/prod-deployments
```

**6. Deploy to Production**

Trigger production deployment:

```bash
./scripts/deploy.sh production
```

The script will:
- Create new pods with updated version
- Wait for health checks to pass
- Gradually shift traffic (10% increments)
- Complete in ~10 minutes

**7. Monitor Deployment**

Watch the rollout progress:

```bash
kubectl rollout status deployment/user-service -n production
```

Monitor key metrics in Datadog:
- Error rate (should stay <0.1%)
- Latency p95 (should stay <200ms)
- CPU/Memory (should stabilize within 5 minutes)

**8. Verify Production**

Run production smoke tests:

```bash
./scripts/smoke-test.sh https://api.example.com
```

Check that:
- [ ] All pods are running
- [ ] Health endpoint returns 200
- [ ] Error rates are normal
- [ ] No alerts firing

**9. Update Status**

Once verified, update Slack:
```
✓ user-service v2.1.0 deployed successfully
Pods: 3/3 running
No errors detected
```

**Troubleshooting**

**Issue**: Pods stuck in `Pending` state

**Cause**: Insufficient cluster capacity

**Solution**:
```bash
# Check node resources
kubectl describe nodes | grep -A 5 "Allocated resources"

# If needed, scale up node group
aws autoscaling set-desired-capacity \
  --auto-scaling-group-name prod-nodes \
  --desired-capacity 6
```

---

**Issue**: Health checks failing

**Cause**: Database connection timeout

**Solution**:
1. Check security group rules allow database access
2. Verify database credentials in Secrets Manager
3. Check database connection limit (max_connections)

---

**Issue**: High error rate after deployment

**Cause**: Breaking change in API

**Solution**:
```bash
# Immediate rollback
kubectl rollout undo deployment/user-service -n production

# Post in Slack
echo "Rolling back user-service deployment due to errors"
```

**Next Steps**

After successful deployment:
- Monitor for 24 hours for any delayed issues
- Update changelog in repository
- Close deployment ticket in Jira
- Schedule post-deployment review (if major release)

**Related Documentation**

- [CI/CD Pipeline Overview](../overview/cicd.md)
- [Monitoring and Alerting Guide](../ops/monitoring.md)
- [Rollback Procedures](../ops/rollback.md)
- [Production Incident Response](../ops/incidents.md)

**Why it works**:
- Clear prerequisites prevent getting stuck mid-process
- Numbered steps are easy to follow
- Code examples are copy-pasteable
- Verification steps at each stage
- Troubleshooting section addresses common issues
- Related documentation helps readers go deeper

---

### Example: API Documentation

**Title**: User Authentication API

**Overview**

The Authentication API provides endpoints for user login, logout, and token refresh. All authenticated endpoints require a valid JWT token in the `Authorization` header.

**Base URL**: `https://api.example.com/v1/auth`

---

**POST /login**

Authenticate a user and receive access and refresh tokens.

**Authentication**: None (public endpoint)

**Request Body**:
```json
{
  "email": "user@example.com",
  "password": "securepassword123"
}
```

**Parameters**:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| email | string | Yes | User's email address |
| password | string | Yes | User's password (min 8 characters) |

**Response** (200 OK):
```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expires_in": 3600,
  "token_type": "Bearer"
}
```

**Response Fields**:

| Field | Type | Description |
|-------|------|-------------|
| access_token | string | JWT token for authenticated requests (1 hour expiry) |
| refresh_token | string | Token for refreshing access token (30 day expiry) |
| expires_in | integer | Access token lifetime in seconds |
| token_type | string | Token type (always "Bearer") |

**Error Responses**:

**401 Unauthorized**:
```json
{
  "error": "invalid_credentials",
  "message": "Email or password is incorrect"
}
```

**429 Too Many Requests**:
```json
{
  "error": "rate_limit_exceeded",
  "message": "Too many login attempts. Try again in 15 minutes."
}
```

**Example Request** (cURL):
```bash
curl -X POST https://api.example.com/v1/auth/login \
  -H "Content-Type: application/json" \
  -d '{
    "email": "user@example.com",
    "password": "securepassword123"
  }'
```

**Example Request** (JavaScript):
```javascript
const response = await fetch('https://api.example.com/v1/auth/login', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    email: 'user@example.com',
    password: 'securepassword123'
  })
});

const { access_token, refresh_token } = await response.json();
```

**Rate Limits**:
- 5 requests per minute per IP address
- 20 requests per hour per IP address

After exceeding limits, wait for the specified time or contact support.

**Security Notes**:
- Always use HTTPS in production
- Store tokens securely (never in localStorage for sensitive apps)
- Implement token refresh before expiry
- Rotate refresh tokens regularly

---

**POST /refresh**

Refresh an expired access token using a refresh token.

**Authentication**: None (uses refresh token in body)

**Request Body**:
```json
{
  "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

**Response** (200 OK):
```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expires_in": 3600,
  "token_type": "Bearer"
}
```

**Error Responses**:

**401 Unauthorized**:
```json
{
  "error": "invalid_token",
  "message": "Refresh token is invalid or expired"
}
```

**Example Request**:
```javascript
const response = await fetch('https://api.example.com/v1/auth/refresh', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    refresh_token: storedRefreshToken
  })
});

const { access_token } = await response.json();
```

**Related Endpoints**:
- [POST /auth/logout](logout.md) - Invalidate tokens
- [GET /auth/me](me.md) - Get current user info
- [POST /users](../users/create.md) - Create new user account

**Why it works**:
- Each endpoint fully documented (not just partial examples)
- Request/response examples in multiple languages
- Error scenarios documented with actual error codes
- Security notes included
- Rate limits clearly stated
- Related endpoints linked

---

### Example: Runbook

**Title**: Database Connection Pool Exhaustion

**Scenario**

Use this runbook when you see alerts for "Database connection pool exhausted" or when applications can't connect to the database despite the database being up.

**Symptoms**

- Alert: "PostgreSQL connection pool at 95%+"
- Application logs: `FATAL: remaining connection slots are reserved`
- Users reporting 500 errors or timeouts
- Database itself is responsive (can connect directly)

**Impact**: High - Users cannot complete transactions

**Immediate Actions** (First 5 Minutes)

1. **Verify the issue**:
   ```bash
   # Check current connections
   psql -h prod-db.example.com -U admin -c \
     "SELECT count(*) FROM pg_stat_activity;"
   ```

   If count is near `max_connections` (default 100), pool is exhausted.

2. **Check for stuck connections**:
   ```bash
   # Find long-running queries
   psql -h prod-db.example.com -U admin -c \
     "SELECT pid, age(clock_timestamp(), query_start), usename, query
      FROM pg_stat_activity
      WHERE state != 'idle' AND query_start < now() - interval '5 minutes'
      ORDER BY query_start;"
   ```

3. **Post in #incidents**:
   ```
   🔴 Database connection pool exhausted
   Impact: Users seeing 500 errors
   Investigating stuck connections
   ```

**Diagnosis**

**Check for connection leaks**:
```bash
# Connections by application
psql -h prod-db.example.com -U admin -c \
  "SELECT application_name, count(*)
   FROM pg_stat_activity
   GROUP BY application_name
   ORDER BY count DESC;"
```

Look for applications with unusually high connection counts.

**Check for slow queries**:
```bash
# Queries running >1 minute
psql -h prod-db.example.com -U admin -c \
  "SELECT pid, now() - query_start AS duration, query
   FROM pg_stat_activity
   WHERE state = 'active' AND now() - query_start > interval '1 minute';"
```

**Resolution**

**Option 1: Kill Stuck Queries** (if specific queries identified)

```bash
# Kill specific query by PID
psql -h prod-db.example.com -U admin -c \
  "SELECT pg_terminate_backend(12345);"
```

Replace `12345` with actual PID from diagnostic query.

**Option 2: Restart Leaking Application** (if specific app identified)

```bash
# Scale down and up to force connection reset
kubectl scale deployment user-service --replicas=0 -n production
kubectl scale deployment user-service --replicas=3 -n production
```

Monitor connection count - should drop immediately.

**Option 3: Increase Connection Limit** (temporary mitigation)

```bash
# Connect to database
psql -h prod-db.example.com -U admin postgres

# Increase limit temporarily
ALTER SYSTEM SET max_connections = 200;

# Restart database (requires downtime - coordinate first)
# aws rds reboot-db-instance --db-instance-identifier prod-db
```

**Warning**: This is temporary. Fix the root cause (connection leak).

**Verification**

After resolution:

1. **Check connection count**:
   ```bash
   psql -h prod-db.example.com -U admin -c \
     "SELECT count(*) FROM pg_stat_activity;"
   ```
   Should be <50 for normal operation.

2. **Verify application health**:
   ```bash
   curl https://api.example.com/health
   ```
   Should return 200 OK.

3. **Check error rates**:
   - Datadog: Database connection errors should drop to 0
   - Application logs: No more "connection pool exhausted" errors

**Escalation**

Escalate to database team if:
- Cannot identify source of leaked connections
- Killing queries/restarting apps doesn't resolve issue
- Issue recurs within 1 hour

**Contact**: #database-team or page @dba-oncall

**Post-Incident Tasks**

1. **Document timeline** in incident ticket
2. **Identify root cause**:
   - Check application logs for connection leaks
   - Review recent code changes
   - Analyze query patterns before incident
3. **Create fix** (e.g., add connection pooling, fix connection leak)
4. **Update monitoring**:
   - Lower alert threshold (90% instead of 95%)
   - Add per-application connection monitoring
5. **Schedule post-mortem** within 48 hours

**Prevention**

To prevent recurrence:
- Implement connection pooling in applications (e.g., PgBouncer)
- Set connection timeouts (don't hold connections open indefinitely)
- Monitor per-application connection usage
- Regular query performance reviews
- Load testing to identify connection limits

**Related Runbooks**

- [Database High CPU Usage](db-high-cpu.md)
- [Slow Query Investigation](slow-queries.md)
- [Database Failover Procedure](db-failover.md)

**Why it works**:
- Clear scenario description (when to use this)
- Symptoms listed upfront (easy to confirm you're in right place)
- Immediate actions (what to do first)
- Diagnostic steps with actual commands
- Multiple resolution options (with tradeoffs)
- Verification steps (how to confirm it's fixed)
- Escalation criteria (when to call for help)
- Post-incident and prevention sections

---

Now, please provide the information requested in the "Prompt for Documentation Creation" section, and I'll create your professional documentation.
