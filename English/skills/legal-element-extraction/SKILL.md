---
name: legal-element-extraction
description: |
  Trigger this skill when legally significant facts need to be extracted from unstructured text such as case descriptions, party statements, chat logs, or media reports.
  Typical trigger scenarios include, but are not limited to:
  - The user provides an everyday-language case description and asks to extract legal facts
  - The user asks to convert colloquial, emotional narratives into a fact structure usable for legal analysis
  - The user asks to distinguish "objective facts," "subjective judgments," and "legal evaluations" in a case narrative
  - The user asks to map extracted facts onto constitutive elements of a particular legal relationship
  - The user asks to organize a case timeline or produce a fact-sorting table
  - The user asks to convert everyday language into legal language (e.g., "he's been dragging his feet and won't pay me back" → "failed to perform after the performance period expired")
  Core value of this skill: Organize mixed life narratives into a fact structure that can enter legal reasoning—a preparatory step for legal analysis.
---

> **Chinese source (authoritative):** [`../../skills/legal-element-extraction/SKILL.md`](../../skills/legal-element-extraction/SKILL.md)

# Legal Element Extraction

## Overview Table

| Item | Content |
|------|------|
| **Capability ID** | 13 |
| **Capability Name** | Legal Element Extraction |
| **Capability Type** | Fact structuring |
| **Core Function** | Extract legally relevant facts from unstructured case narratives, classify them by type, and map them onto legal constitutive elements |
| **Input** | Everyday-language case descriptions, party statements, chat logs, media reports, preliminarily organized case materials |
| **Output** | Structured legal-element checklist; legal-fact analysis table; legal-practice timeline |
| **Related Capabilities** | Legal concept comprehension (identify legal elements); legal rule application (embed facts in rules); claim-basis analysis (map to claim elements) |
| **Key Principles** | Objectification; minimal units; typification; element correspondence |

## Legal Disclaimer

> **Important notices:**
> 1. This skill addresses "fact extraction and structuring" and does not produce legal conclusions. Extracted legal facts still require subsequent analysis under specific legal norms, claim bases, and evidence rules.
> 2. Fact extraction depends on the completeness and truthfulness of the original narrative. Where there are serious information gaps, factual contradictions, or insufficient evidence, the extraction can only form a preliminary framework.
> 3. Identification of "objective facts" is based on textual analysis and cannot replace evidence review and fact-finding. Where key facts are disputed, evidence-based adjudication is the principle.
> 4. When converting everyday language into legal language, the conversion is only a preliminary judgment; concrete formulations should follow actual evidence and legal analysis.

## I. Core Concepts

### 1.1 Three-Layer Fact Structure

Not all information in a case narrative has legal significance. Three layers must be penetrated:

```
Original narrative (life story)
    ↓  Extract and filter
Legally relevant facts (fact units with normative significance)
    ↓  Typify and map
Element facts (facts that can directly correspond to legal constitutive elements)
```

| Layer | Features | Example |
|------|------|------|
| **Original narrative** | Colloquial, emotional, strongly narrative, loosely structured | "He's been dragging his feet and won't pay me back; I'm so angry; this kind of person has no integrity at all" |
| **Legally relevant facts** | Directly related to legal judgment; emotion and evaluation removed | Loan amount RMB 50,000; agreed repayment period 1 month; 3 months overdue unpaid; borrower deleted lender's WeChat |
| **Element facts** | Can directly correspond to constitutive elements of a specific claim or defense | Loan agreement formed (contract formation element) → performance period expired (performance element) → loan not repaid (breach element) |

### 1.2 Nine Categories of Fact Units

All legally relevant facts can be placed in the following nine categories:

| Fact Type | Core Question | Typical Content | Legal Significance |
|----------|----------|----------|----------|
| **Subject facts** | Who? | Actor, victim, contracting parties, agent, platform, third party, and their relationships | Determine attribution of rights and duties; assess party standing |
| **Conduct facts** | What was done? | Signing, payment, delivery, notice, refusal, disclosure, deletion, damage, forwarding, etc. | Characterize conduct; assess whether it constitutes a juridical act or a real act |
| **Time facts** | When? | Time of contract formation, performance deadline, time of damage, time of notice, time of knowledge or constructive knowledge | Determine limitation accrual, performance periods, exclusive periods |
| **Place facts** | Where? | Place of contract formation, place of performance, place of damage, jurisdictional connecting factors | Determine place of performance, court of jurisdiction, applicable law |
| **Object facts** | Directed at what? | Funds, goods, data, works, equipment, personality interests, private information, and other objects | Determine the object of rights; identify what was harmed |
| **Result facts** | What consequences arose? | Non-performance, defective delivery, occurrence of damage, privacy breach, reputational harm, property decrease | Assess existence of damage; endpoint of causation |
| **Causation facts** | Is there a link between conduct and result? | Whether a given act caused a given result; what intervening factors exist | Assess establishment of liability; interruption of causation |
| **Subjective facts** | What was the mental state? | Intent, negligence, actual knowledge, constructive knowledge, failure of reasonable care, good faith / bad faith | Assess fault elements; basis of attribution |
| **Procedural facts** | What procedural steps were taken? | Demand / notice (*cuigao*), negotiation, complaint, report to police, suit, performance of notice duties, raising objections | Assess whether procedural conditions are met; whether limitation is interrupted |

### 1.3 Four-Way Classification of Fact Attributes

Information in the same narrative must be distinguished by four attributes:

| Attribute | Features | Identification Markers | Handling Method |
|------|------|----------|----------|
| **Objective facts** | Can be described and proved by external evidence | States concrete conduct, time, place, object | Extract directly; mark possible evidence sources |
| **Subjective judgments** | Party's judgment based on personal feelings | "I feel," "I think," "obviously," "definitely" | Strip emotion; probe the objective facts behind it |
| **Legal evaluations** | Already carry normative classification or liability judgment | "Constitutes fraud," "amounts to breach," "acted in bad faith," "clearly unlawful" | Reduce to the objective factual basis supporting that evaluation |
| **Background information** | No direct link to legal judgment | Party personality, irrelevant antecedents and consequences, rhetorical description | Exclude; retain only information necessary to aid understanding |

**Key principle:** Evaluative expressions such as "deception," "bad faith," and "clearly unlawful" cannot be used directly as analytical premises; they must be further reduced to objective facts that norms can recognize.

## II. Complete Workflow

### Phase One: Deconstruction and Extraction

#### Step 1: Segment into Minimal Fact Units

Break everyday language, long sentences, compound sentences, emotional expressions, and conclusory descriptions in the case materials into several minimal fact units that can be independently identified and independently assessed.

**Segmentation method:**
- Split compound narratives by sentence
- Each fact unit should include: who (subject) + what was done (conduct) + when (time) + directed at what (object) + what resulted (result)
- For fact units missing elements, mark "to be supplemented"

**Example:**

| Original Narrative | Minimal Fact Units After Segmentation |
|----------|----------------------|
| "Last year I lent a friend fifty thousand yuan; he said then he'd definitely pay me back in a month. Three months later he still hadn't paid; every time I asked he said wait a bit longer; finally he deleted my WeChat." | ① Lender (I) and borrower (friend) reached a loan agreement ② Loan amount: RMB 50,000 ③ Agreed repayment period: 1 month ④ Actual overdue: 3 months unpaid ⑤ Lender made repeated demands ⑥ Borrower refused repayment (stalling) ⑦ Borrower deleted lender's WeChat (cut off contact) |

#### Step 2: Typify and Classify Facts

Classify the segmented minimal fact units into the nine fact categories:

**Output format:**
```markdown
### Structured Legal Element Checklist

#### Subject Facts
- [...]

#### Conduct Facts
- [...]

#### Time Facts
- [...]

#### Place Facts
- [...]

#### Object Facts
- [...]

#### Result Facts
- [...]

#### Causation Facts
- [...]

#### Subjective Facts
- [...]

#### Procedural Facts
- [...]
```

#### Step 3: Attribute Distinctions and Cleansing

For each fact unit, assess its attribute:

1. **Is it an objective fact?** Yes → retain and mark possible evidence sources; No → proceed
2. **Is it a subjective judgment?** Yes → strip emotional words and probe the objective facts behind it; No → proceed
3. **Is it a legal evaluation?** Yes → reduce to the objective factual basis supporting that evaluation; No → proceed
4. **Is it background information?** Yes → exclude (unless necessary to understand the case)

**Distinction examples:**

| Original Expression | Attribute Assessment | Cleansed Result |
|----------|----------|----------|
| "He's been dragging his feet and won't pay me back" | Subjective judgment + legal evaluation | Conduct fact: failed to perform after the performance period expired; procedural fact: creditor made repeated demands |
| "The seller clearly said it was new" | Subjective judgment ("clearly") | Conduct fact: seller represented that "the goods are brand new"; subjective fact: seller knew or ought to have known the goods were not brand new |
| "The platform leaked my information" | Legal evaluation ("leaked") | Conduct fact: platform provided the user's personal information to a third party; object fact: the user's personal information; result fact: information obtained by a third party |
| "This kind of person has no integrity at all" | Subjective judgment + emotion | Background information → exclude |

### Phase Two: Mapping and Conversion

#### Step 4: Everyday Language → Legal Language Conversion

Rewrite cleansed objective facts into normative formulations meaningful for legal analysis:

| Everyday Language | Legal Language |
|----------|----------|
| "He's been dragging his feet and won't pay me back" | "After the debt performance period expired, the debtor failed to perform the repayment obligation" |
| "The seller clearly said it was new" | "The seller made a specific representation as to the quality of the subject matter (that it was brand new)" |
| "The platform leaked my information" | "The information processor provided personal information to a third party, and that provision was without the information subject's consent" |
| "Every time I asked he said wait a bit longer" | "The creditor made repeated demands; the debtor repeatedly promised to perform but never actually performed" |
| "He deleted my WeChat" | "The debtor refused to communicate with the creditor by deleting contact information" |

**Conversion principles:**
- Use neutral, objective normative wording
- Retain concrete elements (amounts, times, quantities, etc.); do not blur them
- For subjective states, use legal concepts such as "knew," "ought to have known," and "negligence," rather than evaluative terms such as "intent" or "bad faith" (unless adequately supported by facts)

#### Step 5: Map onto Legal Constitutive Elements

Around the concrete legal relationship and legal question, map extracted and converted facts onto a specific claim basis, liability structure, or defense ground.

**Mapping method:**
1. Identify possible legal relationships involved (contract, tort, unjust enrichment, negotiorum gestio, etc.)
2. List the constitutive elements of that legal relationship
3. Map facts one by one onto each element
4. Mark: elements satisfied / partially satisfied / elements lacking facts

**Output format (element-mapping table):**
```markdown
### Element Mapping Analysis

**Legal relationship:** [e.g., loan contract relationship]
**Claim basis:** [e.g., Civil Code Art. 675 (claim for return of loan)]

| Constitutive Element | Corresponding Facts | Satisfaction Status | Notes |
|----------|----------|----------|------|
| Loan agreement | Parties agreed on a RMB 50,000 loan | ✅ Satisfied | Supported by chat logs / IOU |
| Delivery of funds | Lender transferred RMB 50,000 to borrower | ✅ Satisfied | Transfer records exist |
| Performance period expired | Agreed 1 month; already 3 months overdue | ✅ Satisfied | Agreement clear |
| Loan not returned | Borrower has returned no funds | ✅ Satisfied | Borrower admits / no repayment records |
```

### Phase Three: Integrated Output

#### Step 6: Output Structured Deliverables

According to the user's needs, choose one or more of the following output forms:

**Form A: Structured legal element checklist** (for early materials organization)
- List all legally relevant facts by the nine fact categories
- Mark evidence sources for each fact (if stated)
- Mark facts to be supplemented and disputed facts

**Form B: Legal-fact analysis table** (for professional legal analysis preparation)
- Columns: original narrative → objectified fact → legal label → fact type → corresponding constitutive element → evidence source → dispute status

**Form C: Legal-practice timeline** (for complex case sorting)
- Arrange important acts, event progress, and legal nodes in chronological order
- Mark: time, actor, content of act, object involved, result of act, key evidence, legal significance

## III. Output Format Templates

### Template A: Structured Legal Element Checklist

```markdown
## Legal Element Extraction Report

### I. Original Narrative Abstract
[Summarize the core content of the original narrative in 1–2 sentences]

### II. Structured Fact Extraction

#### Subject Facts
- [Fact 1]
- [Fact 2]

#### Conduct Facts
- [Fact 1]
- [Fact 2]

#### Time Facts
- [Fact 1]
- [Fact 2]

#### Place Facts
- [If any]

#### Object Facts
- [Fact 1]

#### Result Facts
- [Fact 1]

#### Causation Facts
- [Fact 1]

#### Subjective Facts
- [Fact 1]

#### Procedural Facts
- [Fact 1]

### III. Facts to Be Supplemented
[List facts missing from the original narrative but important for legal analysis]

### IV. Disputed Facts
[List facts that are contradictory in the narrative or require evidentiary confirmation]

### V. Information Excluded
[List content excluded as background information, subjective judgment, or legal evaluation]
```

### Template B: Legal-Fact Analysis Table

```markdown
| Original Narrative Text | Objectified Fact Formulation | Legal Label | Fact Type | Corresponding Constitutive Element | Evidence Source | Dispute Status |
|-------------|---------------|----------|----------|-------------|----------|----------|
| [...] | [...] | [...] | [...] | [...] | [...] | [...] |
```

### Template C: Legal-Practice Timeline

```markdown
| Time | Actor | Content of Act | Object Involved | Result of Act | Key Evidence | Legal Significance |
|------|----------|----------|----------|----------|----------|----------|
| [...] | [...] | [...] | [...] | [...] | [...] | [...] |
```

## IV. Examples

### Example 1: Structured Element Extraction

**Input:**
> "Last year I lent a friend fifty thousand yuan; he said then he'd definitely pay me back in a month. Three months later he still hadn't paid; every time I asked he said wait a bit longer; finally he deleted my WeChat."

**Output:**

```markdown
## Legal Element Extraction Report

### I. Original Narrative Abstract
Lender lent borrower RMB 50,000, agreed to be repaid in 1 month; 3 months overdue unpaid; borrower deleted lender's WeChat.

### II. Structured Fact Extraction

#### Subject Facts
- A loan relationship arose between the lender (narrator) and the borrower (friend)
- The parties are natural persons in a private lending relationship

#### Conduct Facts
- The parties reached agreement on a RMB 50,000 loan
- The lender delivered the loan to the borrower (amount RMB 50,000)
- The borrower promised to repay in 1 month
- The borrower failed to repay after the performance period expired
- The lender repeatedly demanded repayment from the borrower
- The borrower stalled by saying "wait a bit longer"
- The borrower deleted the lender's WeChat and cut off contact

#### Time Facts
- Time of loan: "last year" (specific date needs further confirmation)
- Agreed repayment period: 1 month
- Overdue period: 3 months
- Limitation accrual point: date the agreed repayment period expired (specific date needs confirmation)

#### Place Facts
- [Not mentioned; need to supplement: place of loan delivery, defendant's domicile, etc., for determining jurisdiction]

#### Object Facts
- Loan subject matter: RMB 50,000

#### Result Facts
- Borrower failed to return the loan within the agreed period
- Borrower and lender lost contact

#### Causation Facts
- Borrower's failure to perform repayment → lender's claim unrealized

#### Subjective Facts
- Borrower knew of the repayment obligation (had promised to repay)
- Borrower had capacity to perform but refused to perform (stalled repeatedly, then cut off contact)

#### Procedural Facts
- Lender made repeated demands (may interrupt limitation)
- No lawsuit or arbitration filed

### III. Facts to Be Supplemented
1. Specific date of the loan (affects limitation calculation)
2. Manner of loan delivery (cash / transfer; affects evidentiary strength)
3. Whether there is an IOU, acknowledgment of debt, or loan contract
4. Borrower's identity information (suit requires a clear defendant)
5. Whether the borrower has property leads (affects enforcement)

### IV. Disputed Facts
- Whether the borrower's deletion of WeChat constitutes evidence of bad faith in "evading debt" (must be assessed with other evidence)

### V. Information Excluded
- "I'm so angry" → subjective emotion; excluded
- "This kind of person has no integrity at all" → subjective evaluation; excluded
```

### Example 2: Everyday Language → Legal Language Conversion

**Input:**
> "I bought a computer on a secondhand platform; the seller said it was brand new and unopened; after I received it I found it was a refurbished machine. I asked him to take it back; he refused, and also deleted some of the earlier chat content."

**Output:**

```markdown
## Everyday Language → Legal Language Conversion

| Original Expression | Attribute Assessment | Legal Language Conversion |
|----------|----------|-------------|
| "I bought a computer on a secondhand platform" | Objective fact | A sales contract relationship arose between buyer and seller (secondhand-platform seller); subject matter is one computer |
| "The seller said it was brand new and unopened" | Objective fact (seller's representation) | Seller made a specific representation to buyer as to quality of the subject matter: that it was brand new and unopened |
| "After I received it I found it was a refurbished machine" | Objective fact | The subject matter received by the buyer was a repaired machine, inconsistent with the seller's representation of "brand new and unopened" |
| "I asked him to take it back" | Objective fact (conduct) | Buyer asserted rescission of the contract and demanded return of the goods |
| "He refused" | Objective fact | Seller refused buyer's request to return the goods |
| "Deleted some of the earlier chat content" | Objective fact | Seller deleted some chat records between the parties (may involve destruction of evidence) |

### Preliminary Analysis of Possible Legal Relationships and Constitutive Elements

**Path One: Warranty against defects in a sales contract**
- Element 1: Sales contract formed → ✅ Parties agreed on the computer sale
- Element 2: Subject matter has a defect → ✅ Subject matter is a repaired machine rather than brand new; quality defect exists
- Element 3: Defect existed at contract formation → ❓ Need to prove repair occurred before delivery
- Element 4: Buyer notified within the inspection period → ❓ Need to prove buyer timely raised an objection
- Legal effects: Buyer may claim repair, replacement, return, price reduction, or damages (Civil Code Art. 582)

**Path Two: Fraud (rescission of contract)**
- Element 1: Seller made a false statement → ✅ "Brand new and unopened" was a false representation
- Element 2: Seller had fraudulent intent → ❓ Need to prove seller knew or ought to have known it was a repaired machine
- Element 3: Buyer fell into mistaken understanding because of the fraud → ✅ Buyer decided to purchase based on the "brand new" representation
- Element 4: Buyer made a manifestation of intent because of the mistaken understanding → ✅ Buyer agreed to purchase
- Legal effects: Buyer may request rescission of the contract and return of the price (Civil Code Art. 148)
- Exclusive period: within 1 year from knowing or ought to have known the ground for rescission

**Path Three: Consumer fraud (if the Consumer Rights and Interests Protection Law applies)**
- Need to confirm whether the seller is a business operator and whether the buyer purchased for living consumption needs
- If constituted, may claim "refund one and compensate three" (Consumer Rights and Interests Protection Law Art. 55)
```

### Example 3: Legal-Fact Analysis Table

**Input:**
> "Our company engaged Company B to develop an App; the contract provided for delivery in 3 months at a total price of RMB 300,000. After signing we paid RMB 100,000 as advance payment. When 3 months arrived Company B said it wasn't finished and needed another 2-month extension. We disagreed and demanded a refund. Company B said the advance had already been spent and couldn't be refunded. Later we discovered Company B had subcontracted the project to Company C, even though the contract expressly prohibited subcontracting."

**Output:**

```markdown
## Legal-Fact Analysis Table

| Original Narrative Text | Objectified Fact Formulation | Legal Label | Fact Type | Corresponding Constitutive Element | Evidence Source | Dispute Status |
|-------------|---------------|----------|----------|-------------|----------|----------|
| "Our company engaged Company B to develop an App" | Company A (principal) and Company B (developer) entered a technology development contract; subject matter is App software development | Technology development contract formed | Subject / conduct / object | Contract formation element | Written contract | Undisputed |
| "The contract provided for delivery in 3 months at a total price of RMB 300,000" | Agreed performance period: 3 months; contract price: RMB 300,000 | Performance period / price clause | Time / object | Certainty of contract content | Written contract | Undisputed |
| "Paid RMB 100,000 as advance payment" | Principal paid developer RMB 100,000 as advance | Advance payment made | Conduct / object | Performance conduct | Transfer records | Undisputed |
| "When 3 months arrived Company B said it wasn't finished and needed another 2-month extension" | Developer failed to deliver results when the performance period expired and requested a 2-month extension | Delayed performance | Conduct / time / result | Breach element (non-performance) | Communication records | Undisputed |
| "We disagreed and demanded a refund" | Principal refused the extension request, asserted rescission, and demanded return of the advance | Manifestation of intent to rescind | Conduct / procedure | Exercise of rescission right | Communication records | Undisputed |
| "Company B said the advance had already been spent and couldn't be refunded" | Developer asserted the advance had been used for project expenses and refused to return it | Defense (partial performance / expenses incurred) | Conduct / result | Defense ground | Developer's statement | Disputed (needs verification) |
| "Company B subcontracted the project to Company C" | Developer, without the principal's consent, had Company C actually perform the development project | Unauthorized subcontracting | Conduct / subject | Breach element (violation of contractual no-subcontracting clause) | Fact discovery / evidence of Company C's involvement | Needs confirmation |
| "The contract expressly prohibited subcontracting" | Contract expressly provided that the developer may not subcontract the project to a third party | No-subcontracting clause | Conduct | Contractual obligation | Written contract | Undisputed |
```

## V. Common Errors and Prevention

| Error Type | Error Description | Consequences | Preventive Measures |
|----------|----------|------|----------|
| **Treating evaluation as fact** | Directly taking legal evaluations such as "constitutes fraud" or "amounts to breach" as analytical premises | Skips fact review; conclusions lack factual foundation | When encountering evaluative language, ask "what conduct led you to that conclusion?" |
| **Treating emotion as fact** | Retaining "I'm so angry" / "he's so terrible" as important information | Summary flooded with subjective emotion; objective facts submerged | Identify emotional words ("so," "at all," "obviously," "definitely"); strip them and probe for facts |
| **Omitting key times** | Failing to extract or mis-extracting time elements | Errors in calculating limitation periods, exclusive periods, performance deadlines | Mark a time for every act; if uncertain, mark "to be confirmed" |
| **Confusing different subjects' conduct** | Mixing A's conduct with B's | Unclear attribution of liability; wrong element mapping | Clearly mark the actor for each fact unit |
| **Over-abstraction** | Over-generalizing concrete facts into "there is a dispute" / "a controversy arose" | Loses concreteness of facts; cannot test elements | Retain concrete elements (amounts, times, quantities, specific acts) |
| **Omitting procedural facts** | Ignoring demands, notices, objections, and similar procedural acts | Risk that procedural elements are unmet is overlooked | Especially ask "was there a demand?" "was there notice?" "was an objection raised?" |
| **Ignoring evidence leads** | Not marking possible evidence sources when extracting facts | Cannot assess evidentiary strength in subsequent legal analysis | For each fact, try to mark possible forms of evidence |

## VI. Special Scenario Handling

### 6.1 Multi-Party Cases

- Extract and classify each subject's conduct separately
- Clearly mark legal relationships among subjects (contract counterparties, tortfeasor and victim, joint tortfeasors, etc.)
- For different subjects' versions of the same fact, mark contradictions

### 6.2 Complex Timeline Cases

- Prefer the timeline output format
- Mark legal significance between time points (e.g., how many days after demand; when the exclusive period expires)
- For original materials with disordered time narratives, sort by time first, then extract

### 6.3 Chat Logs / Fragmented Information

- Extract turn by turn; preserve conversational context
- Distinguish "who said what" from "what actually happened"
- Note promises, admissions, apologies, and similar content in chats that may constitute party admissions

### 6.4 Media Reports / Third-Party Narratives

- Identify information sources (party self-report, eyewitness, journalist inference)
- Mark secondhand information as "to be verified"
- Distinguish "confirmed facts" from "speculative statements" in the report

### 6.5 Case Narratives with Insufficient Evidence

- Honestly mark elements that "lack factual support"
- List key facts that need supplementation and possible forms of evidence
- Do not invent facts because of missing information

### 6.6 Cases Involving Specialized Domains

- For specialized terms (medicine, engineering, finance, etc.), retain the original wording while attempting to understand their legal significance
- Where necessary, mark matters that "require expert appraisal"
- Do not convert professional judgments directly into legal facts

## VII. Quality Checklist

```markdown
□ 1. Has the original narrative been segmented into minimal fact units?
□ 2. Has each fact unit clearly identified the actor?
□ 3. Have all facts been classified into the nine fact categories?
□ 4. Have objective facts, subjective judgments, legal evaluations, and background information been distinguished?
□ 5. Have legal evaluative expressions been reduced to an objective factual basis?
□ 6. Have subjective emotional words been stripped?
□ 7. Has everyday language been converted into legal language?
□ 8. Have extracted facts been mapped onto concrete legal constitutive elements?
□ 9. Have facts to be supplemented been listed?
□ 10. Have disputed facts been marked?
□ 11. Have possible evidence sources been marked for each fact?
□ 12. Have key time nodes been extracted (contract formation, performance period, occurrence of damage, time of knowledge, etc.)?
□ 13. Have procedural facts been extracted (demand, notice, objection, suit, etc.)?
□ 14. Does the output use a structured template format?
```

## VIII. Related Skills

| Related Skill | Relationship | Notes |
|----------|------|------|
| Legal concept comprehension | Upstream | Understanding constitutive elements of legal concepts is required to map facts accurately |
| Statutory retrieval | Upstream / parallel | Retrieve legal norms related to the case to determine the constitutive-element framework |
| Legal rule application | Downstream | After fact extraction, embed facts in rules for legal application |
| Claim-basis analysis | Downstream | Map extracted facts onto each element of a concrete claim |
| Legal reasoning | Downstream | Conduct legal argumentation on the basis of facts and rules |
| Evidence analysis | Parallel / downstream | Review and assess the evidentiary foundation of extracted facts |

## IX. Limitations and Risk Notices

- **Functional positioning:** This skill solves "the problem of organizing facts before they enter legal analysis" and cannot replace a complete legal argumentation process. Extracted facts still require subsequent analysis under specific legal norms, claim bases, evidence rules, and methods of legal interpretation.
- **Information dependence:** Extraction quality depends entirely on the completeness and truthfulness of the original narrative. Where there are serious information gaps, factual contradictions, disordered narrative sequence, or insufficient evidentiary materials, results can only form a preliminary framework.
- **Evidentiary boundary:** This skill identifies "possible objective facts" based on textual analysis and cannot replace evidence review. Where key facts are disputed, evidence-based adjudication is the principle; facts must not be found solely from narrative content.
- **Conversion risk:** When converting everyday language into legal language, the conversion is only a preliminary judgment and may be skewed by incomplete information. Concrete formulations should follow actual evidence and legal analysis.
- **Residual subjectivity:** Although objective facts and subjective judgments must be distinguished, the judgment of "what is a key fact" itself still involves professional legal experience; different analysts may emphasize different points.
- **Currency:** When time calculation is involved (limitation periods, exclusive periods), extracted date information may be incomplete or uncertain; mark "to be verified" and advise the user to confirm.
