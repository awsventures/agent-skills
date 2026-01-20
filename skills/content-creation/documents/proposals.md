Reference the writing standards in ../writing-standards.md, then create a professional proposal following these specifications:

## Proposal Specifications

### Structure Requirements
- **Title**: Clear value proposition in 5-10 words
- **Length**: 800-1500 words (brief proposal) OR 1500-2500 words (detailed proposal)
- **Format**:
  - Executive summary
  - Problem/opportunity statement
  - Proposed solution
  - Benefits and outcomes
  - Implementation approach
  - Timeline and milestones
  - Budget/resources required
  - Next steps
- **Tone**: Persuasive but professional

### Proposal Types

**Project Proposal** (1000-1500 words):
- Executive summary (150 words)
- Business problem or opportunity
- Proposed solution (what you'll build/do)
- Expected outcomes and success metrics
- Project approach and methodology
- Timeline with key milestones
- Resource requirements (team, budget, tools)
- Risk assessment and mitigation
- Success criteria
- Approval and next steps

**Budget Proposal** (800-1200 words):
- Executive summary (100 words)
- Current situation and need
- Requested budget amount
- Budget breakdown (detailed line items)
- Justification for each expense
- Expected ROI or value
- Alternative options considered
- Impact if not funded
- Approval process

**Process Improvement Proposal** (1000-1500 words):
- Executive summary (150 words)
- Current process description
- Problems and inefficiencies (with data)
- Proposed new process
- Expected improvements (time, cost, quality)
- Implementation plan
- Change management approach
- Timeline
- Resources needed
- Metrics for measuring success

**Technology Proposal** (1200-1800 words):
- Executive summary (150 words)
- Business need and current gaps
- Proposed technology solution
- Technical approach and architecture
- Integration with existing systems
- Benefits (efficiency, cost savings, capabilities)
- Implementation phases
- Timeline and milestones
- Budget (software, hardware, services)
- Training and support plan
- Risk mitigation
- Success metrics

### Content Elements
- **Problem First**: Establish why this matters before pitching solution
- **Specific Benefits**: Quantify outcomes where possible
- **Realistic**: Set achievable expectations
- **Evidence**: Support claims with data or examples
- **Clear Ask**: Be explicit about what you need approved
- **Risk Awareness**: Acknowledge challenges and show mitigation plans

## Prompt for Proposal Creation

Before creating the proposal, gather this information:

1. **Proposal Type**: Project, Budget, Process Improvement, Technology, or Other?

2. **Audience**:
   - Who makes the decision? (Executive, manager, committee)
   - What's their priority? (Cost, risk, speed, quality)
   - What's their technical level?

3. **Problem/Opportunity**: What are you solving or seizing? (1-2 sentences)

4. **Proposed Solution**: What are you asking to do? (1-2 sentences)

5. **Expected Outcomes**: What specific benefits or results?

6. **Budget/Resources**: What do you need?
   - Money
   - People (FTEs, hours)
   - Tools or technology
   - Time

7. **Timeline**: How long will this take? Key milestones?

8. **Success Metrics**: How will you measure success?

9. **Alternatives Considered**: What other options did you evaluate?

10. **Risks**: What could go wrong? How will you mitigate?

11. **Urgency**: Why now? What's the deadline or trigger?

## Output Format

I will provide:

1. **Title** (value-focused)
2. **Executive Summary** (standalone decision brief)
3. **Proposal Body** with clear structure:
   - Problem/opportunity
   - Proposed solution
   - Benefits and outcomes
   - Implementation approach
   - Timeline and budget
   - Risk mitigation
4. **Clear call-to-action** (what you need approved)
5. **Brief notes** on presentation and delivery

## Quality Checks Applied

Before delivering, I verify:
- ✓ Executive summary enables decision without reading full proposal
- ✓ Problem clearly established before solution
- ✓ Benefits are specific and quantified
- ✓ Timeline is realistic
- ✓ Budget is detailed and justified
- ✓ Risks acknowledged with mitigation
- ✓ Success metrics are measurable
- ✓ Clear next steps and approval process
- ✓ Persuasive but not overselling
- ✓ Professional tone throughout

## Example Outputs

### Example: Technology Proposal

**Title**: Implement Automated Testing Framework - Reduce Defects by 40%

**Executive Summary**

I'm proposing we implement an automated testing framework to address our increasing defect rates and lengthening release cycles. Current manual testing takes 120 hours per release and catches only 60% of defects before production. An automated framework will reduce testing time to 20 hours, catch 85% of defects pre-production, and enable daily releases instead of monthly. Implementation requires $75K investment ($50K tools, $25K training) and 12 weeks. Expected payback: 6 months through reduced defect remediation costs ($15K/month currently). Risk: 12-week timeline assumes no major technical blockers; mitigation includes proof-of-concept phase to validate approach.

**Current Situation**

Our release cycle has grown from 2 weeks to 6 weeks over the past year. Root cause: manual testing can't keep pace with development velocity.

**The Problem**

**Testing Bottleneck**:
- Manual testing: 120 hours per release (3 testers, 1 week)
- Test coverage: 60% of critical paths
- Defects reaching production: 12-15 per release
- Cost to fix production defects: $15K per month average

**Release Delays**:
- Planned cycle: 2 weeks
- Actual cycle: 6 weeks (testing adds 4 weeks)
- Business impact: Features delayed, competitive disadvantage

**Quality Issues**:
- Production incidents: 3-4 per month
- Customer-reported bugs: 8-10 per month
- Reputation impact: NPS declined from 45 to 38

**Proposed Solution**

Implement automated testing framework covering:
1. Unit tests (developer-written, run on commit)
2. Integration tests (automated API and service tests)
3. UI tests (critical user paths automated)
4. Performance tests (load and stress scenarios)

**Technical Approach**:
- Framework: Playwright for UI, Jest for unit/integration
- CI/CD integration: GitHub Actions
- Test environment: Containerized test infrastructure
- Reporting: Automated dashboards and alerts

**Expected Outcomes**

**Quality Improvements**:
- Defect detection: 60% → 85% pre-production
- Production incidents: 3-4/month → 1/month
- Test coverage: 60% → 90% of critical paths

**Efficiency Gains**:
- Testing time: 120 hours → 20 hours per release
- Release cycle: 6 weeks → 2 weeks
- Developer productivity: +15% (faster feedback)

**Cost Savings**:
- Defect remediation: $15K/month → $5K/month
- Testing labor: 120 hours/month → 20 hours/month
- **Net savings**: $10K/month after 6-month payback

**Implementation Plan**

**Phase 1: Foundation** (Weeks 1-4)
- Select and configure testing tools
- Set up test infrastructure
- Train development team (2-day workshop)
- Establish testing standards and practices

**Phase 2: Core Coverage** (Weeks 5-8)
- Automate top 20 critical user paths (80% of usage)
- Implement unit test requirements (>70% coverage)
- Integrate with CI/CD pipeline
- Create automated reporting

**Phase 3: Expansion** (Weeks 9-12)
- Complete remaining test coverage
- Add performance testing
- Optimize test execution (parallel runs)
- Document processes and runbooks

**Budget**

| Item | Cost | Justification |
|------|------|---------------|
| Playwright Enterprise | $20K | UI testing framework with support |
| Test Infrastructure | $15K | Cloud resources for test environments |
| CI/CD Enhancements | $10K | GitHub Actions enterprise features |
| Training & Consulting | $25K | 2-day workshop + 40 hours consulting |
| Contingency (10%) | $5K | Unexpected tool or infrastructure needs |
| **Total** | **$75K** | |

**Return on Investment**:
- Monthly savings: $10K (defect reduction + efficiency)
- Payback period: 6 months
- Year 1 ROI: 60% ($75K investment, $120K savings)

**Risk Assessment**

**Technical Risks**:
- **Risk**: Framework doesn't work with legacy components
- **Mitigation**: 2-week proof-of-concept before full commitment
- **Impact if occurs**: 2-week timeline delay

**Adoption Risks**:
- **Risk**: Developers resist writing automated tests
- **Mitigation**: Include in code review standards, provide training and support
- **Impact if occurs**: Slower test coverage growth (extend Phase 3 by 4 weeks)

**Resource Risks**:
- **Risk**: Key team members unavailable during implementation
- **Mitigation**: Cross-train two developers, schedule around planned leave
- **Impact if occurs**: 2-week timeline delay

**Success Metrics**

We'll measure success by:
1. **Test coverage**: 90% of critical paths by Week 12
2. **Defect detection**: 85% caught pre-production by Month 3
3. **Release cycle**: 2-week average by Month 4
4. **Production incidents**: <1 per month by Month 6
5. **Developer satisfaction**: >80% positive on testing tools survey

**Why This Matters Now**

Our main competitor ships features weekly while we're stuck at monthly releases. We've lost two major deals in Q4 because prospects needed faster feature delivery. Without automated testing, we can't compete on speed without sacrificing quality.

**Next Steps**

1. **Approve proposal**: January 15
2. **Select tools**: January 22 (2-week proof-of-concept)
3. **Begin implementation**: February 1
4. **Complete rollout**: April 30
5. **Measure results**: May-July (3-month evaluation)

I'm requesting approval to proceed with the 2-week proof-of-concept starting January 22. This will validate the technical approach before committing the full $75K budget.

**Why it works**:
- Executive summary provides complete picture and decision criteria
- Problem established with specific data (not vague pain points)
- Solution is concrete and technical but explained clearly
- Benefits quantified (40% defect reduction, $10K monthly savings)
- Timeline is realistic with specific phases
- Budget justified line by line
- Risks acknowledged with mitigation plans
- Clear ROI calculation
- Specific success metrics
- Clear ask (approval for proof-of-concept, not full commitment)

---

### Example: Process Improvement Proposal

**Title**: Streamline Code Review Process - Cut Review Time by 50%

**Executive Summary**

Our code review process takes 3-5 days per PR, creating a bottleneck that delays releases and frustrates developers. I'm proposing a streamlined review process using automated checks, clear guidelines, and dedicated review time blocks. Expected outcomes: review time reduced to 1-2 days, developer satisfaction improved, code quality maintained or improved. Implementation requires minimal investment ($5K for tools) and 2 weeks to roll out. Primary change: shift from ad-hoc reviews to structured daily review blocks and automated quality checks.

**Current Process**

Developers submit PRs and wait for reviews. Reviewers check when they have time (usually end of day or between meetings). Average review cycle: 3-5 days from submission to merge.

**The Problem**

**Slow Reviews**:
- Average time to first review: 24-36 hours
- Average time to approval: 3-5 days
- PRs requiring multiple review rounds: 60%

**Developer Impact**:
- Context switching while waiting for reviews
- Stale PRs requiring conflict resolution
- Frustration scores in developer survey: 6.2/10

**Business Impact**:
- Release delays (waiting for PR approvals)
- Reduced velocity (developers blocked)
- Quality issues from rushed reviews

**Root Causes**

Analysis of 200 PRs from last quarter:
1. **No dedicated review time** (40% of delays): Reviewers fit it around other work
2. **Unclear review criteria** (30% of delays): Back-and-forth on subjective issues
3. **Large PRs** (20% of delays): 500+ line changes take too long to review
4. **Manual quality checks** (10% of delays): Reviewers catch issues that tools should find

**Proposed New Process**

**1. Automated Quality Gates**
Before human review, automated checks verify:
- Code formatting (Prettier)
- Linting (ESLint)
- Test coverage (>70% for new code)
- Security scans (Snyk)

**2. PR Size Guidelines**
- Target: <250 lines per PR
- Automatic warning for PRs >500 lines
- Guidance on splitting large changes

**3. Structured Review Time**
- Daily review block: 10-11 AM (all reviewers)
- Priority queue: PRs >24 hours get first attention
- Review assignment: Round-robin with expertise matching

**4. Clear Review Criteria**
Reviewers focus on:
- Logic and correctness (does it work?)
- Design and architecture (is it well-structured?)
- Tests and edge cases (is it validated?)
- NOT: formatting, style, minor naming (automated checks handle this)

**Expected Improvements**

| Metric | Current | Target | Improvement |
|--------|---------|--------|-------------|
| Time to first review | 24-36 hrs | 4-8 hrs | 75% faster |
| Time to approval | 3-5 days | 1-2 days | 50% faster |
| Review quality | Variable | Consistent | Standardized |
| Developer satisfaction | 6.2/10 | 8.5/10 | +37% |

**Implementation Plan**

**Week 1: Setup**
- Configure automated quality tools
- Create PR size guidelines and templates
- Draft review criteria checklist
- Schedule daily review blocks

**Week 2: Rollout**
- Train team on new process (1-hour session)
- Begin daily review blocks
- Monitor first week metrics
- Gather feedback and adjust

**Ongoing**:
- Weekly review metrics dashboard
- Monthly retrospective on process effectiveness
- Continuous improvement based on team feedback

**Investment Required**

| Item | Cost |
|------|------|
| Snyk security scanning | $3K/year |
| Code quality tools | $2K/year |
| **Total** | **$5K/year** |

Time investment:
- Setup: 16 hours (1 person, 2 weeks)
- Daily review blocks: 1 hour/day (already doing reviews, just structured)
- No additional time required (we're making existing time more effective)

**Change Management**

**Developer Concerns**:
- "Daily review blocks interrupt deep work"
  - Response: Consistent 10-11 AM time allows planning around it
- "250-line PR limit is too restrictive"
  - Response: Guideline, not hard rule; large changes can be staged

**Reviewer Concerns**:
- "1 hour/day for reviews is too much"
  - Response: Most reviewers already spend this time, just spread out
- "Automated checks might miss important issues"
  - Response: These catch mechanical issues so reviewers can focus on logic and design

**Success Metrics**

Track for 3 months:
1. **Average time to first review**: Target <8 hours
2. **Average time to approval**: Target <2 days
3. **PR size**: Target 70% under 250 lines
4. **Developer satisfaction**: Target 8.5/10
5. **Code quality**: Defects per release (should maintain or improve)

**Next Steps**

1. **Get team feedback**: January 10 (30-minute discussion)
2. **Refine proposal**: January 12 (incorporate feedback)
3. **Approve and start setup**: January 15
4. **Team training**: January 22
5. **Launch new process**: January 29
6. **First retrospective**: February 26

I'm looking for approval to proceed with setup starting January 15, with full rollout on January 29.

**Why it works**:
- Problem clearly established with data
- Root cause analysis shows why current process fails
- Solution addresses each root cause specifically
- Expected improvements are realistic (50%, not 90%)
- Minimal investment required
- Change management addresses concerns proactively
- Clear success metrics
- Phased approach (setup, rollout, measure)

---

Now, please provide the information requested in the "Prompt for Proposal Creation" section, and I'll create your professional proposal.
