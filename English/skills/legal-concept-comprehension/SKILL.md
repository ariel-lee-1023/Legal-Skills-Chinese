---
name: legal-concept-comprehension
description: |
  Trigger this skill when the user asks to explain, distinguish, unpack, or understand a legal concept.
  Typical trigger scenarios include, but are not limited to:
  - The user directly asks "what is XX" or "how should XX be understood"
  - The user asks to compare similarities and differences between two legal concepts (e.g., "the difference between unjust enrichment and negotiorum gestio")
  - The user presents specific facts and asks whether they constitute a legal concept (e.g., "A mistakenly transferred money to B; does this constitute unjust enrichment?")
  - The user encounters unfamiliar terminology in legal analysis, drafting, or contract review
  - The user asks to unpack the constitutive elements of a concept or analyze its legal effects
  This skill is a foundational unit of legal analysis, providing the conceptual basis for applying legal rules, analyzing cases, and drafting legal documents.
---

> **Chinese source (authoritative):** [`../../skills/legal-concept-comprehension/SKILL.md`](../../skills/legal-concept-comprehension/SKILL.md)

# Legal Concept Comprehension

## Overview Table

| Item | Content |
|------|------|
| **Capability ID** | 8 |
| **Capability Name** | Legal Concept Comprehension |
| **Capability Type** | Cognitive analysis |
| **Core Function** | Precisely understand the intension, extension, constitutive elements, and legal effects of legal concepts, and distinguish meaning differences across contexts |
| **Input** | Legal concept name; jurisdiction / branch-of-law limits; comparison objects; concrete fact scenarios; specified analytical structure |
| **Output** | Structured concept analysis (basic meaning, systemic position, constitutive elements, boundary distinctions, legal effects, applicable situations) |
| **Related Capabilities** | Legal rule application (apply rules on the basis of concept comprehension); statutory retrieval (supplement legal authorities); legal reasoning (use the concept in argumentation) |
| **Applicable Level** | Foundational capability—provides the conceptual basis for all legal-language tasks |

## Legal Disclaimer

> **Important notices:**
> 1. Concept analysis provided by this skill is a doctrinal understanding framework and does not constitute legal advice on any specific case.
> 2. Legal concepts are open-ended and evolving; the same concept may be understood differently across jurisdictions, periods, and schools of thought. Analytical conclusions must be tied to the concrete application context.
> 3. For highly contested legal concepts (e.g., "public order and good morals" (*gongxu liangsu*), "good faith" (*chengshi xinyong*), "material misunderstanding" (*zhongda wujie*)), element unpacking alone cannot exhaust their practical meaning; judgment must still combine case facts, adjudicative rules, and scholarly views.
> 4. Concept analysis in foreign-law or comparative-law contexts is for reference only and cannot replace professional advice from a locally licensed lawyer.

## I. Core Concepts

### 1.1 Three Semantic Layers of Legal Concepts

A legal concept is not an ordinary word in natural language; it is a "converter" that moves from everyday language into the legal world. Understanding a legal concept requires penetrating three semantic layers:

```
Everyday meaning (ordinary meaning in daily language)
    ↓  Legalization / conversion
Legal meaning (normative meaning in legal rules, judicial interpretations, and case law)
    ↓  Doctrinal deepening
Doctrinal meaning (refined definitions in legal theory and scholarly debate)
```

| Semantic Layer | Source | Function | Example: "possession" (*zhanyou*) |
|----------|------|------|-------------|
| Everyday meaning | Daily language | Preliminary understanding | Holding something in one's hand |
| Legal meaning | Civil Code, Property Rights Book | Normative definition | Factual control over a thing (Art. 458) |
| Doctrinal meaning | Treatises, scholarship | Fine-grained analysis | Direct / indirect possession; autonomous / heteronomous possession; rightful / wrongful possession |

**Core principle:** Many legal terms originate in everyday language but have acquired specialized meanings in law; everyday experience should not be substituted directly for normative understanding.

### 1.2 The Tension Structure of Legal Concepts

Legal concepts have "tension"—a clear core meaning and interpretable border zones:

```
        Border zone (contestable)
      ┌─────────────────┐
      │                 │
      │    Core meaning │
      │  (certain)      │
      │                 │
      └─────────────────┘
        Border zone (contestable)
```

- **Core meaning:** The most typical situations in which the concept applies; uncontroversial
- **Border zone:** Facts partially match the concept's elements; interpretive room remains, and scholarly dispute may arise

### 1.3 Constitutive-Element Theory

The core of understanding a legal concept is "unpacking constitutive elements"—converting an abstract concept into testable factual components:

```
Legal concept
├── Constitutive element A
│   └── Fact components A1, A2, A3...
├── Constitutive element B
│   └── Fact components B1, B2...
├── Constitutive element C
│   └── ...
└── Legal effects (legal consequences that arise once all elements are satisfied)
```

**Dual functions of constitutive elements:**
- **Comprehension function:** Provide a thinking framework for understanding the legal concept
- **Judgment function:** Provide criteria for testing whether particular facts fall within the concept

## II. Complete Workflow

### Phase One: Identification and Positioning

#### Step 1: Identify the Target Concept

Clarify the legal concept to be explained and collect the following background information:
- **Concept name:** Confirm the precise term (note synonyms and near-synonyms)
- **Applicable jurisdiction:** Chinese law, foreign law (common law / civil law), international law
- **Branch of law:** Civil law, criminal law, administrative law, commercial law, economic law, procedural law, etc.
- **Application scenario:** Theoretical research, case analysis, contract review, document drafting

**Judgment tips:**
- If the user does not specify a jurisdiction, default to analysis under the current Chinese legal system
- If the user does not specify a branch of law, make a preliminary judgment from the concept name, then confirm with the user or search multiple possible fields in parallel
- Distinguish different meanings of the same term across branches of law (e.g., "possession" differs in civil and criminal law)

#### Step 2: Everyday Textual Interpretation

Explain the concept's ordinary meaning in general language from the everyday-semantic angle:
- How the word is used in daily communication
- What an ordinary person associates with the word
- Whether there is a significant gap between everyday and legal meaning

**Purpose:** Establish a starting point for understanding, while flagging that "the legal meaning here may differ from everyday understanding."

#### Step 3: Legal Textual Interpretation

Explain the concept from the perspective of legal normative usage:
- **Statutory location:** In which provisions the concept is expressly defined
- **Judicial interpretations:** Whether the Supreme People's Court / Supreme People's Procuratorate has issued related interpretations
- **Case references:** How courts understand and apply the concept in leading cases
- **Doctrinal views:** How mainstream treatises define it

**Output format:**
```markdown
**Legal textual meaning:** [legal definition of the concept]
**Core statutes:** [statute name + article number]
**Judicial interpretations:** [if any]
**Difference from everyday meaning:** [if a significant difference exists, state it expressly]
```

#### Step 4: Systemic Positioning

Clarify the concept's place in the legal system:
- **Legal hierarchy:** Statutes, administrative regulations, departmental rules, judicial interpretations
- **Branch-of-law location:** e.g., civil law → Property Rights Book → ownership → possession
- **Normative function:** What role the concept plays in the normative system (constitutive element / legal effect / ground for exemption / procedural condition)

**Significance of systemic positioning:** The same concept may have different interpretive breadth and depth at different systemic positions.

### Phase Two: In-Depth Analysis

#### Step 5: Unpack Constitutive Elements

Break the legal concept into testable constitutive elements:

1. List, item by item, the constitutive elements summarized in legal norms or doctrine
2. For each element, explain it in language that can map onto life facts
3. Mark the logical relationship among elements (concurrent / sequential / alternative)
4. Identify vague elements where standards of characterization are disputed

**Output format:**
```markdown
**Constitutive elements (X items, [concurrent / sequential / alternative] relationship):**

| No. | Element Name | Element Content | Points of Dispute |
|------|----------|----------|--------|
| 1 | [Element A] | [Specific content] | [If disputed, state the focus of dispute] |
| 2 | [Element B] | [Specific content] | [If disputed, state the focus of dispute] |
| ... | ... | ... | ... |
```

#### Step 6: Boundary Distinctions from Neighboring Concepts

Distinguish the concept from similar concepts and clarify boundaries:

| Comparison Dimension | Target Concept | Neighboring Concept A | Neighboring Concept B |
|----------|----------|----------|----------|
| **Core function** | ... | ... | ... |
| **Differences in constitutive elements** | ... | ... | ... |
| **Typical application scenarios** | ... | ... | ... |
| **Differences in legal effects** | ... | ... | ... |

**Common situations requiring distinction:**
- Neighboring concepts within the same branch of law (e.g., unjust enrichment vs. negotiorum gestio; liquidated damages vs. damages)
- Same-named concepts across branches of law (e.g., possession—civil vs. criminal law)
- Same-named concepts across jurisdictions (e.g., reliance interest—German law vs. Chinese law)

#### Step 7: Legal-Effect Analysis

Clarify the legal consequences that arise once the legal concept is constituted:

- **Direct effects:** Immediate changes in legal status once the concept is established
- **Creation of claims / duties:** Whether a claim, defense, or duty arises
- **Composite effects:** Whether the concept is a component of a more complex legal structure
- **Procedural effects:** Impact on limitation periods, burden of proof, jurisdiction, and other procedural matters

**Output format:**
```markdown
**Legal effects:**
- Direct effects: [...]
- Claims / duties: [...]
- Procedural impact: [...]
- Possible composite concepts: [e.g., claim for restitution of unjust enrichment → claim in personam → limitation periods apply]
```

### Phase Three: Output and Application

#### Step 8: Integrated Output

According to the user's needs, output concept analysis in a structured form:

```markdown
## Concept Analysis: [Concept Name]

### I. Basic Meaning
**Everyday meaning:** [...]
**Legal meaning:** [...]
**Doctrinal meaning:** [...]

### II. Systemic Positioning
- **Core statutes:** [...]
- **Systemic affiliation:** [...]
- **Normative purpose:** [what problem the concept is designed to solve]

### III. Constitutive Elements
[Element table]

### IV. Boundary Distinctions
[Comparison table with neighboring concepts]

### V. Legal Effects
[Effect analysis]

### VI. Typical Application Situations
[List contexts in which the concept frequently appears in legal practice]

### VII. Common Controversies and Scholarship
[If major scholarly disputes exist, briefly state the different views]
```

#### Step 9: Bridge to Follow-On Tasks

After concept analysis is complete, use the clarified concept as a basic unit for subsequent tasks based on the user's further needs:
- **Legal rule application:** Embed the concept in a syllogistic rule structure
- **Case analysis:** Map facts onto concept elements
- **Concept comparison:** Conduct systemic comparison with additional concepts
- **Document drafting:** Use the concept accurately in legal writing

## III. Input Types and Handling Strategies

| Input Type | Example | Handling Strategy |
|----------|------|----------|
| **Concept alone** | "Understand unjust enrichment" | Execute the full 8-step workflow |
| **Concept + jurisdiction** | "Understand unjust enrichment under Chinese law" | Limit to the Chinese legal system; exclude foreign-law interference |
| **Concept + branch of law** | "Understand possession in civil law" | Limit to the civil-law context; note differences from criminal-law possession |
| **Concept + comparison object** | "Compare unjust enrichment and negotiorum gestio" | Focus on Step 6 boundary distinction; expand to multi-concept comparison |
| **Concept + fact scenario** | "A mistakenly transferred money to B; does this constitute unjust enrichment?" | After full concept analysis, perform element-mapping analysis |
| **Concept + specified structure** | "Explain the constitutive elements of unjust enrichment" | Focus on Step 5; simplify other steps |
| **Concept + legal consequences** | "Explain the legal consequences of unjust enrichment" | Focus on Step 7; briefly sketch concept background, then analyze effects in depth |

## IV. Output Format Templates

### Template A: Full Concept Analysis (Default Output)

```markdown
## Concept Analysis: [Concept Name]

### I. Basic Meaning
| Semantic Layer | Meaning |
|----------|------|
| Everyday meaning | ... |
| Legal meaning | ... |
| Doctrinal meaning | ... |

### II. Systemic Positioning
- **Core statutes:** [XXX Law], Art. X
- **Normative purpose:** [what problem it solves]

### III. Constitutive Elements ([relationship])
1. **[Element A]:** ...
2. **[Element B]:** ...
3. ...

### IV. Boundaries with Neighboring Concepts
| Dimension | [Target Concept] | [Neighboring Concept] |
|------|-----------|-----------|
| Core differences | ... | ... |
| Typical scenarios | ... | ... |

### V. Legal Effects
[Specific effect analysis]

### VI. Typical Application Situations
- [Situation 1]
- [Situation 2]
```

### Template B: Element-Mapping Analysis (for Fact-Scenario Input)

```markdown
## Concept Application Analysis: [Concept Name] × [Fact Scenario]

### I. Concept Recap
[Briefly restate the concept's constitutive elements]

### II. Fact Extraction
[Extract fact components relevant to the elements from the user's description]

### III. Element Mapping
| Element | Corresponding Facts | Satisfied? | Notes |
|------|----------|----------|------|
| [Element A] | [Fact X] | ✅/❓/❌ | ... |
| [Element B] | [Fact Y] | ... | ... |

### IV. Conclusion
- **Preliminary judgment:** [constituted / not constituted / more facts needed]
- **Key uncertainties:** [if any]
- **Supplementary information needed:** [if more information is required to decide]
```

### Template C: Multi-Concept Comparison (for Comparison Requests)

```markdown
## Concept Comparison: [Concept A] vs [Concept B]

### I. Common Ground
[Outline shared points in function or system]

### II. Core Differences
| Comparison Dimension | [Concept A] | [Concept B] |
|----------|---------|---------|
| Normative purpose | ... | ... |
| Constitutive elements | ... | ... |
| Legal effects | ... | ... |
| Typical scenarios | ... | ... |

### III. Application Choice Guide
[Under what circumstances to apply A, and under what circumstances to apply B]
```

## V. Examples

### Example 1: Standalone Concept Analysis—Unjust Enrichment (*budang deli*)

**Input:** "Explain the concept of unjust enrichment"

**Output:**

```markdown
## Concept Analysis: Unjust Enrichment (*budang deli*)

### I. Basic Meaning
| Semantic Layer | Meaning |
|----------|------|
| Everyday meaning | Obtaining a benefit that does not belong to oneself without a proper reason |
| Legal meaning | A legal fact whereby one party obtains a benefit without a legal cause, causing the other party to suffer a loss, and thereby giving rise to a duty of restitution (Civil Code Art. 985) |
| Doctrinal meaning | As one of the grounds for creating obligations, it is a statutory obligation with the function of correcting property shifts that lack a legitimate basis |

### II. Systemic Positioning
- **Core statutes:** Civil Code Book Three "Contracts," Subdivision Three "Quasi-Contracts," Chapter 28 (Arts. 985–988)
- **Normative purpose:** Correct property shifts lacking a legitimate basis and uphold the fairness principle that "no one may profit at another's expense"
- **Systemic relationship:** Together with negotiorum gestio (*wuyin guanli*), it belongs to "quasi-contracts," as an independent ground of obligation alongside contract, tort, and negotiorum gestio

### III. Constitutive Elements (four elements, sequential relationship)

| No. | Element Name | Element Content | Points of Dispute |
|------|----------|----------|--------|
| 1 | One party obtains a benefit | Positive increase in property (acquiring rights or possession) or negative increase (expenses that should have been but were not incurred) | Does "benefit" include use benefits and labor benefits?—Prevailing view: yes |
| 2 | The other party suffers a loss | Positive decrease in property (loss of rights or expenditure) or negative decrease (what should have been but was not received) | Must "loss" match the scope of "enrichment"?—Prevailing view adopts the difference theory |
| 3 | Causal link | Causal connection between one party's enrichment and the other's loss | Direct causation theory vs. non-direct causation theory—Chinese judicial practice tends toward direct causation |
| 4 | Without legal cause | Enrichment lacks a lawful basis | Time for judging "without legal cause": at the time of performance vs. at the time of claim—Chinese prevailing view: at the time of performance |

### IV. Boundaries with Neighboring Concepts

| Comparison Dimension | Unjust Enrichment | Negotiorum Gestio | Tort |
|----------|----------|----------|------|
| **Normative purpose** | Correct improper property shifts | Reward mutual assistance | Remedy unlawful infringement |
| **Core difference** | Profiting at another's expense (loss ≠ gain, but without lawful basis) | Benefiting another (managing another's affairs for their benefit) | Unlawfully infringing another's rights and interests |
| **Legal effects** | Restitution of benefits obtained | Reimbursement of necessary expenses | Damages |
| **Subjective element** | Intent not required | Requires intent "to manage for another" | Under fault liability, fault is required |

### V. Legal Effects
- **Direct effects:** The enriched party owes a duty to restore the benefit obtained to the impoverished party
- **Claim created:** The impoverished party has a claim for restitution of unjust enrichment (Civil Code Art. 985)
- **Scope of restitution:** Restitution in kind → if restitution in kind is impossible, compensation at value → necessary expenses may be deducted from restored benefits
- **Exclusion situations:** Performance of moral duties; premature payment of a debt before maturity; payment with knowledge that no debt exists (Art. 985 proviso)

### VI. Typical Application Situations
- Mistaken transfer or mistaken payment
- Restitution of property after a contract is void or revoked
- Payment of a non-existent debt (e.g., double payment)
- Benefits obtained through tort (where claims compete, the unjust-enrichment claim may be chosen)
- Voluntary performance of a natural obligation (application excluded)
```

### Example 2: Concept + Fact Scenario—Does a Mistaken Transfer Constitute Unjust Enrichment?

**Input:** "A mistakenly transferred RMB 50,000 via mobile banking to B, whom A does not know. B received the funds and refused to return them. Does this constitute unjust enrichment?"

**Output:**

```markdown
## Concept Application Analysis: Unjust Enrichment × Mistaken Transfer

### I. Concept Recap
Four elements of unjust enrichment: one party's enrichment; the other's loss; causal link; without legal cause.

### II. Fact Extraction
- A transferred RMB 50,000 to B via mobile banking
- A and B are strangers; no creditor–debtor relationship exists
- A made a mistaken transfer (operational error)
- B received the funds and refused to return them

### III. Element Mapping

| Element | Corresponding Facts | Satisfied? | Notes |
|------|----------|----------|------|
| One party obtains a benefit | B's bank account increased by RMB 50,000 | ✅ Satisfied | B obtained ownership of the money; positive enrichment |
| The other party suffers a loss | A's bank account decreased by RMB 50,000 | ✅ Satisfied | A lost ownership of the money; positive loss |
| Causal link | A's mistaken transfer directly caused B's receipt | ✅ Satisfied | The same performance simultaneously caused loss and enrichment; causation is direct |
| Without legal cause | No creditor–debtor relationship between A and B; mistaken transfer lacks a performance purpose | ✅ Satisfied | Performance purpose never existed |

### IV. Conclusion
**Preliminary judgment:** B's receipt of A's mistakenly transferred RMB 50,000 constitutes unjust enrichment. A is entitled under Civil Code Art. 985 to demand that B return RMB 50,000.

**Key certainties:** All four elements are clear; facts are complete; causation is direct; this is a typical core case of unjust enrichment.

**Possible defenses:** If B asserts that the funds were repayment of a debt owed by A to B, B must prove the existence of the creditor–debtor relationship (Civil Code Art. 987: if the enriched party neither knew nor ought to have known that the benefit lacked a legal basis, and the benefit no longer exists, there is no restitution duty—but B's "refusal to return" here indicates knowledge of the lack of lawful basis).

**Remedies:** A may choose to:
1. Bring an action for restitution of unjust enrichment (civil litigation)
2. Request the bank's assistance in recovery (if the transfer is still being processed)
3. Report to the police (if B is suspected of embezzlement, though civil channels are usually preferred first)
```

### Example 3: Concept Comparison—Liquidated Damages vs. Damages

**Input:** "What is the difference between liquidated damages and damages?"

**Output:**

```markdown
## Concept Comparison: Liquidated Damages (*weiyuejin*) vs. Damages (*sunhai peichang*)

### I. Common Ground
Both are forms of liability for breach of contract, functioning to compensate the non-breaching party for losses caused by breach.

### II. Core Differences

| Comparison Dimension | Liquidated Damages | Damages |
|----------|--------|----------|
| **Basis of creation** | Contractual stipulation or legal provision (Civil Code Art. 585) | Legal provision (Civil Code Arts. 577, 584) |
| **Amount determination** | Specific amount or calculation method agreed in advance | Calculated afterward based on actual loss |
| **Proof requirements** | Non-breaching party need only prove the fact of breach, not the amount of loss | Non-breaching party must prove existence and amount of loss |
| **Adjustment mechanism** | If excessively high, a party may request an appropriate reduction by the court (Art. 585(2)) | Capped by actual loss (including the foreseeability rule) |
| **Functional emphasis** | Combines compensation with a certain punitive / deterrent function | Purely compensatory |
| **Prerequisite for application** | Requires a liquidated-damages clause | Arises upon breach; no prior agreement needed |

### III. Application Choice Guide
- **Liquidated damages already agreed:** Prefer the liquidated-damages clause, but the other party may request court adjustment
- **Liquidated damages below actual loss:** May request an increase to a level commensurate with actual loss (Civil Code Art. 585)
- **Liquidated damages above actual loss:** The breaching party may request an appropriate reduction, but courts generally adjust only where the amount is "excessively higher"
- **No liquidated damages agreed:** Only damages may be claimed; the claimant must prove loss
- **Limits on concurrent use:** Generally, liquidated damages and damages may not both be claimed so as to obtain double recovery for the same loss
```

## VI. Common Errors and Prevention

| Error Type | Error Description | Consequences | Preventive Measures |
|----------|----------|------|----------|
| **Substituting everyday meaning for legal meaning** | Directly applying everyday understanding to legal concepts | Legal analysis rests on a mistaken concept | Always confirm the legal definition; mark differences from everyday meaning |
| **Ignoring jurisdictional differences** | Analyzing a problem under Jurisdiction B with a concept from Jurisdiction A | Incorrect application of law | Expressly limit the jurisdiction; specially mark foreign-law concepts |
| **Incomplete element unpacking** | Omitting an element or misstating the relationship among elements | Incomplete element testing; unreliable conclusions | Strictly follow statutes and doctrine; list all elements and logical relationships one by one |
| **Vague boundary distinctions** | Distinctions from neighboring concepts remain abstract without concrete element differences | User cannot accurately choose which concept applies | Compare item by item in a table; state "under what circumstances it is A, and under what circumstances it is B" |
| **Ignoring conceptual evolution** | Explaining concepts only by outdated law or doctrine, without attending to amendments or doctrinal development | Outdated analysis | Confirm that authorities remain currently in force; attend to the latest judicial interpretations and leading cases |
| **Over-simplifying open concepts** | Giving only a simple definition for highly open concepts such as "public order and good morals" or "good faith" | Fails to reveal the concept's true function and method of use | Explain typified application situations, leading cases, and judicial review standards |

## VII. Special Scenario Handling

### 7.1 Highly Contested Concepts

For highly open concepts such as "public order and good morals," "good faith," "material misunderstanding," and "obvious unfairness" (*xianshi gongping*):

- **Do not pursue a single correct answer:** Note scholarly disputes and list main views
- **Typified analysis:** List typical situations already typified in judicial practice
- **Judicial review standards:** Explain courts' review points and discretionary space when applying the concept
- **Leading-case guidance:** Cite leading cases to show actual application

### 7.2 Same-Named Concepts Across Branches of Law

The same term may have different meanings in different branches of law:

| Concept | Meaning in Civil Law | Meaning in Criminal Law | Meaning in Administrative Law |
|------|-------------|-------------|---------------|
| **Possession** (*zhanyou*) | Factual control over a thing (Civil Code Art. 458) | Purpose of unlawful possession (subjective element of property crimes) | Characterization of possession status in administrative expropriation |
| **Intent** (*guyi*) | Generally not an independent concept (mental state within fault liability) | Core of the subjective element of crime, with a clear statutory definition | Subjective fault element in administrative penalties (Administrative Penalty Law Art. 33) |

**Handling method:** First confirm the branch-of-law context of the user's inquiry; if unspecified, explain each separately.

### 7.3 Concepts in Comparative-Law Contexts

When the user asks to compare same-named concepts across jurisdictions:

- Conduct full analysis separately under each jurisdiction's system
- Focus comparison on: differences in normative function, constitutive elements, and legal effects
- Note conceptual deformation in legal transplants (e.g., "reliance interest" in Chinese law vs. *Vertrauensschaden* in German law)
- Expressly mark: comparative analysis is for reference only; concrete application must follow local law

### 7.4 New Concepts in Emerging Fields

For new concepts in data law, artificial intelligence law, and similar fields (e.g., "personal information," "algorithmic recommendation," "automated decision-making"):

- Take current legislation as the primary authority (e.g., Personal Information Protection Law; Provisions on the Administration of Algorithmic Recommendation)
- Attend to the evolution of supporting regulations and standards
- Explain conceptual uncertainty and regulatory dynamics
- Distinguish three layers: legislative definitions, regulatory practice, and academic discussion

## VIII. Quality Checklist

```markdown
□ 1. Has the target concept been clarified (name, jurisdiction, branch of law)?
□ 2. Has the layered analysis of everyday meaning → legal meaning → doctrinal meaning been completed?
□ 3. Have core statutes been accurately cited (statute name + article number)?
□ 4. Have constitutive elements been fully unpacked (no omissions, no redundancy)?
□ 5. Has the relationship among elements been clarified (concurrent / sequential / alternative)?
□ 6. For elements with scholarly dispute, has the focus of dispute been stated?
□ 7. Have boundaries with neighboring concepts been clarified through concrete points of difference?
□ 8. Have legal effects been fully analyzed (direct effects, claims, procedural impact)?
□ 9. Have typical application situations been listed?
□ 10. If a fact scenario is involved, has element-mapping analysis been completed?
□ 11. Does the output use a structured template format?
□ 12. Have differences from everyday meaning and points requiring special attention been marked?
```

## IX. Related Skills

| Related Skill | Relationship | Notes |
|----------|------|------|
| Legal rule application | Downstream | After concept comprehension, embed the concept in a syllogistic rule structure for application |
| Statutory retrieval | Parallel / upstream | Retrieve statutes, judicial interpretations, and leading cases related to the concept |
| Legal reasoning | Downstream | On the basis of concept comprehension, conduct legal argumentation and adjudicative reasoning |
| Claim-basis analysis | Downstream | Use concept comprehension to construct and test claim bases |
| Legal document drafting | Downstream | Use clarified legal concepts accurately and normatively in documents |

## X. Limitations and Risk Notices

- **Functional positioning:** This skill addresses "legal concept comprehension" as a foundational unit of legal analysis; it cannot alone replace full legal rule application, adjudicative reasoning, or institutional evaluation.
- **Meaning shift:** The same concept may shift meaning across jurisdictions, branches of law, or adjudicative contexts; analytical conclusions must be confined to a specific context.
- **Openness limits:** Some legal concepts are highly open or contested; definition and element unpacking alone cannot exhaust their meaning; dynamic understanding through cases and scholarship remains necessary.
- **Effects are not automatic:** The legal effects of some concepts do not follow automatically; they must be combined with other concepts, rules, or institutional premises to form a complete legal conclusion.
- **Evolutionary risk:** Laws and regulations continually update; concept-analysis conclusions reflect only the currently effective legal state and must attend to subsequent legislative and judicial developments.
