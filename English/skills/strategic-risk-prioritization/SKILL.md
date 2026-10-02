---
name: strategic-risk-prioritization
description: "When legal analysis yields multiple possible conclusions, risk points, or disputed issues, these risks must be systematically ranked by probability of occurrence and degree of impact so decision-makers can focus on the most critical risks and allocate resources rationally. Trigger this skill when: (1) legal due diligence finds multiple compliance risks that need ranking; (2) litigation strategy requires assessing likelihood and consequences of multiple adverse conclusions; (3) transaction structuring requires identifying and ordering key legal obstacles; (4) contract review finds multiple risk clauses that need modification priority; (5) regulatory compliance assessment requires graded management of multiple violation risks; (6) any scenario requiring strategic trade-offs among legal risks under limited resources."
---

> **Chinese source (authoritative):** [`../../skills/strategic-risk-prioritization/SKILL.md`](../../skills/strategic-risk-prioritization/SKILL.md)

# Strategic-Level Risk Prioritization

> **Rank multiple possible conclusions by probability and impact to support resource allocation and strategic trade-offs in legal decision-making.**

## Overview Table

| Item | Content |
|------|------|
| **Capability name** | Strategic-level risk prioritization |
| **Capability type** | Comprehensive judgment (probability assessment × impact assessment × ranking decision) |
| **Input** | Multiple identified legal risk points / possible conclusions / disputed issues |
| **Output** | Priority-ranked risk list with probability rating, impact rating, composite priority, and response suggestions |
| **Upstream capabilities** | Legal element analysis, fact-finding, legal research, stakeholder identification |
| **Downstream capabilities** | Risk-mitigation design, litigation strategy, compliance remediation planning |
| **Core methodology** | Probability-Impact Matrix + legal-context calibration |
| **Applicable fields** | Litigation, compliance, M&A, contracts, IP, criminal defense, and all other fields |

---

## Legal Disclaimer

⚠️ **Important**

1. Risk rankings produced by this skill are **decision-support references**, not final legal opinions. Probability assessments rest on available information and legal analysis; actual outcomes are affected by judicial discretion, evidence changes, policy shifts, and other uncertainties.
2. Rankings should be dynamically adjusted for case facts, governing law of the forum, parties’ risk preferences, and commercial goals.
3. Highly complex rankings or those involving major interests should be reviewed by senior counsel or a specialist team.
4. Probability assessment is not precise prediction; all ratings should carry confidence labels and uncertainty notes.

---

## I. Core Concepts

### 1.1 What Is Strategic-Level Risk Prioritization

Strategic-level risk prioritization is a **structured decision method** whose core logic is:

```
Risk priority = f(probability of occurrence, degree of impact, time urgency, controllability)
```

In a legal context, for each identified risk point systematically assess:
- **How likely is it?** (probability dimension)
- **If it occurs, how severe are the consequences?** (impact dimension)
- **When might it occur?** (time dimension)
- **To what extent can we control or mitigate it?** (controllability dimension)

### 1.2 Legal Specifics of Probability Assessment

Legal-risk probability differs from statistical probability:

| Specificity | Explanation | Example |
|--------|------|------|
| **Normative probability** | Logical inference from legal rules, not frequency statistics | Likelihood a contract clause is void depends on whether legal elements are met |
| **Discretionary uncertainty** | Judge/arbitrator discretion makes outcomes uncertain | Whether liquidated damages are "excessive" varies by judge |
| **Information asymmetry** | Counterparty’s evidence and strategy unknown | Counterparty may hold key evidence not yet disclosed |
| **Dynamic evolution** | Legal environment and policy orientation keep changing | New judicial interpretations may change existing adjudicative rules |
| **Multi-factor coupling** | Risks may correlate and stack | One compliance risk may trigger a chain reaction |

### 1.3 Multidimensional Impact Framework

Legal-risk impact is not limited to direct economic loss:

```
Degree of impact = direct economic loss
          + indirect economic loss (opportunity cost, business interruption)
          + legal consequences (administrative penalties, criminal liability, loss of qualifications)
          + reputational impact (brand harm, market trust)
          + strategic impact (deal failure, blocked market access)
          + compliance cascade effects (triggering other regulatory reviews)
```

### 1.4 Key Term Definitions

| Term | Definition |
|------|------|
| **Risk Item** | An identified matter that may lead to adverse legal consequences |
| **Possible Outcome** | A judgment a decision-maker or regulator may make on a legal issue |
| **Probability Rating** | Graded assessment of likelihood of occurrence |
| **Impact Rating** | Graded assessment of severity of consequences |
| **Risk Score** | Combined quantified result of probability and impact ratings |
| **Risk Tolerance** | Upper bound of risk the decision-maker is willing to accept |
| **Residual Risk** | Risk remaining after mitigation measures |

---

## II. Complete Workflow

### Phase 1: Risk Identification and Aggregation (Input Preparation)

**Goal:** Ensure all relevant risk points are fully identified and clearly described.

#### Step 1.1: Collect Risk Inventory

From prior analysis, aggregate all identified risk points; each should include:

- [ ] Risk ID (unique)
- [ ] Risk name (concise)
- [ ] Risk description (nature, source, and trigger conditions)
- [ ] Legal basis involved (provisions, judicial interpretations, cases, etc.)
- [ ] Relevant factual basis (key facts supporting the risk judgment)
- [ ] Stakeholders (subjects affected by the risk)

#### Step 1.2: Deduplicate and Merge

- Merge substantively identical risks stated differently
- Check containment (A is a subset of B); decide whether to split or merge
- Keep granularity appropriate: not too broad (unevaluable) or too fine (losing strategic view)

#### Step 1.3: Risk Classification

Preliminary classification dimensions:

| Dimension | Categories |
|----------|------|
| **Legal field** | Contract, tort, compliance, IP, labor, criminal, etc. |
| **Risk nature** | Interpretation risk, fact-finding risk, procedural risk, enforcement risk, policy-change risk |
| **Time stage** | Immediate; short-term (within 1 year); medium-term (1–3 years); long-term (3+ years) |
| **Controllability** | Internally controllable; partially controllable; externally uncontrollable |

---

### Phase 2: Probability Assessment

**Goal:** Systematically assess likelihood for each risk point.

#### Step 2.1: Establish Probability Rating Standards

Five-level probability system:

| Level | Label | Probability range | Legal-context description | Typical situation |
|------|------|----------|-------------|----------|
| **P5** | Almost certain | >85% | Clear law, clear facts, almost no room for dispute | Clear contract terms, no exemption, breach facts solid |
| **P4** | Likely | 60%–85% | Mainstream adjudicative view supports, but minority dissent exists | Most cases support; some courts differ |
| **P3** | Possible | 40%–60% | Application of law disputed; outcome uncertain | Vague law; inconsistent courts |
| **P2** | Unlikely | 15%–40% | Minority view supports; cannot fully exclude | Few cases support; mainstream opposite |
| **P1** | Extremely unlikely | <15% | Law clearly excludes, or no factual basis | Limitation expired with no interruption |

#### Step 2.2: Item-by-Item Probability Assessment

For each risk point, consider in turn:

**A. Certainty of legal rules**
- Are relevant provisions clear? Multiple interpretations?
- Authoritative judicial interpretations or guiding cases?
- Legal gaps or conflicts?

**B. Adequacy of factual basis**
- Is evidence supporting the risk adequate?
- Are key facts disputed?
- Is the evidence chain complete? How is the burden of proof allocated?

**C. Adjudicative tendency**
- What is the mainstream view in the field?
- Tendency of the forum court/arbitral institution?
- Recent trend changes?

**D. Counterparty behavior forecast**
- Does the counterparty have motive and ability to assert the risk?
- How might its litigation strategy affect realization of the risk?

**E. External environment**
- Regulatory tightening or loosening trends?
- Public opinion that may affect adjudication?
- Industry-wide systemic risk?

#### Step 2.3: Probability Calibration

After preliminary assessment:

1. **Anchoring check:** Overweighted because identified first?
2. **Availability-bias check:** Overweighted because of a recent similar case?
3. **Overconfidence check:** Too sure of legal analysis, understating uncertainty?
4. **Correlation check:** Do risks correlate (one raises another’s probability)?

---

### Phase 3: Impact Assessment

**Goal:** Multidimensional assessment of consequence severity if each risk materializes.

#### Step 3.1: Establish Impact Rating Standards

Five-level impact system:

| Level | Label | Impact description | Economic-loss reference | Legal-consequence reference |
|------|------|----------|-------------|-------------|
| **I5** | Catastrophic | Threatens organizational survival or core business | >50% of subject matter or >20% of annual revenue | License revocation / criminal liability / compulsory liquidation |
| **I4** | Major | Severely harms core interests or strategic goals | 20%–50% of subject matter or 5%–20% of annual revenue | Major administrative penalty / business restriction / high damages |
| **I3** | Moderate | Significant but bearable loss | 5%–20% of subject matter or 1%–5% of annual revenue | Ordinary administrative penalty / partial damages / contract modification |
| **I2** | Minor | Limited loss; core interests unaffected | 1%–5% of subject matter or <1% of annual revenue | Warning / deadline remediation / small damages |
| **I1** | Negligible | Almost no substantive loss | <1% of subject matter | Oral warning / internal remediation only |

> **Note:** Economic-loss references should adjust for case subject matter and party economic scale.

#### Step 3.2: Multidimensional Impact Assessment

Assess each risk on six dimensions:

| Dimension | Assessment focus | Suggested weight |
|------|----------|----------|
| **Direct economic loss** | Damages, fines, litigation costs | 30% |
| **Indirect economic loss** | Business interruption, opportunity cost, higher financing cost | 20% |
| **Legal consequences** | Administrative penalties, criminal liability, qualifications, contract validity | 20% |
| **Reputational impact** | Brand harm, customer loss, market trust decline | 15% |
| **Strategic impact** | Deal failure, blocked market access, weakened competitive position | 10% |
| **Compliance cascade** | Triggering other regulatory reviews, series of suits | 5% |

> **Weight note:** General suggestion only; adjust for scenario and party priorities (e.g., listed companies may raise reputation weight above 25%).

#### Step 3.3: Special Impact Considerations

- **Worst Case:** Under most adverse assumptions, how far can impact go?
- **Most Likely Case:** Under reasonable expectations, what is the median impact?
- **Cascade analysis:** Does realization trigger other risks? Domino effects?
- **Irreversibility:** Remediable later, or irreversible once it occurs?

---

### Phase 4: Composite Ranking and Matrix Construction

**Goal:** Combine probability and impact into a composite priority ranking.

#### Step 4.1: Calculate Risk Score

**Base risk score:**

```
Base risk score = Probability rating (P) × Impact rating (I)
```

| Score range | Priority | Color | Disposition |
|-----------|--------|----------|----------|
| 20–25 | **Critical** | 🔴 Red | Immediate action; highest priority; needs senior decision |
| 12–19 | **High** | 🟠 Orange | Preferential handling; dedicated response plan |
| 6–11 | **Medium** | 🟡 Yellow | Routine management; risk monitoring list |
| 3–5 | **Low** | 🟢 Green | Accept risk; periodic review |
| 1–2 | **Negligible** | ⚪ White | Record for reference; no dedicated action |

#### Step 4.2: Introduce Adjustment Factors

Base score may not capture all strategic considerations; introduce:

**A. Time-urgency factor (T)**

| Time window | Coefficient |
|----------|----------|
| Immediate (<1 month) | ×1.5 |
| Short-term (1–6 months) | ×1.2 |
| Medium-term (6–12 months) | ×1.0 |
| Long-term (>12 months) | ×0.8 |

**B. Controllability factor (C)**

| Controllability | Coefficient |
|----------|----------|
| Fully uncontrollable | ×1.3 |
| Partially controllable | ×1.0 |
| Highly controllable | ×0.7 |

**C. Irreversibility factor (R)**

| Reversibility | Coefficient |
|----------|----------|
| Fully irreversible | ×1.3 |
| Partially reversible | ×1.0 |
| Highly reversible | ×0.8 |

**Adjusted risk score:**

```
Adjusted risk score = Base risk score × T × C × R
```

#### Step 4.3: Build Risk Matrix

Plot probability-impact matrix and mark all risk points:

```
Impact →    I1       I2       I3       I4       I5
Probability ↓  Negligible  Minor   Moderate   Major  Catastrophic
─────────────────────────────────────────────────
P5      ⚪5     🟡10    🟠15    🔴20    🔴25
Almost certain

P4      ⚪4     🟡8     🟠12    🟠16    🔴20
Likely

P3      ⚪3     🟢6     🟡9     🟠12    🟠15
Possible

P2      ⚪2     🟢4     🟢6     🟡8     🟡10
Unlikely

P1      ⚪1     ⚪2     ⚪3     🟢4     🟢5
Extremely unlikely
```

#### Step 4.4: Final Ranking

1. Rank all risk points by adjusted score high to low
2. For equal scores, prioritize by:
   - Higher impact rating (prefer overestimating impact)
   - Higher time urgency
   - Higher irreversibility
3. Label correlations among risks (trigger chains)

---

### Phase 5: Validation and Output

**Goal:** Validate reasonableness of ranking; produce structured output.

#### Step 5.1: Ranking Reasonableness Checks

- [ ] **Intuition check:** Roughly consistent with experienced practitioners’ intuition? Major deviations need re-examination.
- [ ] **Extreme check:** Highest and lowest risks reasonable? Clear over/underestimation?
- [ ] **Correlation check:** Related risks properly reflected?
- [ ] **Sensitivity check:** Would changing a key assumption significantly change ranking? If so, label sensitivity.
- [ ] **Stakeholder check:** All stakeholders’ concerns considered?

#### Step 5.2: Sensitivity Analysis

For top-ranked risks:

- If probability rating up/down one level, does ranking change?
- If impact rating up/down one level, does ranking change?
- Which risks are most sensitive to rating changes? (need special attention and ongoing monitoring)

#### Step 5.3: Generate Output Report

Produce the full risk-priority ranking report per the output templates below.

---

## III. Common Fields and Legal Sources

| Legal field | Typical risk types | Key sources for probability | Special impact considerations |
|----------|-------------|-----------------|-----------------|
| **Contract disputes** | Validity, breach liability, termination rights | Civil Code Contracts Book; related judicial interpretations; guiding cases | Liquidated-damages adjustment range; lost-profits findings |
| **Corporate governance** | Resolution validity; shareholder rights; D&O liability | Company Law and judicial interpretations; articles of association | Cascade from set-aside resolutions; personal liability |
| **Intellectual property** | Infringement findings; invalidity; damages quantum | Patent/Trademark/Copyright Laws and judicial interpretations | Injunction effects; punitive damages; market-share loss |
| **Labor & employment** | Unlawful termination; social-insurance compliance; non-compete | Labor Contract Law and judicial interpretations; local rules | Collective-incident risk; administrative penalties; reputation |
| **Administrative compliance** | Administrative penalties; licenses; data compliance | Industry regulations; Administrative Penalty Law; Data Security Law; PIPL | Loss of qualifications; business shutdown; cross-border compliance cascade |
| **Criminal risk** | Entity crime; executive criminal liability | Criminal Law and judicial interpretations; criminal policy | Personal liberty; enterprise survival; social impact |
| **M&A transactions** | Closing conditions; reps & warranties; antitrust review | Securities Law; Anti-Monopoly Law; related rules | Deal failure; price adjustment; integration risk |
| **Cross-border law** | Jurisdiction; choice of law; judgment enforcement | Treaties; conflict rules; foreign law | Cross-border enforcement difficulty; diplomatic factors; FX risk |

---

## IV. Verification and Screening Rules

### 4.1 Inclusion Screening

A matter should enter risk ranking if **all** of the following are met:

```
Inclusion = all of:
  (1) Clear legal basis or reasonable legal reasoning supports existence of the risk
  (2) Identifiable trigger conditions or scenarios
  (3) Occurrence would produce assessable adverse consequences
  (4) Substantial nexus with the current decision matter
```

### 4.2 Exclusion Rules

Exclude or handle separately:

- **Purely hypothetical risks:** Theoretical possibilities with no factual basis
- **Fully mitigated risks:** Eliminated by effective measures (record as "handled")
- **Out-of-scope risks:** No substantial nexus with current decision
- **Double-counted risks:** Sub-risks already covered by other items (unless separate assessment needed)

### 4.3 Rating Consistency Rules

| Rule | Explanation |
|----------|------|
| **Like-kind consistency** | Similar risks’ probability ratings should not differ by more than 2 levels without explanation |
| **Legal-logic consistency** | If risk A is a precondition of risk B, then P(A) ≥ P(B) |
| **Impact-progression consistency** | If A’s consequences include B’s, then I(A) ≥ I(B) |
| **Reverse check** | Lowest-ranked risks truly need no preferential action; highest truly most urgent |

---

## V. Output Format Templates

### Template A: Risk Priority Ranking Master Table

```markdown
# Legal Risk Priority Ranking Report

## Basic Information
- Project/case name: [name]
- Assessment date: [date]
- Assessor: [name/team]
- Scope: [description]
- Total risk points: [number]

## Risk Priority Ranking Master Table

| Priority | Risk ID | Risk name | Prob (P) | Impact (I) | Base | Adjusted | Level | Related risks |
|--------|---------|---------|---------|---------|--------|--------|------|---------|
| 1 | R-XX | [name] | P? | I? | ?? | ??.? | 🔴 Critical | R-XX |
| 2 | R-XX | [name] | P? | I? | ?? | ??.? | 🟠 High | — |
| ... | ... | ... | ... | ... | ... | ... | ... | ... |

## Risk Matrix Chart
[Insert probability-impact matrix with risk positions]

## Key Findings Summary
1. [Core conclusion on highest-priority risk]
2. [Items needing immediate action]
3. [Items needing ongoing monitoring]
```

### Template B: Single-Risk Detail Card

```markdown
## Risk Assessment Card: [Risk ID] [Risk name]

### Risk Description
[Nature, source, and trigger conditions]

### Legal Basis
- Statutory provisions: [specific articles]
- Judicial interpretations: [if any]
- Related cases: [if any]

### Probability Assessment
- **Rating: P[?] ([label])**
- Assessment basis:
  - Certainty of legal rules: [analysis]
  - Adequacy of factual basis: [analysis]
  - Adjudicative tendency: [analysis]
  - Counterparty behavior forecast: [analysis]
- Confidence: [High/Medium/Low]
- Uncertainty note: [key uncertain factors]

### Impact Assessment
- **Rating: I[?] ([label])**
- By dimension:
  | Dimension | Assessment | Note |
  |------|------|------|
  | Direct economic loss | [amount range] | [note] |
  | Indirect economic loss | [amount range] | [note] |
  | Legal consequences | [description] | [note] |
  | Reputational impact | [degree] | [note] |
  | Strategic impact | [degree] | [note] |
  | Cascade effects | [description] | [note] |

### Adjustment Factors
- Time urgency: [coefficient] — [note]
- Controllability: [coefficient] — [note]
- Irreversibility: [coefficient] — [note]

### Composite Assessment
- Base risk score: [P×I]
- Adjusted risk score: [result]
- **Priority level: [level]**

### Preliminary Response Suggestions
- Suggested strategy: [avoid / mitigate / transfer / accept]
- Concrete measures: [brief]
- Suggested owner: [role]
- Time node: [deadline]
```

---

## VI. Confidence Labeling System

### 6.1 Overall Assessment Confidence

| Confidence | Label | Conditions | Labeling |
|--------|------|------|----------|
| **High** | ★★★ | Clear law + clear facts + adequate case support + complete information | `[Confidence: High ★★★]` |
| **Medium** | ★★☆ | Basically clear law + basically clear facts + some case reference + basically complete information | `[Confidence: Medium ★★☆]` |
| **Low** | ★☆☆ | Vague law / disputed facts / insufficient cases / missing information | `[Confidence: Low ★☆☆]` |

### 6.2 Single-Rating Confidence

Each probability and impact rating should carry a confidence label:

```
Probability rating: P4 (Likely) [Confidence: Medium ★★☆]
  → Source of uncertainty: Whether counterparty holds key evidence still unclear
  → If counterparty holds favorable evidence, probability may drop to P3

Impact rating: I4 (Major) [Confidence: High ★★★]
  → Economic-loss calculation well founded; legal consequences clear
```

### 6.3 Confidence and Decision-Making

| Confidence | Decision suggestion |
|--------|----------|
| High | May formulate strategy directly on ranking |
| Medium | Further verify key assumptions before final decision |
| Low | Ranking for reference only; supplement information and reassess, or adopt conservative strategy |

---

## VII. Common Errors and Prevention

### 7.1 Fatal Error Table

| ID | Fatal error | Consequence | Prevention |
|------|---------|------|----------|
| **E1** | Omitting key risk points | Unidentified risk may be the greatest threat | Multidimensional identification checklists; cross-review; "red team" thinking |
| **E2** | Confusing probability and impact | Mistaking "severe consequences" for "likely to occur" | Strict stepwise assessment: probability first, then impact, independently |
| **E3** | Ignoring risk correlations | Underestimating systemic risk and cascades | Draw risk-correlation maps; identify trigger chains and common root causes |
| **E4** | Static assessment never updated | Outdated ranking misleads decisions | Periodic review; immediate update on key events |
| **E5** | Over-quantification creating false precision | Decision-makers treat ranking as precise prediction | Clearly label confidence and uncertainty; use ranges, not point values |
| **E6** | Ignoring parties’ risk preferences | Ranking divorced from actual needs | Confirm risk tolerance and priority concerns before ranking |
| **E7** | Labeling all risks "High" | Ranking loses meaning; cannot guide resource allocation | Force distribution: Critical ≤20%; require clear differentiation |

### 7.2 Common Traps

| Trap | Manifestation | Correction |
|------|------|----------|
| **Anchoring** | First-assessed risk becomes reference anchor | Randomize assessment order; assess independently then compare |
| **Availability bias** | Recent cases overweighted | Systematically retrieve historical data, not memory alone |
| **Confirmation bias** | Seeking only evidence supporting initial judgment | Actively seek contrary evidence; devil’s advocate |
| **Groupthink** | Team converges on dominant view | Independent assessment first; anonymous scoring |
| **Ignoring base rates** | Ignoring general occurrence rates in similar cases | Consult statistics or similar-case big data first, then adjust for the case |
| **Zero-risk illusion** | Believing measures eliminate risk completely | Always assess residual risk; there is no zero risk |
| **Single-dimension overweight** | Focusing only on economic loss | Mandate multidimensional impact framework |

---

## VIII. Special Scenario Handling

### 8.1 Ranking When Information Is Severely Insufficient

**Scenario:** Key facts unclear, application of law uncertain, no case reference.

**Handling:**
1. Apply **conservatism**: when uncertain, take higher probability and impact ratings
2. Clearly label `[Insufficient information]` and state missing key information
3. Provide **conditional rankings**: if fact X holds, ranking is A; if not, ranking is B
4. Make "supplement information" itself the highest-priority action item

### 8.2 Ranking When Risks Are Strongly Correlated

**Scenario:** Occurrence of risk A significantly raises probability of risk B (trigger chain).

**Handling:**
1. Draw a **risk-correlation map** with trigger relations and directions
2. Compute **joint risk scores** reflecting stacked effects
3. Raise priority of **root risks** in the trigger chain
4. Explicitly label correlations so decision-makers do not view risks in isolation

### 8.3 Ranking When Parties’ Risk Preferences Are Extreme

**Scenario:** Extreme risk aversion (e.g., listed company facing regulatory review) or extreme risk preference (e.g., startup pursuing rapid expansion).

**Handling:**
1. Provide **objective ranking** (standard methodology) and **subjective ranking** (adjusted for party preference)
2. For risk-averse parties: raise impact weight; use worst-case analysis
3. For risk-preferring parties: raise probability weight; focus on most-likely case
4. Regardless of preference, **fatal risks** (criminal liability, loss of qualifications) always marked highest priority

### 8.4 Cross-Jurisdiction Risk Ranking

**Scenario:** Legal risks across multiple jurisdictions need unified ranking.

**Handling:**
1. Independently assess probability and impact within each jurisdiction
2. Unify impact standards (overall party interests as baseline)
3. Add **enforceability** across jurisdictions as an extra adjustment factor
4. Label confidence differences across jurisdictions

### 8.5 Rapid Ranking for Urgent Decisions

**Scenario:** Extremely limited time; full assessment impossible.

**Handling:**
1. Use **simplified three-level assessment**: High/Medium/Low for both probability and impact
2. Focus on **top three risks**; list others as "to be assessed"
3. Preferentially assess **irreversible** and **time-sensitive** risks
4. Clearly label as "rapid assessment version"; follow with full assessment update

---

## IX. Quality Checklist

After completing risk priority ranking, check item by item:

#### A. Completeness
- [ ] All identified risk points included
- [ ] Each has probability and impact ratings
- [ ] Each rating has clear assessment basis
- [ ] Correlations among risks considered

#### B. Consistency
- [ ] Like-kind risks internally consistent
- [ ] Probability and impact assessed independently (not confused)
- [ ] Adjustment-factor standards uniform
- [ ] Rating standards consistent throughout

#### C. Reasonableness
- [ ] Ranking passes intuition check
- [ ] Critical risks ≤20% of total
- [ ] Sufficient differentiation (not all clustered at one level)
- [ ] Sensitivity analysis done; key assumptions identified

#### D. Usability
- [ ] Output clear; decision-makers can grasp quickly
- [ ] Each risk has preliminary response suggestions
- [ ] Confidence labels complete
- [ ] Uncertainties and limitations clearly stated

#### E. Timeliness
- [ ] Based on latest law and judicial practice
- [ ] Recent policy changes and adjudicative trends considered
- [ ] Review time nodes set
- [ ] Conditions triggering reassessment clarified

---

## X. Complete Examples

### Example 1: Simple Scenario — Risk Ranking in a Contract Dispute

#### Background

Company Jia (buyer) and Company Yi (seller) signed an equipment purchase contract for RMB 5 million. After delivery, Jia found quality problems and intends to assert rights against Yi. Counsel identified the following risk points needing priority ranking.

#### Identified Risk Points

| ID | Risk name | Risk description |
|------|---------|---------|
| R-01 | Quality-objection period risk | Jia raised quality objection only 6 months after receipt; contract provides 30-day objection period |
| R-02 | Adverse quality-appraisal risk | Appraisal may find equipment conforms to contractual technical standards |
| R-03 | Liquidated damages reduced as excessive | Contract liquidated damages 30% of contract amount (RMB 1.5 million); court may reduce |
| R-04 | Jurisdiction-objection risk | Yi may object to jurisdiction, causing transfer |

#### Probability Assessment

**R-01: Quality-objection period risk**
- Legal analysis: Civil Code Art. 621 — buyer must notify within inspection period; failure treated as conforming quality. Contract provides 30 days; Jia raised after 6 months.
- Adjudicative tendency: Most courts strictly apply contractual inspection periods; some may relax if period unreasonably short.
- **Probability: P4 (Likely, 70%)** [Confidence: Medium ★★☆]
- Uncertainty: Whether court finds 30 days reasonable, and whether Jia has reasonable grounds for delayed notice.

**R-02: Adverse quality-appraisal risk**
- Fact analysis: Jia claims performance parameters unmet, but equipment used 6 months; wear may affect appraisal.
- **Probability: P3 (Possible, 50%)** [Confidence: Low ★☆☆]
- Uncertainty: Highly dependent on appraisal institution and method; currently unpredictable.

**R-03: Liquidated damages reduced as excessive**
- Legal analysis: Civil Code Art. 585 and related judicial interpretations — liquidated damages generally "excessive" if over actual loss by 30%. Contract 30% damages likely reduced if actual loss lower.
- Adjudicative tendency: Courts commonly reduce excessive liquidated damages sua sponte or on application.
- **Probability: P4 (Likely, 75%)** [Confidence: High ★★★]

**R-04: Jurisdiction-objection risk**
- Legal analysis: Contract designates Jia’s place court; clear and valid.
- **Probability: P2 (Unlikely, 20%)** [Confidence: High ★★★]
- Note: Yi may object but success unlikely; main impact is time delay.

#### Impact Assessment

| Risk ID | Direct economic | Indirect economic | Legal consequences | Reputation | Strategy | Cascade | Composite |
|---------|---------|---------|---------|------|------|------|---------|
| R-01 | Lose all claims (RMB 5M) | Equipment replacement cost | Lose case | Low | Low | None | **I5 (Catastrophic)** |
| R-02 | Lose quality-claim basis | Appraisal fees | Evidentiary disadvantage | Low | Low | Affects R-01 | **I4 (Major)** |
| R-03 | Liquidated damages reduced ~RMB 1M | None | Partial win | Low | Low | None | **I3 (Moderate)** |
| R-04 | Higher litigation costs | 3–6 month delay | Procedural delay | Low | Low | None | **I2 (Minor)** |

#### Composite Ranking

| Priority | ID | Risk name | P | I | Base | T | C | R | Adjusted | Level |
|--------|------|---------|---|---|--------|---|---|---|--------|------|
| **1** | R-01 | Quality-objection period | P4 | I5 | 20 | 1.0 | 0.7 | 1.3 | 18.2 | 🔴 Critical |
| **2** | R-02 | Adverse quality appraisal | P3 | I4 | 12 | 1.2 | 1.0 | 1.0 | 14.4 | 🟠 High |
| **3** | R-03 | Liquidated-damages reduction | P4 | I3 | 12 | 1.0 | 1.0 | 0.8 | 9.6 | 🟡 Medium |
| **4** | R-04 | Jurisdiction objection | P2 | I2 | 4 | 1.2 | 1.0 | 0.8 | 3.8 | 🟢 Low |

#### Key Conclusions

1. **🔴 Highest priority (R-01):** Objection-period issue is the greatest risk. If the court finds Jia failed to notify within the period, all quality claims are lost. Immediately collect reasonable grounds for delayed notice (latent defects, Yi’s repair promises, etc.) and study whether the 30-day period is unreasonable. Controllability "partially controllable" (0.7) because Jia can improve position with supplementary evidence.
2. **🟠 High priority (R-02):** Appraisal outcome directly shapes the case and correlates with R-01 (finding nonconformity may help the objection-period argument). Apply early for appraisal and prepare materials thoroughly.
3. **🟡 Medium priority (R-03):** Liquidated-damages reduction is likely but limited in impact (reduces part of recovery, not all) and is normal litigation risk. Prepare adequate evidence of actual loss.
4. **🟢 Low priority (R-04):** Jurisdiction objection unlikely to succeed; even if successful, only causes delay. No dedicated response; handle routinely.

**Overall confidence: Medium ★★☆**
> Main uncertainties: R-02 appraisal unpredictable; R-01 outcome highly dependent on individual judicial discretion.

---

### Example 2: Complex Scenario — Risk Ranking in a Tech-Company Acquisition

#### Background

Group A (listed company) proposes to acquire 100% of Company B (AI startup) for RMB 800 million cash. Diligence identified the following risk points needing strategic priority ranking to support Group A’s board acquisition decision.

#### Identified Risk Points

| ID | Risk name | Risk description |
|------|---------|---------|
| R-01 | Core patent invalidity | 1 of B’s 3 core patents under competitor invalidity challenge |
| R-02 | Data-compliance risk | B processes large volumes of personal information with imperfect compliance; risk of violating PIPL |
| R-03 | Core-team attrition | Non-competes of CTO and 3 key engineers soon expire; may leave after acquisition |
| R-04 | Antitrust review risk | Combined share in a specific niche market may exceed review thresholds |
| R-05 | IP ownership dispute | Some algorithms developed by a former employee while employed; employee claims partial IP ownership |
| R-06 | Government-subsidy clawback | B received RMB 20 million local tech subsidy; equity change may trigger clawback |
| R-07 | Related-party transaction compliance | One independent director of A also advises B; may constitute a related-party transaction |
| R-08 | Earn-out / valuation-bet dispute | Ambiguous earn-out wording in acquisition agreement may cause later disputes |

#### Probability Assessment

| ID | Probability | Core basis | Confidence |
|------|---------|---------|--------|
| R-01 | P3 (Possible, 45%) | Invalidity petition accepted; novelty dispute; outcome uncertain | ★★☆ |
| R-02 | P4 (Likely, 70%) | Diligence found multiple defects: no user consent, no impact assessment, cross-border transfer not filed | ★★★ |
| R-03 | P4 (Likely, 65%) | Non-competes expire in 6 months; active headhunters; CTO contact signs | ★★☆ |
| R-04 | P3 (Possible, 40%) | Market definition disputed; narrow definition would exceed thresholds | ★☆☆ |
| R-05 | P2 (Unlikely, 25%) | Former employee signed IP assignment, but clauses defective | ★★☆ |
| R-06 | P4 (Likely, 75%) | Subsidy agreement expressly requires clawback on major equity-structure change | ★★★ |
| R-07 | P5 (Almost certain, 90%) | Facts clear; related-party transaction elements clearly met | ★★★ |
| R-08 | P3 (Possible, 50%) | Calculation of "net profit" in earn-out not clearly defined | ★★☆ |

#### Impact Assessment

| ID | Direct economic | Indirect economic | Legal consequences | Reputation | Strategy | Cascade | Composite |
|------|---------|---------|---------|------|------|------|---------|
| R-01 | Patent value loss ~RMB 150M | Weakened tech barrier | Patent invalid | Medium | High (core asset devalued) | Affects valuation | **I5 (Catastrophic)** |
| R-02 | Fines up to RMB 50M or 5% of annual revenue | Remediation cost | Admin penalty + order to remediate | High (listed co.) | High (AI business constrained) | May trigger CSRC attention | **I4 (Major)** |
| R-03 | Tech capability decline | Project delay, customer loss | No direct legal consequence | Medium | High (core competitiveness lost) | Affects earn-out | **I4 (Major)** |
| R-04 | Deal may be prohibited | Time and opportunity cost | Deal termination | High | Extreme (deal fails) | Full impact | **I5 (Catastrophic)** |
| R-05 | Litigation damages + license fees | Restricted tech use | IP dispute | Low | Medium | Affects R-01 | **I3 (Moderate)** |
| R-06 | Clawback RMB 20M | None | Administrative clawback | Low | Low | None | **I2 (Minor)** |
| R-07 | Deal may be challenged | Shareholder-suit risk | Disclosure violation | High (listed co.) | Medium | Triggers CSRC review | **I4 (Major)** |
| R-08 | Earn-out dispute ~RMB 100–200M | Management distraction | Arbitration/litigation | Medium | Medium | None | **I3 (Moderate)** |

#### Composite Ranking

| Priority | ID | Risk name | P | I | Base | T | C | R | Adjusted | Level |
|--------|------|---------|---|---|--------|---|---|---|--------|------|
| **1** | R-01 | Core patent invalidity | P3 | I5 | 15 | 1.2 | 1.3 | 1.3 | 30.4 | 🔴 Critical |
| **2** | R-04 | Antitrust review | P3 | I5 | 15 | 1.5 | 1.3 | 1.3 | 38.0 | 🔴 Critical |
| **3** | R-02 | Data compliance | P4 | I4 | 16 | 1.2 | 0.7 | 1.0 | 13.4 | 🟠 High |
| **4** | R-03 | Core-team attrition | P4 | I4 | 16 | 1.5 | 1.0 | 1.0 | 24.0 | 🔴 Critical |
| **5** | R-07 | Related-party transaction | P5 | I4 | 20 | 1.5 | 0.7 | 1.0 | 21.0 | 🔴 Critical |
| **6** | R-08 | Earn-out dispute | P3 | I3 | 9 | 0.8 | 0.7 | 0.8 | 4.0 | 🟢 Low |
| **7** | R-05 | IP ownership dispute | P2 | I3 | 6 | 1.0 | 1.0 | 1.0 | 6.0 | 🟡 Medium |
| **8** | R-06 | Subsidy clawback | P4 | I2 | 8 | 1.0 | 0.7 | 0.8 | 4.5 | 🟢 Low |

> **Ranking note:** Although R-04 has the highest adjusted score (38.0), given R-01’s fundamental impact on deal core value and R-04’s low-confidence market-definition uncertainty, R-01 ranks first. R-04 ranks second because failed antitrust review terminates the deal outright.

#### Risk Correlation Map

```
R-01 (patent invalidity) ──→ affects valuation ──→ R-08 (earn-out dispute)
       ↑
R-05 (ownership dispute) ──→ may aggravate patent risk

R-03 (team attrition) ──→ affects performance ──→ R-08 (earn-out dispute)

R-07 (related-party) ──→ triggers regulatory review ──→ may affect R-04 (antitrust)

R-02 (data compliance) ──→ admin penalty ──→ listed-company reputation ──→ may trigger CSRC attention
```

#### Strategic Recommendations

**🔴 Must resolve before deal (gate conditions):**

1. **R-01 Core patent invalidity**
   - Strategy: Make invalidity outcome a closing condition; or deduct expected loss from valuation (~150M × 45% = RMB 67.5M)
   - Alternative: Require seller patent-validity reps and indemnities
   - Timing: Complete assessment before signing

2. **R-04 Antitrust review**
   - Strategy: Engage antitrust counsel for pre-assessment; prepare favorable market-definition arguments; consider conditional filing (e.g., partial divestiture)
   - Alternative: If review risk too high, adjust structure (e.g., stepwise acquisition)
   - Timing: Pre-assessment before signing

3. **R-07 Related-party transaction**
   - Strategy: Immediately require independent director to resign as B’s adviser or recuse from voting; fulfill listed-company related-party disclosure and approval procedures
   - Timing: Immediate

**🟠 Focus controls during deal:**

4. **R-03 Core-team attrition**
   - Strategy: Key-person lock-up in acquisition agreement (3-year service + equity incentive); new non-compete and service agreements with CTO before closing
   - Timing: Synchronize at signing

5. **R-02 Data compliance**
   - Strategy: Require B to start remediation before closing; compliance reps and indemnities; reserve remediation budget (~RMB 5–10M)
   - Timing: Start before closing; finish within 6 months after

**🟡 Routine management:**

6. **R-05 IP ownership** — cover via reps and indemnities
7. **R-08 Earn-out dispute** — clarify calculation before signing

**🟢 Accept risk:**

8. **R-06 Subsidy clawback** — RMB 20M is 2.5% of RMB 800M deal; deduct directly from valuation

**Overall confidence: Medium ★★☆**
> Main uncertainties: (1) R-01 invalidity outcome; (2) R-04 market definition highly uncertain; (3) R-03 true team intentions hard to fully know. Re-rank after key information on these three clarifies.

#### Sensitivity Analysis

| Assumption change | Ranking impact | Suggestion |
|----------|---------|------|
| R-01 patent invalidated (P3→P5) | R-01 adjusted score rises sharply; may become deal-killer | Make patent validity a closing condition |
| R-04 market defined narrowly (P3→P4) | R-04 becomes first priority | Pre-communicate with antitrust authority |
| R-03 CTO clearly intends to leave (P4→P5) | R-03 rises; correlates to R-08 | Immediately start talent lock-up talks |
| R-02 regulator opens investigation (P4→P5) | R-02 rises to Critical | Consider pausing the deal |

---

## Appendix: Quick Reference Card

### Five-Step Rapid Ranking (time-urgent scenarios)

```
Step 1: List all risk points (≤10)
Step 2: Quickly label each High/Medium/Low probability
Step 3: Quickly label each High/Medium/Low impact
Step 4: Rank: High P + High I > High I + Med P > High P + Med I > rest
Step 5: Label response suggestions and time nodes for top 3
```

### Probability Assessment Quick Mnemonics

```
Clear law, clear facts → P5 (Almost certain)
Mainstream support, few dissent → P4 (Likely)
Each side holds ground, hard to predict → P3 (Possible)
Minority view hard to sustain → P2 (Unlikely)
No legal or factual basis → P1 (Extremely unlikely)
```

### Impact Assessment Quick Mnemonics

```
Survival at stake, irreversible → I5 (Catastrophic)
Core interests heavily hit → I4 (Major)
Significant but bearable loss → I3 (Moderate)
Limited loss, no structural harm → I2 (Minor)
Almost no impact → I1 (Negligible)
```
