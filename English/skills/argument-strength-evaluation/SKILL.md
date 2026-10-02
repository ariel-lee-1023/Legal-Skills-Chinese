---
name: argument-strength-evaluation
description: |
  After an AI agent completes a segment of legal reasoning or argumentation, it must self-assess the resulting conclusion: judge the overall strength and confidence of the argument, and identify and flag weak links in the reasoning chain.
  Trigger conditions include, but are not limited to:
  - After completing legal analysis, a reliability rating for the conclusion is needed
  - The user expressly requests an evaluation of the persuasiveness or reliability of a given argument
  - Multiple competing legal interpretations require comparison of argument strength
  - The reasoning involves uncertainties (unclear facts, legal gaps, contested views) that need to be flagged
  - Risk warnings are needed for decision-makers, explaining the limitations of the conclusion
  - Offensive or defensive strength of one's own or the opposing party's legal arguments must be assessed
  - Confidence statements must be attached in legal opinions, memoranda, or similar documents
---

> **Chinese source (authoritative):** [`../../skills/argument-strength-evaluation/SKILL.md`](../../skills/argument-strength-evaluation/SKILL.md)

# Evaluating Argument Strength

## Overview Table

| Item | Content |
|------|------|
| Capability name | Evaluating Argument Strength |
| Capability type | Metacognition / self-assessment |
| Core function | Assess confidence in legal reasoning conclusions; identify and flag weak links |
| Input | A complete legal reasoning process and its conclusion |
| Output | Argument strength rating, weak-link annotations, improvement suggestions |
| Prerequisites | Legal reasoning, statute retrieval, elements analysis, analogous-case comparison, etc. |
| Downstream uses | Drafting legal opinions, litigation strategy, risk assessment, decision advice |
| Key risks | Overconfidence that misses risks; over-conservatism that renders conclusions useless |

## Legal Disclaimer

> **Important notice:** The argument-strength evaluation produced by this skill is an auxiliary analytical tool only and does not constitute formal legal advice. Final judgments on legal reasoning should be made by qualified legal professionals. Argument-strength evaluation is itself subjective; different evaluators may reach different conclusions. AI self-assessment has inherent limitations, including but not limited to: inability to fully foresee uncertainty in judicial adjudication; inability to substitute for firsthand judgment of specific case facts; and possible systematic assessment bias arising from training-data bias. Users should treat evaluation results as reference material, not as definitive conclusions.

---

## I. Core Concepts

### 1.1 What Is Argument Strength

Argument Strength is the degree of support that a segment of legal reasoning provides from premises to conclusion. It reflects the likelihood that the conclusion will be adopted in law and its persuasiveness. It is not a binary judgment (right/wrong), but a position on a continuous spectrum.

### 1.2 Constituent Dimensions of Argument Strength

Argument strength is jointly determined by the following six core dimensions:

| Dimension | Meaning | Weight note |
|------|------|----------|
| **Certainty of legal basis** | Clarity of the cited legal norms, hierarchical rank of legal force, and whether they remain currently in effect | Foundational dimension; highest weight |
| **Adequacy of factual basis** | Whether the facts supporting the reasoning are adequate and whether the evidence is solid | Core dimension; directly affects reliability of the conclusion |
| **Rigor of logical reasoning** | Whether the path from premises to conclusion contains logical leaps or fallacies | Structural dimension; determines whether the argument is internally coherent |
| **Resistance to rebuttal** | Whether the argument can effectively withstand foreseeable objections | Adversarial dimension; reflects robustness of the argument |
| **Consistency with judicial practice** | Whether the conclusion aligns with mainstream judicial tendencies | Practice dimension; affects likelihood of actual adoption |
| **Reasonableness of value judgments** | When interest balancing or purposive interpretation is involved, whether the value orientation is reasonable | Supplementary dimension; weight rises in hard cases |

### 1.3 Relationship Between Argument Strength and Confidence

- **Argument strength**: An objective evaluation of the quality of the argument itself
- **Confidence**: The AI system's degree of certainty about its own assessment result (meta-confidence)
- The two may diverge: for example, the AI may assign high confidence to a judgment that an argument is of "medium strength" (confident in the assessment itself, while the argument still involves uncertainty)

### 1.4 Typology of Weak Links

| Weak-link type | Definition | Severity | Example |
|-------------|------|----------|------|
| **Fatal defect** | A fundamental problem sufficient to overturn the entire argument | ★★★★★ | Citing a repealed statute; factual findings contradict the evidence |
| **Major weakness** | A problem that significantly weakens the persuasiveness of the argument | ★★★★☆ | Key elements lack direct evidence; a strong rebuttal exists |
| **Moderate risk** | A problem that opposing counsel may exploit but that is not fatal | ★★★☆☆ | Inconsistent analogous-case outcomes; substantial scholarly controversy |
| **Minor flaw** | Affects the perfection of the argument but not the core conclusion | ★★☆☆☆ | Suboptimal presentation order; supporting arguments insufficient |
| **Latent hazard** | Not currently a problem, but may surface under certain conditions | ★☆☆☆☆ | Trends toward statutory revision; policy-change risk |

---

## II. Complete Workflow

### Phase One: Deconstruction

**Goal:** Break the argument under evaluation into independently assessable components.

**Step 1: Identify argument structure**

```
1.1 Extract the core Conclusion
    → What is this argument ultimately trying to prove?
1.2 Extract the main Premises
    → Which factual and legal premises does the conclusion depend on?
1.3 Identify Inference Rules
    → What reasoning methods are used from premises to conclusion?
    (Deduction / induction / analogy / purposive interpretation / systematic interpretation, etc.)
1.4 Identify Hidden Assumptions
    → Which unstated premises must hold for the argument to work?
1.5 Draw an argument-chain diagram
    → Organize the above elements into a clear reasoning chain
```

**Step 2: Mark assessment nodes**

```
For each node in the argument chain, mark:
- [F] Fact node: assess factual basis
- [L] Law node: assess legal basis
- [R] Reasoning node: assess logical relations
- [A] Assumption node: assess reasonableness of hidden assumptions
- [V] Value node: assess reasonableness of value judgments
```

### Phase Two: Dimensional Assessment

**Step 3: Assess certainty of legal basis**

```
Checklist:
□ Are the cited legal norms currently in effect?
□ Is the hierarchical rank of legal force sufficient? (Constitution > law > administrative regulation > rule > normative document)
□ Is the meaning of the provision clear, or are multiple interpretations possible?
□ Are there conflicts between special and general law, or between new and old law?
□ Do judicial interpretations clearly support this reading?
□ Are there Guiding Cases (指导性案例) that authoritatively interpret the provision?
□ Is the legal norm under discussion for revision?

Scoring criteria:
- 5 points: Legal basis clear, high hierarchical force, uncontroversial
- 4 points: Legal basis relatively clear; minor room for interpretation
- 3 points: Legal basis exists, but interpretations diverge
- 2 points: Legal basis vague; extensive interpretive argument needed
- 1 point: No direct legal basis; analogy or legal principles needed to fill the gap
```

**Step 4: Assess adequacy of factual basis**

```
Checklist:
□ Are key facts adequately supported by evidence?
□ What is the probative force of the evidence? (Direct vs. circumstantial)
□ Is the chain of evidence complete?
□ Are there unclear or disputed facts?
□ Is the allocation of the burden of proof favorable?
□ What contrary evidence might the other side offer?
□ Does fact-finding depend on rulings on evidence admissibility/credibility?

Scoring criteria:
- 5 points: Facts clear; evidence solid and sufficient; no dispute
- 4 points: Main facts supported by evidence; individual details need reinforcement
- 3 points: Basic facts have evidence, but key links are inadequately supported
- 2 points: Major factual disputes; obvious gaps in the evidence chain
- 1 point: Weak factual basis; core facts lack evidentiary support
```

**Step 5: Assess rigor of logical reasoning**

```
Checklist:
□ Are there logical leaps (premises do not directly entail the conclusion)?
□ Is there circular reasoning?
□ Is there hasty generalization (improper induction)?
□ In analogical reasoning, do the compared objects share substantial similarity?
□ Are sufficient and necessary conditions confused?
□ Is there a slippery-slope fallacy?
□ Is there an improper appeal to authority?
□ Do both the major and minor premises of the syllogism hold?
□ In multi-step reasoning, does each step withstand scrutiny?

Scoring criteria:
- 5 points: Reasoning rigorous; logic without flaw
- 4 points: Reasoning basically rigorous; negligible minor flaws
- 3 points: Reasoning largely holds, but some logical links can be challenged
- 2 points: Obvious logical problems; supplementary argument needed
- 1 point: Fundamental logical error in the reasoning
```

**Step 6: Assess resistance to rebuttal**

```
Checklist:
□ Have all foreseeable objections been identified?
□ What is the other side's strongest rebuttal?
□ Can the argument effectively respond to those rebuttals?
□ Is there a "fatal rebuttal" (one objection that overturns the entire argument)?
□ Might the other side raise procedural defenses?
□ Have exemption grounds, rights of defense, limitation periods, and similar defensive devices been considered?
□ Does the argument over-rely on a single point without fallback options?

Scoring criteria:
- 5 points: All major rebuttals fully anticipated and effectively answered
- 4 points: Most rebuttals answerable; response strength to a few is only average
- 3 points: Strong opposing points exist; effectiveness of responses uncertain
- 2 points: Major rebuttals that are hard to answer effectively
- 1 point: Fatal rebuttal exists; argument difficult to sustain
```

**Step 7: Assess consistency with judicial practice**

```
Checklist:
□ Are there judgments on the same or similar issues?
□ Does the mainstream adjudicative tendency support the conclusion?
□ Is there adjudicative divergence (same case, different outcomes)?
□ What is the attitude of the Supreme People's Court / Supreme People's Procuratorate?
□ Does the local court have special adjudicative tendencies?
□ Have recent adjudicative trends changed?
□ Are Guiding Cases or Gazette cases directly on point?

Scoring criteria:
- 5 points: Highly consistent with mainstream judicial practice; supported by authoritative cases
- 4 points: Consistent with majority adjudicative tendency; a minority of cases differ
- 3 points: Judicial practice diverges; the conclusion is one of the views that may be adopted
- 2 points: Inconsistent with majority tendency; a minority view
- 1 point: Clearly contradicts mainstream judicial practice; almost no supporting cases
```

**Step 8: Assess reasonableness of value judgments**

```
Checklist:
□ Does the argument involve interest balancing? Are the balancing criteria reasonable?
□ Does purposive interpretation align with legislative purpose?
□ Does the value orientation align with the Core Socialist Values (社会主义核心价值观)?
□ Has the balance among the interests of the parties been considered?
□ Does it meet basic requirements of fairness and justice?
□ Has the unity of social effect and legal effect been considered?
□ In hard cases, is the value choice adequately reasoned?

Scoring criteria:
- 5 points: Value judgment reasonable; consistent with mainstream value orientation
- 4 points: Value judgment basically reasonable; some aspects debatable
- 3 points: Value judgment contested; different standpoints may evaluate differently
- 2 points: Value judgment skewed; may invite reasonable challenge
- 1 point: Value judgment clearly improper; contrary to basic legal values
```

### Phase Three: Synthesis

**Step 9: Calculate composite strength score**

```
Weighted formula:
Composite score = Certainty of legal basis × W1 + Adequacy of factual basis × W2 +
           Rigor of logical reasoning × W3 + Resistance to rebuttal × W4 +
           Consistency with judicial practice × W5 + Reasonableness of value judgments × W6

Default weights (adjustable by case type):
- Ordinary cases: W1=0.25, W2=0.25, W3=0.20, W4=0.15, W5=0.10, W6=0.05
- Hard cases: W1=0.15, W2=0.15, W3=0.20, W4=0.15, W5=0.15, W6=0.20
- Fact-dispute cases: W1=0.15, W2=0.35, W3=0.15, W4=0.15, W5=0.15, W6=0.05
- Law-application dispute cases: W1=0.30, W2=0.10, W3=0.20, W4=0.15, W5=0.20, W6=0.05

Note: When a fatal defect exists, regardless of the composite score, the overall rating should drop to "Weak" or "Very Weak."
```

**Step 10: Determine argument-strength grade**

| Composite score | Strength grade | Meaning | Color marker |
|----------|----------|------|----------|
| 4.5-5.0 | **Very Strong** | Argument nearly unassailable; conclusion highly reliable | 🟢 Dark green |
| 3.5-4.4 | **Strong** | Argument forceful; conclusion relatively reliable; minor shortcomings | 🟢 Green |
| 2.5-3.4 | **Medium** | Argument somewhat persuasive, but clear uncertainties remain | 🟡 Yellow |
| 1.5-2.4 | **Weak** | Insufficient persuasiveness; conclusion faces substantial challenge | 🟠 Orange |
| 1.0-1.4 | **Very Weak** | Argument basically fails; conclusion hard to sustain | 🔴 Red |

**Step 11: Annotate weak links**

```
For each identified weak link, record:
1. Location: Specific position in the argument chain
2. Weakness type: Fatal defect / Major weakness / Moderate risk / Minor flaw / Latent hazard
3. Description: Why this link is weak
4. Scope of impact: Which parts of the argument this weak link affects
5. Repairability: Whether it can be fixed by supplementary argument/evidence
6. Repair suggestion: How to strengthen this link
```

### Phase Four: Meta-Assessment

**Step 12: Assess confidence in one's own assessment**

```
Reflect on the entire evaluation process:
□ Have I fully understood the complete context of the argument?
□ Is my legal knowledge adequate in this field?
□ Might I have confirmation bias (tendency to verify rather than challenge)?
□ Have I omitted important assessment dimensions?
□ Was my scoring affected by anchoring?
□ Would the assessment differ if viewed from another angle?
□ Are there recent developments in this field that I do not know?

Meta-confidence levels:
- High confidence: Assessment based on adequate information; methodology appropriate; conclusion reliable
- Medium confidence: Assessment based on reasonable information, but information gaps or methodological limits exist
- Low confidence: Assessment based on limited information; conclusion for reference only
```

---

## III. Common Domains and Sources of Law

| Legal domain | Assessment focus | Common sources of law | Special considerations |
|----------|----------|----------|----------|
| Contract disputes | Contract interpretation, breach determination, damages calculation | Book of Contracts of the Civil Code (《民法典》合同编); related judicial interpretations | Note the boundary between party autonomy and mandatory provisions |
| Tort liability | Causation, fault, allocation of liability | Book of Tort Liability of the Civil Code (《民法典》侵权责任编); interpretations on personal injury damages | Causation argument is often the weakest link |
| Criminal defense | Elements of the offense, sufficiency of evidence, sentencing factors | Criminal Law (《刑法》); Criminal Procedure Law (《刑事诉讼法》); related judicial interpretations | Highest evidentiary standard (beyond reasonable doubt); special attention required |
| Administrative litigation | Legality of administrative acts, procedural propriety, discretion | Administrative Litigation Law (《行政诉讼法》); Administrative Penalty Law (《行政处罚法》), etc. | Burden of proof often reversed; focus on the agency's ability to prove |
| Intellectual property | Validity of rights, infringement comparison, damages | Patent Law (《专利法》); Trademark Law (《商标法》); Copyright Law (《著作权法》), etc. | Technical fact-finding is often a weak link |
| Labor disputes | Existence of employment relationship, legality of termination, economic compensation | Labor Law (《劳动法》); Labor Contract Law (《劳动合同法》); related judicial interpretations | The principle of tilted protection affects argument-strength assessment |
| Corporate governance | Validity of resolutions, shareholder rights, directors' duties | Company Law (《公司法》) and judicial interpretations | Note the impact of the latest Company Law revision |

---

## IV. Validation and Filtering Rules

### 4.1 Pre-Validation of Argument Validity

Before assessing strength, first verify that the argument meets basic validity conditions:

```
Pre-validation checklist (if any item fails, the argument is invalid and strength assessment is unnecessary):
[V1] Does the argument have a clear conclusion?
     → Fail: Require clarification of the argumentative goal, then reassess
[V2] Does the argument have at least one legal basis?
     → Fail: Mark as "lacks legal foundation; argument fails"
[V3] Is there a logical connection between premises and conclusion?
     → Fail: Mark as "argument structure fails"
[V4] Is the argument based on verifiable facts (rather than pure hypothesis)?
     → Fail: Mark as "factual basis missing" (except for hypothetical analyses)
```

### 4.2 Filtering Rules for Assessment Results

```
Rule 1 (Fatal-defect veto):
  IF any dimension score = 1 AND that dimension is Certainty of legal basis or Adequacy of factual basis
  THEN overall rating ≤ "Weak", regardless of composite score

Rule 2 (Weakest-link effect):
  IF two or more dimensions score ≤ 2
  THEN overall rating ≤ "Medium"

Rule 3 (Consistency check):
  IF composite score and intuitive judgment differ by > 1 grade
  THEN trigger review; re-examine each dimension score

Rule 4 (Domain-specific rule):
  IF case type = criminal AND Adequacy of factual basis ≤ 3
  THEN overall rating automatically drops one grade (reflecting the beyond-reasonable-doubt standard)

Rule 5 (Insufficient-information downgrade):
  IF meta-confidence = "Low"
  THEN append annotation "[Insufficient information; assessment reliability limited]" after the final rating
```

---

## V. Output Format Templates

### 5.1 Standard Output Template

```markdown
## Argument Strength Evaluation Report

### I. Argument Summary
- **Subject of evaluation:** [Brief description of the argument being evaluated]
- **Core conclusion:** [Core conclusion of the argument under evaluation]
- **Argument type:** [Deductive / inductive / analogical / combined reasoning]
- **Legal domain:** [Applicable legal field]

### II. Argument Structure Analysis
[Argument-chain diagram or structured description]

### III. Dimensional Scores

| Assessment dimension | Score (1-5) | Brief explanation |
|----------|-----------|----------|
| Certainty of legal basis | X.X | [Explanation] |
| Adequacy of factual basis | X.X | [Explanation] |
| Rigor of logical reasoning | X.X | [Explanation] |
| Resistance to rebuttal | X.X | [Explanation] |
| Consistency with judicial practice | X.X | [Explanation] |
| Reasonableness of value judgments | X.X | [Explanation] |

### IV. Composite Assessment
- **Composite score:** X.X / 5.0
- **Strength grade:** [Very Strong / Strong / Medium / Weak / Very Weak] [Color marker]
- **Meta-confidence:** [High / Medium / Low]

### V. Weak-Link Annotations

#### Weak Link 1: [Name]
- **Type:** [Fatal defect / Major weakness / Moderate risk / Minor flaw / Latent hazard]
- **Location:** [Position in the argument chain]
- **Description:** [Specific explanation]
- **Impact:** [Impact on the argument as a whole]
- **Repairability:** [High / Medium / Low]
- **Repair suggestion:** [Specific suggestion]

#### Weak Link 2: [Name]
[Same format as above]

### VI. Overall Evaluation and Recommendations
[Comprehensive evaluative text, including main strengths, core risks, and directions for improvement]

### VII. Disclaimer
This assessment is based on currently available information; the conclusion is for reference only. [Meta-confidence note]
```

### 5.2 Brief Output Template (for embedding in other analyses)

```markdown
**[Argument Strength Evaluation]**
- Strength grade: 🟢 Strong (3.8/5.0) | Meta-confidence: Medium
- Main strengths: [One-sentence summary]
- Weak links: ⚠️ [Link 1 name] (Moderate risk); ⚠️ [Link 2 name] (Minor flaw)
- Key tip: [Single most important suggestion]
```

---

## VI. Confidence Annotation System

### 6.1 Confidence Labels for Dimensional Scores

Attach a confidence annotation to each dimensional score:

| Annotation | Meaning | Use case |
|----------|------|----------|
| `[Certain]` | Score based on clear legal provisions or solid facts | Clear statute; undisputed facts |
| `[Fairly certain]` | Score based on adequate but not absolute grounds | Supported by mainstream views, with minority dissent |
| `[Uncertain]` | Score based on limited information or substantial controversy | Legal gap; unclear facts; adjudicative divergence |
| `[Speculative]` | Score based on inference rather than direct grounds | No direct information; judgment based on experience or analogy |
| `[Pending verification]` | Score depends on information not yet verified | Further retrieval or confirmation needed |

### 6.2 Template for Overall Assessment Confidence Notes

```
The meta-confidence of this assessment is [High / Medium / Low], as follows:
- Adequacy of information: [Adequate / Basically adequate / Inadequate]——[Reason]
- Domain match: [High / Medium / Low]——[Note on knowledge base in this field]
- Methodological appropriateness: [Appropriate / Basically appropriate / Limited]——[Methodological limits]
- Known blind spots: [List identified assessment blind spots]
```

---

## VII. Common Errors and Safeguards

### 7.1 Fatal Error Table

| No. | Error name | Description | Consequence | Safeguard |
|------|----------|----------|------|----------|
| E01 | **Overconfidence bias** | Systematically overrates argument strength; overlooks weak links | Misleads decision-makers to underestimate risk | Enforce a "devil's advocate" check: construct the strongest rebuttal for each conclusion |
| E02 | **Confirmation bias** | Tends to seek evidence supporting the existing conclusion; ignores contrary evidence | Assessment loses objectivity | Before assessing, expressly list possible contrary arguments |
| E03 | **Anchoring effect** | Scoring influenced by the arguer's confidence or rhetorical style | Scores diverge from actual argument quality | Separate assessment of content from assessment of presentation style |
| E04 | **Missing fatal defects** | Fails to identify fundamental problems sufficient to overturn the argument | Issues a false high rating | Strictly apply pre-validation and the fatal-defect veto rule |
| E05 | **Dimension confusion** | Conflates problems belonging to different dimensions | Disordered assessment structure; cannot locate issues | Assess strictly dimension by dimension; do not skip steps |
| E06 | **Ignoring procedural issues** | Focuses only on substantive-law argument; ignores procedural risk | Misses procedural obstacles that may prevent the argument from succeeding | Add a procedural-compliance check to the assessment |
| E07 | **Static assessment** | Fails to consider dynamic factors such as legal change or policy adjustment | Assessment may quickly become outdated | Annotate the timeliness of the assessment and possible change factors |

### 7.2 Common Traps

| Trap | Manifestation | Response |
|------|------|------|
| **Authority worship** | Awards high scores because the argument cites authoritative scholars | Assess the logic of the argument itself, not the identity of the arguer |
| **Complexity illusion** | The more complex the argument, the more persuasive it seems | Complex arguments are more likely to hide logical gaps; scrutinize more carefully |
| **Quantity bias** | Awards high scores because there are many supporting points | Focus on quality over quantity; one strong point beats ten weak ones |
| **Novelty bias** | Overly lenient or overly harsh toward novel arguments | Apply the same standards to novel and traditional arguments |
| **Outcome orientation** | Awards high scores because the conclusion "seems reasonable" | Strictly assess the reasoning process; do not relax standards due to intuitive reasonableness of the conclusion |
| **Ignoring silence** | Fails to notice what the argument does *not* say | Actively check whether the argument avoids unfavorable issues |
| **Excessive downgrading** | Discovers one problem and rejects the whole argument | Distinguish local from global problems; grade by weak-link type |

---

## VIII. Special Scenario Handling

### 8.1 Legal-Gap Scenarios

```
When the argument involves a legal gap (no direct legal provision):
1. Cap Certainty of legal basis at 3 points
2. Focus on the reasonableness of analogical application
3. Increase weight on legal principles and legislative purpose
4. Expressly annotate "legal gap" risk
5. Recommend monitoring legislative developments and judicial-interpretation trends
```

### 8.2 Novel-Case Scenarios

```
When the argument involves a novel legal issue (no precedent):
1. Mark Consistency with judicial practice as "N/A" or reduce its weight
2. Increase the weight of Reasonableness of value judgments
3. Focus on internal logical consistency of the argument
4. Annotate "novel issue; high uncertainty of adjudicative outcome"
5. Recommend analyzing multiple possible adjudicative directions
```

### 8.3 Competing-Arguments Scenarios

```
When comparing the strength of multiple competing arguments:
1. Assess each argument independently under the same standards
2. Produce a comparison table, dimension by dimension
3. Identify relative strengths and weaknesses of each argument
4. Assess how each argument may perform before different adjudicators
5. State which argument is "most likely to be adopted" and why
```

### 8.4 Incomplete-Evidence Scenarios

```
When facts/evidence on which the argument depends are incomplete:
1. Expressly annotate which fact/evidence information is missing
2. Separately assess argument strength under "best case" and "worst case"
3. Give an interval score for Adequacy of factual basis (e.g., 2–4)
4. Automatically set meta-confidence to "Low"
5. Recommend which information, if supplemented, would allow a more accurate assessment
```

### 8.5 Assessing the Opposing Party's Argument

```
When assessing the strength of the opposing party's argument:
1. Maintain objectivity; do not underrate due to positional bias
2. Focus on the strengths of the other side's argument (not only weaknesses)
3. Assess the likelihood that the court will adopt the other side's argument
4. Identify weak links in the other side's argument that can be attacked
5. Provide a basis for formulating targeted rebuttal strategies for one's own side
```

### 8.6 Time-Pressured Scenarios

```
When rapid assessment is needed (e.g., real-time assessment during hearing):
1. Use the brief output template
2. Prioritize the two core dimensions: Certainty of legal basis and Adequacy of factual basis
3. Quickly scan for fatal defects
4. Give a preliminary strength judgment and the most critical weak link(s)
5. Annotate "Rapid assessment; deeper analysis recommended later"
```

---

## IX. Quality Checklist

Before outputting assessment results, check each item below:

### 9.1 Completeness Check

```
□ Has argument deconstruction been completed?
□ Have all six dimensions been assessed?
□ Have all weak links been identified and annotated?
□ Have a composite score and strength grade been given?
□ Has meta-confidence been annotated?
□ Have improvement suggestions been provided?
```

### 9.2 Accuracy Check

```
□ Have the cited legal norms been verified?
□ Does the factual description accurately reflect the original information?
□ Has the logical analysis been second-checked?
□ Are scores consistent with the explanatory text (no contradictions)?
□ Is the composite score calculation correct?
□ Does the strength grade correspond to the composite score?
```

### 9.3 Objectivity Check

```
□ Has a "devil's advocate" check been performed?
□ Have contrary arguments been considered?
□ Was the assessment improperly influenced by the arguer's identity/position?
□ Is there an outcome-oriented assessment tendency?
□ Are weak-link annotations fair (neither exaggerated nor minimized)?
```

### 9.4 Practicality Check

```
□ Is the assessment result practically helpful to decision-makers?
□ Are weak-link annotations specific enough to support action?
□ Are improvement suggestions actionable?
□ Is the output format clear and readable?
□ Has overly academic language detached from practice been avoided?
```

---

## X. Complete Examples

### Example 1: Simple Scenario — Labor Contract Termination Dispute

#### Argument Under Evaluation

> **Argument content:** The employer's termination of employee Zhang's labor contract for "serious violation of rules and regulations" is lawful and valid. Reasons: (1) The company's *Employee Handbook* expressly provides that "continuous absenteeism of 3 or more days constitutes a serious violation of rules and regulations, and the company may terminate the labor contract"; (2) Zhang was absent from work for 5 consecutive days from March 11 to March 15, 2024, constituting absenteeism; (3) Under Article 39(2) of the Labor Contract Law (《劳动合同法》), where a worker seriously violates the employer's rules and regulations, the employer may terminate the labor contract. Therefore, the company's termination was lawful.

#### Evaluation Report

---

**Argument Strength Evaluation Report**

**I. Argument Summary**
- **Subject of evaluation:** Argument that the employer's termination of a labor contract for serious violation of rules and regulations was lawful
- **Core conclusion:** The termination was lawful and valid
- **Argument type:** Deductive reasoning (syllogism)
- **Legal domain:** Labor dispute

**II. Argument Structure Analysis**

```
Major premise [L]: Labor Contract Law Art. 39(2) — serious violation of rules permits termination
    ↓
Minor premise 1 [L+A]: Employee Handbook provides continuous absenteeism of 3+ days = serious violation
    ↓
Minor premise 2 [F]: Zhang absent 5 consecutive days = absenteeism
    ↓
Conclusion: Termination lawful
```

**III. Dimensional Scores**

| Assessment dimension | Score | Confidence | Brief explanation |
|----------|------|--------|----------|
| Certainty of legal basis | 4.5 | [Certain] | Labor Contract Law Art. 39(2) is clear and uncontroversial |
| Adequacy of factual basis | 3.0 | [Uncertain] | No mention of absenteeism evidence (attendance records, etc.), nor of why Zhang was absent |
| Rigor of logical reasoning | 3.0 | [Fairly certain] | Clear syllogistic structure, but unverified hidden assumptions |
| Resistance to rebuttal | 2.0 | [Fairly certain] | Failed to address multiple foreseeable important defenses |
| Consistency with judicial practice | 3.5 | [Fairly certain] | Many such cases, but courts review relatively strictly |
| Reasonableness of value judgments | 3.5 | [Certain] | Balancing employer management rights and worker protections is a routine issue |

**IV. Composite Assessment**

- **Composite score:** 3.1 / 5.0 (weighted calculation: ordinary-case weights)
- **Strength grade:** 🟡 Medium
- **Meta-confidence:** Medium — assessment based on limited information provided in the argument; some key information missing

**V. Weak-Link Annotations**

**Weak Link 1: Legality of the rules and regulations not argued**
- **Type:** Major weakness ★★★★☆
- **Location:** Minor premise 1 (validity of the *Employee Handbook*)
- **Description:** The argument directly cites the *Employee Handbook* but does not argue whether those rules were formulated through democratic procedures or publicized/notified to workers. Under Article 4 of the Labor Contract Law and Article 50 of the Supreme People's Court's Interpretation (I) on Issues Concerning the Application of Law in the Trial of Labor Dispute Cases (《最高人民法院关于审理劳动争议案件适用法律问题的解释（一）》), rules and regulations may serve as a basis for employment management only if formulated through democratic procedures and publicized.
- **Impact:** If the rules are procedurally unlawful, minor premise 1 fails and the argument chain breaks
- **Repairability:** High — supplement evidence of formulation procedures and publicity
- **Repair suggestion:** Supplement the following evidence: ① records of discussion by the workers' congress or all employees; ② records of consultation with the trade union or employee representatives; ③ evidence of publicity/notification to Zhang (acknowledgment receipts, training records, etc.)

**Weak Link 2: Inadequate factual determination of absenteeism**
- **Type:** Major weakness ★★★★☆
- **Location:** Minor premise 2 (factual finding that Zhang was absent without leave)
- **Description:** The argument merely states that Zhang was "absent from work for 5 consecutive days," without distinguishing "absence from work" from "absenteeism." Absenteeism means unauthorized absence without justified reason. If Zhang was on sick leave, leave without approval, or had other justified reasons, it does not constitute absenteeism. The argument neither addresses why Zhang was absent nor mentions attendance records or similar evidence.
- **Impact:** If Zhang had a justified reason (illness, family emergency, etc.), absenteeism is not established and the conclusion fails
- **Repairability:** Medium — depends on the actual facts
- **Repair suggestion:** ① Supplement attendance-record evidence; ② ascertain why Zhang was absent; ③ if Zhang applied for leave, explain whether leave was approved

**Weak Link 3: Procedural compliance of termination not argued**
- **Type:** Moderate risk ★★★☆☆
- **Location:** Omission in the argument (procedural elements)
- **Description:** The argument focuses only on substantive elements (whether serious violation is established) and does not argue whether termination procedures were compliant. Under Article 43 of the Labor Contract Law, an employer unilaterally terminating a labor contract must notify the trade union of the reasons in advance. Failure to notify the trade union may render the termination unlawful.
- **Impact:** Even if substantive elements are met, procedural illegality may lead to a finding of unlawful termination
- **Repairability:** High — supplement evidence of trade-union notification
- **Repair suggestion:** Supplement written records of trade-union notification and the union's opinion

**Weak Link 4: Foreseeable opposing defenses not anticipated**
- **Type:** Moderate risk ★★★☆☆
- **Location:** Argument as a whole (lack of rebuttal contingency)
- **Description:** The argument failed to anticipate and respond to possible defenses such as: ① Zhang may claim a justified reason; ② Zhang may claim never to have received the rules; ③ Zhang may claim selective enforcement (other employees absented without being terminated); ④ Zhang may claim no opportunity to be heard was given
- **Impact:** In an adversarial setting, the argument lacks defensive depth
- **Repairability:** Medium — responses must be prepared case by case
- **Repair suggestion:** Prepare a response plan for each possible defense

**VI. Overall Evaluation and Recommendations**

The basic logical framework (syllogism) is correct, and the choice of legal basis is accurate. But the argument has "more skeleton than flesh": it builds only a basic reasoning frame without adequately proving key premises—especially the legality of the rules and the determination of absenteeism, both major weaknesses. In judicial practice, courts review employer terminations for serious violation of rules relatively strictly, typically examining legality of the rules, adequacy of fact-finding, and procedural compliance of termination.

**Improvement priority:**
1. 🔴 Highest: Supplement evidence of democratic procedures and publicity/notification of the rules
2. 🔴 Highest: Ascertain and prove that Zhang's absence was unauthorized absenteeism without justified reason
3. 🟠 Next: Supplement procedural-compliance argument for termination (trade-union notification)
4. 🟡 Recommended: Anticipate and respond to possible opposing defenses

**VII. Disclaimer**

Meta-confidence for this assessment is "Medium." The assessment is based on information provided in the argument; complete case materials were not obtained. A more accurate assessment can be made if materials such as rule-formulation procedure documents, attendance records, termination notices, and trade-union notification records are supplemented.

---

### Example 2: Complex Scenario — Right to Inspect Accounting Books in a Shareholder Information-Rights Dispute

#### Argument Under Evaluation

> **Argument content:** Plaintiff Li (holding 10% equity in defendant Company A) is entitled to inspect Company A's accounting books. The argument is as follows:
>
> (1) **Legal basis:** Under Article 57 of the Company Law (2023 revision) (《公司法》第57条), shareholders have the right to inspect and copy the company's accounting books. Li holds 10% of Company A, has shareholder status, and enjoys information rights.
>
> (2) **Proper purpose:** Li's purpose in inspecting the accounting books is to understand the company's business condition and profit distribution, because the company has not distributed dividends for 5 consecutive years, and Li suspects the controlling shareholder of related-party transactions harming the company's interests. This constitutes a proper purpose.
>
> (3) **Pre-action procedure fulfilled:** On January 15, 2024, Li submitted a written inspection request to Company A stating the purpose; Company A refused in writing on January 20, 2024, citing "trade secrets."
>
> (4) **Company's refusal ground fails:** Company A refused on "trade secrets" grounds but did not prove specific risk that Li's inspection would leak trade secrets. In judicial practice, a company may not refuse shareholder inspection solely on a blanket "trade secrets" assertion.
>
> (5) **Scope of inspection:** Li requests to inspect all of Company A's accounting books from 2019 through 2023, including original vouchers.
>
> In sum, the court should uphold Li's request to inspect Company A's accounting books.

#### Evaluation Report

---

**Argument Strength Evaluation Report**

**I. Argument Summary**
- **Subject of evaluation:** Argument that shareholder Li has the right to inspect the company's accounting books (including original vouchers)
- **Core conclusion:** The court should uphold Li's request to inspect all of Company A's accounting books for 2019–2023 (including original vouchers)
- **Argument type:** Combined reasoning (mainly deductive, supplemented by factual and rebuttal arguments)
- **Legal domain:** Corporate governance / shareholder information rights

**II. Argument Structure Analysis**

```
Main argument line:
  Premise 1 [L]: Company Law Art. 57 grants shareholders the right to inspect accounting books
  Premise 2 [F]: Li is a 10% shareholder of Company A
  Premise 3 [F+L]: Li has a proper purpose (5 years without dividends + suspected related-party transactions)
  Premise 4 [F]: Li completed the written-request pre-action procedure
      ↓
  Intermediate conclusion: Li has the right to inspect accounting books and has satisfied the conditions for exercise

Rebuttal argument line:
  Premise 5 [F+L]: Company A's refusal ground is "trade secrets"
  Premise 6 [L]: A blanket trade-secrets defense is insufficient to refuse
      ↓
  Intermediate conclusion: Company A's refusal ground fails

Scope argument line [A]:
  Premise 7 [hidden assumption]: Scope of inspection includes original vouchers
  Premise 8 [hidden assumption]: A 5-year inspection span is reasonable
      ↓
  Ultimate conclusion: Court should uphold Li's request to inspect all 2019–2023 accounting books (including original vouchers)
```

**III. Dimensional Scores**

| Assessment dimension | Score | Confidence | Brief explanation |
|----------|------|--------|----------|
| Certainty of legal basis | 4.0 | [Fairly certain] | Company Law Art. 57 is clear, but whether "accounting books" includes original vouchers is contested |
| Adequacy of factual basis | 4.0 | [Fairly certain] | Shareholder status, written request, and company refusal are clear; adequacy of evidence for "proper purpose" needs assessment |
| Rigor of logical reasoning | 3.5 | [Fairly certain] | Main argument line is clear, but the scope line relies on inadequately argued hidden assumptions |
| Resistance to rebuttal | 3.5 | [Fairly certain] | Effectively answered the trade-secrets defense, but did not anticipate other possible defenses |
| Consistency with judicial practice | 3.5 | [Uncertain] | Courts generally support shareholder information rights, but inspection of original vouchers shows adjudicative divergence |
| Reasonableness of value judgments | 4.0 | [Certain] | Protecting minority shareholders' information rights aligns with Company Law purposes and judicial policy |

**IV. Composite Assessment**

- **Composite score:** 3.7 / 5.0
- **Strength grade:** 🟢 Strong
- **Meta-confidence:** Medium — judicial practice after the 2023 Company Law revision is still forming; parts of the assessment draw on pre-revision adjudicative experience

**V. Weak-Link Annotations**

**Weak Link 1: Contested legal basis for inspecting original vouchers**
- **Type:** Moderate risk ★★★☆☆
- **Location:** Scope argument line — Premise 7 (scope includes original vouchers)
- **Description:** Article 57 of the 2023-revised Company Law provides that shareholders may "inspect and copy" the company's accounting books, but whether the extension of "accounting books" includes original vouchers (bookkeeping vouchers, original documents, etc.) is contested in theory and practice. Article 10 of the pre-revision Company Law Judicial Interpretation (IV) limited inspection to "accounting books"; some courts held that original vouchers are not accounting books. After the 2023 revision, Article 57(2) of the new Company Law added the phrase "accounting vouchers" (会计凭证), but concrete application awaits clarification in judicial practice. The argument directly includes original vouchers in the inspection scope without adequately arguing this controversy.
- **Impact:** The court may uphold inspection of accounting books but not original vouchers, leading to partial dismissal of the claim
- **Repairability:** High
- **Repair suggestion:** ① Expressly cite Article 57(2) of the new Company Law on "accounting vouchers"; ② cite judgments supporting inspection of original vouchers; ③ argue that without original vouchers, information rights are hollow (books alone cannot verify authenticity); ④ if needed, tier the claims: primary claim including original vouchers; alternative claim limited to accounting books

**Weak Link 2: Insufficient argument for reasonableness of the inspection time span**
- **Type:** Minor flaw ★★☆☆☆
- **Location:** Scope argument line — Premise 8 (5-year inspection span)
- **Description:** The argument seeks 5 years of accounting books (2019–2023) without arguing why that span is reasonable. Although the law does not expressly limit the temporal scope of inspection, some courts examine whether the scope matches the purpose asserted by the shareholder. If the proper purpose is to understand recent business condition and profit distribution, whether a 5-year span is necessary needs explanation.
- **Impact:** The court may narrow the temporal scope of inspection
- **Repairability:** High
- **Repair suggestion:** Supplement argument that: ① the company paid no dividends for 5 consecutive years, so those 5 years' books are needed to understand profits; ② suspected related-party transactions may span multiple years, requiring a complete period of data to detect them

**Weak Link 3: Evidentiary support for proper purpose**
- **Type:** Moderate risk ★★★☆☆
- **Location:** Main argument line — Premise 3 (proper purpose)
- **Description:** The argument asserts that Li's proper purpose includes "suspecting related-party transactions by the controlling shareholder harming the company," but this is only a "suspicion," without explaining whether it has preliminary evidentiary support. In judicial practice, although shareholders need not prove that related-party transactions actually exist, they should provide a preliminary basis for reasonable suspicion. If suspicion of related-party transactions rests solely on "5 consecutive years without dividends," the argument may be weak.
- **Impact:** If the court finds the proper-purpose argument inadequate, it may dismiss the inspection request
- **Repairability:** Medium — depends on whether preliminary evidence exists
- **Repair suggestion:** ① Supplement preliminary leads for suspected related-party transactions (e.g., related-party information in public sources, reports from other shareholders); ② emphasize that "5 consecutive years without dividends" itself forms a basis for reasonable suspicion; ③ cite cases applying a lenient review standard to "proper purpose"

**Weak Link 4: Other defenses not anticipated**
- **Type:** Moderate risk ★★★☆☆
- **Location:** Rebuttal argument line (incomplete)
- **Description:** The argument answered only the "trade secrets" defense; Company A may raise others: ① Li competes in the same industry with the company (improper purpose); ② Li previously leaked company information to third parties; ③ Li's true purpose is to gather evidence for litigation (courts differ on this); ④ Li's shareholder status is disputed (e.g., nominee shareholding).
- **Impact:** If the other side raises such defenses with evidentiary support, the argument may face challenge
- **Repairability:** Medium — prepare responses based on actual circumstances
- **Repair suggestion:** ① Verify whether Li has same-industry competition; if so, specially argue the point; ② prepare a plan for Li to sign a confidentiality undertaking; ③ confirm that Li's shareholder status is undisputed

**Weak Link 5: Temporal-effect issue under the new Company Law**
- **Type:** Latent hazard ★☆☆☆☆
- **Location:** Premise 1 (legal basis)
- **Description:** The argument cites Article 57 of the 2023-revised Company Law, which took effect on July 1, 2024. If the inspection request arose before the new law's effective date (the argument mentions a January 2024 application), transitional issues between old and new law may arise. However, information rights are continuing rights, and the new law strengthens shareholder information-rights protection, so applying the new law favors the plaintiff.
- **Impact:** Limited, but the other side may raise procedural objections on this basis
- **Repairability:** High
- **Repair suggestion:** ① Confirm whether the new Company Law was already in effect when the case was heard; ② if needed, cite both old and new Company Law provisions; ③ argue the continuing nature of information rights

**VI. Overall Evaluation and Recommendations**

Overall quality of the argument is relatively good, with these strengths: (1) accurate choice of legal basis—Company Law Art. 57 is the direct provision; (2) complete structure covering rights basis, proper purpose, pre-action procedure, and rebuttal; (3) forceful response to the company's "trade secrets" defense.

Main risks concentrate on inspection scope (especially original vouchers) and evidentiary support for proper purpose. Recommendations:

**Improvement priority:**
1. 🟠 Priority: Strengthen the legal argument for inspecting original vouchers, fully using Art. 57(2) of the new Company Law
2. 🟠 Priority: Supplement preliminary evidentiary support for proper purpose
3. 🟡 Recommended: Anticipate and prepare responses to same-industry competition and other possible defenses
4. 🟡 Recommended: Argue the reasonableness of the inspection time span
5. ⚪ Optional: Address old/new law transitional issues

**Litigation strategy suggestion:** Consider tiering the claims—primary claim including original vouchers; alternative claim limited to accounting books and accounting vouchers—to ensure at least partial success.

**VII. Disclaimer**

Meta-confidence for this assessment is "Medium." After the 2023 Company Law revision, judicial practice on shareholder information rights is still forming; parts of the assessment draw on pre-revision adjudicative experience and scholarly analysis. Recommend monitoring subsequent supporting judicial interpretations from the Supreme People's Court and typical cases after the new law took effect. Complete case evidence was not obtained; assessment of Adequacy of factual basis may adjust based on actual evidence.

---

## Appendix: Quick Reference Card

```
┌─────────────────────────────────────────────┐
│     Argument Strength Evaluation · Quick Ref │
├─────────────────────────────────────────────┤
│ Six dimensions: Legal basis | Factual basis  │
│                 Logical rigor | Rebuttal     │
│                 Judicial practice | Values   │
├─────────────────────────────────────────────┤
│ Five grades: Very Strong(4.5+) | Strong(3.5+)│
│              Medium(2.5+) | Weak(1.5+)       │
│              Very Weak(1.0+)                 │
├─────────────────────────────────────────────┤
│ Veto rules:                                  │
│ · Legal basis or factual basis = 1 → ≤ Weak  │
│ · Two dimensions ≤ 2 → ≤ Medium              │
│ · Criminal + facts ≤ 3 → auto drop 1 grade   │
├─────────────────────────────────────────────┤
│ Must-check:                                  │
│ ✓ Is the statute currently in effect?        │
│ ✓ Is there a fatal rebuttal?                 │
│ ✓ Do hidden assumptions hold?                │
│ ✓ Are procedural elements satisfied?         │
│ ✓ Is meta-confidence annotated?              │
└─────────────────────────────────────────────┘
```
