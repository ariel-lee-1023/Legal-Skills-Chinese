---
name: legal-judgment-prediction
description: Based on a case-fact narrative, orchestrate 8 atomic capabilities to predict charges, applicable provisions, sentence length, and sentencing circumstances, and output a structured prediction report with confidence assessment.
---

> **Chinese source (authoritative):** [`../../skills/legal-judgment-prediction/SKILL.md`](../../skills/legal-judgment-prediction/SKILL.md)

# Legal Judgment Prediction_8skills

## I. Capability Overview

This composite capability is oriented to criminal cases. It takes a case-fact narrative text as input and, by coordinating 8 atomic capabilities, completes a full reasoning chain from fact parsing to judgment prediction, ultimately outputting a structured prediction report that includes charge prediction, applicable provisions, sentence prediction, sentencing-circumstance analysis, and confidence assessment.

---

## II. Atomic Capability Selection List

### 2.1 Selected Atomic Capabilities

| ID | Name | Selection Rationale |
|------|------|----------|
| 4 | Legal core element extraction | The first step of judgment prediction must precisely extract from the case-fact text irreducible core elements such as subject, act, object, time, result, and circumstances—the data foundation for all subsequent reasoning |
| 5 | Legal concept comprehension | Extracted act elements must be matched to the statutory constitutive elements of specific charges; understanding the intension and extension of concepts such as “attempted crime,” “burglary of a dwelling (入户盗窃),” and “joint crime” is required for accurate characterization |
| 6 | Dispute-issue and legal-relationship identification | Cases often involve concurrence of charges, completed vs. attempted offense disputes, principal vs. accessory findings, etc.; identifying these issues directly affects the path chosen for sentence prediction |
| 8 | Legal provision retrieval | After determining the charge, corresponding Criminal Law articles and judicial interpretations must be retrieved to obtain statutory sentencing ranges, sentencing tiers, and legal bases for aggravating or mitigating circumstances |
| 9 | Case retrieval | Retrieve judgments in similar cases to obtain sentencing patterns and range distributions in judicial practice, provide empirical support for sentence prediction, and calibrate confidence |
| 16 | Deductive reasoning | Syllogistically reason from legal norms (major premise) and case facts (minor premise); argue element-by-element whether constitutive requirements are met; layer sentencing circumstances to derive the final sentence range |
| 49 | Legal document format application | The prediction report must be output in a structured format, referencing the argumentation structure of the “本院认为” (this Court’s view) section of judicial documents to ensure professionalism and readability |
| 50 | Standardized legal terminology | Charge names, sentencing-circumstance descriptions, and statutory citations in the prediction report must use standardized legal terminology to avoid ambiguity and ensure the report can be used directly for legal practice reference |

### 2.2 Excluded Atomic Capabilities

**No exclusions.** This composite capability selects all 8 available atomic capabilities. Rationale:

Legal judgment prediction is a highly integrative legal reasoning task. From fact parsing (AS-4) to concept matching (AS-5), dispute identification (AS-6), provision retrieval (AS-8), case reference (AS-9), logical reasoning (AS-16), and finally report format standards (AS-49) and terminology standards (AS-50), every link is indispensable. Missing any capability would reduce the accuracy or professionalism of the prediction.

---

## III. Complete Execution Flow

### Flow Overview

```
Input: Case-fact narrative text
  │
  ▼
[Step 1] AS-4 Legal core element extraction
  │
  ▼
[Step 2] AS-5 Legal concept comprehension
  │
  ▼
[Step 3] AS-6 Dispute-issue and legal-relationship identification
  │
  ▼
[Quality Checkpoint QC-1] ── Verify element completeness and characterization consistency
  │                         │
  │ Pass                    │ Fail → Backtrack to Step 1 or Step 2
  ▼
[Step 4] AS-8 Legal provision retrieval
  │
  ▼
[Step 5] AS-9 Case retrieval
  │
  ▼
[Quality Checkpoint QC-2] ── Verify provision fit and case relevance
  │                         │
  │ Pass                    │ Fail → Backtrack to Step 3 for re-identification
  ▼
[Step 6] AS-16 Deductive reasoning
  │
  ▼
[Quality Checkpoint QC-3] ── Verify logical self-consistency of reasoning
  │                         │
  │ Pass                    │ Fail → Backtrack to Step 4 to supplement provisions
  ▼
[Step 7] AS-49 Legal document format application
  │
  ▼
[Step 8] AS-50 Standardized legal terminology
  │
  ▼
Output: Structured judgment prediction report (with confidence)
```

---

### Step 1: Legal Core Element Extraction

- **Capability invoked:** AS-4 (Legal core element extraction)
- **Input:** Original case-fact narrative text
- **Execution content:**
  - Extract the following irreducible core elements from the text:
    - **Subject elements:** Defendant identity, co-offender information, victim information
    - **Act elements:** Specific criminal acts, manner of commission, tools used
    - **Object elements:** Object of infringement, property involved and amounts
    - **Time elements:** Time of offense, time of apprehension, time span
    - **Causal elements:** Causal chain between act and result
    - **Result elements:** Whether the crime was completed; degree of actual harm
    - **Circumstance elements:** Voluntary surrender, confession, restitution/compensation, prior convictions / recidivism, and other aggravating or mitigating circumstances
- **Output:** Structured element list (key-value pairs)
- **Passed to next step:** Complete structured element list

> **Case One example:** Extract subject (Zhang 3), acts (forging ID card; impersonating to defraud property), purpose (repay debts), target amount (RMB 100,000), result (discovered and unsuccessful), time (28 April 2017).
>
> **Case Two example:** Extract subjects (An Xu + Yang XX joint crime), acts (forced entry into a dwelling with tools and theft), object (gold and silver jewelry), time (offense on 9 May 2016; apprehended on 15 April 2018), mitigating circumstance (surrendered RMB 3,000 of illegal gains).

---

### Step 2: Legal Concept Comprehension

- **Capability invoked:** AS-5 (Legal concept comprehension)
- **Input:** Structured element list from Step 1
- **Execution content:**
  - Preliminarily match possible charges based on act elements (one or more candidates)
  - For each candidate charge, expand its statutory constitutive elements (subject, subjective aspect, object, objective aspect)
  - Precisely define special legal concepts involved, including but not limited to:
    - Crime-form concepts (completed crime, attempt, discontinuation, preparation)
    - Joint-crime concepts (accomplice, principal offender, accessory, coerced accomplice)
    - Special act-type concepts (burglary of a dwelling / 入户盗窃, pickpocketing, theft while carrying a weapon, etc.)
    - Sentencing-circumstance concepts (voluntary surrender, confession, meritorious service, restitution/compensation, recidivism, etc.)
  - Preliminarily compare case elements against constitutive requirements
- **Output:** Candidate charge list with constitutive-element breakdown; definitions of special legal concepts involved
- **Passed to next step:** Candidate charges and constitutive-element comparison table; special-concept list

> **Case One example:** Understand constitutive elements of fraud—purpose of illegal appropriation; fabricating facts or concealing truth; obtaining others’ property by deception; relatively large amount; understand attempted crime—already begun to commit the crime; failed to succeed for reasons beyond the offender’s will.
>
> **Case Two example:** Understand “burglary of a dwelling” for theft—criminalized regardless of amount; understand criteria for joint crime; understand criteria distinguishing principal offender from accessory.

---

### Step 3: Dispute-Issue and Legal-Relationship Identification

- **Capability invoked:** AS-6 (Dispute-issue and legal-relationship identification)
- **Input:** Structured element list from Step 1 + candidate charges and constitutive-element comparison table from Step 2
- **Execution content:**
  - Identify possible core dispute issues in the case, typically including:
    - **Charge dispute:** Whether there is concurrence of charges or this-crime vs. that-crime contention
    - **Crime-form dispute:** Completed or attempted
    - **Accomplice-status dispute:** Principal offender or accessory
    - **Amount / circumstance dispute:** Which sentencing tier the amount involved falls into
    - **Sentencing-circumstance dispute:** Whether a particular mitigating / aggravating circumstance is established
  - Clarify the nature of legal relationships among parties (e.g., joint-crime relationship; victim–defendant relationship)
  - For each dispute issue, annotate its impact weight on the final judgment (high / medium / low)
- **Output:** Dispute-issue list (with impact weights); legal-relationship map
- **Passed to next step:** Dispute-issue list and impact weights

> **Case One example:** Identify dispute issues—whether fraud was completed or attempted (high impact); “huge amount” finding—which sentencing tier of Article 266 applies to RMB 100,000 (high impact).
>
> **Case Two example:** Identify dispute issues—whether An Xu’s status in the joint crime is principal offender or accessory (high impact); impact of surrendering RMB 3,000 on sentencing (medium impact).

---

### 🔍 Quality Checkpoint QC-1: Element Completeness and Characterization Consistency

**Verification logic:**

| Check Item | Verification Standard | On Failure |
|--------|----------|------------|
| Element completeness | Four core elements—subject, act, object, result—have all been extracted without obvious omission | Backtrack to **Step 1**; re-examine the original text and supplement omitted elements |
| Characterization consistency | No obvious contradiction between constitutive elements of candidate charges and extracted elements | Backtrack to **Step 2**; re-examine whether concept comprehension is erroneous |
| Adequacy of dispute identification | At least one dispute issue identified; if facts are clearly undisputed, explicitly annotate “no material dispute” | Backtrack to **Step 3**; check for omitted potential disputes |
| Element–dispute linkage | Each dispute issue can be traced to specific factual elements | Backtrack to **Step 1** or **Step 3**; supplement linkages |

---

### Step 4: Legal Provision Retrieval

- **Capability invoked:** AS-8 (Legal provision retrieval)
- **Input:** Candidate charges from Step 2 + dispute-issue list from Step 3
- **Execution content:**
  - Retrieve Criminal Law articles directly corresponding to candidate charges (conviction clauses)
  - Retrieve General Part articles related to crime forms (e.g., attempt, discontinuation, joint crime)
  - Retrieve articles related to sentencing circumstances (e.g., voluntary surrender, confession, recidivism, restitution/compensation)
  - Retrieve relevant judicial interpretations (e.g., amount standards, sentencing guidelines)
  - For each dispute issue, annotate corresponding legal authority
  - Extract statutory sentencing ranges for each sentencing tier
- **Output:** Applicable provision list (full text or key summaries); statutory sentencing ranges by tier
- **Passed to next step:** Provision list and statutory sentencing-range table

> **Case One example:** Retrieve Criminal Law Art. 266 (fraud and sentencing ranges), Art. 23 (attempted crime), Art. 67 para. 3 (truthful confession as mitigation).
>
> **Case Two example:** Retrieve Criminal Law Art. 264 (theft), Art. 25 (joint crime), Art. 67 para. 3 (truthful confession), Art. 52 (fine), Art. 53 (payment of fine), Art. 64 (recovery of illegal gains).

---

### Step 5: Case Retrieval

- **Capability invoked:** AS-9 (Case retrieval)
- **Input:** Candidate charges from Step 2 + dispute issues from Step 3 + applicable provisions from Step 4
- **Execution content:**
  - Use charge, crime form, amount involved, and sentencing circumstances as search keywords to find similar cases
  - Focus on case matching along these dimensions:
    - Cases with the **same charge**
    - Cases with the **same crime form** (e.g., all attempted)
    - Cases with **similar amounts / circumstances**
    - Cases from the **same region** (if geographic information is available), considering regional sentencing differences
  - Extract sentencing outcome distributions from retrieved cases (sentence ranges, fine ranges)
  - For dispute issues, find adjudicative tendencies of courts in related precedents
  - Statistical concentration trends of sentencing outcomes to form a sentencing reference range
- **Output:** Similar-case retrieval summary; sentencing reference range; adjudicative tendencies on dispute issues
- **Passed to next step:** Sentencing reference range; adjudicative-tendency data

> **Case One example:** Find sentencing patterns in similar attempted-fraud cases to help assess the reasonableness of a seven-month sentence range.
>
> **Case Two example:** Derive Shanghai regional judicial sentencing patterns from similar burglary-of-dwelling theft cases; find precedents on accessory determination standards.

---

### 🔍 Quality Checkpoint QC-2: Provision Fit and Case Relevance

| Check Item | Verification Standard | On Failure |
|--------|----------|------------|
| Provision coverage | Conviction clauses, crime-form clauses, and sentencing-circumstance clauses have all been retrieved | Backtrack to **Step 4**; supplement omitted provisions |
| Provision fit | Retrieved provisions logically match candidate charges and dispute issues; no mismatch | Backtrack to **Step 3**; re-examine charge characterization |
| Case relevance | Retrieved cases are comparable to the current case on charge, circumstances, amount, etc. | Backtrack to **Step 5**; adjust keywords and re-search |
| Reasonableness of sentencing range | Sentencing range from case retrieval falls within statutory sentencing ranges | Check whether provision retrieval omitted aggravating / mitigating circumstance rules |

---

### Step 6: Deductive Reasoning

- **Capability invoked:** AS-16 (Deductive reasoning)
- **Input:** All outputs from Steps 1–5 (element list, constitutive elements, dispute issues, provisions, case references)
- **Execution content:**
  - **Layer 1 — Conviction reasoning:**
    - Major premise: Constitutive elements of Charge X are A, B, C, D (from Steps 2 and 4)
    - Minor premise: Case facts satisfy elements a, b, c, d (from Step 1)
    - Conclusion: The defendant’s conduct constitutes Charge X
    - Argue element-by-element whether each constitutive requirement is met
  - **Layer 2 — Crime-form reasoning:**
    - Determine completed / attempted / discontinued based on result elements
    - If attempted, argue the two conditions “already begun” and “reasons beyond the offender’s will”
  - **Layer 3 — Sentencing-tier reasoning:**
    - Determine the baseline sentencing tier based on amount / circumstances involved
    - Layer the impact of crime form on sentencing (e.g., attempt may warrant lighter or reduced punishment)
  - **Layer 4 — Sentencing-circumstance overlay reasoning:**
    - Assess each sentencing circumstance one by one (voluntary surrender, confession, restitution, recidivism, etc.)
    - Overlay adjustments in the order “reduce first, then lighten”
    - Combine the case-retrieval sentencing range to derive the final sentence point estimate and range
  - **Layer 5 — Accessory-penalty reasoning:**
    - Derive fine amount (referencing statutory rules and case practice)
    - Derive whether restitution, confiscation, or other accessory orders are needed
  - **Dispute-issue adjudication reasoning:**
    - For each dispute issue identified in Step 3, give a reasoned conclusion
    - Annotate the degree of certainty of that conclusion
  - **Confidence assessment:**
    - Assess prediction confidence based on factors including:
      - Clarity of constitutive-element matching
      - Number and complexity of dispute issues
      - Consistency of case-retrieval results
      - Certainty of sentencing circumstances
    - Output confidence level (high / medium / low) and a specific percentage estimate
- **Output:** Complete reasoning chain; charge prediction; sentence prediction (point estimate + range); fine prediction; other order predictions; dispute-issue adjudication conclusions; confidence assessment
- **Passed to next step:** All reasoning conclusions

> **Case One example:** ① Constitutive elements of fraud all satisfied → constitutes fraud; ② discovered and unsuccessful for reasons beyond will → attempt established; ③ RMB 100,000 falls in “huge amount” tier; attempt may be punished lighter or reduced relative to completed offense; ④ overlay truthful confession as mitigation → derive fixed-term imprisonment of seven months + fine of RMB 30,000.
>
> **Case Two example:** ① Constitutive elements of burglary-of-dwelling theft satisfied → theft established; ② two persons conspired and jointly committed → joint crime established; ③ defense claim of accessory status lacks sufficient evidence → not accepted; ④ truthful confession + surrender of gains as mitigation → derive fixed-term imprisonment of six months + fine of RMB 2,000 + restitution order.

---

### 🔍 Quality Checkpoint QC-3: Logical Self-Consistency of Reasoning

| Check Item | Verification Standard | On Failure |
|--------|----------|------------|
| Complete constitutive-element argumentation | Each constitutive element is supported by corresponding factual elements; no leapfrog argumentation | Backtrack to **Step 1** to supplement elements or **Step 2** to correct constitutive-element understanding |
| Correctness of sentencing tier | Derived sentencing tier matches statutory amount / circumstance standards | Backtrack to **Step 4** to verify amount standards in provisions and judicial interpretations |
| Reasonableness of sentence range | Predicted sentence falls within statutory range and roughly matches case-retrieval sentencing range | Backtrack to **Step 5** to broaden case retrieval, or to **Step 6** to reassess circumstance overlay |
| No contradictions in reasoning chain | Conviction, form, and sentencing conclusions are logically self-consistent without internal contradiction | Layer-by-layer backtrack to locate contradictions |
| Reasonableness of confidence | Confidence assessment matches factors such as number of dispute issues and case consistency | Reassess confidence |

---

### Step 7: Legal Document Format Application

- **Capability invoked:** AS-49 (Legal document format application)
- **Input:** All reasoning conclusions from Step 6
- **Execution content:**
  - Identify the output document type as “judgment prediction report”
  - Organize report content in the following structured format:
    1. **Basic case information:** Parties, cause of action, time and place of offense
    2. **Fact-finding summary:** Structured presentation of core factual elements
    3. **Charge prediction:** Predicted charge and constitutive-element argumentation
    4. **Dispute-issue analysis:** Analytical conclusion for each dispute issue
    5. **Applicable provisions:** Complete provision list and reasons for application
    6. **Sentence prediction:**
       - Baseline sentencing tier
       - Sentencing-circumstance adjustments
       - Principal penalty prediction (point estimate + range)
       - Accessory penalty prediction (fines, etc.)
       - Other order predictions (restitution, confiscation, etc.)
    7. **Similar-case references:** Summaries of relevant reference cases
    8. **Confidence assessment:** Overall confidence and per-link confidence items
    9. **Risk notices:** Factors that may cause prediction deviation
- **Output:** Formatted prediction-report framework (with content for each section)
- **Passed to next step:** Complete report draft

> **Case One example (format reference):** Criminal judgment format—parties, prosecution charges, fact findings, this Court’s view, operative part, sentence computation, appeal notice, annexed legal provisions. The prediction report follows this structure but from a prediction perspective.
>
> **Case Two example (format reference):** Operative part lists items separately—(1) conviction and sentence; (2) restitution order. The prediction report likewise lists each predicted order separately.

---

### Step 8: Standardized Legal Terminology

- **Capability invoked:** AS-50 (Standardized legal terminology)
- **Input:** Report draft from Step 7
- **Execution content:**
  - Review legal terminology in the report item by item for accuracy and standardization:
    - Whether charge names fully match Criminal Law articles (e.g., “fraud” / 诈骗罪, not merely “fraud” / 诈骗)
    - Whether crime-form wording is standardized (e.g., “attempted crime” / 犯罪未遂, not “attempt offender” / 未遂犯)
    - Whether sentencing-circumstance wording is standardized (e.g., “truthfully confessed one’s own crimes” / 如实供述自己的罪行, not colloquial “坦白交代”)
    - Whether penalty wording is standardized (e.g., “sentenced to fixed-term imprisonment of X months,” not “given X months”)
    - Whether fine wording is standardized (e.g., “and a fine of RMB X”)
    - Whether statutory citation format is standardized (e.g., “Article 266 of the Criminal Law of the People’s Republic of China”)
  - Check for and correct ambiguous wording
  - Ensure prediction-report diction meets legal stylistic requirements—solemn, accurate, free of colloquialism
- **Output:** Final prediction report after terminology standardization
- **Final output:** Structured judgment prediction report (with confidence)

> **Case One example:** Ensure wording such as “attempted crime,” “may be given a lighter or reduced punishment by reference to a completed offender,” “sentenced to fixed-term imprisonment,” and “and a fine” conforms to criminal-document norms.
>
> **Case Two example:** Ensure wording such as “burglary of a dwelling,” “joint crime,” “surrender of illegal gains,” and “order restitution of illegal gains and return them to the victim” is standardized and accurate.

---

## IV. Conditional Branches and Backtracking Mechanisms

### 4.1 Multi-Charge Candidate Branch

**Trigger:** Step 2 identifies two or more candidate charges that cannot be directly excluded at Step 2.

**Handling path:**
- At Step 3, list “this-crime vs. that-crime contention” as a high-impact dispute issue
- At Step 4, retrieve provisions for all candidate charges
- At Step 6 deductive reasoning, argue constitutive elements for each candidate charge separately and choose one
- If a unique charge still cannot be determined, list primary and alternative charges in the report with separate confidences

### 4.2 Crime-Form Branch

**Trigger:** Result elements extracted at Step 1 show the crime may be incomplete (keywords such as “unsuccessful,” “attempt,” “discontinuation”).

**Handling path:**
- Step 2 must expand concept comprehension of attempt / discontinuation
- Step 4 must retrieve Criminal Law Art. 23 (attempt) or Art. 24 (discontinuation)
- Step 6 deductive reasoning must add “Layer 2 — Crime-form reasoning”
- Sentence prediction must account for attempt / discontinuation adjustments to the statutory penalty

> **Case One is this branch:** Zhang 3 discovered and unsuccessful → trigger attempt branch → retrieve Art. 23 → reason that attempt is established → sentence lighter or reduced by reference to completed offense.

### 4.3 Joint-Crime Branch

**Trigger:** Subject elements extracted at Step 1 show two or more persons jointly committing the criminal act.

**Handling path:**
- Step 2 must expand concept comprehension of joint crime and principal / accessory
- Step 3 must list “defendant’s status in the joint crime” as a dispute issue
- Step 4 must retrieve Criminal Law Arts. 25–29 (joint-crime provisions)
- Step 6 must argue whether the defendant is principal or accessory and adjust sentencing accordingly

> **Case Two is this branch:** An Xu acting with Yang XX → trigger joint-crime branch → retrieve Art. 25 → defense claims accessory but evidence insufficient → not found as accessory → accessory mitigation inapplicable.

### 4.4 Insufficient-Information Backtrack

**Trigger:** At any step, the case-fact narrative lacks key information needed to complete current-step reasoning.

**Handling path:**
- Explicitly annotate missing information items in the report
- Make a best estimate based on available information while lowering confidence for that link
- In “Risk notices,” explain prediction deviation that missing information may cause

### 4.5 Conflicting-Provisions Backtrack

**Trigger:** Provisions retrieved at Step 4 conflict (e.g., transitional application of old and new law; concurrence of general and special law).

**Handling path:**
- Backtrack conceptually to understand application principles such as “apply the old law with preference for the lighter” and “special law prevails over general law”
- At Step 6, expressly argue which provision applies and why
- In confidence assessment, account for uncertainty from provision conflict

---

## V. Quality Checkpoint Summary

| Checkpoint | Location | Core Verification Content | Backtrack Targets |
|--------|------|-------------|----------|
| QC-1 | After Step 3 | Element completeness, characterization consistency, adequacy of dispute identification | Steps 1/2/3 |
| QC-2 | After Step 5 | Provision coverage and fit, case relevance, reasonableness of sentencing range | Steps 3/4/5 |
| QC-3 | After Step 6 | Complete constitutive-element argumentation, correct sentencing tier, reasonable sentence, no contradictory reasoning | Steps 1/4/5/6 |

**Backtrack cap:** Each checkpoint may trigger at most 2 backtracks. If still failing after 2 backtracks, annotate uncertainty for that link in the report, lower confidence, and continue subsequent steps.

---

## VI. Output Format Specification

The final structured judgment prediction report format is as follows:

```
═══════════════════════════════════════
          Legal Judgment Prediction Report
═══════════════════════════════════════

【I. Basic Case Information】
  Defendant:
  Cause of action:
  Time of offense:
  Place of offense:

【II. Fact-Finding Summary】
  (Structured presentation of core factual elements)

【III. Charge Prediction】
  Predicted charge:
  Constitutive-element argumentation:
    (1) ……
    (2) ……
    (3) ……
    (4) ……

【IV. Dispute-Issue Analysis】
  Dispute issue 1: ……
    Analytical conclusion: ……
    Certainty: High / Medium / Low
  Dispute issue 2: ……
    Analytical conclusion: ……
    Certainty: High / Medium / Low

【V. Applicable Provisions】
  (1) Criminal Law Art. XXX — ……
  (2) Criminal Law Art. XXX — ……
  (3) ……

【VI. Sentence Prediction】
  Baseline sentencing tier: ……
  Sentencing-circumstance adjustments:
    - Mitigating circumstances: ……
    - Aggravating circumstances: ……
  Principal penalty prediction: Fixed-term imprisonment of X months (predicted range: X–Y months)
  Accessory penalty prediction: Fine of RMB X
  Other orders: ……

【VII. Similar-Case References】
  Reference case 1: …… (sentencing outcome: ……)
  Reference case 2: …… (sentencing outcome: ……)

【VIII. Confidence Assessment】
  Overall confidence: X% (High / Medium / Low)
  Itemized confidence:
    - Charge prediction: X%
    - Crime form: X%
    - Sentence prediction: X%

【IX. Risk Notices】
  (1) ……
  (2) ……

═══════════════════════════════════════
```

---

## VII. Complete Examples

### Example One: Attempted Fraud Case (Case One)

**Input:** The prosecution alleged: At about 15:00 on 28 April 2017, Defendant Zhang 3, to repay debts, forged an ID card of his sister “Zhang 2,” then impersonated “Zhang 2,” and using the forged ID card of “Zhang 2” and previously obtained real-estate registration information under Zhang 2’s name, sought to obtain RMB 100,000 in cash from Victims Liu XX and Xu XX, but was discovered on the spot by Victims Liu XX and Xu XX and failed. (Evidence omitted.)

**Execution process:**

**Step 1 [AS-4]:**
- Input: Original case-fact text
- Extraction results:
  - Subject: Defendant Zhang 3
  - Acts: Forging ID card; impersonating “Zhang 2”; using forged ID and real-estate registration information to obtain cash by deception
  - Purpose: Repay debts (purpose of illegal appropriation)
  - Object: Cash of Victims Liu XX and Xu XX
  - Amount: RMB 100,000
  - Result: Discovered on the spot; unsuccessful
  - Time: About 15:00 on 28 April 2017
  - Circumstance: Defendant raised no objection at trial (truthful confession)
- Pass: Structured element list

**Step 2 [AS-5]:**
- Input: Structured element list
- Candidate charge: Fraud (Criminal Law Art. 266)
- Constitutive-element breakdown:
  - Subject: General subject ✓
  - Subjective aspect: Purpose of illegal appropriation (repay debts → illegal appropriation)
  - Objective aspect: Fabricating facts (forging ID; impersonation); obtaining others’ property by deception
  - Object: Ownership of public or private property
- Special concept: Attempted crime—already begun to commit the crime; failed to succeed for reasons beyond the offender’s will
- Pass: Candidate charge (fraud), constitutive-element comparison table, attempted-crime concept

**Step 3 [AS-6]:**
- Input: Element list + constitutive-element comparison table
- Dispute-issue identification:
  - Issue 1: Crime form—completed or attempted (high impact)
  - Issue 2: Amount characterization—whether RMB 100,000 is “relatively large” or “huge” (high impact)
- Legal relationship: Fraud-crime relationship between Defendant Zhang 3 and Victims Liu XX and Xu XX
- Pass: Dispute-issue list

**✅ QC-1 verification:** Four core elements complete; fraud constitutive elements consistent with factual elements; two high-impact dispute issues identified. → Pass

**Step 4 [AS-8]:**
- Input: Candidate charge (fraud) + dispute issues
- Retrieval results:
  - Criminal Law Art. 266: Fraud of public or private property in a relatively large amount shall be sentenced to fixed-term imprisonment of not more than three years, criminal detention, or public surveillance, and may concurrently or solely be sentenced to a fine; if the amount is huge or there are other serious circumstances, fixed-term imprisonment of not less than three years and not more than ten years, and a fine
  - Criminal Law Art. 23: A crime that has already been begun but is not completed for reasons beyond the offender’s will is an attempted crime. An attempted offender may be given a lighter or reduced punishment by reference to a completed offender
  - Criminal Law Art. 67 para. 3: A criminal suspect who does not meet the voluntary-surrender circumstances in the preceding two paragraphs but truthfully confesses his or her own crimes may be given a lighter punishment
  - Relevant judicial interpretation: Fraud of RMB 100,000 falls in the “huge amount” tier
- Pass: Provision list; sentencing tier (huge amount: 3–10 years)

**Step 5 [AS-9]:**
- Input: Fraud + attempt + huge amount
- Retrieval results: In similar attempted-fraud cases (huge-amount tier), sentences after reduced punishment often fall between 6 months and 1 year 6 months; fines often between RMB 10,000 and 50,000
- Pass: Sentencing reference range (6 months–1 year 6 months); fine reference range (RMB 10,000–50,000)

**✅ QC-2 verification:** Conviction, attempt, and mitigation clauses all retrieved; cases highly comparable to the current case. → Pass

**Step 6 [AS-16]:**
- Input: All prior outputs
- Reasoning process:
  - Layer 1 (conviction): Zhang 3 had purpose of illegal appropriation → fabricated facts (forged ID and impersonation) → sought others’ property by deception → all fraud elements satisfied → **constitutes fraud**
  - Layer 2 (form): Already begun fraud → discovered on the spot by victims (reasons beyond will) → unsuccessful (not completed) → **attempt established**
  - Layer 3 (sentencing tier): Target amount RMB 100,000 → “huge amount” → baseline tier: not less than 3 years and not more than 10 years
  - Layer 4 (circumstance overlay): Attempt → may reduce punishment by reference to completed offense → may go below the 3-year floor; truthful confession → may lighten further after reduction
  - Layer 5 (accessory penalty): Reference case fine range → predict fine of RMB 30,000
  - Dispute-issue adjudication: Issue 1 → attempt established (high certainty); Issue 2 → RMB 100,000 is huge amount (high certainty)
  - Final prediction: Fixed-term imprisonment of 7 months (range: 6–10 months), and a fine of RMB 30,000
  - Confidence: Overall 85% (charge 95%, form 90%, sentence 75%)

**✅ QC-3 verification:** Constitutive elements fully argued item by item; 7 months within a reasonable post-reduction range; matches case-retrieval range. → Pass

**Step 7 [AS-49]:**
- Organize all content in prediction-report format

**Step 8 [AS-50]:**
- Terminology standardization:
  - “Fraud” / 诈骗罪 (not merely “诈骗”) ✓
  - “Attempted crime” / 犯罪未遂 (not “未遂犯”) ✓
  - “May be given a lighter or reduced punishment by reference to a completed offender” ✓
  - “Sentenced to fixed-term imprisonment of seven months” ✓
  - “And a fine of RMB thirty thousand” ✓

**Final output (summary):**
- Predicted charge: Fraud
- Crime form: Attempted crime
- Applicable provisions: Criminal Law Arts. 266, 23, and 67 para. 3
- Principal penalty prediction: Fixed-term imprisonment of seven months (predicted range: six to ten months)
- Accessory penalty prediction: And a fine of RMB thirty thousand
- Overall confidence: 85%

**Actual judgment comparison:** Defendant Zhang 3 committed fraud and was sentenced to fixed-term imprisonment of seven months and a fine of RMB thirty thousand. **Prediction fully matches the actual judgment.**

---

### Example Two: Burglary-of-Dwelling Joint-Crime Theft Case (Case Two)

**Input:** The People’s Procuratorate of Changning District, Shanghai, alleged: At about 13:00 on 9 May 2016, Defendant An Xu, together with Yang XX (already sentenced), went to Room XXX, Lane XXX, Fuquan Road, Changning District, this Municipality, forced entry by prying the door with tools they brought, stole multiple pieces of gold and silver jewelry that Victim Gong XX had placed in a third-floor storage room, and fled. On 15 April 2018, Defendant An Xu was apprehended by public security authorities at Guangzhou Railway Station. After the case arose, Defendant An Xu, with family assistance, surrendered part of the illegal gains amounting to RMB 3,000. (Evidence omitted.)

**Execution process:**

**Step 1 [AS-4]:**
- Input: Original case-fact text
- Extraction results:
  - Subjects: Defendant An Xu; co-offender Yang XX (already sentenced) → joint crime
  - Acts: Forced entry by prying door with self-provided tools and theft
  - Object: Multiple pieces of gold and silver jewelry of Victim Gong XX
  - Time: Offense on 9 May 2016; apprehended on 15 April 2018
  - Place: Changning District, Shanghai
  - Result: Completed theft (obtained property and fled)
  - Circumstances: Surrendered part of illegal gains RMB 3,000; raised no objection at trial (truthful confession)
- Pass: Structured element list

**Step 2 [AS-5]:**
- Input: Structured element list
- Candidate charge: Theft (Criminal Law Art. 264)
- Constitutive-element breakdown:
  - Subject: General subject ✓
  - Subjective aspect: Purpose of illegal appropriation
  - Objective aspect: Burglary of a dwelling (special act type)
  - Object: Ownership of public or private property
- Special concepts:
  - “Burglary of a dwelling” / 入户盗窃 — illegally entering another’s residence to steal; constitutes theft regardless of amount
  - Joint crime — intentional crime jointly committed by two or more persons
  - Principal vs. accessory — one who plays a principal role in a joint crime is a principal offender; one who plays a secondary or auxiliary role is an accessory
- Pass: Candidate charge (theft), constitutive-element comparison table, special-concept list

**Step 3 [AS-6]:**
- Input: Element list + constitutive-element comparison table
- Dispute-issue identification:
  - Issue 1: An Xu’s status in the joint crime—principal or accessory (high impact)
  - Issue 2: Degree of impact of surrendering RMB 3,000 on sentencing (medium impact)
  - Issue 3: Valuation of the gold and silver jewelry involved (medium impact, but amount not specified in the fact narrative)
- Legal relationships: Joint-crime relationship between An Xu and Yang XX; theft-crime relationship between An Xu and Victim Gong XX
- Pass: Dispute-issue list

**✅ QC-1 verification:** Core elements complete; theft constitutive elements consistent with facts; three dispute issues identified. Note: Specific value of property involved not specified; annotate as insufficient information. → Pass (with insufficient-information annotation)

**Step 4 [AS-8]:**
- Input: Candidate charge (theft) + dispute issues
- Retrieval results:
  - Criminal Law Art. 264: Theft of public or private property in a relatively large amount, or multiple thefts, burglary of a dwelling, theft while carrying a weapon, or pickpocketing, shall be sentenced to fixed-term imprisonment of not more than three years, criminal detention, or public surveillance, and may concurrently or solely be sentenced to a fine
  - Criminal Law Art. 25 para. 1: A joint crime is an intentional crime jointly committed by two or more persons
  - Criminal Law Art. 67 para. 3: One who truthfully confesses his or her own crimes may be given a lighter punishment
  - Criminal Law Art. 52: The amount of a fine shall be determined according to the circumstances of the crime
  - Criminal Law Art. 53: A fine shall be paid in a lump sum or in installments within the period specified in the judgment
  - Criminal Law Art. 64: All property illegally obtained by a criminal shall be recovered or ordered to be restituted
- Pass: Provision list; sentencing tier (burglary of a dwelling: not more than 3 years)

**Step 5 [AS-9]:**
- Input: Theft + burglary of a dwelling + Shanghai region + joint crime
- Retrieval results:
  - Shanghai regional burglary-of-dwelling theft sentences often fall between 6 months and 1 year 6 months
  - In joint crimes, absent sufficient evidence of accessory status, courts typically do not find accessory status
  - Partial surrender of illegal gains may warrant discretionary lighter treatment, but with limited impact
  - Fines often between RMB 1,000 and 5,000
- Pass: Sentencing reference range (6 months–1 year 6 months); adjudicative tendency on accessory findings

**✅ QC-2 verification:** Provision coverage complete; cases highly comparable on charge, act type, and region. → Pass

**Step 6 [AS-16]:**
- Input: All prior outputs
- Reasoning process:
  - Layer 1 (conviction): An Xu used tools to pry open and enter another’s residence to steal → meets “burglary of a dwelling” → constitutes theft regardless of amount → **theft established**
  - Layer 2 (form): Obtained jewelry and fled → completed crime
  - **Joint-crime branch triggered:**
    - An Xu acted together with Yang XX → intentional crime by two persons → joint crime established
    - Dispute-issue adjudication: Is An Xu an accessory? → Fact narrative shows An Xu and Yang XX went together and jointly committed the acts; no evidence that An Xu played only a secondary or auxiliary role → combined with case-retrieval adjudicative tendencies → **accessory status not found** (medium-high certainty)
  - Layer 3 (sentencing tier): Burglary of a dwelling → baseline tier: fixed-term imprisonment of not more than 3 years
  - Layer 4 (circumstance overlay): Truthful confession → lighter; surrender of RMB 3,000 → discretionary lighter; overall → lighter within baseline tier
  - Layer 5 (accessory penalty): Reference cases → fine prediction RMB 2,000; illegal gains → order restitution
  - Final prediction: Fixed-term imprisonment of 6 months (range: 6–10 months), and a fine of RMB 2,000; order restitution of illegal gains and return to the victim
  - Confidence: Overall 80% (charge 95%, accomplice-status finding 75%, sentence 70%)

**✅ QC-3 verification:** Constitutive-element argumentation complete; 6 months within statutory range and case range; reasoning chain free of contradiction. → Pass

**Step 7 [AS-49]:**
- Organize all content in prediction-report format, with particular attention to:
  - Orders split into conviction/sentence and restitution items
  - Dispute-issue analysis expressly stating reasons for not accepting the accessory claim

**Step 8 [AS-50]:**
- Terminology standardization:
  - “Theft” / 盗窃罪 (not “偷窃罪”) ✓
  - “Burglary of a dwelling” / 入户盗窃 ✓
  - “Joint crime” / 共同犯罪 ✓
  - “Sentenced to fixed-term imprisonment of six months” ✓
  - “And a fine of RMB two thousand” ✓
  - “Order Defendant An Xu to make restitution of illegal gains and return them to Victim Gong XX” ✓

**Final output (summary):**
- Predicted charge: Theft
- Crime form: Completed crime
- Applicable provisions: Criminal Law Arts. 264, 25 para. 1, 67 para. 3, 52, 53, and 64
- Principal penalty prediction: Fixed-term imprisonment of six months (predicted range: six to ten months)
- Accessory penalty prediction: And a fine of RMB two thousand
- Other orders: Order restitution of illegal gains and return to the victim
- Dispute-issue conclusion: Defense claim of accessory status not accepted
- Overall confidence: 80%

**Actual judgment comparison:** (1) Defendant An Xu committed theft and was sentenced to fixed-term imprisonment of six months and a fine of RMB two thousand. (2) Defendant An Xu was ordered to make restitution of illegal gains and return them to Victim Gong XX. The defense opinion that An Xu held a secondary position in the joint crime was not accepted by the court. **Prediction fully matches the actual judgment.**

---

## VIII. Notes and Boundary Clarifications

1. **Scope of application:** This composite capability primarily applies to criminal judgment prediction where facts are clear and evidence is sufficient. For cases with major factual disputes or insufficient evidence, confidence should be significantly lowered.

2. **Confidence calibration rules:**
   - Number of dispute issues ≥ 3 and all high-impact → overall confidence capped at 70%
   - High dispersion of sentencing distribution in case-retrieval results → lower sentence-prediction confidence by 10–20%
   - Missing amount / circumstance information → lower sentence-prediction confidence by 15–25%
   - All constitutive elements clearly satisfied and undisputed → charge-prediction confidence may reach 95%

3. **Backtrack efficiency safeguard:** Each quality checkpoint may trigger at most 2 backtracks to avoid infinite loops. If problems remain after 2 backtracks, annotate uncertainty and continue.

4. **Multiple defendants:** If the case involves multiple defendants, run Step 6 sentencing reasoning separately for each defendant; Steps 1–5 results may be shared.

5. **This capability does not cover:** Civil case prediction, administrative case prediction, legal advisory recommendations, defense-strategy formulation, or other tasks beyond criminal judgment prediction.
