---
name: billing-and-litigation-budget
description: |
  Use this skill when the user needs to track or manage attorney hours, expert fees, and investigation costs; control litigation spend; or prepare timesheets or expense statements for clients.
  Typical trigger scenarios include, but are not limited to:
  - Mentions of keywords such as "billable hours," "expert fees," "investigation costs," "case costs," "timesheet," "expense statement," "budget," or "cost control"
  - Questions about a particular attorney's hours, a matter's case costs, or litigation spend
  - Requests to deliver attorney hour summaries, case timesheets, or case expense statements for client delivery or reimbursement
  - Need to prepare a budget, monitor budget execution, or analyze budget variance for a matter or ongoing (retainer) legal services (常法服务)
  - Need to assess litigation cost versus expected benefit and perform litigation economics analysis
---

> **Chinese source (authoritative):** [`../../skills/billing-and-litigation-budget/SKILL.md`](../../skills/billing-and-litigation-budget/SKILL.md)

# Time Billing and Litigation Budget Control

## Overview Table

| Item | Content |
|------|------|
| **Capability Name** | Time Billing and Litigation Budget Control |
| **Capability ID** | 30 |
| **Capability Type** | Legal Practice Management |
| **Core Functions** | Manage attorney hours, expert fees, and investigation costs; prepare and monitor litigation budgets; keep litigation costs under control |
| **Inputs** | Matter information, role time records, expense receipts, budget targets, rate schedules |
| **Outputs** | Timesheets, expense statements, budget execution reports, cost variance analyses, litigation economics assessments |
| **Related Capabilities** | Full Matter Lifecycle Planning (obtain matter milestones); Legal Document Generation (issue formal invoices/bills) |
| **Risk Level** | Medium (billing errors may lead to client disputes or firm losses) |

## Legal Disclaimer

> **Important notices:**
> 1. The time-tracking and fee-management methods in this skill are for reference only. Actual billing must follow the Measures for the Administration of Lawyers' Service Fees (律师服务收费管理办法) and local bar association fee standards.
> 2. Hourly billing requires prior agreement with the client on billing method, rates, and billing granularity (typically 0.1 hour or 6 minutes).
> 3. Contingency (风险代理), fixed-fee, and hourly billing modes use different cost-accounting logic and must be handled separately.
> 4. Client billing data must be properly safeguarded to ensure data security and confidentiality.
> 5. Budget control is for internal management reference only and does not constitute a service commitment to the client.

## I. Core Concepts

### 1.1 Billing Mode Classification

| Billing Mode | Description | Typical Use Cases | Budget Control Focus |
|----------|------|----------|-------------|
| **Hourly billing** | Actual hours worked × hourly rate | Litigation; complex non-contentious matters | Precise time recording; control total hours |
| **Fixed fee** | One-time or staged fixed fee | Standardized legal services (contract review; ongoing/retainer legal services 常法) | Keep actual effort within the agreed fee |
| **Contingency / risk agency (风险代理)** | Base fee + percentage of outcome | Dispute resolution; enforcement matters | Ensure base fee covers costs; treat success fee as upside |
| **Hybrid billing** | Combination of hourly + fixed + contingency | Large, complex projects | Manage by module; account separately |

### 1.2 Cost Components

```
Total Litigation Cost
├── Internal Labor Cost
│   ├── Partner hours × partner rate
│   ├── Lead counsel hours × attorney rate
│   ├── Paralegal / associate hours × assistant rate
│   └── Intern hours × intern rate (usually non-billable or discounted)
├── External Expert Fees
│   ├── Appraisal / forensic fees (judicial appraisal 司法鉴定, asset valuation, audit, etc.)
│   ├── Expert witness fees
│   └── Technical advisor fees
├── Investigation & Evidence Costs
│   ├── Notarization fees (公证费)
│   ├── Investigation / evidence-gathering fees
│   ├── Travel (transport, lodging, meals)
│   └── Translation fees
├── Court / Arbitration Institution Fees
│   ├── Court fees / arbitration fees (诉讼费/仲裁费)
│   ├── Preservation fees (保全费, including guarantee fees)
│   ├── Public notice fees (公告费)
│   └── Enforcement fees (执行费)
└── Other Expenses
    ├── Document printing and binding
    ├── Courier and communications
    └── Third-party platform fees
```

### 1.3 Three Stages of Budget Management

| Stage | Timing | Core Tasks |
|------|------|----------|
| **Budget preparation** | Before matter kickoff / at engagement | Estimate total cost; set rates; confirm budget cap with client |
| **Budget execution** | During the matter | Record time and expenses in real time; issue bills periodically; monitor budget utilization |
| **Budget finalization** | At matter close | Aggregate all costs; issue final bill; perform cost-benefit analysis |

## II. End-to-End Workflow

### Stage One: Initialization

#### Step 1: Confirm Billing Mode and Rates

- Confirm the matter's billing mode (hourly / fixed / contingency / hybrid)
- Specify hourly rates by role (partner, attorney, assistant, intern)
- Specify billing granularity (recommend 0.1 hour or 6 minutes as the minimum unit)
- Confirm whether a budget cap or hour cap applies
- Enter rate information into the system as the basis for subsequent automatic calculation

#### Step 2: Create Matter and Role Profiles

- Enter the matter name (e.g., "Company A v. Company B Infringement Dispute")
- Identify matter type (litigation / arbitration / ongoing retainer 常法 / special project)
- Create or match participating roles (partner, lead counsel, legal assistant, intern)
- Assign a rate to each role
- For ongoing/retainer legal services, also set the service period and monthly/quarterly budget

### Stage Two: Time and Expense Recording

#### Step 3: Time Entry

- Record date, start time, end time (or duration)
- Record a work description (must be specific and verifiable; avoid vague phrases such as "handling case matters")
- Auto-calculate hours × rate = amount
- Tag work type (legal research / drafting / hearing preparation / client communication / travel, etc.)

**Time-entry quality standards:**
- ✅ Specific description: "Drafted initial complaint; organized evidence list; approx. 3 hours"
- ❌ Vague description: "Handled case matters; approx. 3 hours"
- ✅ Accurate time: to 0.1 hour or 6 minutes
- ❌ Fuzzy time: "half a day," "a little while"

#### Step 4: Expense Entry

- Enter expense type (travel, expert fees, notarization, court fees, etc.)
- Enter amount, date incurred, and payer
- Link corresponding receipts (photo/scan upload, store as PDF)
- Run OCR on receipts to extract amount, date, and issuer; reconcile against manual entry
- Mark whether the expense is client-billable or firm-borne (non-billable)

### Stage Three: Billing and Budget Monitoring

#### Step 5: Generate Timesheets

**By role:**
- Aggregate all time entries for a role in a given period
- Sort by date; show daily work description, hours, and amount
- Show cumulative hours and fees for that role on the matter

**By matter:**
- Aggregate all role hours for a matter
- Group statistics by role (partner / attorney / assistant hours)
- Show cumulative matter hours and fees
- Compare against budget cap; show budget utilization rate

#### Step 6: Generate Expense Statements

- Aggregate all expenses for a matter or period
- Group by expense type (travel, expert fees, court fees, etc.)
- Link a receipt list so each expense has supporting documentation
- Show client-billable vs. firm-borne expenses

#### Step 7: Budget Execution Monitoring

- Calculate budget utilization rate = incurred cost / budget cap × 100%
- **Green (<70%)**: Budget ample; proceed normally
- **Yellow (70%–90%)**: Budget tight; remind lead counsel to control costs
- **Red (>90%)**: Overrun risk; assess whether to request additional budget or adjust scope
- Generate a budget execution report listing incurred cost, remaining budget, and projected total cost (extrapolated from current progress)

### Stage Four: Delivery and Archiving

#### Step 8: Issue Formal Bills

- Per client needs, choose billing cycle (monthly / quarterly / matter milestones / at close)
- Generate a firm-standard formal bill (firm letterhead, matter info, billing period, detailed time/expense line items, totals, payment account)
- Attach detailed timesheets and copies of expense receipts
- Record bill send date and expected payment date

#### Step 9: Cost Finalization and Analysis

- After matter close, aggregate all time and expenses
- Calculate variance of actual total cost vs. budget
- Analyze variance drivers (hours over expectation? expenses over? scope creep?)
- Assess litigation economics (cost vs. amount in dispute / client benefit)
- Prepare a closing cost report and archive for reference

## III. Output Format Templates

### Output 1: Role Timesheet

```markdown
# Timesheet

**Matter:** Company A v. Company B Infringement Dispute  
**Billing Period:** March 1, 2025 — March 31, 2025  
**Role:** Attorney Wang Yi  
**Hourly Rate:** RMB 500/hour

| Date | Work Description | Hours | Amount |
|------|----------|------|------|
| Mar 5 | Meeting with client to confirm litigation strategy; inquired into evidence preparation progress | 2.0h | RMB 1,000 |
| Mar 8 | Drafted initial complaint; organized evidence list | 3.5h | RMB 1,750 |
| Mar 12 | Filed case at court; submitted preservation application | 4.0h | RMB 2,000 |
| ... | ... | ... | ... |

**Month total: 15.5h, RMB 7,750**  
**Matter cumulative: 45.5h, RMB 22,750**
```

### Output 2: Matter Expense Statement

```markdown
# Case Expense Statement

**Matter:** Company A v. Company B Infringement Dispute  
**Expense Period:** March 1, 2025 — March 31, 2025

| Date | Expense Type | Amount | Payer | Receipt Status |
|------|----------|------|--------|----------|
| Mar 10 | Travel – train ticket | RMB 497 | Attorney Wang Yi | ✓ Archived |
| Mar 15 | Lodging | RMB 1,089 | Partner Liu Yi | ✓ Archived |
| Mar 20 | Notarization fee | RMB 800 | Assistant Zhao Yi | ✓ Archived |

**Month total: RMB 2,386**  
**Matter cumulative: RMB 8,650**
```

### Output 3: Budget Execution Report

```markdown
# Budget Execution Report

**Matter:** Company A v. Company B Infringement Dispute  
**Report Date:** March 31, 2025

## I. Budget Overview

| Item | Budget | Incurred | Remaining | Utilization |
|------|----------|-----------|----------|--------|
| Internal labor cost | RMB 80,000 | RMB 45,500 | RMB 34,500 | 56.9% 🟢 |
| External expert fees | RMB 20,000 | RMB 12,000 | RMB 8,000 | 60.0% 🟢 |
| Investigation & evidence costs | RMB 15,000 | RMB 8,650 | RMB 6,350 | 57.7% 🟢 |
| Court fees | RMB 5,000 | RMB 3,200 | RMB 1,800 | 64.0% 🟢 |
| **Total** | **RMB 120,000** | **RMB 69,350** | **RMB 50,650** | **57.8% 🟢** |

## II. Projected Total Cost

Based on current matter progress (first-instance proceedings ongoing; ~2 hearings and 1 judgment remaining), projected total cost:
- Internal labor cost: RMB 75,000 (remaining effort ~30 attorney hours + 10 partner hours)
- External expert fees: RMB 18,000 (one supplemental appraisal still needed)
- Investigation & evidence costs: RMB 12,000 (one more travel for evidence gathering)
- Court fees: RMB 5,000 (court fees already paid in full)
- **Projected total cost: RMB 110,000** (within budget; surplus ~RMB 10,000)

## III. Risk Alerts

- If the opposing party files a counterclaim, expect ~20 additional attorney hours; request additional budget of RMB 10,000
- If the matter proceeds to second instance, expect total cost to increase by RMB 40,000–50,000
```

## IV. Examples

### Example 1: Monthly Bill for an Hourly-Billed Matter

**Input:**
> "We need to prepare Company A's March work-hour statement for that case with Company B."

**Processing flow:**
1. Matter match: Company A v. Company B Infringement Dispute
2. Task identification: retrieve March 2025 timesheet for the matter
3. Confirm scope: include partners, attorneys, and legal assistants; exclude interns
4. Generate timesheet: group by role; show all entries from March 1–31
5. Also generate expense statement: show March travel, notarization, etc.
6. Update budget monitoring: show cumulative utilization for the matter

**Output:** Role timesheet + matter expense statement + budget execution alert

### Example 2: Budget Warning

**Input:**
> "Check how much budget is left on Company A's M&A deal."

**Processing flow:**
1. Matter match: Special legal services for Company A's acquisition of Company B
2. Query budget status: total budget RMB 300,000; incurred RMB 285,000
3. Trigger red alert: utilization 95%
4. Analyze remaining work: final review of transaction documents, closing assistance, transitional support
5. Estimate remaining cost: at least RMB 20,000 more needed
6. Generate warning report: recommend discussing additional budget with client or trimming scope

**Output:** Budget execution report (red alert) + recommended options

### Example 3: Litigation Economics Analysis

**Input:**
> "The amount in dispute is RMB 500,000. How much have we spent so far—is it worth continuing?"

**Processing flow:**
1. Matter match: a contract dispute
2. Query incurred cost: attorney fees RMB 80,000 + court fees RMB 8,800 + appraisal fees RMB 15,000 = RMB 103,800
3. Query projected remaining cost: second-instance attorney fees RMB 40,000 + court fees RMB 8,800 = RMB 48,800
4. Cost-benefit ratio: incurred + projected = RMB 152,600 vs. amount in dispute RMB 500,000
5. Assess win probability: ~70% based on existing evidence
6. Expected value: 500,000 × 70% − 152,600 = RMB 197,400

**Output:** Cost-benefit analysis report

```markdown
# Litigation Economics Analysis Report

**Matter:** Contract Dispute  
**Amount in Dispute:** RMB 500,000  
**Assessment Date:** April 15, 2025

## Cost Analysis

| Stage | Incurred Cost | Projected Remaining | Subtotal |
|------|-----------|-------------|------|
| First instance | RMB 103,800 | RMB 0 | RMB 103,800 |
| Second instance | RMB 0 | RMB 48,800 | RMB 48,800 |
| **Total** | | | **RMB 152,600** |

## Benefit Assessment

- Win probability: 70% (based on existing evidence and counterparty's ability to perform)
- Expected recovery: 500,000 × 70% = RMB 350,000
- Net expected value: 350,000 − 152,600 = RMB 197,400

## Conclusion and Recommendations

**Recommend continuing litigation.** Although incurred costs already exceed 20% of the amount in dispute, win probability is relatively high and net expected value is positive.
Recommendations:
1. Attempt mediation before second instance to reduce further costs
2. If mediation fails, seek property preservation to secure enforcement
3. Cap second-instance attorney hours at 30
```

## V. Common Errors and Controls

| Error Type | Description | Consequences | Preventive Measures |
|----------|----------|------|----------|
| **Delayed time entry** | Attorneys backfill hours from memory, causing inaccurate time | Billing disputes; client distrust | Require same-day or weekly batch entry; set reminders |
| **Rate mix-up** | Different matters use different rates, but system not updated and old rates still applied | Under- or over-billing | Force rate confirmation when creating each new matter |
| **Expense misclassification** | Firm-borne costs wrongly classified as client-billable | Client complaints; trust crisis | Maintain an expense classification list clarifying billable vs. non-billable |
| **No overrun warning** | Client informed only after utilization hits 100% | Client dissatisfaction; collection difficulty | Set 70% and 90% warning thresholds; communicate proactively |
| **Missing receipts** | Expense incurred but no supporting receipt | Cannot reimburse; tax risk | Require receipt upload on expense entry; otherwise mark as "pending" |
| **Intern hour billing disputes** | Inconsistent rules on whether/how intern hours are billed | Client challenges bill reasonableness | Specify intern hour billing rules in the engagement letter |

## VI. Special Scenario Handling

### 6.1 Cost Control under Fixed Fees

Under fixed fees, firm revenue is capped, so cost control is especially critical:
- At engagement, estimate an hour ceiling (e.g., fixed fee RMB 5,000 for contract review; expect ~4 attorney hours)
- Monitor actual effort in real time; if overrun is imminent, assess scope creep
- If client needs exceed original scope, issue a supplemental agreement clarifying additional fees

### 6.2 Cost Accounting for Contingency / Risk Agency (风险代理)

Contingency matters have low early revenue; ensure the base fee covers costs:
- Calculate floor cost (minimum hours and expenses required)
- Ensure base fee ≥ floor cost
- Probability-weight expected success fees; do not use expected upside as the basis for cost control

### 6.3 Multi-Client Cost Allocation

When multiple clients share the same attorney team or investigation activity:
- Record total hours / total expenses
- Allocate by benefit to each client or by a pre-agreed ratio
- Issue separate bills noting the allocation basis

### 6.4 Multi-Year Matters

When a matter spans multiple calendar years:
- Issue bills by year (supports client annual budgeting and firm annual revenue recognition)
- At year-end, issue a cumulative annual report showing full-year costs and budget utilization
- At the start of the new year, confirm whether the budget continues or is adjusted

## VII. Quality Checklist

```markdown
□ 1. Has the billing mode been confirmed with the client in writing?
□ 2. Have rates for each role been entered and verified?
□ 3. Are time entries specific, accurate, and auditable?
□ 4. Does each expense have a corresponding receipt?
□ 5. Has budget utilization been calculated and tagged with a warning level?
□ 6. Does the bill format meet firm standards?
□ 7. Are bill amounts calculated correctly (hours × rate + expenses)?
□ 8. Have client-billable and firm-borne expenses been distinguished?
□ 9. Is projected total cost within budget?
□ 10. Has the client received and confirmed the bill?
```

## VIII. Best Practices

1. **Rate transparency:** Specify rates by role in the engagement letter or supplemental agreement to avoid later disputes.
2. **Time granularity:** Prefer 0.1 hour (6 minutes) as the minimum unit; coarser increments (e.g., 0.5-hour minimum) distort cost estimates.
3. **Real-time recording:** Encourage same-day time entry; delayed entry causes omissions and estimation bias.
4. **Budget up front:** Set a budget cap at matter kickoff rather than controlling only after overrun.
5. **Periodic reconciliation:** Send clients bills and budget execution reports monthly or quarterly to maintain transparency.
6. **Cost-benefit mindset:** Before major decisions (appeal, appraisal application, etc.), estimate cost and assess economics.

## IX. Related Skills

| Related Skill | Relationship | Notes |
|----------|------|------|
| Full Matter Lifecycle Planning | Upstream / parallel | Obtain matter milestones to estimate remaining effort and cost |
| Legal Document Generation | Downstream | Integrate timesheets and expense statements into firm-standard formal bills |
| Standardized Legal Terminology | Supporting | Ensure accurate, standardized legal terms and amount wording in bills and reports |

## X. Limitations and Risk Notices

- **Data dependency:** Accuracy depends entirely on the quality of input time and expense data—Garbage In, Garbage Out.
- **No automatic capture:** Unless integrated with the firm's practice management system or email/calendar, time entry relies on manual input.
- **Rate dynamics:** Attorney rates may change over time (e.g., annual raises); update system rate baselines promptly.
- **Client sensitivity:** Billing data involves sensitive client information; transmission and storage must meet data-protection requirements.
