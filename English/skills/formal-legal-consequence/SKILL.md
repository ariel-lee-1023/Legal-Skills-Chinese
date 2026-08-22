---
name: formal-legal-consequence
description: |
  Trigger this skill when you need to derive concrete legal consequences from confirmed legal facts, identified legal relationships, and matched legal norms—including but not limited to types and scope of civil liability, calculation of damages, determination of criminal sentences, types and ranges of administrative penalties, and contract validity status.
  Typical trigger scenarios include:
  - The user asks "how much compensation can I get" or "what liability will the other party bear"
  - The user asks "how many years would this conduct get" or "how much is the fine"
  - Deriving specific legal effects from whether constitutive elements (构成要件) are satisfied
  - Calculating quantified outcomes such as damages amounts, sentencing ranges, or liquidated damages
  - Reaching a final legal consequence after weighing aggravating, mitigating, and exempting adjustment factors
  This skill is the terminal link in the legal reasoning chain: it converts abstract legal norms into concrete, actionable legal conclusions.
---

> **Chinese source (authoritative):** [`../../skills/formal-legal-consequence/SKILL.md`](../../skills/formal-legal-consequence/SKILL.md)

# Formal Derivation of Legal Consequences

## Overview Table

| Item | Content |
|------|------|
| **Capability ID** | 21 |
| **Capability Name** | Formal Derivation of Legal Consequences |
| **Capability Type** | Terminal legal-reasoning capability |
| **Input Elements** | Established facts + matched legal norms + satisfaction of constitutive elements + adjustment factors |
| **Output Elements** | Concrete legal consequences (liability type, damages amount, sentencing range, penalty range, etc.) |
| **Prerequisite Capabilities** | Fact-finding, legal-relationship identification, legal-norm matching, constitutive-element analysis |
| **Core Logic** | Major premise (legal norm) + minor premise (subsumption of facts) → conclusion (legal consequence) |
| **Risk Level** | High (quantified conclusions that directly affect parties’ rights and interests) |

## Legal Disclaimer

> **Important notice:** Legal-consequence derivations produced by this skill are for reference only and do not constitute formal legal advice. The final determination of legal consequences rests with judicial or administrative authorities and is affected by evidence admission, judicial discretion, changes in judicial interpretations, and local adjudicative standards. Parties should consult a practicing lawyer or seek professional legal services for specific cases. AI-derived results should carry a confidence level; low-confidence conclusions must clearly flag uncertainty.

---

## I. Core Concepts

### 1.1 Definition and Classification of Legal Consequences

A **legal consequence** (法律后果) is the legal effect prescribed by a legal norm when legal facts satisfy the constitutive elements.

```
Legal-consequence taxonomy:
├── Civil legal consequences
│   ├── Contract-validity consequences (valid / void / voidable / pending effectiveness)
│   ├── Breach-of-contract consequences (specific performance / damages / liquidated damages / deposit penalty)
│   ├── Tort consequences (cessation of infringement / damages / apology / mental-distress damages)
│   ├── Property-rights change consequences (ownership transfer / mortgage creation / bona fide acquisition)
│   └── Unjust enrichment / negotiorum gestio consequences (restitution / compensation)
├── Criminal legal consequences
│   ├── Principal penalties (public surveillance / criminal detention / fixed-term imprisonment / life imprisonment / death penalty)
│   ├── Supplementary penalties (fine / deprivation of political rights / confiscation of property / deportation)
│   ├── Sentencing adjustments (aggravation / lighter punishment / mitigation below statutory minimum / exemption)
│   └── Non-penal dispositions (exemption from criminal punishment / suspended sentence / parole)
├── Administrative legal consequences
│   ├── Administrative penalties (warning / fine / confiscation / revocation of license / administrative detention)
│   ├── Administrative compulsion (sealing / seizure / freezing / compulsory enforcement)
│   └── Administrative-licensing consequences (grant / denial / revocation / cancellation)
└── Procedural legal consequences
    ├── Limitation consequences (loss of the right to win on the merits / 丧失胜诉权)
    ├── Burden-of-proof consequences (bearing adverse consequences)
    └── Jurisdiction consequences (transfer / dismissal)
```

### 1.2 Logical Structure of Formal Derivation

Derivation of legal consequences follows the basic structure of **syllogistic deductive reasoning**, extended into a multi-layer derivation model:

```
【Basic syllogism】
Major premise: If conditions C₁∧C₂∧...∧Cₙ are satisfied, legal consequence E arises
Minor premise: Case facts F satisfy conditions C₁∧C₂∧...∧Cₙ
Conclusion: Legal consequence E arises in this case

【Extended derivation model】
Layer 1: Determine baseline consequence
  R(norm) + F(facts) → E₀(baseline legal consequence)

Layer 2: Apply adjustment factors
  E₀ + A₊(aggravating) + A₋(mitigating) + A₀(exempting) → E₁(adjusted legal consequence)

Layer 3: Handle concurrence and aggregation
  E₁ + concurrence rules / aggregation rules → E₂(final legal consequence)

Layer 4: Quantification
  E₂ + calculation standards / discretion benchmarks → E_final(concrete quantified result)
```

### 1.3 Key Terms

| Term | Definition | Example |
|------|------|------|
| **Legal effect** (法律效果) | The consequence prescribed in the “then” part of a legal norm | “shall be sentenced to fixed-term imprisonment of not more than three years” |
| **Baseline consequence** (基准后果) | The initial legal consequence before adjustment | Baseline sentence, baseline damages |
| **Adjustment factors** (调整因素) | Aggravating / mitigating / exempting grounds that affect the final consequence | Voluntary surrender, recidivism, contributory negligence |
| **Sentencing range** (量刑幅度) | The statutory penalty interval under the Criminal Law | “not less than three years and not more than seven years” |
| **Scope of damages** (赔偿范围) | Categories of recoverable loss | Direct loss, consequential loss, mental distress |
| **Concurrence of liabilities** (责任竞合) | The same facts satisfy multiple claim bases | Concurrence of breach and tort |
| **Aggregation of liabilities** (责任聚合) | Multiple liabilities may be asserted concurrently | Liquidated damages coexisting with compensatory damages |
| **Discretion benchmark** (裁量基准) | Reference standards for judicial discretion | Local courts’ sentencing guidance opinions |

---

## II. Complete Workflow

### Stage One: Confirm and Organize Input Elements

**Goal:** Confirm that all inputs required for derivation are complete, and organize them structurally.

```
Step 1.1: Confirm the factual foundation
├── Have the core facts been established?
├── Are there contradictions among the facts?
├── Are key facts supported by evidence?
└── Is the factual timeline clear?

Step 1.2: Confirm the legal norms
├── Have the applicable legal norms been determined?
├── Is there a special-law-prevails-over-general-law situation?
├── Are the norms currently in force?
└── Are there supplementary judicial interpretations?

Step 1.3: Confirm satisfaction of constitutive elements
├── Has each constitutive element been checked one by one?
├── To what degree is each element satisfied?
├── Are there any grounds that bar liability (阻却事由)?
└── Is causation established?

Step 1.4: Identify adjustment factors
├── Are there aggravating circumstances?
├── Are there mitigating / lighter-punishment circumstances?
├── Are there grounds for exemption?
└── Is there contributory negligence / comparative fault (过失相抵/与有过失)?
```

**Input-element organization template:**

```
┌─────────────────────────────────────────┐
│      Input Element Organization Sheet    │
├──────────┬──────────────────────────────┤
│ Established facts │ [List item by item]          │
│ Applicable norms  │ [Article number + content]   │
│ Element status    │ [Mark each: satisfied / not / doubtful] │
│ Aggravating       │ [List]                       │
│ Mitigating        │ [List]                       │
│ Exempting         │ [List]                       │
│ Special situations│ [Concurrence / aggregation / limitation, etc.] │
└──────────┴──────────────────────────────┘
```

### Stage Two: Determine the Baseline Legal Consequence

**Goal:** From the legal-effect portion of the applicable norm, determine the type and range of the baseline legal consequence.

```
Step 2.1: Locate the legal-effect clause
  → Find the concrete prescription in the “then” part of the norm
  → Distinguish mandatory consequences from elective consequences
  → Note the difference between “shall” (应当) and “may” (可以)

Step 2.2: Determine the consequence type
  → Liability-bearing (damages, penalties) or rights-altering (acquisition, loss)?
  → Single consequence or compound consequences?
  → Fixed consequence or discretionary consequence?

Step 2.3: Determine the initial range / amplitude
  → Criminal: determine the statutory penalty range (e.g., “fixed-term imprisonment of not less than three years and not more than seven years”)
  → Civil: determine basic categories of recoverable damages (direct loss, lost profits, etc.)
  → Administrative: determine penalty types and range intervals
```

**Derivation formula for baseline consequence:**

```
IF all constitutive elements are satisfied AND no barring grounds
THEN baseline legal consequence = legal effect prescribed by the norm
     consequence type = [liability / rights-altering / procedural]
     consequence range = [statutory amplitude / statutory categories]

IF constitutive elements are only partially satisfied
THEN check whether elements of other nearby norms are satisfied
     → Yes: switch to deriving consequences under that norm
     → No: that legal consequence does not arise

IF barring grounds exist
THEN check the type and effect of the barring grounds
     → Complete bar: no legal consequence arises
     → Partial bar: proceed to the adjustment stage
```

### Stage Three: Apply Adjustment Factors

**Goal:** Incorporate aggravating, mitigating, exempting, and similar adjustment factors to revise the baseline legal consequence.

#### 3.1 Adjustment Factors in the Criminal Domain

```
Step 3.1.1: Identify and apply statutory sentencing circumstances
┌──────────────────────────────────────────────────┐
│ Statutory circumstance type │ Effect              │ Priority │
├──────────────────────────────────────────────────┤
│ Shall exempt from punishment │ Exempt from penalty │ Highest │
│ May exempt from punishment   │ Discretionary exemption │ High │
│ Shall mitigate punishment    │ Sentence below statutory minimum │ High │
│ May mitigate punishment      │ Discretionary mitigation │ Medium │
│ Shall give a lighter punishment │ Lighter within the statutory range │ Medium │
│ May give a lighter punishment   │ Discretionary lighter punishment │ Medium │
│ Shall give a heavier punishment │ Heavier within the statutory range │ Medium │
│ May give a heavier punishment   │ Discretionary heavier punishment │ Low │
└──────────────────────────────────────────────────┘

Step 3.1.2: Determine the sentencing starting point
  → Within the statutory range, set the starting point based on the criminal facts
  → Refer to the Supreme People’s Court’s Sentencing Guidance Opinions on Common Crimes

Step 3.1.3: Determine the baseline sentence (基准刑)
  → Sentencing starting point + incremental punishment for additional constitutive facts = baseline sentence

Step 3.1.4: Adjust for sentencing circumstances
  → Baseline sentence × (1 ± adjustment ratios for each circumstance) = provisional declared sentence
  → For multiple circumstances: add same-direction adjustments; subtract opposite-direction adjustments

Step 3.1.5: Determine the declared sentence (宣告刑)
  → After overall consideration, finalize the declared sentence from the provisional figure
  → The declared sentence generally must not fall below the statutory minimum (except where mitigation applies)
```

#### 3.2 Adjustment Factors in the Civil Domain

```
Step 3.2.1: Contributory negligence / comparative fault (过失相抵 / 与有过失)
  → If the injured party was also at fault for the occurrence of the harm, the tortfeasor’s liability may be reduced
  → Determine each party’s fault proportion
  → Damages = total loss × tortfeasor’s fault proportion

Step 3.2.2: Benefit offset (损益相抵)
  → Benefits the victim obtained from the same harmful event should be deducted from damages
  → Damages = actual loss − benefits obtained because of the harm

Step 3.2.3: Duty to mitigate (减损义务)
  → If the victim failed to take reasonable measures to prevent enlargement of loss
  → The enlarged portion is not compensable

Step 3.2.4: Fair-share allocation of loss (公平责任分担)
  → Where neither party is at fault, allocate loss according to the circumstances
  → Consider economic condition, degree of benefit, and similar factors

Step 3.2.5: Punitive damages (惩罚性赔偿)
  → Specific fields (consumer protection, IP, eco-environment, etc.)
  → When statutory conditions are met, add punitive damages on top of compensatory damages
```

#### 3.3 Adjustment Factors in the Administrative Domain

```
Step 3.3.1: Circumstances for lighter / mitigated penalties
  → Voluntarily eliminating or mitigating harmful consequences of the illegal act
  → Committing the illegal act under duress by others
  → Cooperating with the administrative agency’s investigation and performing meritorious service
  → Other circumstances for lighter or mitigated administrative penalties as provided by law

Step 3.3.2: Circumstances for non-punishment
  → The illegal act is minor, promptly corrected, and caused no harmful consequences
  → First-time violation with minor harmful consequences and prompt correction (added in the 2021 revision of the Administrative Penalty Law)
  → The party has evidence sufficient to prove absence of subjective fault (unless otherwise provided by law or administrative regulations)

Step 3.3.3: Circumstances for heavier penalties
  → Determined under the specific administrative laws and regulations
```

### Stage Four: Handle Concurrence and Aggregation

**Goal:** Resolve relationships among multiple legal consequences and determine the final combination that may be asserted.

```
Step 4.1: Identify the type of concurrence

Claim concurrence (civil):
├── Concurrence of breach and tort
│   → Rule: the party may elect only one claim (Civil Code Art. 186)
│   → Derivation: compare the damages scopes of the two claims and flag the optimal choice
├── Concurrence of property-rights claims and creditor claims
│   → Rule: may be exercised concurrently, but no double recovery
└── Concurrence of unjust enrichment and other claims
    → Rule: supplementary claim; other claims take priority

Imaginative concurrence (刑事想象竞合):
├── One act violates multiple offenses
│   → Rule: punish under the heavier offense
│   → Derivation: compare statutory penalties of each offense and choose the heavier
└── Concurrence of legal provisions (法条竞合)
    → Rule: special law prevails over general law

Substantial concurrence / joinder of punishments for plural crimes (数罪并罚):
├── Multiple acts constituting multiple crimes
│   → Rule: joinder of punishments
│   → Derivation: convict and sentence each crime, then determine the executed sentence under joinder rules
└── Joinder rules
    → Fixed-term imprisonment: not more than the sum of terms and not less than the highest single term
    → Criminal detention: maximum not more than one year
    → Public surveillance: maximum not more than three years

Step 4.2: Identify aggregation relationships
├── Liquidated damages and deposit may not be used together (apply the higher)
├── Relationship between liquidated damages and compensatory damages (if liquidated damages are insufficient to cover loss, an increase may be sought)
├── Mental-distress damages and property damages may run in parallel
└── Principal and supplementary penalties may be imposed together
```

### Stage Five: Quantification

**Goal:** Convert legal consequences into concrete numerical values or clear conclusions.

#### 5.1 Civil Damages Calculation

```
【Personal injury damages calculation】(refer to the Supreme People’s Court Interpretation on Several Issues Concerning the Application of Law in the Trial of Personal Injury Compensation Cases)

Medical expenses = reasonably incurred actual medical costs (supported by invoices)
Lost wages = days of work missed × daily income
  (fixed income: calculate actual reduction; no fixed income: average income over the past three years or industry average wage)
Nursing expenses = nursing days × daily income of the nursing person (or local nursing-worker standard)
Transportation expenses = reasonably incurred actual transportation costs
Hospital meal subsidy = hospitalization days × meal-subsidy standard for ordinary staff of local state organs on official travel
Nutrition expenses = determined by disability/injury status with reference to medical-institution opinions
Disability compensation = prior-year per capita disposable income of urban residents in the place of the court seized of the case × 20 years × disability coefficient
  (for age 60+: reduce one year for each additional year of age; for age 75+: calculate on a 5-year basis)
Death compensation = prior-year per capita disposable income of urban residents in the place of the court seized of the case × 20 years
  (same age-adjustment rules as above)
Funeral expenses = prior-year average monthly employee wage in the place of the court seized of the case × 6 months
Dependents’ living expenses = prior-year per capita consumption expenditure of urban residents in the place of the court seized of the case × years of support ÷ number of supporters
Mental-distress solatium = comprehensively determined by degree of tortfeasor fault, means of infringement, consequences, profits obtained, financial capacity, local living standards, etc.

Total damages = Σ each head of damages × (1 − victim’s fault proportion)

【Contract breach damages calculation】
Agreed liquidated damages: calculate per contract
  → Too high: if exceeding 30% of the loss caused, a party may request an appropriate reduction
  → Too low: if below the loss caused, a party may request an increase
Statutory damages: actual loss + lost profits
  → Lost profits must not exceed what the breaching party foresaw or ought to have foreseen when concluding the contract
  → Mitigation rule: deduct enlarged loss the injured party failed reasonably to mitigate
  → Benefit offset: deduct benefits the injured party obtained because of the breach

【IP infringement damages calculation】
Priority order:
  1. Right-holder’s actual loss
  2. Infringer’s illegal gains
  3. Reasonable multiple of a licensing fee
  4. Statutory damages (patents: RMB 30,000–5,000,000; trademarks: up to RMB 5,000,000; copyright: RMB 500–5,000,000)
  5. Punitive damages: 1–5× (intentional infringement with serious circumstances)
```

#### 5.2 Criminal Sentencing Calculation

```
【Sentencing calculation steps】(refer to sentencing guidance opinions)

Step 1: Determine the sentencing starting point
  → Within the statutory range, based on the basic constitutive facts of the crime
  → Example: theft, relatively large amount (RMB 3,000–100,000), starting point fixed-term imprisonment of six months to one year

Step 2: Determine the baseline sentence
  → Starting point + incremental punishment for other facts affecting the constitutive elements
  → Example: for every additional RMB 1,500 of theft amount, add one month of imprisonment

Step 3: Adjust the baseline sentence for sentencing circumstances
  Common adjustment ratios:
  ├── Voluntary surrender (自首): reduce baseline by 20%–40% (for lighter crimes, may reduce by more than 40% or exempt)
  ├── Confession / frank admission (坦白): reduce baseline by 10%–30%
  ├── Meritorious service (立功): ordinary meritorious service reduce baseline by up to 20%; major meritorious service reduce by 20%–50%
  ├── Recidivism (累犯): increase baseline by 10%–40%
  ├── Minor: reduce baseline by 10%–50%
  ├── Accessory (从犯): reduce baseline by 20%–50% (for lighter crimes, may reduce by more than 50% or exempt)
  ├── Attempt: reduce baseline by up to 50%
  ├── Restitution / return of stolen property: reduce baseline by up to 30%
  ├── Compensation and victim understanding: reduce baseline by up to 40%
  └── Voluntary admission of guilt in court: reduce baseline by up to 10%
  
  Leniency for admission of guilt and acceptance of punishment (认罪认罚从宽):
  ├── May reduce baseline by up to 30%
  └── Where the criminal suspect admits guilt and accepts punishment, a acknowledgment statement (具结书) is signed

Step 4: Determine the declared sentence
  → On the basis of the provisional declared sentence, finalize after overall consideration of the whole case
  → The declared sentence must fall within the statutory range (except where mitigation applies)
  → Consider whether a suspended sentence applies (fixed-term imprisonment of not more than three years; relatively light circumstances; remorse; no risk of reoffending; suspension would not cause major adverse impact on the community)
```

#### 5.3 Administrative Penalty Calculation

```
【Fine calculation】
  → Determine the statutory fine range (e.g., “not less than RMB 10,000 and not more than RMB 100,000”)
  → Set the concrete amount based on facts, nature, circumstances, and degree of social harm of the illegal act
  → Lighter penalty: toward the low end of the statutory range (generally below 30% of the range)
  → Ordinary penalty: mid-range of the statutory amplitude
  → Heavier penalty: toward the high end of the statutory range (generally above 70% of the range)
  → Mitigated penalty: below the statutory minimum fine

【Other administrative penalties】
  → Administrative detention: determine days (typically 5–15 days; combined enforcement not more than 20 days)
  → Revocation of license / permit: determine whether revocation conditions are met
  → Order to suspend production or business: determine the period
```

### Stage Six: Output and Verify the Conclusion

**Goal:** Form a structured legal-consequence conclusion and verify it internally.

```
Step 6.1: Form the conclusion
  → Specify the type of legal consequence
  → Give a concrete quantified result or range
  → Mark the confidence level
  → State the derivation basis

Step 6.2: Internal verification (see verification rules)
  → Logical-consistency check
  → Legal-boundary check
  → Reasonableness check
  → Completeness check

Step 6.3: Output the conclusion
  → Organize content per the output-format template
  → Attach necessary qualifications and risk warnings
```

---

## III. Common Domains and Sources of Law

### 3.1 Civil Domain

| Consequence Type | Primary Source | Key Articles |
|----------|----------|----------|
| Consequences of contract invalidity | Civil Code | Art. 157 |
| Breach of contract | Civil Code | Arts. 577–588 |
| Tort damages | Civil Code | Arts. 1179–1187 |
| Mental-distress damages | Civil Code + judicial interpretations | Art. 1183 |
| Personal injury damages standards | Personal Injury Damages Judicial Interpretation | Full text |
| Product liability | Civil Code + Product Quality Law | Arts. 1202–1207 |
| Motor-vehicle traffic accident liability | Civil Code + Road Traffic Safety Law | Arts. 1208–1217 |
| Medical damage liability | Civil Code | Arts. 1218–1228 |
| Consumer punitive damages | Law on Protection of Consumer Rights and Interests | Art. 55 (refund + triple / refund + tenfold) |
| Labor-dispute compensation | Labor Contract Law | Arts. 46–48, 82, 87 |
| IP damages | Patent Law, Trademark Law, Copyright Law | Damages provisions of each law |

### 3.2 Criminal Domain

| Consequence Type | Primary Source | Key Articles |
|----------|----------|----------|
| Types and ranges of principal penalties | Specific provisions of the Criminal Law | Offense-specific articles |
| Sentencing rules | General Provisions of the Criminal Law | Arts. 61–63 |
| Voluntary surrender | Criminal Law | Art. 67 |
| Meritorious service | Criminal Law | Art. 68 |
| Recidivism | Criminal Law | Arts. 65–66 |
| Joinder of punishments for plural crimes | Criminal Law | Arts. 69–71 |
| Suspended sentence | Criminal Law | Arts. 72–77 |
| Sentencing guidance | SPC Sentencing Guidance Opinions | Full text |
| Leniency for admission of guilt and acceptance of punishment | Criminal Procedure Law + guidance opinions | Art. 15 etc. |

### 3.3 Administrative Domain

| Consequence Type | Primary Source | Key Articles |
|----------|----------|----------|
| Types of administrative penalties | Administrative Penalty Law | Art. 9 |
| Lighter / mitigated / exemption | Administrative Penalty Law | Arts. 30–33 |
| Administrative-penalty discretion | Agency discretion benchmarks | Specific rules |
| Administrative compulsion | Administrative Compulsion Law | Full text |
| Tax penalties | Law on the Administration of Tax Collection | Arts. 60–73 |
| Environmental penalties | Environmental Protection Law etc. | Specific clauses |
| Market-regulation penalties | Provisions on Administrative Penalty Procedures for Market Regulation | Full text |

---

## IV. Verification and Screening Rules

### 4.1 Logical-Consistency Verification

```
Rule L1: Consequence must correspond to constitutive elements
  → Check: Is the derived legal consequence the legal effect prescribed by the applied norm?
  → Violation example: Applying theft constitutive elements but deriving a fraud sentencing range

Rule L2: Adjustment direction must be correct
  → Check: Do aggravating circumstances aggravate the consequence? Do mitigating circumstances mitigate it?
  → Violation example: Finding voluntary surrender yet increasing the baseline sentence

Rule L3: The derivation chain must be complete
  → Check: Does every step from facts to conclusion have a legal basis?
  → Violation example: Skipping constitutive-element analysis and jumping from facts to a damages figure

Rule L4: No internal contradiction
  → Check: Are conclusions within the derivation consistent with one another?
  → Violation example: Finding the contract valid while applying restitution rules for contract invalidity
```

### 4.2 Legal-Boundary Verification

```
Rule B1: Must not exceed the statutory range
  → Criminal: declared sentence must not exceed the statutory range (except mitigation, which requires SPC approval where applicable)
  → Administrative: fines must not exceed the statutory upper limit (except mitigated penalties)
  → Civil: damages must not exceed actual loss (except punitive damages)

Rule B2: Must not violate prohibitive rules
  → Must not impose the death penalty on a person under 18
  → Must not impose the death penalty on a woman who is pregnant at the time of trial
  → Must not apply the death penalty to a person aged 75 or older (except where death is caused by especially cruel means)

Rule B3: Must not violate proportionality
  → Legal consequences should fit the nature, circumstances, and social harm of the illegal act
  → Administrative penalties should follow the principle that the penalty matches the offense (过罚相当)

Rule B4: Limitation constraints
  → After the limitation period expires, the right to win on the merits is lost (voluntary performance by the obligor remains unaffected)
  → After the prosecution limitation expires, criminal liability is no longer pursued (except where approved by the SPP)
```

### 4.3 Reasonableness Verification

```
Rule R1: Amount reasonableness
  → Is the damages amount within a reasonable band for comparable cases?
  → Are there obvious calculation errors?
  → Are the proportions among heads of damages reasonable?

Rule R2: Sentence reasonableness
  → Is the sentencing result consistent with trends in comparable cases?
  → Is the combined adjustment of multiple sentencing circumstances reasonable?
  → Does it conform to the principle that punishment fits crime and culpability (罪责刑相适应)?

Rule R3: Penalty reasonableness
  → Does the administrative penalty match the offense?
  → Has the party’s financial capacity been considered?
  → Is it consistent with penalty standards for comparable illegal acts?
```

### 4.4 Completeness Verification

```
Rule C1: Missing heads of damages?
  → Do personal injury damages cover all statutory heads?
  → Was mental-distress damages omitted?
  → Were dependents’ living expenses omitted?

Rule C2: Missing supplementary penalties?
  → Should a fine be imposed concurrently?
  → Should political rights be deprived?
  → Should property be confiscated?

Rule C3: Missing attendant consequences?
  → After contract invalidity, were both restitution and damages derived?
  → Was civil compensation incidental to the criminal case considered?
  → After administrative penalty, was the rectification obligation mentioned?
```

---

## V. Output Format Templates

### 5.1 Standard Output Template

```markdown
## Legal Consequence Derivation Conclusion

### I. Foundation of Derivation
- **Summary of established facts:** [Briefly list key facts]
- **Applicable legal norms:** [List statutory articles]
- **Satisfaction of constitutive elements:** [Explain one by one]

### II. Baseline Legal Consequence
- **Consequence type:** [Liability type / rights-altering type]
- **Legal basis:** [Specific articles]
- **Baseline consequence content:** [Concrete description]

### III. Adjustment Factors and Their Effects
| Adjustment Factor | Type | Legal Basis | Adjustment Effect |
|----------|------|----------|----------|
| [Factor 1] | Aggravating / Mitigating / Exempting | [Article] | [Concrete impact] |
| [Factor 2] | ... | ... | ... |

### IV. Final Legal Consequence
- **Conclusion:** [Concrete legal-consequence conclusion]
- **Quantified result:** [Specific amount / sentence / penalty range]
  - Low end: [value]
  - High end: [value]
  - Most likely / midpoint: [value] (if applicable)
- **Attendant consequences:** [if any]

### V. Derivation Confidence
- **Confidence level:** [High / Medium / Low]
- **Uncertainty factors:** [List factors affecting certainty]
- **Possibility of alternative conclusions:** [If different derivation paths exist, briefly explain]

### VI. Risk Warnings
- [Flag factors that may affect the final result]
- [Flag matters requiring further confirmation]
```

### 5.2 Brief Output Template (for quick answers)

```markdown
**Legal Consequence Derivation Conclusion:**

Based on [legal basis], and on the established facts, the derived legal consequences are as follows:

1. **Liability / consequence type:** [type]
2. **Concrete content:** [description of consequence]
3. **Quantified range:** [low] — [high]
4. **Key adjustment factors:** [factors and effects]
5. **Confidence:** [level] | **Main uncertainty factors:** [explanation]

> ⚠️ The above conclusion is for reference only; the final result depends on adjudication by judicial/administrative authorities.
```

---

## VI. Confidence Annotation System

### 6.1 Confidence Level Definitions

| Level | Marker | Definition | Applicable Scenarios |
|------|------|------|----------|
| **High** | 🟢 | Highly certain: clear law, clear facts, uniform calculation standards | Clear statutory damages standards with undisputed facts; fixed statutory sentence; clear administrative-penalty standards |
| **Medium** | 🟡 | Fairly likely, but some discretion or factual uncertainty remains | Judicial discretion; some facts pending confirmation; regional differences; adjustment factors requiring overall judgment |
| **Low** | 🔴 | Substantial uncertainty; multiple reasonable conclusions possible | Vague law; major factual disputes; complex concurrence; novel cases without precedent; policy-laden discretion |

### 6.2 Factors Affecting Confidence

```
Factors that raise confidence:
├── Clear and specific legal prescriptions (e.g., statutory damages standards)
├── Clear facts and sufficient evidence
├── Clear judicial interpretations or guiding cases
├── Uniform calculation standards (e.g., personal injury damages heads)
├── No discretion or extremely narrow discretion
└── Highly consistent outcomes in comparable cases

Factors that lower confidence:
├── Ambiguous legal gray zones
├── Disputed facts or insufficient evidence
├── Judicial discretion involved (e.g., amount of mental-distress damages)
├── Regional differences in adjudicative standards
├── Novel legal issues without precedent
├── Multiple possible legal interpretations
├── Uncertainty in applying adjustment factors
└── Policy considerations (e.g., economic conditions affecting sentencing)
```

### 6.3 Confidence Annotation Rules

```
Rule P1: Confidence must be annotated
  → Every legal-consequence conclusion must carry a confidence annotation

Rule P2: Itemized annotation
  → When a conclusion has multiple components, annotate confidence for each
  → Example: medical expenses (High), lost wages (Medium), mental-distress damages (Low)

Rule P3: State reasons
  → For Medium and Low confidence conclusions, state the specific factors affecting confidence

Rule P4: Provide a range
  → For Low-confidence quantified conclusions, provide a possible result range rather than a single figure
```

---

## VII. Common Errors and Prevention

### 7.1 Fatal Error Table

| No. | Error Type | Description | Severity | Prevention |
|------|----------|----------|------------|----------|
| F1 | **Wrong law applied** | Deriving consequences under the wrong legal norm | ⚠️⚠️⚠️ Fatal | Before deriving, repeatedly confirm the correct applicable norm; check whether special law prevails |
| F2 | **Omitted constitutive elements** | Deriving consequences without checking all constitutive elements | ⚠️⚠️⚠️ Fatal | Build a constitutive-element checklist and verify item by item |
| F3 | **Exceeding statutory range** | Derived sentence/fine exceeds statutory upper or lower limits | ⚠️⚠️⚠️ Fatal | After derivation, boundary-check the result against the statutory range |
| F4 | **Broken causation** | No causal link between facts and legal consequence | ⚠️⚠️⚠️ Fatal | Check that every step of the causal chain is complete |
| F5 | **Ignoring limitation** | Failing to consider that civil limitation / prosecution limitation has expired | ⚠️⚠️ Serious | Check limitation issues before deriving |
| F6 | **Wrong concurrence handling** | Treating mutually exclusive claims as concurrently assertable | ⚠️⚠️ Serious | Identify the concurrence type and apply the correct concurrence rules |
| F7 | **Wrong calculation standard** | Using the wrong base figure or standard | ⚠️⚠️ Serious | Confirm that the year and locality of statistical data are correct |
| F8 | **Wrong adjustment direction** | Applying a mitigating circumstance as if it were aggravating | ⚠️⚠️ Serious | Check the statutory effect direction of each adjustment factor |

### 7.2 Common Traps

```
Trap 1: Confusing “shall” (应当) with “may” (可以)
  ❌ Wrong: Treating “may give a lighter punishment” as “must give a lighter punishment”
  ✅ Correct: “Shall” is mandatory; “may” is authorizing and leaves discretion
  → Prevention: In derivation, explicitly mark “shall” vs. “may”; lower confidence for “may”-type circumstances

Trap 2: Ignoring regional differences in damages items
  ❌ Wrong: Using a nationwide standard for personal injury damages
  ✅ Correct: Use statistical data for the place of the court seized of the case
  → Prevention: Ask or confirm the venue; use corresponding local statistical data

Trap 3: Mishandling liquidated damages vs. compensatory damages
  ❌ Wrong: Fully awarding both liquidated damages and full compensatory damages
  ✅ Correct: Liquidated damages are compensatory; if insufficient to cover loss, an increase may be sought; if too high, a reduction may be sought
  → Prevention: First determine actual loss, then compare with liquidated damages

Trap 4: Ignoring contribution among joint tortfeasors
  ❌ Wrong: Making one joint tortfeasor bear all damages without considering internal contribution
  ✅ Correct: Joint tortfeasors bear joint and several liability externally, but share internally by degree of fault
  → Prevention: Distinguish external liability (joint and several) from internal liability (proportionate); derive separately

Trap 5: Wrong stacking of multiple criminal sentencing circumstances
  ❌ Wrong: Simply multiplying adjustment ratios of multiple mitigating circumstances
  ✅ Correct: Add same-direction circumstances; subtract opposite-direction ones; apply “shall”-type first, then “may”-type
  → Prevention: Strictly follow the calculation method in the sentencing guidance opinions

Trap 6: Confusing deposit with liquidated damages
  ❌ Wrong: Applying both the deposit penalty and liquidated damages
  ✅ Correct: Deposit and liquidated damages may only be elected alternatively (Civil Code Art. 588)
  → Prevention: Confirm whether the contract provides for both; advise the party to elect one

Trap 7: Ignoring temporal effect of legal amendments
  ❌ Wrong: Applying new-law standards to a case arising under old law
  ✅ Correct: Generally apply the law at the time of the act; exception for criminal “old law preferential, new law if lighter” or special provisions
  → Prevention: Confirm when the act occurred and which legal version applies

Trap 8: Wrong scope for mental-distress damages
  ❌ Wrong: Awarding mental-distress damages in a pure contract dispute
  ✅ Correct: Mental-distress damages generally apply only in tort (e.g., personality-rights infringement); contract breach generally does not support them
  → Prevention: Confirm whether the claim basis is tort or breach
```

---

## VIII. Special-Scenario Handling

### 8.1 Legal Gaps or Ambiguity

```
Handling method:
1. Search for judicial interpretations, guiding cases, or Gazette cases that fill the gap
2. Derive using legal principles (fairness, good faith, etc.)
3. Refer to prevailing doctrinal views and mainstream judicial practice
4. Clearly mark as Low confidence
5. Provide multiple possible derivation paths and their respective bases
6. Advise the party to consult a professional lawyer
```

### 8.2 Transition Between Old and New Law

```
Handling method:
1. Determine when the act occurred and when the amended law took effect
2. Civil: generally apply the law at the time of the act, unless the new law has retrospective provisions
3. Criminal: principle of applying the old law, or the new law if lighter
   → If the old law treated it as a crime but the new law does not, apply the new law
   → If both treat it as a crime, apply the law at the time of the act
   → But if the new law provides a lighter punishment, apply the new law
4. Administrative: generally apply the law at the time of the act; the new law may apply if more favorable to the party
5. Clearly mark the legal version applied
```

### 8.3 Cross-Domain Liability Concurrence

```
Handling method:
1. Criminal–civil crossover:
   → Criminal and civil liability may coexist
   → In criminal incidental civil actions, mental-distress damages are generally not supported
   → Criminal-first-then-civil or parallel tracks, depending on the case

2. Administrative–civil crossover:
   → Administrative penalties and civil damages may coexist
   → An administrative fine cannot substitute for civil damages

3. Criminal–administrative crossover:
   → Administrative detention may be credited against a sentence (1 day offsets 1 day)
   → Administrative fines may be credited against criminal fines
   → Criminal punishment is primary; administrative penalties are secondary
```

### 8.4 Multi-Party Scenarios

```
Handling method:
1. Determine each party’s legal status and liability type
2. Distinguish joint and several, proportionate, and supplementary liability
3. Derive each party’s liability scope separately
4. Address internal contribution / reimbursement relationships
5. Note the effect of third-party liability on primary liability

Liability-type reference:
├── Joint and several liability (连带责任): each liable person answers for the whole debt; share internally by portion
├── Proportionate liability (按份责任): each liable person answers only for their share
├── Supplementary liability (补充责任): the supplementary obligor answers when the primary obligor cannot
├── Improper joint and several liability (不真正连带责任): each liable person, on different grounds, answers in full for the same harm
└── Corresponding supplementary liability: a security-duty holder bears supplementary liability within the scope of fault
```

### 8.5 Insufficient Evidence

```
Handling method:
1. Clearly mark which facts are uncertain due to insufficient evidence
2. Derive legal consequences under alternative fact-findings separately
3. Provide both “most favorable” and “least favorable” derivation conclusions
4. Mark as Low confidence
5. Advise the party on the direction and importance of supplementing evidence
```

---

## IX. Quality Checklist

Before outputting a legal-consequence derivation conclusion, check each of the following:

```
□ 1. 【Factual foundation】 Are the facts relied on clearly listed?
□ 2. 【Legal basis】 Does every conclusion rest on a clear statutory article?
□ 3. 【Constitutive elements】 Have all constitutive elements been checked one by one?
□ 4. 【Barring grounds】 Have possible barring grounds been excluded?
□ 5. 【Adjustment factors】 Have all relevant aggravating / mitigating / exempting factors been identified and applied?
□ 6. 【Adjustment direction】 Is the application direction of each adjustment factor correct?
□ 7. 【Concurrence handling】 Has liability concurrence / provision concurrence been handled correctly?
□ 8. 【Statutory boundaries】 Do quantified results fall within the statutory range?
□ 9. 【Calculation accuracy】 Are numerical calculations accurate? Are calculation standards correct?
□ 10.【Completeness】 Were any legal-consequence items that should have been derived omitted?
□ 11.【Consistency】 Are conclusions within the derivation consistent and free of contradiction?
□ 12.【Limitation check】 Have civil limitation / prosecution limitation been considered?
□ 13.【Temporal effect】 Does the legal version applied match when the act occurred?
□ 14.【Confidence】 Has a confidence level been annotated with reasons?
□ 15.【Risk warnings】 Have uncertainty factors that may affect the final result been flagged?
□ 16.【Regional differences】 Where local standards apply, has the applicable locality been confirmed?
□ 17.【Prohibitive rules】 Does the conclusion violate any prohibitive rule?
□ 18.【Proportionality】 Is the legal consequence proportionate to the nature and seriousness of the conduct?
```

---

## X. Complete Examples

### Example One: Civil Tort Damages Derivation (Simple Scenario)

#### Facts

Zhang (age 35, monthly income RMB 8,000) was riding an e-bike normally in a city when Li, driving a car through a red light, struck and injured him. Traffic police found Li fully at fault. Zhang’s injuries: right-leg fracture; 30 days of hospitalization; 90 days of rest after discharge; appraisal as Grade-10 disability. Li’s vehicle carried compulsory traffic insurance (交强险) and RMB 1,000,000 of commercial third-party liability insurance.

#### Derivation Process

**Step 1: Confirm input elements**

```
Established facts:
1. Li ran a red light and struck Zhang
2. Traffic police found Li fully at fault
3. Zhang’s right-leg fracture; 30 days hospitalized; 90 days rest
4. Grade-10 disability
5. Zhang age 35, monthly income RMB 8,000
6. Li carried compulsory traffic insurance + RMB 1,000,000 commercial third-party cover

Applicable legal norms:
- Civil Code Art. 1179 (scope of personal injury damages)
- Civil Code Art. 1213 (motor-vehicle traffic accident liability)
- SPC Interpretation on Several Issues Concerning the Application of Law in the Trial of Personal Injury Compensation Cases
- Regulation on Compulsory Motor Vehicle Traffic Accident Liability Insurance

Constitutive-element status:
- Tortious act: ✅ driving through a red light
- Harmful result: ✅ personal injury (fracture, Grade-10 disability)
- Causation: ✅ directly caused by the traffic accident
- Fault: ✅ red-light running; full-fault finding

Adjustment factors:
- Aggravating: none
- Mitigating: none (Zhang not at fault)
- Exempting: none
```

**Step 2: Determine baseline legal consequence**

```
Consequence type: Tort damages liability
Legal basis: Civil Code Art. 1179
Baseline consequence: Li shall compensate Zhang for all losses caused by the traffic accident
```

**Step 3: Quantification**

(Assume prior-year per capita disposable income of urban residents in the place of the court seized of the case is RMB 55,000/year; per capita consumption expenditure RMB 35,000/year; average monthly employee wage RMB 7,500)

```
1. Medical expenses: per actual invoices (assume RMB 45,000)
   Confidence: 🟢 High (determined by invoices)

2. Lost wages: RMB 8,000/month ÷ 30 days × (30+90) days = RMB 32,000
   Confidence: 🟢 High (fixed income; clear calculation standard)

3. Nursing expenses: assume local nursing-worker standard RMB 150/day × 30 days = RMB 4,500
   Confidence: 🟡 Medium (nursing period and standard may be disputed)

4. Hospital meal subsidy: RMB 100/day × 30 days = RMB 3,000
   Confidence: 🟢 High (clear standard)

5. Nutrition expenses: assume RMB 50/day × 90 days = RMB 4,500
   Confidence: 🟡 Medium (requires medical-institution opinion)

6. Transportation expenses: per actual invoices (assume RMB 2,000)
   Confidence: 🟢 High (determined by invoices)

7. Disability compensation: RMB 55,000/year × 20 years × 10% (Grade-10 disability coefficient) = RMB 110,000
   Confidence: 🟢 High (clear calculation standard; age 35 uses 20-year base)

8. Mental-distress solatium: Grade-10 disability; referring to local standards, about RMB 5,000–10,000
   Confidence: 🟡 Medium (substantial judicial discretion)

9. Appraisal fees: per actual amount (assume RMB 2,500)
   Confidence: 🟢 High

Total: 45,000 + 32,000 + 4,500 + 3,000 + 4,500 + 2,000 + 110,000 + 7,500 + 2,500 = RMB 211,000
```

**Step 4: Manner of bearing liability**

```
Order of bearing compensation liability (Civil Code Art. 1213):
1. Within compulsory insurance limits: insurer pays within compulsory-insurance liability limits
   - Medical-expense limit: RMB 18,000 (covers medical expenses, hospital meal subsidy, nutrition expenses)
   - Death/disability limit: RMB 180,000 (covers disability compensation, lost wages, nursing expenses, mental-distress solatium, etc.)
   - Property-loss limit: RMB 2,000
   
2. Amounts exceeding compulsory insurance: commercial third-party insurance pays within its limit
   
3. Any remaining shortfall: borne by Li personally

Concrete allocation:
- Under compulsory medical-expense coverage: RMB 18,000
- Under compulsory death/disability coverage: 32,000+4,500+110,000+7,500 = RMB 154,000 (within limit)
- Compulsory insurance total payout: RMB 172,000
- Commercial third-party payout: 211,000 − 172,000 = RMB 39,000
- Li personally: RMB 0 (insurance sufficient)
```

#### Derivation Conclusion

```markdown
## Legal Consequence Derivation Conclusion

### I. Foundation of Derivation
- Li ran a red light and struck Zhang; traffic police found Li fully at fault
- Zhang’s right-leg fracture; 30 days hospitalized; Grade-10 disability; monthly income RMB 8,000
- Applicable: Civil Code Arts. 1179 and 1213, and the personal injury damages judicial interpretation

### II. Final Legal Consequence
Zhang may recover total damages of approximately **RMB 211,000** (subject to actual invoices and court findings)

Itemized damages:
| Damages Item | Amount (RMB) | Confidence |
|----------|-----------|--------|
| Medical expenses | 45,000 | 🟢 High |
| Lost wages | 32,000 | 🟢 High |
| Nursing expenses | 4,500 | 🟡 Medium |
| Hospital meal subsidy | 3,000 | 🟢 High |
| Nutrition expenses | 4,500 | 🟡 Medium |
| Transportation expenses | 2,000 | 🟢 High |
| Disability compensation | 110,000 | 🟢 High |
| Mental-distress solatium | 7,500 | 🟡 Medium |
| Appraisal fees | 2,500 | 🟢 High |
| **Total** | **211,000** | |

### III. Bearing of Liability
1. Compulsory insurance payout: about RMB 172,000
2. Commercial third-party payout: about RMB 39,000
3. Li personally: RMB 0

### IV. Overall Confidence: 🟢 High
- Clear facts, clear liability, uniform calculation standards
- Uncertainty factors: amount of mental-distress solatium, nursing-expense standard, and nutrition-expense standard involve some discretion

### V. Risk Warnings
1. The above calculation uses assumed statistical data; actual figures should use the latest statistics for the place of the court seized of the case
2. Medical and transportation expenses are determined by actual invoices
3. If Zhang later needs continued treatment, subsequent treatment expenses may be claimed separately
4. If the disability grade changes upon reappraisal, disability compensation will adjust accordingly
```

---

### Example Two: Criminal Sentencing Derivation (Complex Scenario)

#### Facts

Wang (age 28, no prior record), due to financial hardship, between March and June 2024 committed three successive household burglaries, stealing property totaling RMB 85,000. During the third theft he was discovered by the householder; Wang shoved the householder and fled (householder sustained minor injury). After capture, Wang truthfully confessed all criminal facts (not voluntary surrender / auto-surrender), voluntarily returned all stolen property, and obtained understanding from the victim of the third theft. Wang voluntarily admitted guilt and accepted punishment and signed an acknowledgment statement (具结书).

#### Derivation Process

**Step 1: Confirm input elements and analyze the offense**

```
Established facts:
1. Three household burglaries totaling RMB 85,000
2. On the third occasion, discovered; shoved householder causing minor injury, then fled
3. After capture, truthfully confessed all facts (frank admission / 坦白)
4. Voluntarily returned all stolen property
5. Obtained understanding from the third victim
6. Admitted guilt and accepted punishment; signed acknowledgment statement
7. No prior record; age 28

Key legal issue: Does the third act constitute converted robbery (转化型抢劫)?
Analysis:
- Criminal Law Art. 269: Whoever commits theft, fraud, or forcible seizure and, to conceal stolen goods, resist arrest, or destroy criminal evidence, uses violence or threatens violence on the spot shall be convicted and punished as robbery
- Wang shoved the householder and fled after being discovered during theft
- Does “shoving” reach the degree of “violence”? Judgment required:
  → If the shove was slight, merely to break free from entanglement, generally not treated as converted robbery
  → If the shove had some force and caused minor injury, it may be treated as converted robbery
- Here the householder suffered only minor injury; the violence degree of the shove is disputed

Path One: Does not constitute converted robbery (shove was slight)
  → Three household burglaries; huge amount
  → Offense: theft

Path Two: Constitutes converted robbery (shove reaches violence threshold)
  → First two household burglaries + third converted robbery (household robbery)
  → Offenses: theft + robbery (joinder of punishments)
  → Household robbery is an aggravated circumstance; statutory penalty of ten years or more

Derive both paths below:
```

**Path One: Theft (no converted robbery)**

```
Applicable legal norms:
- Criminal Law Art. 264: theft
- Huge theft amount (threshold varies by locality; generally RMB 30,000–100,000 is “huge”)
- Household burglary (aggravating circumstance)
- Multiple thefts (three or more)

Statutory sentencing range:
- Huge amount: fixed-term imprisonment of not less than three years and not more than ten years, and a fine
- Household burglary itself constitutes theft regardless of amount, but here the amount already reaches the huge standard
- Apply the “huge amount” range: not less than three years and not more than ten years

Sentencing starting point:
- Per sentencing guidance, for huge-amount theft the starting point is fixed-term imprisonment of three to four years
- This case: take starting point of three years six months (42 months)

Baseline sentence:
- Theft amount RMB 85,000; assume huge-amount threshold starts at RMB 30,000
- Excess RMB 55,000; add one month per increment of amount
- Assume one month per additional RMB 5,000: 55,000 ÷ 5,000 = 11 months
- Household-burglary circumstance: add six months (multiple household entries)
- Baseline = 42 + 11 + 6 = 59 months ≈ four years eleven months

Sentencing-circumstance adjustments:
1. Frank admission (truthful confession, not voluntary surrender): reduce baseline by 10%–30%
   → Take 20%: 59 × 20% = 11.8 months; reduce about 12 months
   
2. Restitution / return of stolen property (full return): reduce baseline by up to 30%
   → Take 25%: 59 × 25% = 14.75 months; reduce about 15 months
   
3. Victim understanding: reduce baseline by up to 40%
   → Only the third victim’s understanding; partial understanding
   → Take 10%: 59 × 10% = 5.9 months; reduce about 6 months
   
4. Leniency for admission of guilt and acceptance of punishment: reduce baseline by up to 30%
   → Take 20%: 59 × 20% = 11.8 months; reduce about 12 months

Same-direction mitigating aggregate ratio: 20% + 25% + 10% + 20% = 75%
→ Note: Where multiple circumstances adjust the baseline within the statutory range, the result may be taken directly as the declared sentence
→ But when the adjustment ratio is excessively high, overall consideration is required

Provisional declared sentence = 59 × (1 − 75%) = 14.75 months ≈ one year three months

Verification:
- Statutory range: not less than three years and not more than ten years
- Provisional declared sentence of one year three months is below the statutory minimum of three years
- Unless a mitigation-below-minimum circumstance applies, the sentence must not fall below three years
- Frank admission, restitution, understanding, and admission of guilt/acceptance of punishment are all lighter-punishment (从轻) circumstances, not mitigation-below-minimum (减轻) circumstances
- Under the admission-of-guilt-and-acceptance-of-punishment system, the procuratorate may recommend a lighter penalty
- Overall: declared sentence should be around three years

Adjusted declared sentence: fixed-term imprisonment of three years

Suspended-sentence analysis:
- Fixed-term imprisonment of not more than three years (including three): ✅ met
- Relatively light circumstances: 🟡 three household burglaries; circumstances are not light
- Remorse: ✅ frank admission, restitution, admission of guilt and acceptance of punishment
- No risk of reoffending: ✅ no prior record
- Suspension would not cause major adverse community impact: ✅ generally may be found
→ Likelihood of suspended sentence: 🟡 Medium (multiple household burglaries; some courts may deny suspension)

Supplementary penalty:
- Concurrent fine: theft requires a concurrent fine
- Fine amount: generally 50%–100% of the theft amount, i.e., RMB 42,500–85,000
- Given full restitution, the fine may be set toward the low end
- Provisional fine: RMB 50,000

Final conclusion (Path One):
- Principal penalty: fixed-term imprisonment of three years (suspended sentence possibly applicable; probation period four years)
- Supplementary penalty: concurrent fine of RMB 50,000
- Confidence: 🟡 Medium
```

**Path Two: Theft + robbery (converted robbery)**

```
Offense One: Theft (first two household burglaries)
- Assume first two thefts totaled RMB 55,000 (huge amount)
- Household burglary
- Statutory range: not less than three years and not more than ten years
- After sentencing circumstances: provisional declared sentence about three to four years

Offense Two: Robbery (third act as converted robbery)
- Household robbery: Criminal Law Art. 263(1)
- Statutory penalty: fixed-term imprisonment of ten years or more, life imprisonment, or death, and a fine or confiscation of property
- But violence degree here is low (shove causing minor injury); robbery amount about RMB 30,000
- Starting point: ten to twelve years
- Considering low violence, restitution, understanding, frank admission, admission of guilt and acceptance of punishment, etc.
- Provisional declared sentence about ten to eleven years

Joinder of punishments:
- Theft: three to four years
- Robbery: ten to eleven years
- Sum of terms: thirteen to fifteen years
- Highest single term: ten to eleven years
- Executed sentence range: ten to thirteen years
- Provisional executed sentence: about eleven to twelve years

Supplementary penalties:
- Theft: concurrent fine
- Robbery: concurrent fine or confiscation of property
- Combined enforcement

Final conclusion (Path Two):
- Principal penalty: fixed-term imprisonment of eleven to twelve years
- Supplementary penalty: concurrent fine
- Confidence: 🟡 Medium (converted-robbery characterization is disputed)
```

#### Derivation Conclusion

```markdown
## Legal Consequence Derivation Conclusion

### I. Foundation of Derivation
- Wang committed three household burglaries totaling RMB 85,000
- On the third occasion, after discovery, shoved the householder causing minor injury
- Frank admission, full restitution, partial understanding, admission of guilt and acceptance of punishment

### II. Key Dispute
Whether the third act constitutes converted robbery directly drives the sentencing outcome:

### III. Path Comparison

| Item | Path One (no converted robbery) | Path Two (converted robbery) |
|------|------------------------|----------------------|
| Offense(s) | Theft (one offense) | Theft + robbery (joinder) |
| Principal penalty | Fixed-term imprisonment of three years | Fixed-term imprisonment of eleven to twelve years |
| Suspended sentence | Possibly applicable | Not applicable |
| Fine | About RMB 50,000 | Higher |
| Confidence | 🟡 Medium | 🟡 Medium |

### IV. Overall Assessment
- **Most likely conclusion:** Path One (no converted robbery) is more probable
  - Reason: the shove was slight and caused only minor injury; judicial practice generally does not treat this as converted robbery
  - Caveat: some courts apply stricter standards to violence in a “household” setting
- **Most likely sentencing outcome:** fixed-term imprisonment of three years, concurrent fine of about RMB 50,000
- **Likelihood of suspended sentence:** about 40%–50% (multiple household burglaries are an adverse factor)

### V. Overall Confidence: 🟡 Medium
**Uncertainty factors:**
1. Whether the third act constitutes converted robbery (key dispute)
2. Local thresholds for “huge amount” in theft differ
3. Suspended-sentence application involves judicial discretion
4. Concrete adjustment ratios for sentencing circumstances vary by case

### VI. Risk Warnings
1. ⚠️ If the third act is characterized as converted robbery, the sentence will jump substantially to ten years or more
2. Suggested defense focus: argue that the shove did not reach the violence threshold for converted robbery
3. The sentencing recommendation in the acknowledgment statement for admission of guilt and acceptance of punishment is an important reference for the court
4. Actively seek understanding from the remaining victims to further reduce the sentence
5. The above sentencing derivation is based on general sentencing guidance; specific cases should refer to local sentencing implementation rules
```

---

## Appendix: Quick Reference Cards

### A. Derivation Flow Cheat Sheet

```
Fact confirmation → Norm matching → Element check → Baseline consequence → Adjustment factors → Concurrence handling → Quantification → Verify and output
```

### B. Common Damages Formulas Cheat Sheet

```
Disability compensation = per capita disposable income × compensation years × disability coefficient
Death compensation = per capita disposable income × 20 years (age-adjusted)
Funeral expenses = average monthly employee wage × 6
Lost wages = daily income × days of work missed
Liquidated-damages adjustment = 130% of actual loss as upper reference
Consumer fraud = price × 3 (refund + triple; minimum RMB 500)
Food safety = price × 10 (refund + tenfold; minimum RMB 1,000)
```

### C. Sentencing Circumstance Adjustment Ratios Cheat Sheet

```
Voluntary surrender: −20%~−40%    Frank admission: −10%~−30%
Meritorious service: up to −20%   Major meritorious service: −20%~−50%
Recidivism: +10%~+40%             Accessory: −20%~−50%
Attempt: up to −50%               Minor: −10%~−50%
Restitution: up to −30%           Compensation & understanding: up to −40%
Admission of guilt & acceptance of punishment: up to −30%    In-court admission: up to −10%
```
