---
name: counterfactual-reasoning
description: "Trigger this skill when you need to assess how legal outcomes would differ if a given fact, act, or condition did not exist or were altered. Typical trigger scenarios include: causation determinations (whether harm would still have occurred without the act), allocation of fault and liability shares, delimiting the scope of damages, calculating contract breach losses, hypothetical legality tests for administrative acts, assessing interruption of criminal causation, and legislative impact assessment. The core method is to construct a 'counterfactual world' that differs from the actual world only in the target variable, compare outcome differences between the two worlds, and thereby determine the target variable's contribution to the result."
---

> **Chinese source (authoritative):** [`../../skills/counterfactual-reasoning/SKILL.md`](../../skills/counterfactual-reasoning/SKILL.md)

# Counterfactual Reasoning（反事实推理）

## I. Overview Table

| Item | Content |
|------|------|
| **Capability Name** | Counterfactual Reasoning |
| **English Name** | Counterfactual Reasoning |
| **Capability Type** | Atomic legal reasoning capability |
| **Core Question** | "If X had not occurred / had been altered, would outcome Y still have arisen?" |
| **Classic Formulations** | But-for Test; Conditio Sine Qua Non (indispensable condition) |
| **Applicable Domains** | Tort law, contract law, criminal law, administrative law, insurance law, competition law, constitutional review |
| **Input** | The actual chain of facts + the target variable to be hypothetically altered |
| **Output** | Projection of the counterfactual world + comparative analysis versus the actual world + legal conclusion |
| **Difficulty Level** | ★★★★☆ (advanced reasoning; requires tight logical control) |
| **Risk Level** | High—errors in counterfactual reasoning may directly cause erroneous causation findings |

## II. Legal Disclaimer

> **Important notice:** Counterfactual reasoning is a tool of legal analysis. Its conclusions depend on accurate mastery of the facts and correct application of legal rules. This skill file provides a methodological framework and does not constitute legal advice on any specific case. Counterfactual reasoning inherently involves hypothetical judgments about events that did not occur and therefore carries intrinsic uncertainty. In practice, it should be combined with rules of evidence, standards of proof, and the case law of the relevant jurisdiction for an integrated judgment.

## III. Core Concepts

### 3.1 The Nature of Counterfactual Reasoning

Counterfactual reasoning is a **hypothetical method of causal analysis**. Its core logical structure is:

```
Actual world: A occurs → B occurs
Counterfactual world: Assume A does not occur → Does B still occur?

If B no longer occurs → A is a cause of B (A has causal contribution to B)
If B still occurs → A is not a cause of B (A has no causal contribution to B)
```

### 3.2 Key Term Definitions

| Term | Definition | Example |
|------|------|------|
| **Target Variable** | The fact/act/condition that is assumed to be altered or removed | "The defendant's speeding" |
| **Outcome Variable** | The legal consequence whose change (or lack of change) is to be observed | "The plaintiff's personal injury" |
| **Counterfactual World** | The hypothetical situation after the target variable is altered | "A world in which the defendant drove at a lawful speed" |
| **Actual World** | The factual state of affairs that actually occurred | "The defendant sped and injured the plaintiff" |
| **Background Conditions** | Other facts held constant in the counterfactual analysis | "Weather, road conditions, and the plaintiff's location at the time" |
| **But-for Causation** | The "but-for" test—but for A, B would not have occurred | "But for the defendant's speeding, the collision would not have occurred" |
| **NESS Test** | Necessary Element of a Sufficient Set test | Used in complex multi-cause, single-effect scenarios |
| **Novus Actus Interveniens (Interruption of the Causal Chain)** | An intervening factor that severs the original causal chain | Intervention by a third party's intentional act |

### 3.3 Philosophical Foundations of Counterfactual Reasoning

The use of counterfactual reasoning in law rests on the following assumptions:

1. **Possible-worlds semantics**: We can meaningfully discuss "what would have happened if things had been different"
2. **Minimal departure principle**: The counterfactual world should resemble the actual world as closely as possible, differing only in the target variable
3. **Stability of causal laws**: Natural and social regularities continue to hold in the counterfactual world
4. **Judgment-possibility assumption**: Outcomes in the counterfactual world can be judged within a reasonable range

### 3.4 Relationship Between the But-for Test and the NESS Test

```
                    Causation Tests
                        │
            ┌───────────┴───────────┐
            │                       │
   Single-cause, single-effect   Multi-cause, single-effect
            │                       │
      But-for Test              NESS Test
     "But for A, not B"     "A is a necessary element
                             of some sufficient set"
            │                       │
   Simple counterfactual      Compound counterfactual
   (remove a single variable) (analyze multi-variable interaction)
```

## IV. Complete Workflow

### Phase One: Issue Identification and Framework Construction

#### Step 1: Identify the Need for Counterfactual Reasoning

**Trigger signal detection:**
- Appearances of formulations such as "if … then … would not …"
- Need to determine causation between an act and an outcome
- Need to delimit the scope of damages ("what would have happened but for the breach")
- Need to assess a party's contribution of fault to the outcome
- Need to determine whether an intervening factor interrupted the causal chain
- Appearances of a defense such as "even if …, still …"

**Operational requirements:**
```
□ Clearly identify whether the current legal issue requires counterfactual reasoning
□ Locate counterfactual reasoning within the overall legal analysis (causation element, damages scope, or other)
□ Determine whether it is a simple counterfactual (single cause, single effect) or a complex counterfactual (multiple causes/effects)
```

#### Step 2: Precisely Define the Target Variable

**Core principle: The target variable must be specific, operationalizable, and legally meaningful**

```
Incorrect example: "If the defendant had not done wrong" → too vague
Correct example: "If the defendant had not placed the defective product on the market on 15 March 2023" → specific and operationalizable

Incorrect example: "If circumstances had been different" → not operationalizable
Correct example: "If the defendant had installed safety barriers during construction in accordance with GB50300" → specific and operationalizable
```

**Target-variable definition checklist:**
```
□ Is the target variable specific enough? (time, place, content of the act)
□ Does the target variable correspond to a breach of duty or infringement of a right under law?
□ Is alteration of the target variable physically/logically possible?
□ Is the target variable within the party's control? (relevant to attribution analysis)
□ Is it necessary to define multiple target variables? (multi-cause, single-effect scenarios)
```

#### Step 3: Precisely Define the Outcome Variable

```
□ Does the outcome variable correspond to legally cognizable harm/consequences?
□ Can the outcome variable be observed/measured?
□ Is the scope of the outcome variable clear? (all harm, or specific heads of damage)
```

#### Step 4: Lock Background Conditions

**Application of the minimal departure principle:**

When constructing the counterfactual world, all conditions other than the target variable should remain consistent with the actual world.

```
Actual-world fact list:
  F1: 15 March 2023, clear weather
  F2: Defendant driving at 80 km/h (speed limit 60 km/h) ← target variable
  F3: Plaintiff walking on the crosswalk
  F4: Dry road surface
  F5: Defendant's vehicle braking system functioning normally
  ...

Counterfactual world:
  F1: 15 March 2023, clear weather ← held constant
  F2': Defendant driving at 60 km/h ← target variable altered
  F3: Plaintiff walking on the crosswalk ← held constant
  F4: Dry road surface ← held constant
  F5: Defendant's vehicle braking system functioning normally ← held constant
  ...
```

**Notes on locking background conditions:**
- Facts that are causally dependent on the target variable may need to be adjusted accordingly
- Facts independent of the target variable must be held constant
- Whether a fact is "independent" may itself be disputed

### Phase Two: Constructing and Projecting the Counterfactual World

#### Step 5: Construct the Counterfactual World

**Construction methods:**

```
Method A: Simple substitution (for a single, clear target variable)
  Replace the target variable with its "lawful / normal / ought-to-be" state

Method B: Elimination (for determining whether a factor is a cause)
  Remove the target variable entirely from the chain of facts

Method C: Gradual adjustment (for assessing degree/proportion)
  Incrementally adjust the value of the target variable and observe changes in the outcome variable
```

#### Step 6: Project Outcomes in the Counterfactual World

**Projection rules:**

1. **Apply known causal regularities**: laws of physics, medical knowledge, economic regularities, common social knowledge
2. **Apply rules of experience**: what ordinarily occurs under similar conditions
3. **Apply expert opinion**: for causal judgments in specialized fields
4. **Apply statistical data**: for probabilistic causation

**Projection process recording template:**

```
Counterfactual projection chain:
  Premise: [Target variable altered to X']
  Step 1 projection: Because of X', intermediate fact M1 would / would not occur
    Basis: [causal regularity / rule of experience / expert opinion]
    Degree of certainty: [high / medium / low]
  Step 2 projection: Because of M1, intermediate fact M2 would / would not occur
    Basis: [causal regularity / rule of experience / expert opinion]
    Degree of certainty: [high / medium / low]
  ...
  Ultimate conclusion: Outcome variable Y in the counterfactual world [would / would not / would partially] occur
    Basis: [synthesis of the above projection chain]
    Degree of certainty: [high / medium / low]
```

#### Step 7: Compare the Two Worlds

```
Comparison matrix:
┌──────────────┬──────────────┬──────────────┬──────────────┐
│  Dimension   │ Actual World │Counterfactual│  Difference  │
├──────────────┼──────────────┼──────────────┼──────────────┤
│ Target var.  │     A        │     A'       │   Altered    │
│ Intermed. 1  │     M1       │     M1'      │ Diff. yes/no │
│ Intermed. 2  │     M2       │     M2'      │ Diff. yes/no │
│ Outcome var. │     Y        │     Y'       │ Diff. yes/no │
│ Harm extent  │     D        │     D'       │ Diff.=D-D'   │
└──────────────┴──────────────┴──────────────┴──────────────┘
```

### Phase Three: Extracting Legal Conclusions

#### Step 8: Extract Legal Conclusions from the Comparison

**Conclusion-type correspondence table:**

| Comparison Result | Legal Conclusion | Applicable Scenario |
|----------|----------|----------|
| Y does not occur at all in the counterfactual world | A is a sufficient cause of Y (but-for causation established) | Simple causation determination |
| Y still occurs in the counterfactual world | A is not a but-for cause of Y | Negation of causation / need to switch to NESS |
| Y partially occurs in the counterfactual world | A is a partial cause of Y; contribution = D−D' | Proportional liability / delimiting damages |
| Y occurs differently in the counterfactual world | A changed the manner of Y's occurrence but not whether Y occurred | Complex causation scenarios |
| Y occurs later in the counterfactual world | A accelerated the occurrence of Y | Accelerating causation |
| Cannot determine whether Y would occur in the counterfactual world | Causation uncertain; apply the applicable standard of proof | Insufficient evidence |

#### Step 9: Confidence Assessment and Qualifications

Annotate the confidence level of the counterfactual conclusion (see Section IX).

#### Step 10: Integrate into the Overall Legal Analysis

Treat the counterfactual conclusion as the analysis of the causation element (or other element) and integrate it into the complete legal argument.

## V. Common Domains and Sources of Law

### 5.1 Tort Law

| Specific Scenario | Counterfactual Question | Primary Source of Law | Test Method |
|----------|-----------|----------|----------|
| General tort causation | But for the tortious act, would the harm have occurred? | Civil Code arts. 1165 | But-for test |
| Multi-cause, single-effect | What is each cause's proportional contribution to the harm? | Civil Code arts. 1171–1172 | NESS + proportional analysis |
| Product liability | But for the product defect, would the harm have occurred? | Civil Code arts. 1202–1207 | But-for test |
| Medical harm | If the medical conduct had complied with norms, would the patient's outcome have differed? | Civil Code arts. 1218–1222 | But-for test + loss-of-chance theory |
| Environmental tort | But for the pollution discharge, would the environmental harm have occurred? | Civil Code arts. 1229–1235 | But-for test (burden of proof reversed) |
| Third-party intervention | Did the intervening act interrupt the original causal chain? | Case-law doctrine | Dual counterfactual test |

### 5.2 Contract Law

| Specific Scenario | Counterfactual Question | Primary Source of Law | Test Method |
|----------|-----------|----------|----------|
| Damages for breach | If the contract had been performed normally, what would the non-breaching party's economic position have been? | Civil Code art. 584 | Expectation-interest counterfactual |
| Culpa in contrahendo (pre-contractual liability) | But for the culpa in contrahendo, what would the relying party's economic position have been? | Civil Code art. 500 | Reliance-interest counterfactual |
| Foreseeability rule | Could the breaching party have foreseen the loss at the time of contracting? | Civil Code art. 584 | Reasonable-person counterfactual |
| Duty to mitigate | If the non-breaching party had taken reasonable measures, could the loss have been reduced? | Civil Code art. 591 | Mitigation counterfactual |

### 5.3 Criminal Law

| Specific Scenario | Counterfactual Question | Primary Source of Law | Test Method |
|----------|-----------|----------|----------|
| Causation in result crimes | But for the criminal act, would the harmful result have occurred? | Causation theory under the General Part of the Criminal Law | But-for test + adequate causation |
| Omission offenses | If the actor had performed the duty to act, could the result have been avoided? | Theory of omission offenses | Hypothetical-act counterfactual |
| Intervening factors | Was the intervening factor so abnormal as to interrupt the causal chain? | Objective imputation theory | Risk-realization counterfactual |
| Alternative causation | Two independent acts each sufficient to produce the result | Modified condition formula theory | NESS test |

### 5.4 Administrative Law

| Specific Scenario | Counterfactual Question | Primary Source of Law | Test Method |
|----------|-----------|----------|----------|
| Illegality of an administrative act | If the agency had administered according to law, would the outcome have differed? | Administrative Litigation Law | Lawful-act counterfactual |
| Administrative compensation | But for the unlawful administrative act, would the party's loss have occurred? | State Compensation Law | But-for test |
| Legitimate expectation / reliance protection | If the agency had not made the prior act, would the party have made the same decision? | Principle of reliance protection (信赖保护) | Decision counterfactual |

## VI. Validation and Screening Rules

### 6.1 Validity Checks for Counterfactual Reasoning

#### Rule 1: Substitutability of the Target Variable

```
Check question: Is alteration of the target variable physically and logically possible?
  ✓ Valid: "If the defendant had not run the red light" (the conduct could have been different)
  ✗ Invalid: "If the defendant were not human" (physically impossible substitution)
  ✗ Invalid: "If Earth had no gravity" (violates basic physical laws)
```

#### Rule 2: Minimal Departure Check

```
Check question: Does the counterfactual world differ from the actual world only in the target variable?
  ✓ Valid: Change only the defendant's driving speed; hold other conditions constant
  ✗ Invalid: Change the defendant's driving speed and also assume the weather improved
  ⚠ Note: If altering the target variable necessarily causes other facts to change, those cascade effects must be traced
```

#### Rule 3: Reliability of the Projection Chain

```
Check each step in the projection chain:
  □ Is this step supported by a reliable causal regularity?
  □ Are there alternative possibilities at this step?
  □ What is the degree of certainty of this step?
  □ Does the overall certainty of the chain meet the applicable legal standard of proof?
```

#### Rule 4: Overdetermination Check

```
Check question: Are there other independent sufficient causes?
  Scenario: A and B are each independently sufficient to produce Y
  But-for results: Remove A, Y still occurs (because of B); remove B, Y still occurs (because of A)
  → But-for test fails; switch to NESS
  NESS: A is a necessary element of the sufficient set {A, C1, C2...}
         B is a necessary element of the sufficient set {B, C3, C4...}
  → Both A and B are causes of Y
```

#### Rule 5: Preemption Check

```
Check question: Is there a "backup cause"—if the actual cause were absent, another cause would produce the same result?
  Scenario: A precedes B in causing Y, but if A were absent, B would also have caused Y
  Analysis: A is the actual cause of Y (because A in fact caused Y)
            B is a potential cause of Y (preempted by A)
  → The existence of B does not negate A's causation
```

### 6.2 Boundaries of Applicability

```
Conditions for applying counterfactual reasoning:
  ✓ Clear factual foundation exists
  ✓ The target variable can be meaningfully altered
  ✓ Reliable causal regularities support the projection
  ✓ Outcomes in the counterfactual world can be judged within a reasonable range

Situations where counterfactual reasoning does not apply:
  ✗ Pure questions of legal interpretation (no factual causation)
  ✗ The target variable cannot be meaningfully altered
  ✗ Lack of basic knowledge of causal regularities
  ✗ Outcomes in the counterfactual world are wholly unpredictable
  ✗ Law expressly provides an alternative method of determining causation
```

## VII. Output Format Templates

### Template A: Standard Counterfactual Reasoning Report

```markdown
## Counterfactual Reasoning Analysis Report

### 1. Purpose of Analysis
[Explain why counterfactual reasoning is needed and which legal element it addresses]

### 2. Variable Definitions
- **Target variable**: [Specific description of the fact/act assumed to be altered]
- **Outcome variable**: [Specific description of the legal consequence to be observed]
- **Counterfactual hypothesis**: [The state to which the target variable is altered]

### 3. Locked Background Conditions
[List key facts held constant in the counterfactual analysis]
| No. | Background Fact | Status |
|------|----------|------|
| F1   | ...      | Held constant |
| F2   | ...      | Held constant |
| ...  | ...      | ... |

### 4. Actual-World Fact Chain
[Describe the causal chain that actually occurred]
A → M1 → M2 → ... → Y

### 5. Counterfactual-World Projection
[Describe the projected causal chain in the counterfactual world]
A' → M1' → M2' → ... → Y'

Bases for projection:
- Step 1: [explanation of basis]
- Step 2: [explanation of basis]
- ...

### 6. Comparative Analysis
| Dimension | Actual World | Counterfactual World | Difference |
|------|----------|------------|------|
| Target variable | A | A' | Altered |
| Outcome variable | Y | Y' | [describe difference] |
| Harm extent | D | D' | ΔD = D − D' |

### 7. Legal Conclusion
[Legal conclusion based on the comparative analysis]

### 8. Confidence Assessment
- Reliability of projection chain: [high / medium / low]
- Certainty of conclusion: [high / medium / low]
- Principal uncertainties: [list]

### 9. Qualifications and Notes
[Limiting conditions and matters requiring attention]
```

### Template B: Brief Embedded Counterfactual Reasoning

```markdown
**Counterfactual analysis**: If [alteration of the target variable], then according to [basis for projection], [outcome variable] [would / would not / would partially] occur.
Reasoning: [brief projection process].
Therefore, causation between [target variable] and [outcome variable] [exists / does not exist / partially exists].
(Confidence: [high / medium / low])
```

## VIII. Confidence Annotation System

### 8.1 Projection-Chain Confidence

| Level | Tag | Meaning | Typical Scenario |
|------|------|------|----------|
| **High certainty** | `[CF-HIGH]` | Projection based on settled natural laws or undisputed rules of experience; conclusion nearly certain | Physical causation (e.g., without ignition there is no combustion) |
| **Moderately high certainty** | `[CF-MED-HIGH]` | Projection based on reliable professional knowledge or statistical regularities; conclusion highly likely | Medical causation (e.g., timely surgery yields 90% survival) |
| **Medium certainty** | `[CF-MEDIUM]` | Projection based on reasonable experiential judgment; conclusion possible but alternatives exist | Economic causation (e.g., profits that might have been earned but for breach) |
| **Moderately low certainty** | `[CF-MED-LOW]` | Projection based on general speculation; conclusion uncertain | Behavioral prediction (e.g., whether disclosure of risk would have led the party to decide differently) |
| **Low certainty** | `[CF-LOW]` | Highly speculative projection; conclusion highly uncertain | Long projection chains involving multiple uncertain variables |

### 8.2 Overall Conclusion Confidence

```
Overall confidence = min(confidence of each projection step)

That is: overall confidence of the chain is determined by its weakest link.

Example:
  Step 1 confidence: high
  Step 2 confidence: medium
  Step 3 confidence: high
  → Overall confidence: medium
```

### 8.3 Correspondence Between Confidence and Standards of Proof

| Legal Domain | Standard of Proof | Minimum Required Confidence |
|----------|----------|---------------|
| Civil cases (general) | High probability (>75%) (高度盖然性) | CF-MEDIUM or above |
| Criminal cases | Beyond reasonable doubt | CF-HIGH |
| Administrative cases | Clear preponderance of evidence | CF-MED-HIGH or above |
| Insurance claims | Preponderance of the evidence | CF-MEDIUM or above |

## IX. Common Errors and Safeguards

### 9.1 Fatal Error Table

| No. | Error Name | Description | Consequence | Safeguard |
|------|----------|----------|------|----------|
| E1 | **Vague target variable** | Failure to define precisely the fact assumed to be altered | Projection cannot proceed or conclusion is unreliable | Strictly apply Step 2 checklist |
| E2 | **Excessive departure** | Counterfactual world differs too much from the actual world; more than the target variable is changed | Results cannot be attributed to the target variable | Strictly apply the minimal departure principle |
| E3 | **Ignoring overdetermination** | Using only the but-for test in multi-cause, single-effect scenarios | Erroneous negation of causation | Detect multiple independent sufficient causes; switch to NESS when needed |
| E4 | **Ignoring preemption** | Negating the actual cause because a backup cause exists | Erroneous negation of causation | Distinguish actual causes from potential causes |
| E5 | **Broken projection chain** | Skipping key intermediate steps in the projection | Conclusion lacks support | Project step by step; annotate the basis for each step |
| E6 | **Certainty inflation** | Assigning excessive certainty to speculative conclusions | Misleading legal judgment | Strictly apply confidence annotation |
| E7 | **Counterfactual traced too far back** | Tracing the counterfactual hypothesis to an excessively remote past | Counterfactual world becomes uncontrollable | Limit the temporal scope of the counterfactual hypothesis |
| E8 | **Conflating factual and legal causation** | Equating factual but-for causation with legal causation | Ignoring legal limiting doctrines (e.g., adequacy, foreseeability) | Clearly distinguish factual causation from legal causation |

### 9.2 Common Traps

#### Trap 1: Hindsight Bias

```
Problem: Knowing the actual outcome, one tends to treat that outcome as "obvious" even in the counterfactual world
Example: After a failed surgery, one tends to think "another approach would certainly have succeeded"
Safeguards:
  - Project from an ex ante rather than an ex post perspective
  - Consider multiple possible outcomes in the counterfactual world
  - Cite ex ante statistical data and professional standards
```

#### Trap 2: Slippery Counterfactual

```
Problem: The counterfactual hypothesis triggers cascading changes, making the counterfactual world differ excessively from the actual world
Example: "If the defendant had never been born" → the entire world is different
Safeguards:
  - Confine the counterfactual hypothesis to the nearest, most concrete level of conduct
  - Do not trace back to deep factors such as character or upbringing
  - Apply the "nearest possible world" principle
```

#### Trap 3: Cherry-picking Counterfactual

```
Problem: Selecting the counterfactual hypothesis favorable to one's side while ignoring other equally reasonable hypotheses
Example: Plaintiff claims "if the defendant had not delayed delivery, I would have earned 1 million in profit"
         but ignores "even with timely delivery, falling market prices would have reduced profit"
Safeguards:
  - Systematically consider all reasonable counterfactual hypotheses
  - Project each hypothesis separately
  - Clearly annotate which hypotheses are adopted and why
```

#### Trap 4: Probability Neglect

```
Problem: Equating "possible" with "certain," ignoring the probabilistic nature of counterfactual outcomes
Example: "If treated in time, the patient would not have died" (when timely treatment may have only a 60% survival rate)
Safeguards:
  - Explicitly annotate the probability of the counterfactual outcome
  - Use loss-of-chance theory for probabilistic causation
  - Distinguish "would certainly have been avoided" from "had some probability of being avoided"
```

#### Trap 5: Wrong Time Frame

```
Problem: Inappropriate choice of temporal frame for the counterfactual projection
Example: When assessing breach losses, projecting the counterfactual world into an unbounded future
Safeguards:
  - Determine a reasonable time frame according to legal rules
  - Consider foreseeability limits on temporal scope
  - Lower confidence for long-horizon projections
```

## X. Special Scenario Handling

### 10.1 Multi-Cause, Single-Effect Scenarios

**Scenario description:** Multiple causes jointly produce one outcome

**Handling method:**

```
Step 1: Identify all possible causes A1, A2, A3, ...
Step 2: Apply the but-for test to each cause separately
  - Remove A1: does Y still occur?
  - Remove A2: does Y still occur?
  - ...
Step 3: Classify by but-for results

Case A: Removing any one cause, Y does not occur
  → All causes are but-for causes
  → Allocate liability according to each cause's degree of contribution

Case B: Removing some causes, Y still occurs (overdetermination)
  → Switch to NESS
  → Determine whether each cause is a necessary element of some sufficient set

Case C: Each cause alone is insufficient for Y, but together they produce Y
  → All causes are but-for causes (removing any one leaves the remainder insufficient for Y)
  → Joint causation; allocate liability by contribution share
```

### 10.2 Counterfactual Reasoning for Omissions

**Scenario description:** The actor failed to perform a duty to act; one must assess whether performing the duty would have changed the outcome

**Special difficulty:** One must construct a counterfactual world in which the actor affirmatively acted, but the concrete content of that affirmative action may be uncertain

**Handling method:**

```
Step 1: Determine the content of the actor's duty to act
  - Specific duties prescribed by law
  - Specific requirements of industry standards / duty of care
  - Specific obligations under contract

Step 2: Construct a "duty-performed" counterfactual world
  - Assume the actor took action as required by the duty
  - If the duty admits multiple modes of performance, choose the mode a "reasonable person" would adopt

Step 3: Project outcomes in the counterfactual world
  - Note: Counterfactual reasoning for omissions usually has lower confidence
  - Because "what if X had been done" is often harder to judge than "what if X had not been done"

Step 4: Pay special attention to probabilistic conclusions
  - "If the doctor had diagnosed in time, the patient had a 70% chance of survival"
  - Combine with loss-of-chance theory for legal evaluation
```

### 10.3 Hypothetical Causation

**Scenario description:** The defendant argues "even if I had not committed the tortious act, the same harm would have occurred for other reasons"

**Handling method:**

```
Step 1: Distinguish the "lawful alternative conduct" defense from the "hypothetical causation" defense

Lawful alternative conduct defense:
  "Even if I had acted lawfully, the same result would have occurred"
  Example: Although the doctor misdiagnosed, even a correct diagnosis would not have cured the patient
  → Ordinarily may negate causation

Hypothetical causation defense:
  "Although my conduct caused the harm, if I had not done it, someone else would have done the same"
  Example: Although the defendant cut down the tree, if the defendant had not, a storm would have blown it down
  → Ordinarily cannot negate causation (because it was in fact the defendant's conduct that produced the result)

Step 2: Assess whether the hypothetical cause had already "started"
  - If the hypothetical cause was already underway when the actual harm occurred → may affect the scope of damages
  - If the hypothetical cause is purely hypothetical → ordinarily does not affect the finding of causation

Step 3: Distinguish effects on causation from effects on the scope of damages
  - Hypothetical causation ordinarily does not negate causation itself
  - But it may affect the scope and duration of recoverable damages
```

### 10.4 Cumulative Causation

**Scenario description:** Multiple causes are each insufficient alone, but cumulatively produce the result

```
Example: Several factories each discharge small amounts of pollutant; no single discharge is sufficient to cause harm,
         but cumulative discharge causes environmental harm

Handling method:
  - But-for test: removing any one factory's discharge, harm may still occur
    (because other factories' discharges still exceed the threshold)
  - That does not mean the factory had no causal contribution
  - Apply a "substantial contribution" standard: did the factory's discharge substantially contribute to the harm?
  - Or use alternative theories such as market-share liability
```

### 10.5 Expectation-Interest Counterfactuals in Contract Law

**Scenario description:** When calculating damages for breach, one must construct a counterfactual world of "normal contractual performance"

```
Step 1: Determine the concrete content and performance conditions of the contract
Step 2: Construct a "normal performance" counterfactual world
  - Assume the breaching party fully performed as agreed
  - Hold other market conditions, third-party conduct, etc. constant
Step 3: Calculate the non-breaching party's economic position in the counterfactual world
Step 4: Calculate the difference = counterfactual economic position − actual-world economic position
Step 5: Apply the foreseeability rule and the duty to mitigate to limit recovery

Special attention:
  - Treatment of market price fluctuations: market price at breach or at judgment?
  - The non-breaching party's own capacity to perform: could that party have obtained the expected benefit in the counterfactual world?
  - Third-party factors: would third-party conduct have differed in the counterfactual world?
```

## XI. Quality Checklist

### 11.1 Post-Analysis Checklist for Counterfactual Reasoning

```
□ Foundation checks
  □ Is the target variable precisely defined?
  □ Is the outcome variable precisely defined?
  □ Is the counterfactual hypothesis clearly stated?
  □ Are background conditions fully listed and locked?

□ Logic checks
  □ Was the minimal departure principle observed?
  □ Does each step of the projection chain have a basis?
  □ Are there breaks in the projection chain?
  □ Were alternative projection paths considered?
  □ Was overdetermination checked?
  □ Was preemption checked?

□ Bias checks
  □ Is there hindsight bias?
  □ Is there cherry-picking of counterfactuals?
  □ Is there probability neglect?
  □ Is there a wrong time frame?
  □ Is there a slippery counterfactual?

□ Legal checks
  □ Does the counterfactual conclusion map to the correct legal element?
  □ Were factual and legal causation distinguished?
  □ Were legal limiting doctrines of causation considered?
  □ Does confidence meet the applicable standard of proof?

□ Presentation checks
  □ Is the projection process clear and traceable?
  □ Is confidence annotated?
  □ Are uncertainties explained?
  □ Is the conclusion appropriately qualified?
```

## XII. Complete Examples

### Example 1: Simple Scenario—Causation in a Traffic Accident

#### Facts

At 3:00 p.m. on 10 January 2024, defendant Zhang drove a small passenger car westbound on Jiefang Road in a certain city. At the intersection of Jiefang Road and Heping Road, Zhang ran a red light through the intersection. At that time, plaintiff Li was crossing the pedestrian crosswalk northbound on Heping Road on a green light. Zhang's vehicle collided with Li, causing a fracture of Li's left leg. Li was hospitalized for 45 days, incurring medical expenses of RMB 80,000 and lost wages of RMB 30,000.

At the time of the accident the weather was clear, the road was dry, and visibility was good. Zhang's speed was approximately 40 km/h (speed limit on that segment: 60 km/h). Traffic police determined that Zhang bore full responsibility for the accident.

**Legal question:** Is there a causal relationship between Zhang's running of the red light and Li's harm?

#### Counterfactual Reasoning Analysis

**1. Purpose of Analysis**

To determine whether there is factual (but-for) causation between Zhang's running of the red light (tortious act) and Li's personal injury (harmful result), as one of the elements of tort liability.

**2. Variable Definitions**

- **Target variable**: Zhang's act of running the red light at approximately 3:00 p.m. on 10 January 2024 at the intersection of Jiefang Road and Heping Road
- **Outcome variable**: Li's personal injury (fracture of the left leg and related losses)
- **Counterfactual hypothesis**: Zhang stopped and waited at the red light, and proceeded through the intersection only after the light turned green

**3. Locked Background Conditions**

| No. | Background Fact | Status |
|------|----------|------|
| F1 | Approximately 3:00 p.m. on 10 January 2024 | Held constant |
| F2 | Clear weather, dry road, good visibility | Held constant |
| F3 | Li crossing the pedestrian crosswalk northbound on Heping Road on a green light | Held constant |
| F4 | Zhang's speed approximately 40 km/h | Held constant |
| F5 | Zhang's vehicle braking system functioning normally | Held constant |
| F6 | Intersection traffic signals operating normally | Held constant |

**4. Actual-World Fact Chain**

```
Zhang runs the red light and enters the intersection
  → Zhang's vehicle and Li (who is proceeding on green) occupy the same space
  → Collision between Zhang's vehicle and Li
  → Fracture of Li's left leg
  → Li hospitalized 45 days; medical expenses RMB 80,000; lost wages RMB 30,000
```

**5. Counterfactual-World Projection**

```
Premise: Zhang stops and waits at the red light

Step 1 projection: Zhang remains behind the stop line and does not enter the intersection
  Basis: Direct physical consequence of obeying the red signal
  Degree of certainty: High [CF-HIGH]

Step 2 projection: Li safely crosses the pedestrian crosswalk on green
  Basis: No other abnormal conditions at the intersection (background conditions locked);
         Li proceeding normally on green would not encounter a vehicle from Zhang's direction
  Degree of certainty: High [CF-HIGH]

Step 3 projection: No collision between Zhang's vehicle and Li
  Basis: The two are not in the same space; collision is physically impossible
  Degree of certainty: High [CF-HIGH]

Ultimate conclusion: Li's left-leg fracture and related harm would not occur in the counterfactual world
  Degree of certainty: High [CF-HIGH]
```

**6. Comparative Analysis**

| Dimension | Actual World | Counterfactual World | Difference |
|------|----------|------------|------|
| Target variable | Zhang runs red light | Zhang waits at red light | Altered |
| Intermediate fact | Zhang's vehicle enters intersection | Zhang's vehicle remains behind stop line | Difference exists |
| Collision event | Collision occurs | No collision | Difference exists |
| Outcome variable | Fracture of Li's left leg | Li crosses safely | Difference exists |
| Harm extent | Medical RMB 80,000 + lost wages RMB 30,000 | No harm | ΔD = RMB 110,000 |

**7. Legal Conclusion**

But for Zhang's running of the red light, Li's personal injury would not have occurred. Zhang's running of the red light is a but-for cause of Li's harm; factual causation is established. `[CF-HIGH]`

**8. Confidence Assessment**

- Reliability of projection chain: High—each step rests on determinate physical causation
- Certainty of conclusion: High—the counterfactual outcome is nearly certain
- Principal uncertainties: Virtually none (a typical simple causation scenario)

---

### Example 2: Complex Scenario—Multi-Cause, Single-Effect and Loss of Chance in Medical Harm

#### Facts

Patient Wang, a 55-year-old male, presented to Hospital A on 1 February 2024 with persistent chest pain. Attending physician Zhao performed an electrocardiogram showing mild ST-segment changes, but Zhao did not give them due attention, diagnosed "intercostal neuralgia," prescribed analgesics, and sent Wang home.

In the early morning of 3 February 2024, Wang suffered an acute myocardial infarction at home and was rushed to Hospital B. Hospital B diagnosed "acute anterior wall myocardial infarction" and immediately performed PCI (percutaneous coronary intervention). Although the procedure successfully opened the occluded vessel, extensive myocardial necrosis had already occurred; Wang's cardiac function was severely impaired and was assessed as Grade III disability.

Medical appraisal opinions:
1. Zhao's diagnosis on 1 February was negligent—failure to recognize early manifestations of acute coronary syndrome
2. If diagnosis and PCI had been performed on 1 February, Wang would have had approximately a 70% probability of avoiding extensive myocardial necrosis, and cardiac function might have remained normal or only mildly impaired
3. Even with diagnosis and surgery on 1 February, there remained approximately a 30% probability of similar myocardial necrosis due to the severity of the coronary pathology
4. Wang himself had underlying coronary heart disease, hypertension, and diabetes; these diseases were the root cause of the myocardial infarction

**Legal question:** Is there a causal relationship between Zhao's misdiagnosis and Wang's harm? If so, what proportion of liability should Zhao (Hospital A) bear?

#### Counterfactual Reasoning Analysis

**1. Purpose of Analysis**

To determine causation between Zhao's misdiagnosis and Wang's harm (extensive myocardial necrosis leading to Grade III disability), and to determine Hospital A's share of liability. The case involves multi-cause, single-effect (misdiagnosis + underlying disease) and probabilistic causation (loss of chance), requiring compound counterfactual reasoning.

**2. Variable Definitions**

- **Target variable**: Zhao's misdiagnosis on 1 February 2024 (failure to recognize early manifestations of acute coronary syndrome; failure to order further examination and treatment)
- **Outcome variable**: Wang's extensive myocardial necrosis and Grade III disability
- **Counterfactual hypothesis**: Zhao correctly recognizes acute coronary syndrome on 1 February, immediately arranges hospitalization, and performs PCI

**Note:** Two independent harm-producing factors exist in this case:
- Factor A: Zhao's misdiagnosis (delay in treatment)
- Factor B: Wang's own coronary heart disease and other underlying conditions (root etiology)

**3. Locked Background Conditions**

| No. | Background Fact | Status |
|------|----------|------|
| F1 | Wang, 55-year-old male, with coronary heart disease, hypertension, and diabetes | Held constant |
| F2 | Severe stenosis/occlusion of Wang's coronary arteries | Held constant |
| F3 | Wang develops chest pain symptoms on 1 February 2024 | Held constant |
| F4 | Then-prevailing medical technology and PCI conditions | Held constant |
| F5 | Hospital A has the capacity to perform PCI | To be confirmed (assumed present) |

**4. Actual-World Fact Chain**

```
Severe coronary stenosis (underlying disease)
  + Zhao misdiagnoses as intercostal neuralgia (misdiagnosis)
  → Wang does not receive timely treatment
  → Two days later (3 February) complete coronary occlusion; acute myocardial infarction
  → Extensive myocardial necrosis
  → Despite PCI rescue at Hospital B, cardiac function severely impaired
  → Grade III disability
```

**5. Counterfactual-World Projection**

```
Premise: Zhao correctly diagnoses on 1 February and immediately arranges PCI

Step 1 projection: Wang undergoes coronary angiography on 1 February
  Basis: Standard diagnostic and treatment pathway after correct diagnosis of acute coronary syndrome
  Degree of certainty: High [CF-HIGH]

Step 2 projection: Angiography reveals severe stenosis; PCI performed immediately
  Basis: Standard treatment protocol for acute coronary syndrome
  Degree of certainty: Moderately high [CF-MED-HIGH]

Step 3 projection (key fork): Effect of PCI
  Scenario A (probability 70%): Successful surgery; vessel opened; no extensive myocardial necrosis
    → Wang's cardiac function normal or mildly impaired
    → Does not constitute Grade III disability (possibly Grade X or no disability)
    Basis: Medical appraisal—70% probability of avoiding extensive necrosis
    Degree of certainty: Medium [CF-MEDIUM] (probabilistic conclusion)

  Scenario B (probability 30%): Due to severity of coronary pathology, extensive necrosis still occurs even with timely surgery
    → Wang's cardiac function severely impaired
    → May still constitute Grade III disability or a similar grade
    Basis: Medical appraisal—30% probability of similar necrosis
    Degree of certainty: Medium [CF-MEDIUM] (probabilistic conclusion)
```

**6. Comparative Analysis**

| Dimension | Actual World | Counterfactual World (Scenario A, 70%) | Counterfactual World (Scenario B, 30%) |
|------|----------|--------------------------|--------------------------|
| Target variable | Misdiagnosis; 2-day delay | Correct diagnosis; immediate surgery | Correct diagnosis; immediate surgery |
| Myocardial necrosis | Extensive necrosis | None / mild necrosis | Extensive necrosis |
| Disability grade | Grade III | None / Grade X | Grade III or similar |
| Difference from actual | — | Significant difference | No significant difference |

**7. Legal Analysis**

**Layer One: Factual Causation (But-for Test)**

- Removing Zhao's misdiagnosis (assuming correct diagnosis and treatment), Wang had a 70% probability of avoiding extensive myocardial necrosis
- But there remained a 30% probability of a similar outcome
- **Conclusion**: The but-for test yields a probabilistic result—the misdiagnosis deprived Wang of a 70% chance of avoiding severe harm

**Layer Two: Multi-Cause, Single-Effect Analysis**

```
Factor A (misdiagnosis / delay): Deprived Wang of the opportunity for timely treatment
Factor B (underlying disease): Root etiology of the myocardial infarction

Relationship between the two factors:
  - Factor B is a necessary condition (without coronary heart disease there is no MI)
  - Factor A is an aggravating condition (delayed treatment turned harm from "possibly avoidable" into "certain to occur")
  - The two acted jointly to produce the ultimate severe harm
```

**Layer Three: Determining Liability Share**

```
Method One: Loss-of-chance theory
  Zhao's misdiagnosis deprived Wang of a 70% chance of avoiding severe harm
  → Hospital A should compensate 70% of Wang's harm

Method Two: Comparison of causal force (原因力)
  Underlying disease is the root cause (greater causal force)
  Misdiagnosis is an aggravating cause (lesser but significant causal force)
  → On balance, Hospital A bears 40%–60% of liability

Method Three: Comprehensive judgment (common in practice)
  Factors considered:
  - Degree of fault in the misdiagnosis (failure to recognize ST-segment changes; clear fault)
  - Severity of underlying disease (CHD + hypertension + diabetes; inherently serious)
  - Probability of lost chance (70%)
  - Patient's own responsibility for health management
  → Suggested that Hospital A bear 50%–70% of liability
```

**8. Confidence Assessment**

- Reliability of projection chain: Medium—the key step (surgical outcome) depends on probabilistic medical judgment
- Certainty of conclusions:
  - Existence of causation: Moderately high `[CF-MED-HIGH]` (misdiagnosis did delay treatment)
  - Specific liability share: Medium `[CF-MEDIUM]` (depends on application of loss-of-chance theory and judgment of causal force)
- Principal uncertainties:
  - Actual success rate of surgery on 1 February (appraisal gives 70%, itself an estimate)
  - Even with timely surgery, Wang's precise degree of recovery is uncertain
  - Effect of Wang's underlying disease on long-term prognosis

**9. Qualifications and Notes**

1. This analysis depends on the medical appraisal conclusion of a "70% probability of avoiding extensive necrosis"; if that conclusion is overturned, the causation analysis must be redone
2. Determining liability share involves legal-policy judgment; different courts may exercise different discretion
3. Application of "loss of chance" theory remains contested in Chinese judicial practice; some courts may use a different analytical framework
4. Further evidence is recommended to increase certainty of the analysis:
   - Whether Hospital A had the capacity to perform PCI on 1 February
   - The specific severity of Wang's coronary pathology (angiography results)
   - Statistical data from similar cases

---

## Appendix: Counterfactual Reasoning Quick-Reference Decision Tree

```
Start: Need to determine causation between A and Y
  │
  ├─ Q1: Is there only one possible cause A?
  │   ├─ Yes → Use simple but-for test
  │   │        Remove A: does Y still occur?
  │   │        ├─ Y does not occur → A is a cause of Y ✓
  │   │        ├─ Y still occurs → A is not a cause of Y ✗
  │   │        └─ Uncertain → Annotate confidence; apply standard of proof
  │   │
  │   └─ No → Multiple possible causes A1, A2, ...
  │            │
  │            ├─ Q2: Is each cause independently sufficient for Y? (overdetermination)
  │            │   ├─ Yes → Use NESS test
  │            │   │        Is each cause a necessary element of some sufficient set?
  │            │   │        ├─ Yes → That cause is a cause of Y ✓
  │            │   │        └─ No → That cause is not a cause of Y ✗
  │            │   │
  │            │   └─ No → Causes jointly produce Y
  │            │            Use but-for test (remove any one cause → Y does not occur)
  │            │            + compare causal force to determine each cause's contribution share
  │            │
  │            └─ Q3: Is there probabilistic causation?
  │                ├─ Yes → Use loss-of-chance theory
  │                │        Calculate the target variable's effect on the probability of the outcome
  │                └─ No → Use standard multi-cause analysis
  │
  ├─ Q4: Is there an intervening factor?
  │   ├─ Yes → Dual counterfactual test
  │   │        (1) Remove original act A: does Y still occur?
  │   │        (2) Remove intervening factor I: does Y still occur?
  │   │        (3) Is the intervening factor so "abnormal" as to interrupt the causal chain?
  │   └─ No → Continue standard analysis
  │
  └─ Q5: Is this an omission scenario?
      ├─ Yes → Construct a "hypothetical act" counterfactual world
      │        Note: Confidence is usually lower
      └─ No → Use the standard counterfactual reasoning workflow
```
