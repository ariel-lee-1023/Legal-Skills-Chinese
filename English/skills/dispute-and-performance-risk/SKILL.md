---
name: dispute-and-performance-risk
description: |
  Trigger this skill when the user submits a contract text, transaction arrangement, commercial agreement, or description of a legal relationship and needs an assessment of potential legal disputes or breach-of-contract risks.
  Typical trigger scenarios include, but are not limited to:
  - The user asks for a contract review and identification of potential risks
  - The user asks whether a transaction arrangement has performance obstacles
  - The user describes difficulties in contract performance and needs a judgment on whether they constitute breach
  - The user asks for a risk rating of contract clauses
  - The user provides an agreement between two or more parties and asks to identify likely dispute focal points
  - The user describes an already-occurred performance deviation and needs an assessment of legal consequences
  - Forward-looking risk identification in contract review, due diligence, deal negotiation, and similar scenarios
  This skill focuses on two core questions—"whether legal disputes may arise" and "whether breach risks exist"—
  and outputs a structured risk inventory with response recommendations.
---

> **Chinese source (authoritative):** [`../../skills/dispute-and-performance-risk/SKILL.md`](../../skills/dispute-and-performance-risk/SKILL.md)

# Identifying Dispute and Performance Risks

## Overview Table

| Item | Content |
|------|------|
| **Capability name** | Identifying Dispute and Performance Risks |
| **Capability ID** | 13 |
| **Core objective** | Systematically identify risk points in a contract or legal relationship that may give rise to disputes or breach |
| **Input** | Contract text, description of the transaction arrangement, performance status notes, party background information |
| **Output** | Structured risk inventory (including risk level, risk description, legal basis, and response recommendations) |
| **Related capabilities** | Contract clause parsing, legal relationship identification, breach liability analysis, dispute resolution path planning |
| **Applicable jurisdiction** | Primarily the legal system of mainland China; expandable to other jurisdictions |
| **Typical users** | In-house counsel, lawyers, compliance officers, commercial negotiators, investors |

---

## Legal Disclaimer

> **Important notice:**
> 1. Output from this skill is a reference legal risk analysis and does not constitute a formal legal opinion.
> 2. Risk identification is inferred from the information provided; incomplete information may lead to omissions.
> 3. Legal risk assessments are time-sensitive; changes in laws and regulations may affect the conclusions.
> 4. For high-risk matters, engage a qualified lawyer for in-depth review.
> 5. The final determination in a specific case rests with the judicial authority's findings.

---

## Core Concepts

### I. Distinguishing Dispute Risk and Performance Risk

| Dimension | Dispute Risk | Performance Risk |
|------|----------|----------|
| **Definition** | Risk that contract clauses or a legal relationship may give rise to disagreement or confrontation between the parties | Risk that one or more parties may be unable to perform obligations as agreed |
| **Time dimension** | May arise at any stage—before signing, during performance, or after performance | Mainly surfaces during the performance stage |
| **Manifestations** | Divergent clause interpretations, disputes over rights and obligations, disputes over allocation of liability | Delayed performance, incomplete performance, impossibility of performance, refusal to perform |
| **Root causes** | Ambiguous clauses, conflicting rights, imbalanced interests, external change | Insufficient capacity, lack of willingness, changed conditions, force majeure |
| **Consequences** | Negotiation, mediation, arbitration, litigation | Breach liability, contract termination, damages |

### II. Three-Layer Risk Structure Model

```
┌─────────────────────────────────────────────┐
│         Layer 1: Clause-level risk           │
│  (Defects, ambiguity, omissions, conflicts   │
│   in the contract text itself)               │
├─────────────────────────────────────────────┤
│         Layer 2: Transaction-level risk      │
│  (Deal structure, commercial logic,          │
│   counterparty capacity and credit)          │
├─────────────────────────────────────────────┤
│         Layer 3: Environment-level risk      │
│  (Legal/policy change, market shifts,        │
│   force majeure)                             │
└─────────────────────────────────────────────┘
```

### III. Key Legal Concepts

1. **Breach of contract (违约)**: A party fails to perform contractual obligations or performs inconsistently with the agreement.
2. **Anticipatory breach (预期违约)**: Before the performance period expires, a party clearly indicates, or demonstrates by conduct, that it will not perform its main obligations.
3. **Fundamental breach (根本违约)**: A breach that renders the purpose of the contract unattainable.
4. **Change of circumstances (情势变更)**: After contract formation, a material change in objective circumstances makes continued performance clearly unfair.
5. **Force majeure (不可抗力)**: Objective circumstances that could not be foreseen, avoided, and overcome.
6. **Contract interpretation dispute**: Parties have different understandings of the meaning of contractual clauses.
7. **Standard-form clause risk (格式条款风险)**: The party providing standard-form clauses fails to fulfill reasonable notice and explanation duties.
8. **Validity defect (效力瑕疵)**: The contract may be held void or voidable for reasons such as violation of mandatory legal provisions.

---

## Complete Workflow

### Stage 1: Information Gathering and Preprocessing

```
Step 1.1 → Confirm the object of analysis
  ├── Clarify the scope of the contract/agreement/transaction arrangement to analyze
  ├── Confirm the parties' identities and roles (Party A / Party B / third party)
  ├── Confirm the user's stance (on whose behalf risk identification is conducted)
  └── Confirm the analytical focus (full review vs specific clauses / specific risks)

Step 1.2 → Collect background information
  ├── Background to signing and commercial purpose
  ├── Basic party information (qualifications, credit, performance capacity)
  ├── Current performance status (not yet performed / partially performed / completed)
  ├── Known disputes or disagreements
  └── Relevant industry practice and regulatory requirements

Step 1.3 → Text preprocessing
  ├── Read the full text and build an overall contract framework understanding
  ├── Mark key clauses (core rights and obligations, breach liability, dispute resolution)
  ├── Identify contract type (sale, lease, services, cooperation, investment, etc.)
  └── Mark missing or ambiguous information
```

### Stage 2: Clause-Level Risk Scan

```
Step 2.1 → Review core clauses one by one
  Systematically review each of the following clause categories:

  ┌─ Party clauses ────────────────────────────────┐
  │ □ Are the contracting parties properly qualified │
  │ □ Are there agency / representative authority     │
  │   issues?                                        │
  │ □ Do party qualifications meet contractual        │
  │   requirements?                                  │
  └──────────────────────────────────────────────────┘

  ┌─ Subject-matter clauses ───────────────────────┐
  │ □ Is the subject matter / service description    │
  │   clear and specific?                            │
  │ □ Are quality standards clear and measurable?    │
  │ □ Are quantity / scope determined?               │
  └──────────────────────────────────────────────────┘

  ┌─ Price and payment clauses ────────────────────┐
  │ □ Is the pricing method clear?                   │
  │ □ Are payment conditions and timing clear?       │
  │ □ Is there a price adjustment mechanism?         │
  │ □ Are invoicing and tax arrangements clear?      │
  └──────────────────────────────────────────────────┘

  ┌─ Performance clauses ──────────────────────────┐
  │ □ Is the performance period clear?               │
  │ □ Is the method of performance specific?         │
  │ □ Is the place of performance determined?        │
  │ □ Are acceptance standards and procedures clear? │
  │ □ Are delivery conditions complete?              │
  └──────────────────────────────────────────────────┘

  ┌─ Breach liability clauses ─────────────────────┐
  │ □ Are breach scenarios sufficiently enumerated?  │
  │ □ Is the liquidated damages ratio reasonable     │
  │   (too high / too low)?                          │
  │ □ Is the scope of damages clear?                 │
  │ □ Are liability limitation clauses fair?         │
  │ □ Are exemption clauses lawful and valid?        │
  └──────────────────────────────────────────────────┘

  ┌─ Amendment and termination clauses ────────────┐
  │ □ Are termination conditions clear?              │
  │ □ Are unilateral termination rights reciprocal?  │
  │ □ Are consequences of termination clearly agreed?│
  │ □ Are amendment procedures proper?               │
  └──────────────────────────────────────────────────┘

  ┌─ Dispute resolution clauses ───────────────────┐
  │ □ Is the dispute resolution method clear         │
  │   (litigation / arbitration)?                    │
  │ □ Is the competent court / arbitral institution  │
  │   determined?                                    │
  │ □ Is the governing law clear?                    │
  │ □ Are there pre-dispute procedures               │
  │   (negotiation / mediation)?                     │
  └──────────────────────────────────────────────────┘

Step 2.2 → Review relationships among clauses
  ├── Check for contradictions or conflicts among clauses
  ├── Check whether rights and obligations are reciprocal and balanced
  ├── Check for logical gaps (e.g., a condition triggers with no corresponding consequence)
  ├── Check consistency between annexes and the main text
  └── Check that defined terms are used consistently

Step 2.3 → Identify omitted clauses
  ├── Compare against a checklist of common clauses for this contract type; identify gaps
  ├── Assess how much missing clauses affect risk
  └── Mark key clauses that should be supplemented
```

### Stage 3: Transaction-Level Risk Assessment

```
Step 3.1 → Analyze transaction structure
  ├── Is the transaction structure reasonable and lawful?
  ├── Is the flow of funds clear?
  ├── Are there special arrangements such as circular deals or related-party transactions?
  ├── Are security / credit enhancement measures adequate?
  └── Are the links among transaction stages tightly connected?

Step 3.2 → Assess counterparty risk
  ├── Counterparty performance capacity (financial condition, technical capability, resource reserves)
  ├── Counterparty willingness to perform (historical credit, industry reputation)
  ├── Counterparty legal risk (litigation, administrative penalties, dishonest-debtor records)
  └── Organizational stability (equity changes, management changes)

Step 3.3 → Validate commercial logic
  ├── Does the contractual arrangement accord with ordinary commercial sense?
  ├── Is profit allocation sustainable?
  ├── Are there fragile links that over-depend on a single condition?
  └── Is the exit mechanism feasible?
```

### Stage 4: Environment-Level Risk Assessment

```
Step 4.1 → Legal and policy risk
  ├── Does the industry involved have special regulatory requirements?
  ├── Is administrative approval / filing required?
  ├── Is there a reasonable expectation of legal or policy change?
  ├── Do special regimes such as foreign investment or cross-border transactions apply?
  └── Do compliance requirements such as antitrust or data protection apply?

Step 4.2 → Market and economic risk
  ├── Is there potential for large price swings in the subject matter?
  ├── Exchange-rate risk (cross-border contracts)
  ├── Supply-chain risk
  └── Industry cyclical risk

Step 4.3 → Force majeure and unexpected events
  ├── Does the force majeure clause cover major risk scenarios?
  ├── Are notice duties and burden of proof clear?
  └── Is the handling of force majeure consequences reasonable?
```

### Stage 5: Comprehensive Risk Rating and Output

```
Step 5.1 → Classify and aggregate risks
  Classify all identified risks along these dimensions:
  ├── By risk type: dispute risk / performance risk / compliance risk / validity risk
  ├── By risk layer: clause-level / transaction-level / environment-level
  └── By affected party: own-side risk / counterparty risk / shared risk

Step 5.2 → Rate risks
  Rate each risk (see "Confidence and Risk-Level Annotation System")

Step 5.3 → Generate response recommendations
  For each risk, propose:
  ├── Preventive measures (contract amendment suggestions)
  ├── Control measures (performance management suggestions)
  └── Remedial measures (response strategy after a dispute arises)

Step 5.4 → Output a structured report
  Generate the final report according to the "Output Format Templates"
```

---

## Common Domains and Legal Sources Cross-Reference

### I. General Legal Sources

| Law / regulation | Relevant provisions | Applicable scenarios |
|----------|----------|----------|
| 《民法典》 Civil Code, Book on Contracts (Book Three) | Arts. 464–988 | Baseline rules for all contract types |
| 《民法典》 Civil Code, General Provisions | Arts. 143–157 | Validity of civil juristic acts |
| 《民法典》 Civil Code, Contracts · General Rules | Arts. 509–534 | Rules on contract performance |
| 《民法典》 Civil Code, Contracts · General Rules | Arts. 577–594 | Breach liability |
| 《民法典》 Civil Code, Contracts · General Rules | Arts. 535–542 | Contract preservation (subrogation, revocation) |
| 《最高人民法院关于适用〈中华人民共和国民法典〉合同编通则若干问题的解释》 SPC Interpretation on Several Issues Concerning the Application of the General Rules of the Contracts Book of the Civil Code of the PRC | Full text | Guidance for adjudicating contract disputes |

### II. Specialized Sources by Contract Type

| Contract type | Primary legal sources | Key focus provisions / areas |
|----------|----------|-------------------|
| **Sale contracts** | Civil Code Arts. 595–647; SPC judicial interpretation on sale contracts | Risk transfer of subject matter, quality objection period, retention of title |
| **Construction project contracts** | Civil Code Arts. 788–808; Construction Project Judicial Interpretation (I) | Project quality, schedule delay, price settlement, actual constructors |
| **Lease contracts** | Civil Code Arts. 703–734 | Lease-term limits, right of first refusal to purchase, sublease restrictions |
| **Loan contracts** | Civil Code Arts. 667–680; private lending judicial interpretation | Interest-rate caps, upfront interest ("cutting the head"), security validity |
| **Labor contracts** | Labor Contract Law, Labor Law | Termination restrictions, economic compensation, non-compete |
| **Equity transfer / investment agreements** | Company Law, Foreign Investment Law | Validity of valuation adjustment (VAM) clauses, priority rights, shareholder information rights |
| **IP license contracts** | Copyright Law, Patent Law, Trademark Law | Scope of license, warranty against title defects, infringement risk |
| **Guarantee / security contracts** | Civil Code Arts. 681–702; judicial interpretation on the security system | Scope of security, independent guarantees, maximum-amount security |

### III. Specialized-Domain Sources

| Domain | Legal sources | Risk focus |
|------|------|------------|
| Antitrust | Anti-Monopoly Law | Monopoly agreements, abuse of dominant market position |
| Data compliance | Personal Information Protection Law, Data Security Law | Authorization for data processing, cross-border transfer |
| Consumer protection | Law on the Protection of Consumer Rights and Interests | Validity of standard-form clauses, punitive damages for fraud |
| Bidding and tendering | Bidding and Tendering Law | Consistency between winning bid contract and tender documents |
| International trade | CISG, UCP600, Incoterms | Trade terms, letter-of-credit conditions, governing law |

---

## Verification and Screening Rules

### I. Verification Standards for Risk Identification

Each identified risk must pass the following "Four-Element Verification":

```
┌──────────────────────────────────────────────────┐
│            Four-Element Risk Verification         │
│                                                    │
│  1. [Factual basis] Is the risk grounded in        │
│     contract text or facts?                        │
│     → Must point to specific clauses or facts      │
│     → No speculation from thin air                 │
│                                                    │
│  2. [Legal basis] Is the risk supported by legal   │
│     norms?                                         │
│     → Cite specific statutes or judicial           │
│       interpretations                              │
│     → Or cite recognized legal principles /        │
│       judicial practice                            │
│                                                    │
│  3. [Causal logic] Is the reasoning chain from     │
│     facts to risk complete?                        │
│     → Clause defect → possible dispute scenario →  │
│       adverse consequence                          │
│     → No leaps in the logic chain                  │
│                                                    │
│  4. [Realistic possibility] Does the probability   │
│     of occurrence warrant reasonable attention?    │
│     → Exclude extremely remote events (unless      │
│       consequences are extremely severe)           │
│     → Consider common dispute types in industry    │
│       practice                                     │
└──────────────────────────────────────────────────┘
```

### II. Risk Screening Rules

```
Rule 1: Materiality screening
  → Prioritize risks that may render the contract void / voidable
  → Prioritize risks that may cause material economic loss
  → Prioritize risks that may render the contractual purpose unattainable

Rule 2: Actionability screening
  → Prioritize risks preventable by contract amendment
  → Prioritize risks controllable through performance management
  → For uncontrollable risks, still report but mark as "uncontrollable"

Rule 3: Deduplication
  → Merge multiple manifestations arising from the same root cause into one risk item
  → Annotate relationships among risks

Rule 4: Stance relevance
  → Adjust priority ranking according to the user's represented stance
  → Prioritize reporting risks adverse to one's own side
```

---

## Output Format Templates

### Template 1: Full Risk Analysis Report

```markdown
# Dispute and Performance Risk Analysis Report

## Basic Information
- **Contract name**: [contract name]
- **Contract type**: [contract type]
- **Parties**: [Party A] vs [Party B] (analytical stance: [represented party])
- **Analysis date**: [date]
- **Information completeness**: [complete / partially missing (specify missing items)]

## Risk Overview

| Risk level | Count | Share |
|----------|------|------|
| 🔴 High risk | X items | X% |
| 🟡 Medium risk | X items | X% |
| 🟢 Low risk | X items | X% |

**Overall risk assessment**: [one-sentence summary]

## Risk Inventory

### 🔴 High Risk

#### Risk 1: [risk name]
- **Risk type**: dispute risk / performance risk / compliance risk / validity risk
- **Risk layer**: clause-level / transaction-level / environment-level
- **Related clause(s)**: Art. X, para. X (quote original text)
- **Risk description**: [specific description of the risk and possible dispute scenarios]
- **Legal basis**: [cite specific legal provisions]
- **Probability of occurrence**: high / medium / low
- **Impact severity**: severe / substantial / ordinary
- **Response recommendations**:
  - Prevention: [contract amendment suggestions]
  - Control: [performance management suggestions]
  - Remedy: [response after a dispute arises]
- **Confidence**: [high / medium / low, with explanation]

### 🟡 Medium Risk
[same format as above]

### 🟢 Low Risk
[same format as above]

## Key Recommendations Summary
1. [most important recommendation]
2. [next most important recommendation]
3. ...

## Limitations of the Analysis
- [explain how missing information affects the analysis]
- [explain uncertainty in legal application]
- [other reservations]
```

### Template 2: Brief Risk Alert (for quick review)

```markdown
# Risk Snapshot: [contract name]

⚠️ **High-risk alerts** (X items in total):
1. [risk name]: [one-sentence description] → Recommendation: [one-sentence recommendation]
2. ...

⚡ **Medium-risk alerts** (X items in total):
1. [risk name]: [one-sentence description] → Recommendation: [one-sentence recommendation]
2. ...

💡 **Low-risk alerts** (X items in total):
1. [risk name]: [one-sentence description]
2. ...

📋 **Priority action items**:
1. [most urgent matter to address]
2. [next most urgent matter]
```

---

## Confidence and Risk-Level Annotation System

### I. Risk-Level Rating Matrix

```
              Impact severity
              Severe  Substantial  Ordinary
Oc  High      🔴High  🔴High       🟡Med
cur
ren Medium    🔴High  🟡Med        🟡Med
ce
pro Low       🟡Med   🟡Med        🟢Low
ba-
bil-
ity
```

**Criteria for impact severity:**
- **Severe**: Contract void / voidable; contractual purpose unattainable; material economic loss (exceeding 30% of contract value); criminal law risk
- **Substantial**: Partial clauses void; significant breach liability; project delay; breakdown of commercial relationship
- **Ordinary**: Minor economic loss; resolvable by negotiation; does not affect the main purpose of the contract

**Criteria for probability of occurrence:**
- **High**: Based on the contract text and known facts, triggering conditions already exist or are highly likely
- **Medium**: Triggering conditions partly exist; reasonably possible under ordinary commercial conditions
- **Low**: Triggering requires a combination of specific conditions; unlikely under ordinary circumstances

### II. Analytical Confidence Annotation

| Confidence | Marker | Meaning | Applicable scenarios |
|--------|------|------|----------|
| **High confidence** | `[Confidence: High]` | Conclusion based on clear contractual clauses and settled legal rules | Clause clearly violates mandatory provisions; clauses contain clear contradictions |
| **Medium confidence** | `[Confidence: Medium]` | Conclusion based on reasonable inference and ordinary judicial practice | Ambiguous clauses may cause disputes; counterparty performance capacity is doubtful |
| **Low confidence** | `[Confidence: Low]` | Inference from limited information with substantial uncertainty | Incomplete information; disputed legal application; involves judicial discretion |

### III. Special Annotations

- `[Information needed]`: Marks risk points that require more information from the user for accurate assessment
- `[Legal controversy]`: Marks issues where legal application itself is disputed
- `[Regional variation]`: Marks issues where judicial practice may differ across regions
- `[Time-sensitive]`: Marks risks heavily affected by timing (e.g., statute of limitations, exclusion periods)

---

## Common Errors and Prevention

### I. Fatal Error Table

| ID | Fatal error | Error description | Possible consequences | Prevention |
|------|----------|----------|----------|----------|
| F-01 | **Omitting validity risk** | Failing to identify circumstances that may render the contract void or voidable | User transacts on an invalid contract and suffers major loss | Conduct validity review first; check item by item against Civil Code Arts. 143–157 |
| F-02 | **Ignoring mandatory provisions** | Failing to identify clauses that violate mandatory provisions of laws or administrative regulations | Relevant clauses held void | Maintain a mandatory-provisions checklist; match applicable special laws by contract type |
| F-03 | **Confusing regulatory vs validity mandatory rules** | Mistaking regulatory (administrative) mandatory rules for validity mandatory rules, or vice versa | Incorrect judgment of contract validity | Distinguish by reference to the latest judicial interpretations and guiding cases |
| F-04 | **Omitting related-contract risk** | Reviewing only a single contract and ignoring cross-effects of related contracts | Missing systemic risk | Ask whether related contracts, supplemental agreements, framework agreements, etc. exist |
| F-05 | **Ignoring limitation / time-bar risk** | Failing to flag statutes of limitations, exclusion periods, objection periods, and similar time limits | User loses avenues for rights relief | Annotate all clauses and statutory periods involving time limits |
| F-06 | **Incorrect legal application** | Using repealed laws or inapplicable jurisdictional rules as the analytical basis | Analytical conclusions entirely wrong | Confirm that cited laws remain currently in force; confirm the applicable jurisdiction |

### II. Common Traps

| ID | Trap name | Description | Response |
|------|----------|------|----------|
| T-01 | **Surface-compliance trap** | Clause wording appears compliant, but actual operations will inevitably lead to breach | Simulate real performance scenarios; test clause enforceability |
| T-02 | **One-sided perspective trap** | Analyzing only from one's own side, ignoring the other party's possible claims and defenses | Conduct a "counterparty simulation"—review the contract from the other party's stance |
| T-03 | **Static analysis trap** | Analyzing only based on circumstances at signing, ignoring changes during performance | Consider risk evolution across the full contract lifecycle |
| T-04 | **Over-riskification trap** | Labeling every uncertainty as a risk, causing the report to lose focus | Strictly apply risk screening rules; distinguish risk from ordinary commercial uncertainty |
| T-05 | **Template trap** | Applying a generic risk checklist and ignoring case-specific features | First understand the commercial logic of the specific deal, then analyze accordingly |
| T-06 | **Literal-text trap** | Analyzing only the written contract, ignoring oral agreements, trade customs, and industry practice | Proactively ask for background information beyond the contract text |
| T-07 | **Liquidated-damages panacea trap** | Believing that agreeing liquidated damages fully protects rights | Assess enforceability (counterparty ability to pay) and the likelihood of judicial adjustment |
| T-08 | **Arbitration-clause neglect trap** | Failing to review the validity of the arbitration clause and its pros/cons for one's own side | Specifically review dispute resolution clauses; weigh arbitration vs litigation |

---

## Special Scenario Handling

### Scenario 1: Contract Partially Performed

```
Handling points:
1. Distinguish risks for performed vs unperformed portions
2. Assess whether the performed portion has defects (which may trigger retrospective disputes)
3. Focus on whether changes during performance were confirmed in writing
4. Compare the risks of continued performance versus terminating the contract
5. Note limitation periods / time bars that have already run or are about to expire
```

### Scenario 2: Standard-Form / Form Contracts

```
Handling points:
1. Focus on whether notice and explanation duties for standard-form clauses were fulfilled
2. Identify clauses that may be held to "exempt one's own liability, aggravate the other party's liability, or exclude the other party's main rights"
3. Assess conflicts between standard-form clauses and non-standard clauses (handwritten / supplemental clauses)
4. Focus on application of Civil Code Arts. 496–498
5. For consumer contracts, additionally apply the Law on the Protection of Consumer Rights and Interests
```

### Scenario 3: Cross-Border Contracts

```
Handling points:
1. Confirm the validity of the governing-law clause
2. Assess uncertainty of applying foreign law
3. Review dispute resolution clauses (international arbitration vs domestic litigation)
4. Focus on foreign-exchange controls and approval requirements
5. Assess feasibility of cross-border enforcement
6. Note application of international treaties (e.g., automatic application and opt-out of CISG)
```

### Scenario 4: Multi-Party Contracts / Related-Party Transactions

```
Handling points:
1. Map the rights-and-obligations relationships among all parties
2. Identify "chain-break" risk (one party's breach triggering cascading effects)
3. Assess conflicts of interest among the parties
4. Review fairness of related-party transactions
5. Focus on information asymmetry risk
6. Assess the impact of one party's exit on the overall transaction
```

### Scenario 5: Severely Insufficient Information

```
Handling points:
1. Clearly inform the user how insufficient information affects analytical quality
2. List key information that needs to be supplemented
3. Conduct limited analysis based on available information, clearly annotating assumptions
4. Mark all conclusions with low confidence
5. Provide conditional "if... then..." analysis
6. Recommend that the user supplement information before a full analysis
```

### Scenario 6: Doubtful Contract Validity

```
Handling points:
1. Prioritize validity analysis (validity is the premise for all other risks)
2. Distinguish void, voidable, and pending-effectiveness situations
3. Assess whether partial invalidity affects the validity of other clauses
4. Analyze property restitution and damages after contract invalidity
5. Consider whether the contract can be cured into validity
6. Cite Civil Code Arts. 143–157 and related judicial interpretations
```

---

## Quality Checklist

Before outputting the final report, verify each item on the following checklist:

### A. Completeness Check

- [ ] Have all core contractual clauses been reviewed?
- [ ] Have risks at the clause, transaction, and environment layers all been covered?
- [ ] Have both dispute-risk and performance-risk dimensions been considered?
- [ ] Has contract validity been checked?
- [ ] Have dispute resolution clauses been reviewed?
- [ ] Have limitation / time-bar issues been considered?
- [ ] Have omitted clauses been identified?

### B. Accuracy Check

- [ ] Has each risk passed the "Four-Element Verification"?
- [ ] Are cited legal provisions accurate and currently in force?
- [ ] Does the risk-level rating conform to the rating matrix?
- [ ] Have definitive conclusions been distinguished from speculative judgments?
- [ ] Has confidence been correctly annotated?

### C. Practicality Check

- [ ] Does each risk include specific response recommendations?
- [ ] Are the recommendations actionable?
- [ ] Are risks prioritized?
- [ ] Does the report clearly mark information the user needs to supplement?
- [ ] Are priority action items provided?

### D. Normative Check

- [ ] Is a legal disclaimer / liability notice included?
- [ ] Are limitations of the analysis explained?
- [ ] Does the output format conform to the templates?
- [ ] Is the language professional, accurate, and unambiguous?
- [ ] Have absolute formulations (e.g., "certainly," "inevitably") been avoided?

### E. Error-Prevention Check

- [ ] Have the six fatal errors in the "Fatal Error Table" been checked item by item?
- [ ] Have the eight traps in "Common Traps" been checked?
- [ ] Has a "counterparty simulation" (review from the other party's stance) been conducted?
- [ ] Has risk across the full contract lifecycle been considered?

---

## Complete Examples

### Example 1: Simple Scenario—Risk Identification for a Premises Lease Contract

**User input:**

> I am the lessee and signed a shop lease for a 5-year term at an annual rent of RMB 500,000. Please help me identify risks. The main clauses are as follows:
> - Art. 3: Rent increases by 8% each year
> - Art. 5: Lessee may not sublease
> - Art. 7: Lessor may immediately terminate the contract upon lessee's breach and forfeit the entire deposit (deposit equals 6 months' rent, i.e., RMB 250,000)
> - Art. 9: Lessee's fit-out investment in the shop belongs to the lessor upon contract termination
> - Art. 11: Disputes are subject to the jurisdiction of the court at the lessor's domicile
> - No agreement on a preferential renewal right
> - No agreement on the lessor's repair obligations

**AI output:**

---

# Dispute and Performance Risk Analysis Report

## Basic Information
- **Contract name**: Shop Lease Contract
- **Contract type**: Premises lease contract
- **Parties**: Lessor (Party A) vs Lessee (Party B) (analytical stance: Lessee)
- **Analysis date**: [current date]
- **Information completeness**: Partially missing (full contract text not seen; analysis based only on main clauses provided by the user)

## Risk Overview

| Risk level | Count | Share |
|----------|------|------|
| 🔴 High risk | 2 items | 29% |
| 🟡 Medium risk | 3 items | 43% |
| 🟢 Low risk | 2 items | 29% |

**Overall risk assessment**: Overall, the contract is relatively unfavorable to the lessee, with multiple clauses markedly skewed toward the lessor; substantive negotiation and amendment before signing are recommended.

## Risk Inventory

### 🔴 High Risk

#### Risk 1: Termination right and deposit-forfeiture clause are clearly unfair
- **Risk type**: Dispute risk + validity risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 7—"Lessor may immediately terminate the contract upon lessee's breach and forfeit the entire deposit"
- **Risk description**: This clause has two serious problems: (1) "breach" does not distinguish minor breach from fundamental breach; any breach may trigger termination, giving the lessor an excessively broad unilateral termination right; (2) "forfeit the entire deposit" is in substance liquidated damages, and RMB 250,000 may be held excessive for a minor breach. The greater risk is that the lessor may use this clause to terminate on a minor breach, forfeit the deposit, and reclaim a shop that has already appreciated in value.
- **Legal basis**:
  - 《民法典》 Civil Code Art. 563 (conditions for statutory termination rights)
  - 《民法典》 Civil Code Art. 585, para. 2 (judicial adjustment of excessive liquidated damages)
  - 《民法典》 Civil Code Art. 497 (invalidity of standard-form clauses that unreasonably aggravate the other party's liability)
- **Probability of occurrence**: High (the clause itself constitutes risk, and the lessor has incentive to use it)
- **Impact severity**: Severe (may lose both the business premises and RMB 250,000 deposit at once)
- **Response recommendations**:
  - Prevention: Amend Art. 7 to enumerate severe breach scenarios that justify termination; replace deposit forfeiture with compensation for actual loss; add written notice and a reasonable cure period (e.g., 30 days) before lessor termination
  - Control: Strictly comply with all contractual obligations; retain all performance evidence
  - Remedy: If the lessor terminates for a minor breach, argue improper exercise of the termination right and seek judicial reduction of liquidated damages
- **Confidence**: `[Confidence: High]` Clause content is clear; legal application is clear

#### Risk 2: Fit-out attribution clause may cause major economic loss
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 9—"Lessee's fit-out investment in the shop belongs to the lessor upon contract termination"
- **Risk description**: Shop operations usually require large fit-out investment. This clause means that regardless of the reason for termination (including termination caused by lessor breach), all of the lessee's fit-out investment belongs to the lessor. Combined with Art. 7's broad termination right, the lessor may seek a pretext to terminate after the lessee completes fit-out and obtain the fit-out results for free. Fit-out investment over a 5-year lease may reach hundreds of thousands or even over RMB 1 million.
- **Legal basis**:
  - 《民法典》 Civil Code Art. 715 (lessee who improves with lessor's consent may request appropriate compensation)
  - 《民法典》 Civil Code Art. 584 (scope of damages)
- **Probability of occurrence**: High (contract termination is inevitable; fit-out attribution disputes are extremely common)
- **Impact severity**: Severe (may lose the entire fit-out investment)
- **Response recommendations**:
  - Prevention: Amend Art. 9 to distinguish fit-out compensation schemes for normal expiry, lessee breach, and lessor breach; agree a method for calculating residual fit-out value (e.g., annual depreciation); agree full compensation of fit-out investment if lessor breach causes termination
  - Control: Retain all fit-out contracts, invoices, and payment vouchers
  - Remedy: If termination is caused by the lessor, claim fit-out compensation under the principle of fairness
- **Confidence**: `[Confidence: High]`

### 🟡 Medium Risk

#### Risk 3: Rent escalation rate is too high
- **Risk type**: Performance risk
- **Risk layer**: Clause-level + transaction-level
- **Related clause(s)**: Art. 3—"Rent increases by 8% each year"
- **Risk description**: An 8% annual increase means Year-5 rent will reach about RMB 680,000 (500,000 × 1.08⁴ ≈ 680,200), roughly 36% above Year 1. If shop revenue growth underperforms expectations, later rent burden may cause operating difficulty and thus performance risk. An 8% escalation also significantly exceeds the 3%–5% market practice for ordinary commercial leases.
- **Legal basis**: 《民法典》 Civil Code Art. 533 (change of circumstances)—if the market environment changes materially, adjustment may be requested
- **Probability of occurrence**: Medium (depends on operating results and market conditions)
- **Impact severity**: Substantial (may lead to inability to pay rent and thus breach)
- **Response recommendations**:
  - Prevention: Negotiate escalation down to within 5%, or agree a floating mechanism linked to CPI / market rent; set an escalation cap
  - Control: Plan finances carefully and reserve room for rent growth
  - Remedy: If the market environment changes materially, invoke change-of-circumstances principles to seek adjustment
- **Confidence**: `[Confidence: Medium]` Whether the risk materializes depends on future operating results

#### Risk 4: Missing preferential renewal right
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Contract does not agree a preferential renewal right
- **Risk description**: After the 5-year term expires, the lessee has no contractual preferential renewal right. If the shop performs well and has accumulated customer resources and goodwill, the lessor may sharply raise rent or refuse renewal; the lessee faces forced relocation, and previously accumulated commercial value may be heavily impaired. Although 《民法典》 Civil Code Art. 734 provides a preferential leasing right on equal terms, its protection is weaker than an express contractual agreement.
- **Legal basis**: 《民法典》 Civil Code Art. 734 (upon expiry of the lease term, the lessee has a preferential right to lease on equal terms)
- **Probability of occurrence**: Medium (depends on market conditions and lessor's willingness at the time)
- **Impact severity**: Substantial (may lose the business premises and commercial accumulation)
- **Response recommendations**:
  - Prevention: Add a preferential renewal clause specifying renewal conditions and procedures; agree advance notice by the lessor (e.g., 6 months)
  - Control: Maintain a good relationship with the lessor during the term; begin renewal negotiations one year in advance
  - Remedy: Assert the preferential leasing right under Civil Code Art. 734
- **Confidence**: `[Confidence: Medium]`

#### Risk 5: Missing lessor repair obligations
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Contract does not agree the lessor's repair obligations
- **Risk description**: During use of the shop, the main structure, common facilities, etc. may need repair. Absence of an agreed allocation of repair duties may lead to disputes over repair responsibility. Although 《民法典》 Civil Code Art. 712 provides that the lessor shall perform repair obligations, the specific scope and response time lack agreement, which may cause delayed repairs that affect operations.
- **Legal basis**: 《民法典》 Civil Code Arts. 712–713 (lessor's repair obligations and cost bearing when the lessee repairs itself)
- **Probability of occurrence**: Medium (probability of repair needs over a 5-year term is relatively high)
- **Impact severity**: Ordinary (usually resolvable by negotiation; statutory rules provide a fallback)
- **Response recommendations**:
  - Prevention: Add repair-obligation clauses clarifying that the lessor is responsible for the main structure and common facilities, and agree response times and cost allocation
  - Control: Upon discovering a repair need, promptly notify the lessor in writing
  - Remedy: If the lessor fails to repair, the lessee may repair itself and require the lessor to bear the costs
- **Confidence**: `[Confidence: High]`

### 🟢 Low Risk

#### Risk 6: Sublease restriction
- **Risk type**: Performance risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 5—"Lessee may not sublease"
- **Risk description**: An absolute ban on subleasing limits the lessee's flexibility. If operations go poorly and transfer is needed, exit via sublease is unavailable; the only options are termination and bearing breach liability.
- **Probability of occurrence**: Low (depends on operating results)
- **Impact severity**: Ordinary
- **Response recommendations**:
  - Prevention: Negotiate amendment to "sublease with lessor's written consent," and agree that the lessor may not refuse without justified reason
- **Confidence**: `[Confidence: High]`

#### Risk 7: Jurisdiction clause inconvenient for the lessee
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 11—"Disputes are subject to the jurisdiction of the court at the lessor's domicile"
- **Risk description**: If the lessor's domicile differs from the shop location, the lessee must sue at the lessor's domicile, increasing enforcement costs. If the shop location is the lessor's domicile, this risk does not exist.
- **Probability of occurrence**: Low (need to confirm whether lessor's domicile coincides with the shop location) `[Information needed]`
- **Impact severity**: Ordinary
- **Response recommendations**:
  - Prevention: Negotiate amendment to "jurisdiction of the court at the place of performance (i.e., the shop location)"
- **Confidence**: `[Confidence: Medium]` Lessor domicile information needs confirmation

## Key Recommendations Summary
1. **Highest priority**: Amend Art. 7 termination clause—limit to severe breach scenarios, add notice and cure period, remove "forfeit entire deposit"
2. **High priority**: Amend Art. 9 fit-out attribution clause; establish scenario-based fit-out compensation mechanisms
3. **Medium priority**: Negotiate rent escalation down to within 5% or switch to a floating mechanism
4. **Medium priority**: Add a preferential renewal right clause
5. **Recommended**: Add lessor repair-obligation clauses
6. **Recommended**: Amend the sublease clause to "sublease with consent"

## Limitations of the Analysis
- This analysis is based on 7 main clauses provided by the user; the full contract was not seen, so risks in other clauses may be omitted
- No lessor background (credit, title status, etc.) was obtained, so counterparty risk cannot be assessed
- No specific shop location or market rent levels were obtained, so rent reasonableness cannot be precisely assessed
- The user is advised to provide the full contract text for a more complete risk analysis

---

### Example 2: Complex Scenario—Risk Identification for a Technology Development Contract

**User input:**

> We are an internet company (Party A) intending to commission a software development company (Party B) to develop an enterprise management system; contract amount RMB 3 million. The draft contract is complete; please help identify risks. Main clauses:
>
> - Art. 2: Party B shall complete system development and deliver within 6 months after signing
> - Art. 3: The system shall meet Party A's business requirements (specific requirements to be based on a requirements document Party A will provide later)
> - Art. 4: Payment: 30% on signing (RMB 900,000), 40% on mid-term acceptance (RMB 1.2 million), 30% on final acceptance (RMB 900,000)
> - Art. 5: Mid-term acceptance standard: core system functions can be demonstrated as running
> - Art. 6: Final acceptance standard: system passes Party A-organized user acceptance testing
> - Art. 7: Party B shall warrant the system has no major defects; warranty period is 6 months after acceptance
> - Art. 8: System source code and all intellectual property belong to Party A
> - Art. 9: Party B may not subcontract development work to third parties
> - Art. 10: If Party B delivers late, liquidated damages of 0.5% of the contract amount per day of delay
> - Art. 11: Party A may terminate the contract at any time; amounts already paid are non-refundable
> - Art. 12: Both parties owe confidentiality regarding contract contents and technical information; confidentiality period is 3 years after contract termination
> - Art. 13: Disputes submitted to Beijing Arbitration Commission for arbitration
> - Party B is a small company founded 2 years ago with a team of about 20 people

**AI output:**

---

# Dispute and Performance Risk Analysis Report

## Basic Information
- **Contract name**: Enterprise Management System Technology Development Contract
- **Contract type**: Technology development contract (commissioned development)
- **Parties**: Internet company (Party A / commissioning party) vs software development company (Party B / developer) (analytical stance: Party A)
- **Contract amount**: RMB 3 million
- **Analysis date**: [current date]
- **Information completeness**: Partially missing (full contract and requirements document not seen; detailed Party B qualification information insufficient)

## Risk Overview

| Risk level | Count | Share |
|----------|------|------|
| 🔴 High risk | 4 items | 36% |
| 🟡 Medium risk | 5 items | 45% |
| 🟢 Low risk | 2 items | 18% |

**Overall risk assessment**: The contract has multiple major risks; the most prominent are acceptance-dispute risk from missing requirements definition and counterparty performance-capacity risk. Although payment cadence and IP ownership afford Party A some protection, there are clear gaps in requirements management, change control, quality assurance, and other key links; substantive amendments before signing are recommended.

## Risk Inventory

### 🔴 High Risk

#### Risk 1: Missing requirements definition—the greatest dispute hazard
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level + transaction-level
- **Related clause(s)**: Art. 3—"The system shall meet Party A's business requirements (specific requirements to be based on a requirements document Party A will provide later)"
- **Risk description**: This is the contract's most serious risk. Requirements are not fixed at signing and are only "to be provided later," creating chained risks:
  1. **Scope disputes**: Party A may continually expand scope; Party B may claim work is outside the original scope; disagreement over "reasonable requirements" is inevitable
  2. **Fuzzy acceptance standards**: Art. 6's final acceptance standard is "pass user acceptance testing," but the basis for testing (the requirements document) itself is unsettled, so acceptance standards are in substance unsettled
  3. **Schedule disputes**: Requirements changes necessarily affect the development timeline, but the contract has no mechanism for how changes affect the schedule
  4. **Fee disputes**: Whether added requirements increase fees is entirely unaddressed
  5. **Purpose failure**: If the requirements document cannot be finalized or the parties cannot agree, the contract may deadlock
- **Legal basis**:
  - 《民法典》 Civil Code Art. 851 (technology development contracts should clarify technical goals and technical solutions)
  - 《民法典》 Civil Code Art. 510 (supplementary rules where contract content is unclear)
  - 《民法典》 Civil Code Art. 511 (handling where quality requirements are unclear)
- **Probability of occurrence**: High (requirements disputes are the most common dispute type in software development)
- **Impact severity**: Severe (may cause project failure and unattainability of the contractual purpose)
- **Response recommendations**:
  - Prevention:
    - Complete and mutually confirm the requirements document before signing; attach the confirmed document as a contract annex
    - If later determination is truly needed, agree: timelines and procedures for requirements confirmation; approval workflow for change; mechanisms adjusting schedule and fees for change; handling when agreement cannot be reached
    - Add requirements baseline management clauses
  - Control: Designate a person responsible for requirements management; all requirements changes must be confirmed in writing
  - Remedy: If a dispute has arisen, collect all requirements communication records as evidence
- **Confidence**: `[Confidence: High]`

#### Risk 2: Party B performance-capacity risk
- **Risk type**: Performance risk
- **Risk layer**: Transaction-level
- **Related clause(s)**: Comprehensive assessment
- **Risk description**: Party B is a small company founded only 2 years ago with a team of about 20, taking on a RMB 3 million enterprise management system project, with the following capacity risks:
  1. **Technical capacity risk**: A small team may lack experience and technical depth for large enterprise management systems
  2. **Personnel stability risk**: Loss of core developers at a small company may directly stall the project
  3. **Financial risk**: If Party B takes multiple projects at once, funding stress may reduce investment in this project
  4. **Ongoing service risk**: If Party B struggles or fails during the warranty period, Party A may lose technical support
  5. **Subcontracting risk**: Although Art. 9 prohibits subcontracting, Party B may covertly subcontract due to insufficient capacity
- **Legal basis**:
  - 《民法典》 Civil Code Art. 509 (duty of full performance)
  - 《民法典》 Civil Code Art. 528 (right of defense of insecurity—performance may be suspended upon definite evidence that the other party has lost performance capacity)
- **Probability of occurrence**: Medium to high (reasonable inference from company size and founding time) `[Information needed: Party B's past project experience, financial condition, core team background]`
- **Impact severity**: Severe (may cause complete project failure)
- **Response recommendations**:
  - Prevention:
    - Conduct due diligence before signing (financial statements, past project cases, core team résumés)
    - Require a performance bond or bank guarantee from Party B
    - Agree a list of core developers who may not be replaced without Party A's consent
    - Add milestone acceptance points; shorten payment intervals; reduce single payment amounts
    - Agree Party A may review project progress and staffing
  - Control: Establish periodic progress reporting (e.g., weekly / biweekly); Party A assigns a project manager to follow up
  - Remedy: Upon discovering serious capacity shortfalls, promptly exercise the right of defense of insecurity and suspend payment; prepare alternate vendors
- **Confidence**: `[Confidence: Medium]` Detailed Party B background information needed

#### Risk 3: Party A's unilateral termination clause—a double-edged risk
- **Risk type**: Dispute risk + validity risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 11—"Party A may terminate the contract at any time; amounts already paid are non-refundable"
- **Risk description**: The clause appears favorable to Party A but actually carries these risks:
  1. **Validity risk**: If Party A terminates without justified reason, "amounts already paid are non-refundable" may be held unfair to Party B. More critically, the clause does not address ownership and handover of work already completed upon Party A's termination, so Party A may terminate yet obtain no development deliverables
  2. **Reverse-use risk**: Party B may argue the clause only grants Party A a termination right without Party B's termination right or compensation when Party A terminates, and in a dispute claim Party A must compensate for expected benefits
  3. **Operational risk**: If Party A terminates after mid-term acceptance (70% already paid, i.e., RMB 2.1 million), losses are huge
- **Legal basis**:
  - 《民法典》 Civil Code Art. 563 (statutory termination rights)
  - 《民法典》 Civil Code Art. 566 (handling after contract termination)
  - 《民法典》 Civil Code Art. 580 (exceptions to continued performance of non-monetary obligations)
- **Probability of occurrence**: Medium (depends on project execution)
- **Impact severity**: Severe (may lose amounts already paid and obtain no development deliverables)
- **Response recommendations**:
  - Prevention: Amend Art. 11 to clearly provide:
    - Upon Party A termination, Party B shall deliver completed work product and source code
    - Settle fees based on completed work volume
    - Distinguish consequences of termination for Party A's reasons versus Party B's breach
    - Add Party B's termination rights (e.g., upon Party A's material breach)
  - Control: Exercise termination cautiously; before terminating, assess the value relationship between amounts paid and deliverables obtained
  - Remedy: If termination is needed, first demand in writing that Party B deliver completed work product
- **Confidence**: `[Confidence: High]`

#### Risk 4: Excessive late-delivery liquidated damages—likely judicial reduction and confrontation
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 10—"If Party B delivers late, liquidated damages of 0.5% of the contract amount per day of delay"
- **Risk description**: 0.5% per day annualizes to 182.5%; 67 days of delay reaches the full contract amount. Problems include:
  1. **Judicial reduction risk**: Courts / arbitral tribunals are highly likely to reduce liquidated damages to a reasonable range relative to actual loss under 《民法典》 Civil Code Art. 585, para. 2; Party A's actual protection will be far below expectation
  2. **Confrontation effect**: Excessive liquidated damages may lead Party B, when approaching delay, to adopt confrontation strategies (e.g., claiming requirements changes extended the schedule) rather than actively catching up
  3. **Reverse risk**: If the contract lacks Party A late-payment liquidated damages, or Party A's rate is far lower, rights and obligations may be held severely unequal
- **Legal basis**:
  - 《民法典》 Civil Code Art. 585, para. 2 (adjustment of excessive liquidated damages)
  - Related provisions of the Minutes of the National Courts Work Conference on Implementing the Civil Code
- **Probability of occurrence**: High (delay is common in software projects; the liquidated damages clause will almost certainly be triggered and disputed)
- **Impact severity**: Substantial (Party A's liquidated-damages protection may shrink substantially)
- **Response recommendations**:
  - Prevention: Adjust liquidated damages to a reasonable level (e.g., 0.03%–0.05% per day, annualizing ~11%–18%), and agree a cap (e.g., 20%–30% of contract amount); add reciprocal liquidated damages for Party A late payment; add a right for Party A to terminate if delay exceeds a set period (e.g., 60 days)
  - Control: Manage project progress carefully; spot delay risk early
  - Remedy: Upon Party B delay, in addition to claiming liquidated damages, collect evidence of actual loss
- **Confidence**: `[Confidence: High]`

### 🟡 Medium Risk

#### Risk 5: Acceptance standards insufficiently objective—final-acceptance dispute risk
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 5 (mid-term acceptance), Art. 6 (final acceptance)
- **Risk description**:
  1. Mid-term standard "core functions can be demonstrated as running" is too broad—what are "core functions"? Does "demonstrable as running" equal "actually usable"?
  2. Final standard "pass Party A-organized UAT"—who writes test cases? What is the pass criterion? May Party A indefinitely fail to organize acceptance or deliberately set overly high standards?
  3. No time limits for acceptance or deemed-acceptance rules
- **Legal basis**: 《民法典》 Civil Code Art. 853 (acceptance standards for technology development contracts)
- **Probability of occurrence**: High
- **Impact severity**: Substantial
- **Response recommendations**:
  - Prevention: Specify concrete mid-term and final acceptance standards (function lists, performance metrics, defect severity and quantity limits); agree Party A shall organize acceptance within X business days after Party B's acceptance application; agree that Party A's failure to organize acceptance on time is deemed acceptance; agree remediation rounds and deadlines if acceptance fails
- **Confidence**: `[Confidence: High]`

#### Risk 6: Incomplete IP ownership clause
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 8—"System source code and all intellectual property belong to Party A"
- **Risk description**: Although IP is assigned to Party A, the clause is incomplete in these respects:
  1. **Pre-existing components**: Party B may use its own code libraries, frameworks, and tools (pre-existing components); do their IP rights also transfer to Party A? If not, does Party A receive a license?
  2. **Third-party components**: The system may use open-source or third-party commercial components whose license terms may conflict with "all IP belongs to Party A"
  3. **Delivery scope**: Only "source code" is agreed; technical docs, design docs, test cases, deployment scripts, etc. are omitted
  4. **Non-compete**: May Party B use the same technology to develop similar systems for Party A's competitors?
- **Legal basis**:
  - 《民法典》 Civil Code Art. 859 (IP ownership in commissioned development)
  - 《著作权法》 Copyright Law Art. 19
- **Probability of occurrence**: Medium
- **Impact severity**: Substantial
- **Response recommendations**:
  - Prevention: Clearly distinguish IP arrangements for newly developed results, pre-existing components, and third-party components; require Party B to provide a third-party component list and license information; expand delivery scope to all technical documentation; add Party B non-compete clauses
- **Confidence**: `[Confidence: High]`

#### Risk 7: Warranty period too short and warranty content unclear
- **Risk type**: Performance risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 7—"Party B shall warrant the system has no major defects; warranty period is 6 months after acceptance"
- **Risk description**:
  1. "Major defects" is undefined—what constitutes "major"? Are ordinary defects covered?
  2. A 6-month warranty is short for an enterprise management system—many defects surface only after full production use
  3. No response times or fix deadlines during the warranty period
  4. No post-warranty technical support arrangement
  5. Combined with Risk 2 (Party B is a small company), Party B may be unable to support during the warranty period
- **Probability of occurrence**: Medium
- **Impact severity**: Substantial
- **Response recommendations**:
  - Prevention: Define defect severity levels (critical / major / ordinary / minor) and response/fix SLAs for each; extend warranty to 12 months; agree a warranty-period SLA; retain 5%–10% of the contract price as a warranty retention, payable after warranty expiry with no major issues
- **Confidence**: `[Confidence: High]`

#### Risk 8: Missing requirements change management mechanism
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Contract does not agree change management clauses
- **Risk description**: Requirements change is almost inevitable in software development. Complete absence of a change management mechanism will lead to:
  1. When Party A proposes change, Party B may refuse or demand a price increase as "outside contract scope"
  2. Party B may attribute its own development mistakes to "requirements change"
  3. Impact of change on schedule and fees cannot be fairly allocated
  4. Combined with Risk 1 (missing requirements definition), the probability of project failure greatly increases
- **Legal basis**: 《民法典》 Civil Code Art. 543 (parties may amend the contract by consensus)
- **Probability of occurrence**: High
- **Impact severity**: Substantial
- **Response recommendations**:
  - Prevention: Add a complete change management clause covering: change request process, evaluation procedures, approval authority, assessment of schedule and fee impact, and a change confirmation template
- **Confidence**: `[Confidence: High]`

#### Risk 9: Incomplete confidentiality clause
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 12—"Both parties owe confidentiality regarding contract contents and technical information; confidentiality period is 3 years after contract termination"
- **Risk description**:
  1. Scope of "technical information" is unclear—does it include Party A's business data and user data?
  2. No exceptions to confidentiality (e.g., public information, independent development)
  3. No liquidated damages or compensation standard for breach of confidentiality
  4. No duty for Party B to return or destroy Party A's data after termination
  5. If personal information processing is involved, 《个人信息保护法》 Personal Information Protection Law requirements may apply
- **Probability of occurrence**: Medium
- **Impact severity**: Substantial (involves trade secrets and data security)
- **Response recommendations**:
  - Prevention: Broaden the definition of confidential information; add confidentiality exceptions; agree liquidated damages; add data return/destruction clauses; if personal information is involved, add a data processing agreement (DPA)
- **Confidence**: `[Confidence: High]`

### 🟢 Low Risk

#### Risk 10: Difficulty enforcing the subcontracting ban
- **Risk type**: Performance risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 9—"Party B may not subcontract development work to third parties"
- **Risk description**: Although subcontracting is prohibited, Party A can hardly monitor in real time whether Party B covertly subcontracts. A small company with insufficient capacity has strong incentives to subcontract.
- **Probability of occurrence**: Low to medium
- **Impact severity**: Ordinary
- **Response recommendations**:
  - Prevention: Agree that Party B shall develop at a Party A-designated site or in a manner Party A can monitor; require periodic reports of project team membership; agree liquidated damages for violating the subcontracting ban
- **Confidence**: `[Confidence: Medium]`

#### Risk 11: Pros and cons of the arbitration clause
- **Risk type**: Dispute risk
- **Risk layer**: Clause-level
- **Related clause(s)**: Art. 13—"Disputes submitted to Beijing Arbitration Commission for arbitration"
- **Risk description**: Arbitration is final and not appealable. If the award is unfavorable, Party A lacks appellate relief. Arbitration also offers confidentiality and relatively high efficiency; overall it is a reasonable choice for technology contract disputes.
- **Probability of occurrence**: Low (the arbitration clause itself is valid; risk lies in outcome uncertainty)
- **Impact severity**: Ordinary
- **Response recommendations**:
  - If Party A prefers to retain appeal rights, switch to court jurisdiction; if accepting arbitration, confirm the full and accurate name "Beijing Arbitration Commission" (avoid confusion with bodies such as CIETAC)
- **Confidence**: `[Confidence: High]`

## Key Recommendations Summary

1. **Highest priority—complete the requirements document before signing**: Complete and mutually confirm the requirements document before signing and attach it as an annex. This is the key measure to reduce the contract's greatest risk.
2. **Highest priority—Party B due diligence**: Conduct due diligence on Party B before signing—assess technical capacity, financial condition, and past project experience. Consider requiring a performance bond.
3. **High priority—add change management**: Establish a complete requirements change management process.
4. **High priority—improve acceptance standards**: Clarify concrete mid-term and final acceptance standards, timelines, and procedures.
5. **High priority—amend the termination clause**: Clarify post-termination delivery of work product and fee settlement.
6. **High priority—adjust liquidated damages**: Bring late-delivery liquidated damages to a reasonable level and add reciprocal clauses.
7. **Medium priority—improve IP clauses**: Distinguish newly developed results, pre-existing components, and third-party components.
8. **Medium priority—strengthen warranty clauses**: Extend the warranty period, clarify defect levels and response standards, and retain a warranty amount.
9. **Medium priority—improve confidentiality clauses**: Broaden confidentiality scope; add data processing and return clauses.

## Limitations of the Analysis
- This analysis is based on 12 main clauses provided by the user; the full contract was not seen, so risks in other clauses may be omitted
- Detailed Party B background (past projects, financial statements, core team) was not obtained; counterparty risk assessment is inferred from limited information
- No requirements document was seen (not yet prepared), so technical feasibility risk cannot be assessed
- Party A's IT infrastructure and integration needs are unknown; technical compatibility risk may be omitted
- The user is advised to provide the full contract text and detailed Party B materials for supplemental analysis

---

*This report is a reference legal risk analysis and does not constitute a formal legal opinion. For high-risk matters, engage a qualified lawyer for in-depth review.*
