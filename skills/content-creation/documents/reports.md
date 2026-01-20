Reference the writing standards in ../writing-standards.md, then create a professional report following these specifications:

## Report Specifications

### Structure Requirements
- **Title**: Clear, specific topic in 5-10 words
- **Length**: 500-1500 words (brief report) OR 1500-3000 words (detailed report)
- **Format**:
  - Executive summary (100-200 words)
  - Introduction/background
  - Main sections with clear headings
  - Data and findings
  - Conclusions and recommendations
  - Appendices (if needed)
- **Tone**: Professional and objective

### Report Types

**Status Report** (500-800 words):
- Executive summary (100 words)
- Period covered (dates)
- Accomplishments and milestones
- Metrics and KPIs
- Issues and risks
- Next period priorities
- Resources needed

**Analysis Report** (1000-1500 words):
- Executive summary (150 words)
- Problem or question being analyzed
- Methodology and data sources
- Findings (organized by theme)
- Data visualization references
- Key insights
- Recommendations
- Next steps

**Incident Report** (800-1200 words):
- Executive summary (100 words)
- Incident overview (what, when, where)
- Timeline of events
- Root cause analysis
- Impact assessment
- Response actions taken
- Preventive measures recommended
- Follow-up items

**Performance Report** (600-1000 words):
- Executive summary (100 words)
- Reporting period
- Key metrics and targets
- Performance highlights (what went well)
- Performance challenges (what didn't)
- Trend analysis
- Comparative data (vs. previous periods)
- Action plan

### Content Elements
- **Executive Summary**: Standalone overview that busy readers can use
- **Data**: Specific numbers, percentages, dates
- **Structure**: Clear headings and subheadings for navigation
- **Visuals**: Reference to charts, graphs, tables (if applicable)
- **Objectivity**: Present facts, then interpretations separately
- **Actionability**: Clear next steps or recommendations

## Prompt for Report Creation

Before creating the report, gather this information:

1. **Report Type**: Status, Analysis, Incident, Performance, or Other?

2. **Audience**:
   - Who will read this? (Executives, managers, technical team, board)
   - What's their familiarity with the topic?

3. **Purpose**: What decision or action should this report support?

4. **Reporting Period**: What timeframe does this cover?

5. **Key Message**: What's the most important takeaway in one sentence?

6. **Data Available**: What metrics, findings, or information do you have?

7. **Context**: What background information does the reader need?

8. **Recommendations**: What actions are you proposing (if any)?

9. **Length Preference**: Brief (500-800 words) or Detailed (1000-1500 words)?

10. **Urgency**: Is this routine reporting or time-sensitive?

## Output Format

I will provide:

1. **Title** (clear and descriptive)
2. **Executive Summary** (standalone overview)
3. **Report Body** with proper structure:
   - Introduction/background
   - Main sections with headings
   - Data and findings
   - Conclusions
   - Recommendations
4. **Brief notes** on formatting and delivery

## Quality Checks Applied

Before delivering, I verify:
- ✓ Executive summary is standalone and complete
- ✓ Data and facts presented clearly
- ✓ Headings create clear structure
- ✓ Objective tone throughout
- ✓ Key findings highlighted
- ✓ Recommendations are specific and actionable
- ✓ Appropriate length for report type
- ✓ Scannable format (bullets, headings, short paragraphs)
- ✓ Professional but accessible language
- ✓ Clear next steps

## Example Outputs

### Example: Status Report

**Title**: Q4 2025 Infrastructure Migration - Status Report

**Executive Summary**

The Q4 infrastructure migration is 75% complete and on track for March 15 delivery. We've successfully migrated dev and staging environments with zero downtime. Production cutover is scheduled for March 15, pending final security sign-off by March 10. The project remains on budget ($450K of $500K spent) and timeline. Primary risk: security approval delay could push production cutover to March 22.

**Project Overview**

**Period Covered**: October 1 - December 31, 2025
**Status**: On Track (Green)

**Accomplishments**

Completed during this period:
• Migrated 12 development environments (Oct 15-Nov 10)
• Migrated 4 staging environments (Nov 15-Dec 1)
• Completed failover testing with 99.9% success rate
• Trained 40 engineers on new infrastructure
• Updated all deployment documentation

**Key Metrics**

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Environments Migrated | 16 | 16 | ✓ |
| Downtime During Migration | <30 min | 12 min | ✓ |
| Budget Remaining | 10% | 10% | ✓ |
| Team Training Completion | 90% | 95% | ✓ |

**Current Risks**

**High Priority**:
- Security team sign-off delayed due to holiday schedules
- Mitigation: Daily check-ins scheduled, backup date of March 22 established

**Medium Priority**:
- Two team members out during production cutover week
- Mitigation: Cross-training completed, backup coverage identified

**Next Period Priorities**

January - March 2026:
1. Complete security review and obtain final sign-off (Target: March 10)
2. Execute production cutover (Target: March 15)
3. Monitor production environment for 30 days
4. Conduct post-migration review and lessons learned
5. Archive legacy infrastructure

**Resources Needed**

- Security team: 20 hours for final review (Jan-Feb)
- Infrastructure team: Full availability March 13-17 for cutover
- Budget: $50K remaining for contingency

**Why it works**:
- Executive summary gives complete picture upfront
- Clear status indicator (On Track - Green)
- Metrics show objective progress
- Risks identified with mitigation plans
- Specific next steps with dates and ownership

---

### Example: Analysis Report

**Title**: Email System Performance Analysis - December 2025

**Executive Summary**

Analysis of December email system performance reveals a 40% increase in delivery failures compared to November. Root cause: ISP throttling due to reputation score drop from 8.5 to 6.2. Primary contributors: (1) spike in complaint rates from new marketing campaign, (2) three blacklist incidents from compromised accounts. Recommendations: pause bulk sends, implement stricter authentication, rebuild reputation over 60-90 days. Estimated recovery cost: $15K-$25K in deliverability tools and consultant fees.

**Background**

The marketing team reported declining email open rates in mid-December. IT investigated and found increased bounce rates and delivery failures across all campaigns.

**Analysis Scope**

- **Period Analyzed**: November 1 - December 31, 2025
- **Data Sources**: Email platform logs, ISP feedback loops, blacklist monitoring
- **Methodology**: Comparative analysis of delivery metrics, reputation scores, and complaint rates

**Findings**

**1. Delivery Rate Decline**
- November delivery rate: 94.2%
- December delivery rate: 56.8%
- Decline: 40% (significant threshold: 15%)

**2. Reputation Score Drop**
- November sender score: 8.5/10 (excellent)
- December sender score: 6.2/10 (poor)
- Contributing factors:
  - Complaint rate increased from 0.02% to 0.18%
  - Blacklist appearances: 3 incidents
  - Authentication failures: 5% of sends

**3. Campaign Analysis**
New product launch campaign (Dec 10-15) sent to 500K contacts:
- Used purchased list (not verified)
- No prior engagement from 78% of recipients
- Complaint rate: 0.4% (industry standard: <0.1%)
- This single campaign triggered ISP throttling

**4. Account Security**
Three user accounts compromised (Dec 12-14):
- Sent 45K spam messages before detection
- Resulted in blacklist additions at Spamhaus and SURBL
- Average detection time: 8 hours (industry best practice: <1 hour)

**Key Insights**

The reputation drop wasn't gradual decline but acute damage from two specific events: the unvetted campaign launch and compromised accounts. Both are preventable with proper processes.

Recovery will take 60-90 days because ISPs use rolling averages. We can't fix this quickly; we need consistent good behavior over time.

**Recommendations**

**Immediate Actions** (This Week):
1. Pause all bulk email sends until reputation recovers
2. Remove purchased lists from platform
3. Implement mandatory 2FA for all users
4. Engage deliverability consultant ($5K-$10K)

**Short-term** (Next 30 Days):
1. Implement DMARC authentication (currently only SPF)
2. Set up real-time compromise detection (<15 min alert)
3. Create list hygiene process (verify before import)
4. Rebuild sender reputation with engaged subscribers only

**Long-term** (60-90 Days):
1. Develop email governance policy
2. Train marketing team on deliverability best practices
3. Implement gradual send volume increase (10% weekly)
4. Monitor reputation scores weekly

**Estimated Costs**:
- Deliverability consultant: $5K-$10K
- Authentication tools: $3K-$5K
- Security enhancements: $7K-$10K
- **Total**: $15K-$25K

**Next Steps**

1. Present findings to marketing leadership (Jan 10)
2. Obtain budget approval for consultant and tools (Jan 15)
3. Implement immediate security measures (Jan 20)
4. Begin reputation rebuild program (Feb 1)

**Why it works**:
- Executive summary provides complete picture and bottom-line cost
- Clear data showing the problem
- Root cause identified specifically
- Recommendations are prioritized and actionable
- Realistic timeline (60-90 days, not "we'll fix it quickly")
- Specific costs and next steps

---

Now, please provide the information requested in the "Prompt for Report Creation" section, and I'll create your professional report.
