---
name: internal-compliance-risk-identification
description: |
  Trigger this skill when a systematic review of an enterprise’s internal compliance management system is needed to identify gaps in policies, process defects, and data-privacy compliance risks.
  Typical triggers include, without limitation:
  - An enterprise engaging counsel or a compliance adviser for an internal compliance risk assessment
  - Pre-IPO, M&A, or regulatory-inspection self-checks
  - After a compliance incident, when systemic defects in the management system must be investigated
  - When building or updating a compliance management system and assessing fit between existing policies and laws/regulations
  - When the user asks to review internal rules, core business processes, or privacy policy/agreements for compliance
  This skill covers three review dimensions: completeness of the policy system, effectiveness of business-process controls, and personal-information-protection compliance.
---

> **Chinese source (authoritative):** [`../../skills/internal-compliance-risk-identification/SKILL.md`](../../skills/internal-compliance-risk-identification/SKILL.md)

# Internal Compliance Risk Identification

## Overview Table

| Item | Content |
|------|---------|
| **Capability ID** | 14 |
| **Capability Name** | Internal Compliance Risk Identification |
| **Capability Type** | Compliance review |
| **Core Function** | Identify enterprise internal compliance gaps across policy systems, business processes, and data privacy |
| **Input** | Internal rules and policies; business-process descriptions/flowcharts; privacy policy/agreements; industry information |
| **Output** | Structured compliance risk inventory (issue description, legal basis, risk level, remediation recommendations) |
| **Related Capabilities** | Legal-norm validity check (confirm current effectiveness of applicable rules); statutory provision retrieval (supplement legal bases) |
| **Risk Level** | High (compliance gaps may lead to administrative penalties, civil liability, or criminal liability) |

## Legal Disclaimer

> **Important notice:**
> 1. Compliance risk identification under this skill is auxiliary analysis and does not constitute a formal legal opinion.
> 2. Review conclusions depend on the completeness and truthfulness of information provided by the enterprise; incomplete information may omit material risks.
> 3. Different industries (finance, healthcare, internet, energy, etc.) have special regulatory rules; review must incorporate industry-specific requirements.
> 4. For specialized areas such as cross-border data transfers, antitrust, and anti-bribery, separate dedicated reviews are recommended.
> 5. Remediation recommendations should be implemented only after review by a practicing lawyer or compliance professional.

## I. Core Concepts

### 1.1 Three Review Dimensions

```
Internal Compliance Risk Identification
├── Dimension 1: Completeness of the Policy System
│   └── Core question: Has the enterprise established internal rules covering all compliance obligations?
├── Dimension 2: Effectiveness of Business-Process Controls
│   └── Core question: Are control points in core business processes complete and effectively executed?
└── Dimension 3: Personal Information Protection Compliance
    └── Core question: Do privacy policies/agreements and data-processing activities comply with the Personal Information Protection Law (PIPL) and related rules?
```

### 1.2 Compliance Risk Level Definitions

| Level | Marker | Definition | Typical Situations |
|------|------|----------|----------|
| **Major risk** | 🔴 | Violation of mandatory legal provisions; may lead to administrative penalties, criminal liability, or major civil damages | No AML system (financial institutions); failure to fulfill cybersecurity graded-protection obligations |
| **Important risk** | 🟡 | Violation of regulatory rules or industry norms; may lead to supervisory measures, fines, or reputational harm | Procurement without three-party price comparison; privacy policy omits retention period |
| **General risk** | 🟢 | Incomplete policies or weak execution; compliance hazards exist but serious short-term consequences are unlikely | Policies lag behind statutory amendments; approval authorities insufficiently granular |

### 1.3 Common Sources of Compliance Obligations

| Source Type | Examples | Hierarchy of Force |
|----------|------|----------|
| Laws | Company Law; Personal Information Protection Law (PIPL); Anti-Unfair Competition Law | Highest |
| Administrative regulations | Network Data Security Regulation | High |
| Departmental rules | CSRC rules; former CBIRC / NFRA rules; MIIT rules | High |
| Judicial interpretations | SPC judicial interpretations on personal information protection | High |
| Industry standards | Sector self-regulatory norms; technical security standards | Medium |
| Local regulations | Local data regulations; consumer-protection ordinances | Medium (territorial limits) |

## II. Full Workflow

### Phase One: Preparation and Information Gathering

#### Step 1: Confirm Basic Enterprise Information

- **Enterprise name**, **Unified Social Credit Code**
- **Industry** (determines applicable special regulatory rules)
- **Enterprise scale** (affects intensity and scope of compliance obligations)
- **Business geography** (cross-border operations; multi-jurisdiction operations)
- **Scope of this review**: Policy review / process review / privacy review / all

#### Step 2: Collect Materials Needed for Review

| Review Dimension | Materials Required |
|----------|----------|
| Policy-system review | Inventory and full text of all current internal rules and policies |
| Business-process review | Written operating guides, flowcharts, and sample forms for core processes |
| Privacy-compliance review | Full text of current privacy policies/agreements; description of data-processing activities; list of third-party partners |

### Phase Two: Completeness Review of the Policy System

#### Step 3: Map Compliance Obligations the Enterprise Must Observe

1. Based on industry, identify the applicable inventory of laws and regulations
2. Extract from those instruments the compliance obligations binding on the enterprise
3. Categorize obligations (e.g., corporate governance, labor and employment, workplace safety, data protection, anti-commercial bribery)

#### Step 4: Build a Policy–Statute Mapping Matrix

| Obligation Category | Required Policy | Existing Policy | Status |
|-------------|----------|----------|----------|
| Data protection | Data Security Management Policy | Information Security Management Measures | 🟡 Partially covered |
| Anti-commercial bribery | Anti-Commercial Bribery Compliance Policy | (None) | 🔴 Missing |

#### Step 5: Review Compliance of Existing Policy Content

For each established policy, review item by item:
- Whether content is consistent with current laws and regulations (no conflict; no outdated clauses)
- Whether responsible parties are clearly specified
- Whether operating procedures are concrete and executable
- Whether consequences of violation and accountability mechanisms are provided

#### Step 6: Output Policy-Gap Review Results

For each issue found, output in the following format:

```markdown
**Issue ID:** G-01
**Issue Type:** Missing policy
**Compliance Obligation:** Establish an anti-commercial bribery compliance policy
**Legal Basis:** Anti-Unfair Competition Law Arts. 7 and 19
**Risk Level:** 🔴 Major
**Issue Description:** The enterprise has no dedicated anti-commercial bribery policy; sales commission policies have not undergone compliance review; commercial-bribery risk exposure exists.
**Remediation Recommendations:**
1. Adopt an Anti-Commercial Bribery Compliance Policy with a clear prohibited-conduct list
2. Establish distributor/agent onboarding due-diligence mechanisms
3. Train sales staff on anti-commercial bribery
4. Establish approval and registration for gifts, entertainment, and commissions
**Remediation Priority:** High
```

### Phase Three: Effectiveness Review of Business-Process Controls

#### Step 7: Obtain and Reconstruct Business Processes

1. Obtain written operating guides or flowcharts from business units
2. If no written documents exist, reconstruct the process via interviews, clarifying:
   - Process start and end
   - Names and sequence of steps
   - Roles and duties at each step
   - Approvers and approval authority at each step
   - Records, forms, or system logs produced at each step
3. Draw a process reconstruction diagram (annotate roles, approval nodes, document flows)

#### Step 8: Identify Missing Compliance Control Points

Against laws, regulations, and industry norms, determine whether the process lacks these key control points:

| Control Point | Applicable Scenarios | Risk if Missing |
|----------|----------|----------|
| Supplier/partner onboarding review | Procurement, outsourcing, cooperation | Unqualified counterparties; related-party conflicts |
| Conflict-of-interest declaration | Related-party transactions; personal interests | Benefit transfer; self-dealing |
| Three-party price comparison or tendering | Procurement above prescribed thresholds | Inflated prices; corruption risk |
| Legal review of contracts | Before signing | Adverse terms; missing rights |
| Seal/chop approval and registration | Use of company seals | Seal abuse; forged contracts |
| Acceptance and confirmation | Delivery of goods/services | Quality mismatch; quantity shortfalls |
| Exception reporting and handling | Process deviation from normal path | Concealed risk; expanded loss |

#### Step 9: Check Segregation of Incompatible Duties

Incompatible duties are positions that, under internal-control requirements, must not be held by the same person. Common incompatible pairs:

| Position Pair | Risk Explanation |
|----------|----------|
| Procurement request and procurement approval | Self-request, self-approve; lack of oversight |
| Selecting suppliers and accepting goods | May choose related suppliers and loosen acceptance standards |
| Fund disbursement and bookkeeping | May misappropriate funds and alter accounts |
| Contract signing and contract review | May execute contracts adverse to the company |
| Seal application and seal approval | May use seals privately |

**Review method:**
- Obtain staffing lists; check whether incompatible roles are held by different persons
- If staffing shortages prevent segregation, check compensating controls (periodic rotation, cross-review, system audit trails)

#### Step 10: Assess Reasonableness of Approval Authorities

- Whether approval authority is tiered by amount/risk level
- Whether large-value or high-risk matters require higher-level approval
- Whether temporary delegated approvals have post-hoc ratification
- Whether approval authority is documented in writing, avoiding oral authorization alone

#### Step 11: Check Traceability of Record Retention

- Whether each step produces written or electronic records
- Whether records are completely retained and traceable to specific operators and times
- Whether electronic approval systems keep operation logs and whether logs are tamper-resistant
- Whether paper documents have numbering and archiving systems
- Whether retention periods meet statutory requirements

#### Step 12: Output Business-Process Review Results

```markdown
**Issue ID:** P-01
**Issue Type:** Missing control point
**Process Node:** Supplier selection
**Legal Basis:** Basic Norms for Enterprise Internal Control Art. 29
**Risk Level:** 🔴 Major
**Issue Description:** No supplier onboarding review; business staff may choose suppliers freely, with no qualification review or background check.
**Remediation Recommendations:**
1. Establish supplier onboarding; procurement or a designated unit reviews qualifications
2. Maintain an approved-supplier list and update it periodically
3. Conduct background checks on new suppliers to exclude conflicts of interest
**Remediation Priority:** High
```

### Phase Four: Personal Information Protection Compliance Review

#### Step 13: Obtain and Review Privacy Policies/Agreements

Obtain the full text of all currently effective privacy policies/agreements (website, App, mini-program, and all other versions).

#### Step 14: Review Privacy Compliance Points Item by Item

| Review Item | Review Focus | Legal Basis |
|--------|----------|----------|
| **Lawfulness of processing** | Whether purposes, methods, and types of processing are clearly notified; whether user consent is obtained (or another lawful basis exists) | PIPL Arts. 13–17 |
| **Minimum necessity** | Whether the scope of personal information collected is necessary for the product/service; whether there is over-collection | PIPL Art. 6 |
| **Consent mechanisms** | Whether voluntary, explicit consent is obtained at first use; whether refusal is available; whether basic and extended functions are distinguished | PIPL Arts. 14 and 16 |
| **Sensitive personal information** | Before collecting biometrics, financial accounts, location/trajectory, etc., whether separate consent is obtained | PIPL Art. 29 |
| **Completeness of notice** | Whether purposes, methods, and retention periods are notified; if retention is hard to determine, whether the determination method is explained | PIPL Art. 17 |
| **Third-party sharing** | Whether providing personal information to third parties has separate consent; whether third parties are listed by name, shared data types, and purposes | PIPL Art. 23; Network Data Security Management Regulation Art. 21 |
| **SDK disclosure** | Whether embedded third-party SDKs list name, package name, data types collected, and purposes; whether SDK terms are conveniently accessible | PIPL Art. 17 |
| **User rights safeguards** | Whether users are informed how to access, copy, correct, delete, withdraw consent, and cancel accounts | PIPL Arts. 44–47 |
| **Cross-border transfers** | Whether outbound provision of personal information has a lawful basis (security assessment, standard contract, or certification) | PIPL Arts. 38–43 |
| **Minors’ protection** | Whether processing information of minors under 14 obtains guardian consent and has dedicated rules | PIPL Art. 31 |

#### Step 15: Output Privacy Compliance Review Results

```markdown
**Issue ID:** D-01
**Issue Type:** Incomplete notice
**Review Item:** Retention-period notice
**Legal Basis:** PIPL Art. 17
**Risk Level:** 🟡 Important
**Issue Description:** The privacy policy does not clearly state retention periods for each category of personal information, only “for the time needed to achieve the purpose,” which does not meet the statutory notice requirement on retention periods.
**Remediation Recommendations:**
1. Supplement retention-period statements for each data category
2. For information whose retention is hard to determine, state the determination method (e.g., “retain 5 years after order completion, then delete or anonymize”)
**Remediation Priority:** Medium
```

### Phase Five: Consolidation and Reporting

#### Step 16: Consolidate All Compliance Risks

1. Unify numbering across three dimensions (policies G-XX; processes P-XX; data D-XX)
2. Sort by risk level (🔴 Major → 🟡 Important → 🟢 General)
3. Count risks by category

#### Step 17: Generate the Compliance Risk Review Report

```markdown
# Internal Compliance Risk Review Report

**Review Subject:** XXX Company  
**Industry:** XXX  
**Review Date:** YYYY-MM-DD  
**Review Scope:** Policy-system completeness / Business-process control effectiveness / Personal information protection compliance

## I. Executive Summary of Findings

| Risk Level | Count |
|----------|------|
| 🔴 Major risk | X items |
| 🟡 Important risk | X items |
| 🟢 General risk | X items |
| **Total** | **X items** |

## II. Major Risk Inventory (🔴)

[List all major risks; each item includes: Issue ID, description, legal basis, remediation recommendations, remediation deadline]

## III. Important Risk Inventory (🟡)

[List all important risks]

## IV. General Risk Inventory (🟢)

[List all general risks]

## V. Consolidated Remediation Recommendations

| No. | Remediation Item | Responsible Unit | Suggested Deadline | Priority |
|------|----------|----------|-------------|--------|
| 1 | ... | ... | ... | High |

## VI. Disclaimer

This report is based on information provided by the enterprise as of the review date, is for internal compliance management reference only, and does not constitute a formal legal opinion.
Industry-specific regulatory rules require separate dedicated review.
```

## III. Output Format Templates

### Output 1: Single-Issue Record Card

```markdown
**Issue ID:** [G/P/D]-[serial]
**Issue Type:** [Missing policy / Policy content non-compliant / Missing control point / Incompatible duties not segregated / Unreasonable approval authority / Record-retention defect / Incomplete notice / Consent-mechanism defect / Third-party sharing violation / Insufficient user-rights safeguards / Other]
**Review Dimension:** [Policy system / Business process / Privacy compliance]
**Policy/Process/Policy Document Involved:** [specific name]
**Legal Basis:** [law name + article]
**Risk Level:** [🔴/🟡/🟢]
**Issue Description:** [concrete, verifiable description]
**Remediation Recommendations:** [concrete, actionable measures]
**Remediation Priority:** [High/Medium/Low]
**Estimated Remediation Effort:** [e.g., adopt 1 new policy, revise 2 existing policies, 1 system change]
```

### Output 2: Consolidated Compliance Risk Inventory Table

```markdown
| ID | Dimension | Type | Brief Issue | Level | Priority |
|------|------|------|----------|------|--------|
| G-01 | Policy | Missing policy | No anti-commercial bribery policy | 🔴 | High |
| P-01 | Process | Missing control point | Supplier selection without onboarding review | 🔴 | High |
| D-01 | Data | Incomplete notice | Privacy policy omits retention periods | 🟡 | Medium |
```

## IV. Examples

### Example 1: Procurement Process Compliance Review

**Input:**
> Enterprise procurement process: Business unit raises demand → department head approves → business staff finds suppliers independently (no qualification review, no price comparison) → business staff drafts contract → department head signs and affixes seal (no legal review) → warehouse clerk accepts and stocks → finance pays. Purchases above RMB 50,000 are still approved only by the department head. Seal use records only the date, not contract name or counterparty. Purchase request forms are kept by business staff themselves.

**Review output (excerpt):**

| ID | Node | Issue | Level | Remediation |
|------|------|------|------|----------|
| P-01 | Supplier selection | No onboarding review; no price comparison | 🔴 | Establish supplier onboarding and price-comparison rules |
| P-02 | Contract signing | No legal review | 🔴 | Add a contract legal-review control point |
| P-03 | Approval authority | No tiered approval for large purchases | 🟡 | ≤50k → department head; 50–200k → VP; 200k+ → GM |
| P-04 | Acceptance & stocking | Acceptance and stocking roles not segregated | 🟡 | Assign different persons |
| P-05 | Seal management | Incomplete seal-registration information | 🟡 | Record contract name, counterparty, amount, purpose |
| P-06 | Record retention | No unified archiving system | 🟢 | Establish procurement records management |

### Example 2: Privacy Policy Compliance Review

**Input:**
> App privacy policy highlights: Registration requires authorizing phone number and WeChat OpenID; global shopping requires ID card number; order information is shared with payment platforms and logistics providers; privacy policy does not clearly state retention periods by category; account-cancellation path is not explained.

**Review output (excerpt):**

| ID | Review Item | Issue | Level | Remediation |
|------|--------|------|------|----------|
| D-01 | Sensitive-info consent | ID number collection without stating separate consent | 🔴 | Separate-consent prompt before first use of global shopping |
| D-02 | Retention period | Retention periods by category not clearly notified | 🟡 | Supplement retention periods or determination methods |
| D-03 | Third-party sharing | Third parties not listed in inventory form | 🟡 | Table third-party names, shared types, purposes |
| D-04 | User rights | Account-cancellation path not stated | 🟡 | Supplement operational paths for exercising rights |

## V. Common Errors and Prevention

| Error Type | Description | Consequence | Prevention |
|----------|----------|------|----------|
| **Incomplete statute mapping** | Only general laws retrieved; industry-specific rules missed | Material compliance risks omitted | Build industry statute inventories; consult sector experts when needed |
| **Policy–statute mapping is formalistic** | Check only policy titles, not whether content matches statutes | Policies outdated or conflicting with law | Clause-by-clause compliance review of existing policies |
| **Narrow interview scope** | Interview only legal/compliance, not business units | Actual operations diverge from written rules | Interview front-line business staff for real practices |
| **Privacy review too narrow** | Review only privacy-policy text, not actual processing | Actual processing diverges from stated policy | Require processing-activity descriptions and verify against them |
| **Non-actionable remediation** | Vague advice (e.g., “strengthen management”) | Enterprise cannot execute; issues persist | Specify responsible units, deadlines, and acceptance criteria |
| **Ignoring cross-border compliance** | Fail to identify outbound data transfers | Breach of outbound data security-assessment duties | Proactively ask about overseas servers and overseas partners |

## VI. Special Scenario Handling

### 6.1 Multi-Industry Group Enterprises

For groups operating multiple business lines (e.g., finance, real estate, and technology simultaneously):
- Map applicable regulatory rules by business line
- Identify conflicts or gaps between group-wide unified policies and line-specific policies
- Watch cross-line risks such as related-party transactions and fund transfers within the group

### 6.2 Pre-IPO Enterprises

In addition to general review, pre-IPO compliance review should especially cover:
- Compliance of historical equity changes
- Fairness of related-party transaction pricing
- Labor compliance (social insurance and housing fund contributions; labor-dispatch ratios)
- Environmental, workplace-safety, and other industry-specific licenses
- Tax compliance (legality of tax preferences; transfer pricing)

### 6.3 Foreign-Invested / Cross-Border Operations

- Review compliance with the foreign-investment negative list
- Review cross-border data-transfer compliance (security assessment, standard contract, certification)
- Review localization/storage requirements (e.g., map data, genetic data, important data)
- Watch international sanctions compliance (OFAC, EU sanctions lists)

### 6.4 Data-Driven Internet Enterprises

- Focus on algorithmic-recommendation compliance (opt-out options; algorithm filing)
- Review transparency of automated decision-making (user notice; appeal channels)
- Review personal information protection impact assessments (PIA) for large-scale personal-information processing

## VII. Quality Checklist

```markdown
□ 1. Has the enterprise’s industry been clearly identified?
□ 2. Is the applicable laws-and-regulations inventory complete (including industry-specific rules)?
□ 3. Does the policy–statute mapping cover all material compliance obligations?
□ 4. Is process reconstruction based on actual operations (not written rules alone)?
□ 5. Does incompatible-duty segregation review cover all material processes?
□ 6. Does privacy-policy review cover all statutory notice items?
□ 7. Is each risk tagged with legal basis, risk level, and remediation recommendations?
□ 8. Are remediation recommendations concrete, actionable, and assigned to responsible parties?
□ 9. Are all major risks (🔴) listed and prioritized?
□ 10. Does the review report include a disclaimer and limitations statement?
```

## VIII. Related Skills

| Related Skill | Relationship | Explanation |
|----------|------|------|
| Legal-norm validity check | Prerequisite / parallel | Confirm that laws and regulations relied on are currently effective |
| Statutory provision retrieval | Prerequisite / parallel | Supplement legal bases for specific compliance obligations |
| Legal risk identification | Complementary | This skill focuses on compliance gaps at the management-system level; legal risk identification focuses on lawfulness of concrete legal acts |

## IX. Limitations and Risk Notices

- **Information dependence**: Review conclusions depend entirely on information provided by the enterprise; deliberate concealment or false information will cause material omissions.
- **Dynamic change**: Laws and regulations continually update; conclusions reflect compliance status only as of the review date.
- **Industry specificity**: Special regulatory rules differ greatly by industry; a generic checklist cannot cover all industry-specific requirements.
- **Depth limits**: This skill is a compliance risk screen; issues found require further formal legal opinions from professional counsel or compliance advisers.
