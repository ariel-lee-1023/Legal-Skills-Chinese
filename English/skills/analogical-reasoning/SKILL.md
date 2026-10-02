---
name: analogical-reasoning
description: |
  Trigger this skill when the AI agent must handle any of the following situations:
  1. The current case/issue has no direct, clear rule in positive law (a legal gap / lacuna);
  2. Existing precedents, similar cases, or closely related legal norms must be used to derive a solution for the present issue;
  3. The user expressly asks to "refer to," "apply by analogy," or "analogically apply" (参照 / 比照 / 类推适用) a particular norm or case;
  4. Legal argumentation must rest on the principle that "like cases should be treated alike" (相似案件相似处理);
  5. Similarity and difference between two or more cases/norms must be assessed to decide whether analogy is warranted;
  6. In contexts such as contract interpretation, determination of tort liability, or discretionary administrative penalties, experience from similar situations must be used to build the argument.
  The core of this skill is: identify the basis of similarity (tertium comparationis), justify the analogy, and on that basis reach a reasoned legal conclusion.
---

> **Chinese source (authoritative):** [`../../skills/analogical-reasoning/SKILL.md`](../../skills/analogical-reasoning/SKILL.md)

# Analogical Reasoning (类比推理)

> **Like Cases Should Be Treated Alike · 相似案件相似处理**

## I. Overview Table

| Item | Content |
|------|------|
| **Capability name** | Analogical Reasoning |
| **Core principle** | Like cases should be treated alike (same case, same judgment / 同案同判) |
| **Latin formulations** | Argumentum a simili / Analogia legis / Analogia iuris |
| **Preconditions for use** | A legal gap exists or the norm is unclear, and there is substantive similarity between the matter to be decided and the reference object |
| **Prohibited domains** | Areas that strictly forbid analogy, e.g. criminal conviction and sentencing (principle of legality / 罪刑法定), and tax-charging elements (principle of tax legality / 税收法定) |
| **Output goal** | An analogy-based conclusion with supporting argumentation, including similarity analysis, difference assessment, and justification |
| **Risk level** | High (analogical reasoning is essentially creative legal application; conclusions are contestable) |

## II. Legal Disclaimer

> ⚠️ **Important Disclaimer**
>
> 1. Analogical reasoning is a methodological tool of law. Its conclusions are not equivalent to a direct statutory rule and carry contestability and uncertainty.
> 2. Outputs of this skill are for legal analysis reference only and do not constitute formal legal advice. Final legal judgments should be made by qualified legal professionals.
> 3. The status and use of analogical reasoning differ across legal systems (civil law / common law). Users should heed the special requirements of the applicable system.
> 4. In fields that strictly apply the principle of legal reservation (法律保留)—especially criminal law and tax law—analogical reasoning is strictly limited or even prohibited (particularly analogy unfavorable to the party). The AI agent must identify and observe these limits.
> 5. The AI agent should always mark the confidence level of analogical conclusions and alert the user to the limits of the argumentation.

## III. Core Concepts

### 3.1 Definition of Analogical Reasoning

Analogical Reasoning (类比推理) is a method of legal application whereby, when the case to be decided lacks a directly applicable legal norm, one seeks an existing norm or case that is similar in **essential features**, and **analogically applies** (类推适用) that norm’s or case’s legal consequence to the case at hand.

### 3.2 Logical Structure of Analogical Reasoning

```
Premise 1: Case A has feature set {F1, F2, F3, F4} and legal consequence R applies
Premise 2: Case B has feature set {F1, F2, F3, F5}
Premise 3: Features {F1, F2, F3} are the essential features that give rise to legal consequence R (basis of similarity)
Premise 4: The difference between F4 and F5 is insufficient to affect application of legal consequence R (difference assessment)
────────────────────────────────────────────────
Conclusion: Case B should receive legal consequence R by analogical application
```

### 3.3 Key Terminology

| Term | Meaning | Notes |
|------|------|------|
| **Target Case (待决案件)** | The case presently to be resolved that lacks a direct legal rule | Starting point of analogical reasoning |
| **Source Case / Norm (参照案件/规范)** | A case or norm with a clear legal rule or judgment already in place | Foundation of analogical reasoning |
| **Basis of Similarity (Tertium Comparationis / 相似性基础)** | Essential features shared by the two cases that are relevant to legal evaluation | Core of analogy—must be similarity that is “legally significant” |
| **Legal Gap / Lacuna (法律漏洞)** | A state in which the law fails to regulate a matter that ought to be regulated | Precondition for analogical reasoning |
| **Statutory Analogy (Analogia Legis / 法律类推)** | Analogically applying a specific statutory provision to an unregulated similar situation | Individual / particular analogy |
| **Legal Analogy (Analogia Iuris / 法律类推)** | Extracting a general legal principle from multiple norms and applying it to an unregulated situation | Holistic / principle-based analogy |
| **Argumentum e Contrario (反面推理)** | Where the law regulates only specified situations, unregulated situations should be treated in the opposite way | The opposite method to analogy; requires judging whether the legislature intended exclusion |
| **Ratio Legis (规范目的)** | The purpose and values pursued by a legal norm | Key criterion for judging similarity |

### 3.4 Distinguishing Analogical Reasoning from Related Concepts

| Method | Relation to Analogical Reasoning | Key Distinction |
|------|------------------|----------|
| **Extensive Interpretation (扩张解释)** | Easily confused | Extensive interpretation remains within the possible semantic range of the text; analogical reasoning goes beyond that range |
| **Argumentum e Contrario (反面推理)** | Opposite method | Contrario treats the statutory enumeration as exhaustive; analogy treats it as incomplete |
| **Purposive Restriction (目的性限缩)** | Complementary method | Purposive restriction narrows a norm’s scope of application; analogy expands it |
| **Precedent Application (common law)** | Functionally similar | Precedent application rests on stare decisis; analogical reasoning rests on consistency of normative purpose |
| **A fortiori (举重以明轻 / 举轻以明重)** | Special type | A form of “obvious interpretation” (当然解释)—a strengthened form of analogy with especially clear similarity argumentation |

### 3.5 Justificatory Foundations of Analogical Reasoning

The legitimacy of analogical reasoning derives from the following legal values:

1. **Equality principle**: Like situations should be treated alike—a concrete expression of equality before the law
2. **Systemic coherence**: The legal order should be internally coherent; like matters should not receive contradictory legal evaluations
3. **Realization of normative purpose**: If the legislative purpose covers the target case, analogical application is a necessary means of achieving that purpose
4. **Legal certainty and predictability**: Filling gaps by analogy is more predictable than pure judicial discretion

## IV. Complete Workflow

### Stage One: Preliminary Check—Confirm Preconditions for Analogy

```
Step 1.1 → Confirm existence of a legal gap
  ├─ Search current laws and regulations; confirm whether the issue has a direct rule
  ├─ Distinguish a “genuine legal gap” from “intentional legislative silence”
  │   ├─ Genuine legal gap: the legislature did not foresee the situation; it ought to have regulated but did not
  │   └─ Intentional silence: the legislature deliberately chose not to regulate (analogy should not be used)
  └─ Record the basis for the gap determination (legislative materials, systemic interpretation, etc.)

Step 1.2 → Check prohibited zones for analogy
  ├─ Criminal law: analogy unfavorable to the defendant is strictly forbidden (nullum crimen / 罪刑法定)
  │   └─ Note: analogy favorable to the defendant is theoretically acceptable
  ├─ Tax law: tax-charging elements may not be applied by analogy (税收法定)
  ├─ Administrative penalties: types and ranges of penalties may not be applied by analogy
  ├─ Other legal-reservation fields: norms restricting citizens’ fundamental rights may not be applied by analogy
  └─ If in a prohibited zone → terminate analogical reasoning and clearly inform the user

Step 1.3 → Confirm whether other legal methods have priority
  ├─ Can textual, systemic, or purposive interpretation resolve the issue?
  ├─ Is there a directly applicable general clause (e.g., good faith / 诚实信用)?
  └─ If a priority method exists → use it first; use analogy as supplementary argumentation
```

### Stage Two: Find the Reference Object—Identify Comparable Norms or Cases

```
Step 2.1 → Define the search scope
  ├─ Related norms within the same area of law (priority)
  ├─ Related norms in adjacent areas of law
  ├─ Judicial interpretations and Guiding Cases (指导性案例)
  ├─ SPC Gazette cases and typical cases
  └─ Prevailing scholarly views (通说)

Step 2.2 → Preliminary screening of candidate reference objects
  ├─ List all potentially relevant provisions or cases
  ├─ Conduct a preliminary similarity assessment for each candidate
  └─ Retain higher-similarity candidates (recommend keeping 2–5)

Step 2.3 → Select the best reference object
  ├─ Compare each candidate’s degree of similarity to the target case
  ├─ Prefer:
  │   ├─ Norms within the same legal field (systemic proximity)
  │   ├─ Norms whose purpose is closest
  │   └─ Analogical solutions already supported by judicial practice
  └─ Record the reasons for selection
```

### Stage Three: Similarity Analysis—Establish the Basis for Analogy

```
Step 3.1 → Extract key features of the target case
  ├─ Factual features: subjects, objects, conduct, results, causation, etc.
  ├─ Legal features: nature of the legal relationship, rights and duties, interest structure, etc.
  └─ Value features: legal values implicated, type of interest conflict, etc.

Step 3.2 → Extract key features of the reference object
  ├─ Extract features along the same dimensions
  └─ Pay special attention to: constitutive elements and legal consequences of the reference norm

Step 3.3 → Build a similarity comparison table
  ┌──────────────┬──────────────┬──────────────┬──────────┐
  │  Dimension   │ Target Case  │ Source Object│ Similar/ │
  │              │              │              │ Different│
  ├──────────────┼──────────────┼──────────────┼──────────┤
  │  Dimension 1 │   ...        │   ...        │ Similar/ │
  │              │              │              │ Different│
  │  Dimension 2 │   ...        │   ...        │ Similar/ │
  │              │              │              │ Different│
  │  ...         │   ...        │   ...        │ ...      │
  └──────────────┴──────────────┴──────────────┴──────────┘

Step 3.4 → Identify the basis of similarity (Tertium Comparationis)
  ├─ From shared features, select those that are “legally significant”
  ├─ Criterion: whether the similarity relates to the reference norm’s purpose (ratio legis)
  ├─ Core question: Do the reasons why the reference norm attaches that legal consequence also apply to the target case?
  └─ State the basis of similarity expressly
```

### Stage Four: Difference Assessment—Test the Reliability of the Analogy

```
Step 4.1 → Identify all points of difference
  ├─ Differences at the factual level
  ├─ Differences at the level of legal relationships
  └─ Differences at the level of interest structure

Step 4.2 → Assess the legal significance of each difference
  ├─ For each difference: is it enough to defeat the analogy?
  ├─ Criteria:
  │   ├─ Does the difference affect realization of the reference norm’s purpose?
  │   ├─ Does the difference cause a substantive change in the interest structure?
  │   └─ Is the difference a factor the legislature intentionally treated differently?
  └─ Rate each difference: “negligible / noteworthy / sufficient to defeat”

Step 4.3 → Overall judgment
  ├─ If all differences are “negligible” → analogy holds; high confidence
  ├─ If “noteworthy” differences exist → analogy may hold; additional argumentation required
  ├─ If a “sufficient to defeat” difference exists → analogy fails; seek other solutions
  └─ Record reasons for the overall judgment
```

### Stage Five: Justification—Build a Complete Analogical Argument

```
Step 5.1 → Construct a ratio legis argument
  ├─ Articulate the reference norm’s purpose (ratio legis)
  ├─ Argue that this purpose also covers the target case
  └─ Explain that refusing analogy would yield a result contrary to that purpose

Step 5.2 → Construct an equality-principle argument
  ├─ Argue that the target and source cases occupy the same position in legal evaluation
  ├─ Explain that refusing analogy would produce unreasonable differential treatment
  └─ Cite constitutional/statutory bases for equality

Step 5.3 → Construct a systemic-coherence argument
  ├─ Show that the analogical conclusion aligns with the legal system’s overall value orientation
  ├─ Check whether the conclusion conflicts with other legal norms
  └─ If conflicts exist, provide a reconciling argument

Step 5.4 → Respond to possible objections
  ├─ Anticipate the possibility of argumentum e contrario
  ├─ Argue why analogy is preferable to contrario
  ├─ Address doubts raised by differences
  └─ State the limits and uncertainty of the analogy
```

### Stage Six: Form the Conclusion and Output

```
Step 6.1 → Form the analogical conclusion
  ├─ State clearly: which legal consequence should be analogically applied to the target case
  ├─ Explain the mode of application (full analogy / modified analogy)
  └─ Mark the confidence level

Step 6.2 → Draft the full analogical reasoning report
  ├─ Organize content according to the output template
  ├─ Ensure a complete argumentative chain and clear logic
  └─ Attach necessary risk warnings and alternatives

Step 6.3 → Quality check
  ├─ Verify item by item against the quality checklist
  └─ Confirm there are no fatal errors
```

## V. Common Domains and Sources of Law

### 5.1 Civil and Commercial Law (the most active domain for analogy)

| Typical Scenario | Reference Norm / Case | Basis of Analogy |
|----------|---------------|----------|
| Proprietary protection of virtual property | Civil Code (民法典) Property Rights Book rules on movables | Similarity of exclusive controlling interests |
| Protection of data interests | Civil Code rules on IP / property rights | Similarity of intangible property interests |
| Characterization of novel contracts (e.g., livestream e-commerce contracts) | Civil Code nominate contract provisions | Similarity of contractual purpose and rights–duties structure |
| Validity of electronic signatures | Civil Code rules on written form | Similarity of the function of fixing a manifestation of intent |
| Property division upon ending cohabitation | Civil Code Marriage and Family Book rules on divorce property division | Similarity of property commingling during shared life |
| Handling corporate deadlock | Company Law (公司法) dissolution rules + partnership withdrawal rules | Similarity of governance failure within an organization |

### 5.2 Administrative Law

| Typical Scenario | Reference Norm / Case | Basis of Analogy | Caveats |
|----------|---------------|----------|----------|
| Procedural requirements for novel administrative acts | Procedural rules for existing types of administrative acts | Similarity of impact on the relative party’s rights and interests | Must not analogically aggravate penalties |
| Regulation of new business models | Regulatory norms for traditional models | Similarity of business substance and risk profile | Heed the proportionality principle |

### 5.3 Procedural Law

| Typical Scenario | Reference Norm / Case | Basis of Analogy |
|----------|---------------|----------|
| Admitting electronic evidence | Rules for traditional documentary / audio-visual evidence | Similarity of evidentiary function (proving facts) |
| Jurisdiction over novel disputes | Jurisdictional rules for existing dispute types | Similarity of dispute nature and connecting factors |

### 5.4 Criminal Law (strictly limited)

| Scenario | Analogy Allowed? | Explanation |
|------|-------------|------|
| Conviction analogy unfavorable to the defendant | ❌ Strictly prohibited | Core requirement of nullum crimen sine lege (罪刑法定) |
| Sentencing analogy unfavorable to the defendant | ❌ Strictly prohibited | Same as above |
| Analogy favorable to the defendant (e.g., analogy for grounds excluding unlawfulness) | ⚠️ Theoretically allowed; cautious in practice | Contested in scholarship; requires special justification |
| Extensive interpretation in criminal law (not analogy) | ✅ Allowed within the semantic range | Carefully distinguish the boundary between extensive interpretation and analogy |

### 5.5 International / Comparative Law

| Scenario | Explanation |
|------|------|
| Referring to similar rules of other jurisdictions | May serve as auxiliary argumentation, not as a direct basis |
| Analogical application of treaties | Must follow special rules of treaty interpretation |
| Comparative-law analogy | May be used to argue the reasonableness of a legal solution |

## VI. Verification and Screening Rules

### 6.1 Necessary Conditions for a Valid Analogy (all must be satisfied)

| No. | Condition | Verification Method |
|------|------|----------|
| V1 | A genuine legal gap exists | Exhaustive legal search; confirm no direct rule; exclude “intentional silence” |
| V2 | Not in a prohibited field for analogy | Check whether criminal conviction/sentencing, tax-charging elements, etc. are involved |
| V3 | A usable reference norm or case exists | Find at least one reference object with substantive similarity |
| V4 | Basis of similarity is established | Shared features relate to the reference norm’s purpose |
| V5 | Differences are insufficient to defeat the analogy | Differences do not prevent realization of the normative purpose |
| V6 | Analogical conclusion does not violate higher law | Conclusion does not conflict with mandatory constitutional or statutory provisions |
| V7 | Analogical conclusion does not violate basic legal principles | Conclusion does not violate public order and good morals, good faith, etc. |

### 6.2 Screening Criteria for Similarity Assessment

```
Layer 1 screening: Surface similarity
  → Are the target case and reference object in the same legal field?
  → Do they involve the same or closely related type of legal relationship?
  → Pass → proceed to Layer 2; Fail → stronger argumentation required

Layer 2 screening: Structural similarity
  → Are the rights–duties structures similar?
  → Is the type of interest conflict the same?
  → Pass → proceed to Layer 3; Fail → analogy may fail

Layer 3 screening: Purposive similarity (core)
  → Does the reference norm’s purpose cover the target case?
  → Would refusing analogy yield a result contrary to that purpose?
  → Pass → basis for analogy established; Fail → analogy fails
```

### 6.3 Reverse Check: When Analogy Should Be Refused

- The target case’s special feature is precisely a factor the legislature intentionally treated differently
- The reference norm is an exception (exceptions may not be extended—Singularia non sunt extendenda)
- The analogical conclusion would produce an unacceptable imbalance of interests
- A superior legal method can resolve the issue
- Analogy would break the basic framework of the legal system

## VII. Output Format Templates

### 7.1 Standard Output Template

```markdown
## Analogical Reasoning Analysis Report

### I. Problem Overview
- **Issue to be decided**: [Brief description of the target case/issue]
- **Legal gap**: [Explain why current law cannot apply directly]
- **Analytical goal**: [State the specific question this analogy addresses]

### II. Preliminary Check
- **Legal gap confirmed**: [✅ Confirmed / ❌ Not confirmed]
  - Search scope: [List laws and regulations searched]
  - Gap type: [Genuine gap / Intentional silence]
- **Prohibited-zone check**: [✅ Not in prohibited zone / ❌ In prohibited zone—terminate analysis]
- **Priority-method check**: [✅ No priority method / ⚠️ Priority method exists—explain]

### III. Reference Object
- **Reference norm/case**: [Specific provision or case citation]
- **Reference content**: [Quote the original text]
- **Selection rationale**: [Explain why this reference was chosen]

### IV. Similarity Analysis

| Comparison Dimension | Target Case | Reference Object | Evaluation |
|----------|----------|----------|------|
| [Dimension 1] | [Description] | [Description] | Similar / Different |
| [Dimension 2] | [Description] | [Description] | Similar / Different |
| ... | ... | ... | ... |

- **Basis of Similarity (Tertium Comparationis)**: [Express statement]

### V. Difference Assessment

| Difference | Content | Legal Significance | Rating |
|--------|----------|------------|------|
| [Diff. 1] | [Description] | [Analysis] | Negligible / Noteworthy / Sufficient to defeat |
| [Diff. 2] | [Description] | [Analysis] | Negligible / Noteworthy / Sufficient to defeat |

### VI. Justification
1. **Ratio legis argument**: [Discussion]
2. **Equality-principle argument**: [Discussion]
3. **Systemic-coherence argument**: [Discussion]
4. **Response to objections**: [Discussion]

### VII. Conclusion
- **Analogical conclusion**: [Clear statement]
- **Confidence**: [★☆☆☆☆ to ★★★★★]
- **Confidence explanation**: [Reasons for the rating]
- **Risk warnings**: [Main risks and uncertainties]
- **Alternatives**: [If any, other possible legal solutions]
```

### 7.2 Brief Output Template (for quick analysis)

```markdown
## Brief Analogical Reasoning Analysis

**Issue to be decided**: [Description]
**Reference object**: [Norm/case]
**Basis of similarity**: [Core similar points]
**Key differences**: [Main differences and assessment]
**Conclusion**: [Apply by analogy / Do not apply] | Confidence: [Level]
**Rationale**: [One-paragraph overview]
```

## VIII. Confidence Labeling System

### 8.1 Five-Level Confidence Scale

| Level | Marker | Meaning | Typical Situations |
|------|------|------|----------|
| **Very High** | ★★★★★ | Analogical conclusion almost certainly holds | Judicial interpretation expressly supports the analogy; SPC Guiding Case adopts the same analogy; scholarly consensus agrees |
| **High** | ★★★★☆ | Analogical conclusion is highly likely | Basis of similarity clear and sufficient; differences all negligible; majority of scholars support; local court precedents support |
| **Medium** | ★★★☆☆ | Some basis exists but the conclusion is contested | Basis of similarity holds but “noteworthy” differences remain; scholarly disagreement; no clear precedent yet |
| **Low** | ★★☆☆☆ | Substantial uncertainty | Weak basis of similarity; important differences; contrario is also plausible; major scholarly controversy |
| **Very Low** | ★☆☆☆☆ | Conclusion is only one possibility | Similarity barely holds; differences are significant; better alternatives may exist; for reference of approach only |

### 8.2 Factors Affecting Confidence

**Factors that raise confidence:**
- The reference norm’s purpose clearly covers the target case
- Judicial practice has already adopted the same or a similar analogy
- Prevailing scholarly opinion supports the analogy
- Differences do not affect realization of the normative purpose
- Refusing analogy would produce a clearly unjust result
- The analogical conclusion aligns with the legal system’s overall value orientation

**Factors that lower confidence:**
- Basis of similarity is unclear or contested
- Important differences are hard to exclude
- Argumentum e contrario is equally persuasive
- The reference norm is an exception
- Major scholarly disagreement exists
- The analogical conclusion may trigger unforeseeable cascading effects
- The legal field involved is conservative toward analogy

## IX. Common Errors and Prevention

### 9.1 Fatal Error Table

| No. | Error Type | Description | Consequence | Prevention |
|------|----------|----------|------|----------|
| E1 | **Criminal conviction by analogy** | In criminal law, analogizing to treat conduct not defined as a crime as criminal, to the defendant’s detriment | Grave violation of nullum crimen; conclusion wholly invalid | Strict screening at the preliminary check; for criminal issues, immediately check whether conviction/sentencing is implicated |
| E2 | **Skipping gap confirmation** | Proceeding to analogy without confirming a gap when a directly applicable rule exists | Analogy is unnecessary; conclusion may conflict with the direct rule | Exhaustive legal search; cross-check multiple legal databases |
| E3 | **Surface similarity in place of substantive similarity** | Analogizing merely because cases look similar on the surface, without analyzing legally significant similarity | Analogy lacks justificatory foundation; conclusion unreliable | Strictly apply the three-layer screening; always ask about similarity at the ratio legis level |
| E4 | **Ignoring key differences** | Failing to identify or deliberately overlooking important differences between target and source | Analogical conclusion may be entirely wrong | Systematically list all differences; assess legal significance of each |
| E5 | **Analogy from exceptions** | Extending an exception (special rule) to other situations | Violates the methodological principle that exceptions may not be extended | Determine whether the reference is a general rule or an exception; exceptions are limited to their expressly regulated situations |
| E6 | **Circular argument** | Using the analogical conclusion itself to prove the existence of similarity | Argumentative logic is invalid | Ensure the similarity argument is independent of the analogical conclusion |

### 9.2 Common Traps

| No. | Trap | Description | Response Strategy |
|------|------|------|----------|
| T1 | **Confirmation bias** | Reaching a conclusion first, then seeking supporting evidence while ignoring contrary evidence | Conduct both forward analogy and reverse verification; actively seek reasons against analogy |
| T2 | **Over-analogy** | Indefinitely expanding the scope of analogy until normative certainty is lost | Strictly limit the scope of analogy; clearly define the boundary of the conclusion |
| T3 | **Confusing extensive interpretation with analogy** | Packaging substantive analogy as extensive interpretation to evade limits on analogy | Clearly demarcate the possible semantic range; beyond that range it is analogy |
| T4 | **Ignoring interest balancing** | Focusing only on formal similarity and ignoring the analogy’s real impact on parties’ interests | Conduct interest balancing in the justification stage |
| T5 | **Biased selection of reference** | Choosing the reference that best fits a preconceived conclusion rather than the most similar one | List all candidates, rank by similarity, prefer the most similar |
| T6 | **Ignoring social change** | Directly analogizing from norms/cases from a different social context that may no longer fit | Consider how changed social background affects similarity judgments |
| T7 | **Single reference object** | Relying on only one reference; weak argumentative base | Seek multiple references where possible, forming an “analogy cluster” to strengthen persuasiveness |

## X. Special Scenario Handling

### 10.1 Competing Multiple Analogies

**Scenario**: The target case can be analogized to multiple different norms/cases, but different analogies yield different legal consequences.

**Handling**:
1. Complete a full analysis for each analogy separately
2. Compare the strength of similarity of each scheme (which basis of similarity is stronger)
3. Compare how well each scheme fits the normative purpose
4. Balance interests and assess which legal consequence is more reasonable
5. Choose the optimal scheme, but also report the alternatives and their reasons
6. If superiority cannot be clearly distinguished, report candidly and mark lower confidence

### 10.2 Competition Between Argumentum e Contrario and Analogy

**Scenario**: For the same legal gap, one may either apply by analogy or exclude application by contrario, yielding opposite conclusions.

**Handling**:
1. Analyze legislative intent: Is the enumeration illustrative or exhaustive?
   - Illustrative → lean toward analogy
   - Exhaustive → lean toward contrario
2. Analyze normative purpose: Would refusing analogy frustrate the purpose?
3. Analyze systemic position: Is the norm a general rule or an exception?
   - General rule → lean toward analogy
   - Exception → lean toward contrario
4. If still uncertain, present both schemes and mark the controversy

### 10.3 Cross-Field Analogy

**Scenario**: No suitable reference exists within the target case’s field of law; one must look across fields.

**Handling**:
1. First confirm that no usable reference exists within the field
2. Choose the field whose legal-relationship nature is closest to the target case
3. Pay special attention to differences in basic principles across fields (e.g., public vs. private law)
4. Cross-field analogy requires stronger argumentation; lower confidence accordingly
5. Clearly state the special nature and limits of cross-field analogy

### 10.4 Analogy from Legal Principles (Analogia Iuris)

**Scenario**: No single concrete norm can serve as reference; a general principle must be extracted from multiple norms.

**Handling**:
1. Collect multiple related norms and analyze their shared purpose
2. Extract a general principle (e.g., good faith, fairness, protection of reliance)
3. Argue that the principle applies to the target case
4. Note: principle-based analogy is more uncertain than analogy from a concrete norm; lower confidence accordingly
5. Prefer principles already recognized in judicial practice

### 10.5 Analogy Driven by New Technology / New Business Models

**Scenario**: Legal issues arising from AI, blockchain, gene editing, etc., that positive law did not foresee at all.

**Handling**:
1. Deeply understand the essential features and operating mechanisms of the new technology/model
2. Seek functionally equivalent traditional legal relationships (functional equivalence)
3. Pay special attention to new risks and interest structures the technology may create
4. Analogy may require “modified analogy”—apply the reference norm but adjust for the technology’s special features
5. Clearly mark limits of technical understanding and high uncertainty of the conclusion
6. Advise monitoring legislative developments; analogical conclusions may change with new legislation

### 10.6 Analogical Application of Guiding Cases

**Scenario**: Analogy by reference to Guiding Cases (指导性案例) issued by the Supreme People’s Court.

**Handling**:
1. Accurately identify the Guiding Case’s adjudication points (裁判要点), not the entire case narrative
2. Compare similarity between the target case and the Guiding Case on key facts implicated by the adjudication points
3. Note the Guiding Case’s “shall refer to” (应当参照) effect—similar cases should refer to it
4. If important differences exist, argue why reference should not be made (distinguishing technique)
5. Cite in standard form: Guiding Case number + adjudication points

## XI. Quality Checklist

### 11.1 Completeness Check

| No. | Check Item | Status |
|------|--------|------|
| Q1 | Has the existence of a legal gap been confirmed? | □ |
| Q2 | Have prohibited fields for analogy been excluded? | □ |
| Q3 | Have priority legal methods been checked? | □ |
| Q4 | Has the reference object and selection rationale been stated? | □ |
| Q5 | Has a complete similarity comparison table been built? | □ |
| Q6 | Has the basis of similarity (tertium comparationis) been expressly stated? | □ |
| Q7 | Have all differences been systematically identified and assessed? | □ |
| Q8 | Has a ratio legis argument been made? | □ |
| Q9 | Has an equality-principle argument been made? | □ |
| Q10 | Have possible objections been addressed? | □ |
| Q11 | Has confidence been marked and explained? | □ |
| Q12 | Have risk warnings been provided? | □ |

### 11.2 Logic Check

| No. | Check Item | Status |
|------|--------|------|
| L1 | Is the argumentative chain complete, without leaps? | □ |
| L2 | Is there circular argumentation? | □ |
| L3 | Does the basis of similarity relate to normative purpose (not mere surface similarity)? | □ |
| L4 | Is difference assessment objective (no selective disregard of unfavorable differences)? | □ |
| L5 | Does the conclusion reasonably follow from the premises? | □ |
| L6 | Have both analogy and contrario been considered? | □ |

### 11.3 Compliance Check

| No. | Check Item | Status |
|------|--------|------|
| C1 | Does the analogical conclusion violate mandatory constitutional or statutory provisions? | □ |
| C2 | Does the analogical conclusion violate public order and good morals? | □ |
| C3 | Has analogy unfavorable to the defendant been used in criminal law? | □ |
| C4 | Has an exception been improperly extended by analogy? | □ |
| C5 | Have necessary legal disclaimers and risk warnings been added? | □ |

## XII. Complete Examples

### Example 1: Simple Scenario—Inheritance of Virtual Property

#### Background

During his lifetime, Zhang owned substantial virtual equipment and game currency in an online game, worth about RMB 50,000. After Zhang’s death, his son Xiao Zhang sought to inherit this virtual property. The game company refused on the ground that “virtual property is not part of the estate.” The Inheritance Book of the current Civil Code does not expressly regulate inheritance of virtual property.

---

## Analogical Reasoning Analysis Report

### I. Problem Overview
- **Issue to be decided**: Can online virtual property (game equipment, game currency) be inherited as part of the estate?
- **Legal gap**: Civil Code Art. 1122 provides that “an estate is the lawful personal property left by a natural person upon death,” but does not expressly list virtual property; Art. 127 provides that “where the law has provisions on the protection of data and online virtual property, those provisions shall apply,” yet no specific protective rules yet exist.
- **Analytical goal**: Argue whether virtual property can be brought within inheritance rules by analogical application.

### II. Preliminary Check
- **Legal gap confirmed**: ✅ Confirmed
  - Search scope: Civil Code Inheritance, Property Rights, and Contracts Books; Cybersecurity Law; related judicial interpretations
  - Gap type: Genuine gap. Art. 127 shows the legislature recognized the need to protect virtual property but has not yet enacted concrete rules—a “planned gap,” not “intentional silence”
- **Prohibited-zone check**: ✅ Not in a prohibited zone (civil field; no criminal conviction or tax-charging elements)
- **Priority-method check**: ✅ No priority method. Art. 1122’s “lawful personal property” could be extensively interpreted, but the special features of virtual property (platform dependence; possible user-agreement limits) make pure extensive interpretation insufficient; analogy is needed as supplementary argumentation.

### III. Reference Object
- **Reference norms**: Civil Code Art. 1122 (scope of estate) + Art. 240 (powers of ownership) + Art. 127 (declaratory provision on virtual property protection)
- **Reference content**:
  - Art. 1122: “An estate is the lawful personal property left by a natural person upon death. Property that may not be inherited under law or by its nature shall not be inherited.”
  - Art. 240: “An owner has the rights to possess, use, benefit from, and dispose of the owner’s immovable or movable property in accordance with law.”
- **Selection rationale**: The core of inheritance is protecting a natural person’s disposition of lawful property interests. If virtual property has the essential features of “property,” it should fall within the estate.

### IV. Similarity Analysis

| Comparison Dimension | Virtual Property (Target) | Traditional Property (Reference) | Evaluation |
|----------|------------------|------------------|------|
| Economic value | Quantifiable economic value (≈ RMB 50,000) | Has economic value | **Similar** |
| Lawful acquisition | Obtained through lawful gameplay and transactions | Obtained through lawful means | **Similar** |
| Exclusive control | Account holder exclusively controls and uses | Owner exclusively possesses and uses | **Similar** |
| Transferability | Transferable via in-game trade or account transfer | Transferable by sale, gift, etc. | **Similar** |
| Form of existence | Electronic data, dependent on network platforms | Tangible things or rights certificates | **Different** |
| Duration | May be limited by platform operating life | Generally no such duration limit | **Different** |

- **Basis of Similarity (Tertium Comparationis)**: Virtual and traditional property share the essential feature of “lawfully acquired interests of economic value subject to exclusive control.” The purpose of inheritance is to protect continuity of disposition of a natural person’s lawful property interests—a purpose that equally applies to virtual property.

### V. Difference Assessment

| Difference | Content | Legal Significance | Rating |
|--------|----------|------------|------|
| Form of existence | Virtual property exists as electronic data, without physical form | Modern property law already recognizes intangibles (IP, claims); form does not defeat property characterization | **Negligible** |
| Platform dependence | Virtual property depends on the game platform’s operation | Similar to bank deposits depending on banks; does not defeat property characterization, but may affect how inheritance is implemented | **Noteworthy** |
| User-agreement limits | User agreements may restrict account transfer | Standard terms cannot exclude statutory inheritance rights, but clause validity must be reviewed case by case | **Noteworthy** |

### VI. Justification

1. **Ratio legis argument**: The purpose of inheritance is to protect a natural person’s freedom to dispose of lawful property and ensure that property interests pass according to the decedent’s will or statutory rules after death. If valuable lawful virtual property cannot be inherited, that interest would disappear upon the right-holder’s death—contrary to the purpose of inheritance.

2. **Equality-principle argument**: A person with RMB 50,000 in virtual property and a person with RMB 50,000 in tangible property occupy the same legal position on inheritance. Denying inheritance merely because of the form of existence would be unreasonable differential treatment.

3. **Systemic-coherence argument**: Civil Code Art. 127 already declares a protective stance toward virtual property; although concrete rules are lacking, including virtual property in the estate aligns with that legislative spirit. Art. 1122’s open formulation “lawful personal property,” rather than an exhaustive list, also leaves room for analogy.

4. **Response to objections**:
   - Objection 1: “Virtual property is essentially a service-contract relationship, not a property right”—Response: Even if characterized as a contractual claim, claims are likewise inheritable property.
   - Objection 2: “The user agreement prohibits transfer”—Response: The validity of standard terms excluding statutory inheritance rights is doubtful and may be void for violating fairness.

### VII. Conclusion
- **Analogical conclusion**: Online virtual property (game equipment, game currency) has the essential features of property and should be analogically brought under Civil Code Art. 1122 within the estate and may be inherited. Concrete implementation (account transfer, transfer of virtual items, etc.) must be determined in light of platform rules and technical conditions.
- **Confidence**: ★★★★☆ (High)
- **Confidence explanation**: Art. 127 shows the legislature’s positive attitude toward protecting virtual property; scholarly consensus supports its property character; some local courts have upheld inheritance of virtual property. There is not yet an SPC-level clear rule or Guiding Case, and platform dependence and user-agreement issues may affect enforcement.
- **Risk warnings**: (1) Courts may characterize the legal nature of virtual property differently; (2) restrictive user-agreement clauses may become focal points of dispute; (3) virtual property involving personal privacy (e.g., social accounts) may require special treatment.
- **Alternatives**: The issue can also be resolved by extensively interpreting “lawful personal property” in Art. 1122; analogy can serve as supplementary argumentation for that extensive interpretation.

---

### Example 2: Complex Scenario—Copyright Protection of AI-Generated Content

#### Background

Company A used a self-developed AI painting system to generate a series of digital artworks and used them in commercial advertising. Company B copied those artworks without permission for its own product packaging. Company A sued Company B for copyright infringement. Company B argued that AI-generated content is not a “work” under copyright law because there is no human “authorship” / creation.

The current Copyright Law does not expressly define the legal status of AI-generated content.

---

## Analogical Reasoning Analysis Report

### I. Problem Overview
- **Issue to be decided**: Can AI-generated digital artworks receive copyright protection? If so, to whom does copyright belong?
- **Legal gap**: Copyright Law Art. 3 requires a “work” to be an “intellectual achievement” with “originality,” but does not clarify whether these elements require direct human creation; Art. 11 provides that “the natural person who creates a work is the author,” without addressing AI participation.
- **Analytical goal**: Through analogical reasoning, argue whether AI-generated content can receive copyright protection by analogy, and how ownership should be allocated.

### II. Preliminary Check
- **Legal gap confirmed**: ✅ Confirmed
  - Search scope: Copyright Law and its Implementing Regulations; 2020 Copyright Law amendment; related judicial interpretations; Beijing Internet Court “AI text-to-image” case (2023)
  - Gap type: Genuine gap. Legislation did not foresee AI-generated content—a technology-driven lacuna. Note: the Beijing Internet Court has related precedent (“first AI text-to-image case”); its reasoning is an important reference.
- **Prohibited-zone check**: ✅ Not in a prohibited zone (civil IP field)
- **Priority-method check**: ⚠️ A priority method may exist
  - One may purposively interpret “intellectual achievement” and “originality” to ask whether AI-generated content meets those elements
  - Given substantial controversy, analogy remains useful as supplementary argumentation

### III. Reference Objects

This case needs multiple references forming an “analogy cluster”:

**Reference A: Juridical-person works regime**
- Copyright Law Art. 11(3): “Where a work is organized by a juridical person or unincorporated organization, represents its will, and is created under its responsibility, that juridical person or unincorporated organization shall be deemed the author.”
- Selection rationale: A juridical person cannot itself “create,” yet the law deems it the author—recognizing “organized creation.”

**Reference B: Employment works regime**
- Copyright Law Art. 18: Works created by a natural person to fulfill the work tasks of a juridical person or unincorporated organization.
- Selection rationale: Reflects the ownership logic of “creation completed using others/tools.”

**Reference C: Commissioned works regime**
- Copyright Law Art. 19: For commissioned works, ownership of copyright is determined by agreement between commissioner and commissionaire.
- Selection rationale: Reflects the rights position of the “funder / initiator” in creative activity.

**Reference D: Copyright in photographic works**
- In photography, the camera automatically performs much technical work (focus, exposure, etc.), yet copyright belongs to the photographer.
- Selection rationale: Reflects the ownership logic of “humans creating through tools,” structurally similar to AI-assisted creation.

### IV. Similarity Analysis

**4.1 Analogy to the juridical-person works regime**

| Comparison Dimension | AI-Generated Content (Target) | Juridical-Person Work (Reference) | Evaluation |
|----------|-------------------|------------------|------|
| Creative subject | AI system (not a natural person) | Juridical person (not a natural person) | **Similar**—neither is direct natural-person creation |
| Organizer’s role | Company A developed the AI, set parameters, selected outputs | Juridical person organizes creation representing its will | **Similar**—organizer directs creative direction |
| Assumption of responsibility | Company A bears responsibility for AI outputs | Juridical person bears responsibility for juridical-person works | **Similar** |
| Human participation in creation | Humans set prompts, choose parameters, screen outputs | Human employees create under juridical-person direction | **Different**—human participation in AI generation may be lower |

**4.2 Analogy to photographic works**

| Comparison Dimension | AI-Generated Content (Target) | Photographic Work (Reference) | Evaluation |
|----------|-------------------|------------------|------|
| Degree of tool automation | AI highly automates image generation | Camera automatically handles focus, exposure, etc. | **Similar**—both involve automated tool processing |
| Human creative contribution | Choose subject, set prompts, adjust parameters, screen outputs | Choose subject, composition, timing, post-processing | **Similar**—both embody aesthetic choice and creative judgment |
| Unpredictability of output | AI outputs have some randomness | Photographic results also affected by light, environment, etc. | **Similar** |
| Degree to which the tool determines output | AI has a higher determining role over final output | Camera’s determining role is relatively lower | **Different**—degree difference is significant |

**Basis of Similarity (Tertium Comparationis)**:
- **Core similarity**: Across all references, what the law protects is not the “physical process of creation,” but “human intellectual contribution and creative choices embodied in the creative activity.” In AI generation, humans contribute creatively by choosing tools, setting prompts and parameters, and screening/editing outputs.
- **Consistency of normative purpose**: Copyright law aims to incentivize creation and promote cultural flourishing. If AI-assisted creative results were unprotected, people’s incentive to create with AI tools would be chilled—contrary to copyright’s purpose.

### V. Difference Assessment

| Difference | Content | Legal Significance | Rating |
|--------|----------|------------|------|
| Degree of human participation | Direct human participation in AI generation may be lower than in traditional creation | Core controversy. If humans input only simple prompts and AI does all creation, “creative contribution” may fall short of originality | **Noteworthy**—requires case-by-case judgment of human participation |
| Controllability of the process | AI outputs are highly random; creator control over final output is limited | May affect originality findings, but photography and improvisation also involve similar uncontrollability | **Noteworthy** |
| Legal status of the creative subject | AI is not a legal subject and cannot be an “author” | Fundamental difference, but solvable by analogy to juridical-person works—treating the AI user/developer as author | **Noteworthy**—needs an institutional solution |
| Possibility of mass generation | AI can generate large volumes in a short time | May flood copyright protection and upset the existing balance | **Noteworthy**—protection scope may need limits |
| Training-data copyright issues | AI training may use copyrighted works | An independent legal issue; does not directly decide copyrightability of outputs, but may affect exercise of rights | **Negligible** (for this analogical analysis) |

### VI. Justification

1. **Ratio legis argument**:
   The fundamental purpose of copyright law is “to encourage the creation and dissemination of works beneficial to socialist spiritual and material civilization” (Copyright Law Art. 1). AI-assisted creation is a product of technological progress. If its results were wholly unprotected, adverse effects would follow: (a) chilling incentives to create with AI tools; (b) casting AI outputs into the “public domain,” allowing free copying and denying return on the original creator’s (AI user’s) investment; (c) harming healthy development of the AI-creation industry. Therefore, where humans make a substantive creative contribution to the AI process, copyright protection aligns with copyright’s purpose.

2. **Equality-principle argument**:
   Creating with AI tools and creating with traditional digital tools such as Photoshop are both essentially “humans creating with tools.” Denying copyrightability merely because of the tool’s intelligence level would be unreasonable differential treatment. The key is whether humans made a substantive creative contribution—not the tool’s technical level.

3. **Systemic-coherence argument**:
   The juridical-person works regime already shows that copyright law does not require the “author” to be the natural person who physically completes the creative acts. Law may, for policy reasons, vest copyright in the subject that organizes creative activity. Vesting copyright in AI-generated content in the AI user/developer is consistent with that logic.

4. **Response to objections**:
   - **Objection 1**: “Copyright law requires ‘human creation’; AI is not human”—Response: Analogize photography: a camera is not human, yet the photographer obtains copyright through creative choices. The key is not who/what performed the physical operation, but who made the creative decisions.
   - **Objection 2**: “AI-generated content lacks originality”—Response: Originality should be judged by whether the final result embodies the creator’s individualized choices, not by the nature of the tool. If carefully designed prompts, parameter tuning, and output screening make the final result embody distinctive aesthetic judgment, originality can be satisfied.
   - **Objection 3**: “Protecting AI-generated content will flood copyright”—Response: This concern has some force, but can be addressed by raising the originality threshold (e.g., requiring “substantive creative contribution”), not by categorically denying copyrightability of all AI-generated content.

### VII. Conclusion

- **Analogical conclusion**:
  1. **Copyrightability**: Where humans make a substantive creative contribution to AI generation (including but not limited to carefully designing prompts, adjusting parameters, selecting and editing outputs), AI-generated digital artworks may by analogy receive copyright protection and constitute “works” under copyright law.
  2. **Ownership**: By analogy to juridical-person works and tool-based creation, copyright should vest in the natural or juridical person who made a substantive creative contribution to the AI process (here, Company A).
  3. **Infringement**: If Company A’s AI-generated artworks constitute “works,” Company B’s unauthorized copying constitutes copyright infringement.
  4. **Limiting condition**: If humans input only extremely simple prompts (e.g., “draw a flower”) with almost no creative contribution, the output may fail originality and not constitute a “work.”

- **Confidence**: ★★★☆☆ (Medium)

- **Confidence explanation**:
  - Raising factors: Beijing Internet Court “first AI text-to-image case” (2023) held that AI-generated images can constitute works where humans invest sufficient intellect—supporting this analogy in practice; more scholars increasingly support conditional protection of AI-generated content.
  - Lowering factors: The issue remains highly contested globally; jurisdictions diverge sharply (e.g., the U.S. Copyright Office currently tends not to protect purely AI-generated content); the SPC has not yet issued guiding opinions; the “substantive creative contribution” standard remains unclear, leaving wide case-by-case discretion.

- **Risk warnings**:
  1. Law in this field develops rapidly; analogical conclusions may change with new legislation or judicial interpretations
  2. Standards for “substantive creative contribution” are not yet uniform; courts may differ
  3. Training-data copyright issues may indirectly affect exercise of rights in AI outputs
  4. International legal conflicts may affect cross-border protection

- **Alternatives**:
  1. **Anti-Unfair Competition Law protection**: Even if AI outputs are not “works,” Company A may still obtain protection under the Anti-Unfair Competition Law (Company B’s copying may constitute unfair competition)
  2. **Contractual protection**: Protect AI outputs through user agreements, licenses, and other contractual arrangements
  3. **Neighboring-rights protection**: By analogy to producers of sound recordings/video recordings, grant neighboring rights to producers of AI-generated content (requires legislative support)

---

## Appendix: Analogical Reasoning Methodology Quick Reference

```
┌─────────────────────────────────────────────────────┐
│     Analogical Reasoning Decision Tree (Quick Ref.) │
├─────────────────────────────────────────────────────┤
│                                                       │
│  1. Does a legal gap exist?                           │
│     ├─ No  → Apply law directly; no analogy needed    │
│     └─ Yes → Continue                                 │
│                                                       │
│  2. Is it a prohibited field for analogy?             │
│     ├─ Yes → Terminate analogical reasoning           │
│     └─ No  → Continue                                 │
│                                                       │
│  3. Can a suitable reference object be found?         │
│     ├─ No  → Consider principle analogy (analogia     │
│     │         iuris)                                  │
│     └─ Yes → Continue                                 │
│                                                       │
│  4. Is the basis of similarity established?           │
│     ├─ No  → Analogy fails                            │
│     └─ Yes → Continue                                 │
│                                                       │
│  5. Are differences sufficient to defeat the analogy? │
│     ├─ Yes → Analogy fails                            │
│     └─ No  → Continue                                 │
│                                                       │
│  6. Is the justification adequate?                    │
│     ├─ No  → Supplement argument or lower confidence  │
│     └─ Yes → Analogy holds; form the conclusion       │
│                                                       │
└─────────────────────────────────────────────────────┘
```

---

> **Final reminder**: Analogical reasoning is among the most creative—and most contested—methods in legal methodology. When applying this skill, the AI agent should remain humble and cautious, fully mark uncertainty, and avoid presenting analogical conclusions as definitive legal answers. The value of analogy lies not only in its conclusion but in its argumentation—a well-argued but uncertain analogy is far preferable to a crude but dogmatic analysis.
