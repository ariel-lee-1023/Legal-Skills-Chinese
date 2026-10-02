---
name: structured-element-extraction
description: |
  When the AI agent must systematically analyze a legal question, case facts, legal provision, or legal relationship, it must first decompose it into a structured element checklist. Trigger this skill when:
  - A description of case facts is received and all legal elements must be extracted before analysis
  - Determining whether a legal relationship is established (e.g., contract formation, tort composition, crime composition)
  - Comparing similarities and differences among two or more legal facts or provisions
  - As a pre-quality gate before downstream tasks such as legal reasoning, application of law, or legal advice
  - The user expressly asks to "list elements," "analyze item by item," or "check for omissions"
  Core goal: ensure element extraction is complete and without omission, forming a traceable, verifiable structured checklist before allowing the next stage of reasoning. It is the "quality gate" in the legal analysis chain.
---

> **Chinese source (authoritative):** [`../../skills/structured-element-extraction/SKILL.md`](../../skills/structured-element-extraction/SKILL.md)

# 07 Structured Element Checklist

## I. Overview Table

| Item | Content |
|---|---|
| **Capability name** | Structured Element Checklist |
| **Capability type** | Pre-analysis / Quality gate |
| **Core function** | Decompose a legal question into a complete, mutually exclusive, verifiable element checklist |
| **Upstream input** | Case facts, legal provisions, user questions, contract text, and other raw materials |
| **Downstream output** | Verified structured element checklist for legal reasoning, application of law, risk assessment, etc. |
| **Key principles** | Completeness first (prefer over-listing to omission); exhaust then prune; status-label each item |
| **Quality standard** | Enter the next stage only after passing the "triple completeness check" |

## II. Legal Disclaimer

> **Important:** This skill file is an operational guide for an AI agent and does not constitute legal advice. Extraction of a structured element checklist depends on accurate understanding of the constituent elements of the relevant legal field. In actual legal services, the checklist should be reviewed and confirmed by a licensed legal professional. When outputting an element checklist, the AI agent should clearly label confidence and prompt the user to manually review key elements.

## III. Core Concepts

### 3.1 What Are "Structured Elements"

Structured elements are the result of breaking a legal question into **minimal decidable units**. Each element should satisfy:

- **Atomicity**: Cannot be further meaningfully subdivided
- **Decidability**: Can receive a clear judgment of "satisfied / not satisfied / to be verified"
- **Independence**: Elements do not logically contain one another (MECE)
- **Traceability**: Each element can be traced to a specific legal provision or doctrinal basis

### 3.2 Three Sources of Elements

| Source type | Explanation | Example |
|---|---|---|
| **Statutory elements** | Constituent requirements expressly provided in law | Four elements of tort under Civil Code Art. 1165 |
| **Judicial-interpretation elements** | Refinement or supplementation of statutory elements in judicial interpretations | SPC standards for recognizing "经营场所" (business premises) |
| **Doctrinal / practice elements** | Judgment standards formed in prevailing doctrine or adjudicative practice | Factors for judging "substantial modification" of a contract |

### 3.3 Element Status Labeling System

Each extracted element must be labeled with one of the following statuses:

| Status | Symbol | Meaning |
|---|---|---|
| **Satisfied** | ✅ | Existing materials sufficiently prove the element |
| **Not satisfied** | ❌ | Existing materials clearly show the element is not established |
| **To be verified** | ⚠️ | Existing materials insufficient to judge; information needed |
| **Not applicable** | ➖ | The element need not be examined on these facts |
| **Disputed** | 🔶 | Whether the element is satisfied admits different interpretations |

### 3.4 MECE in Legal Element Extraction

**MECE = Mutually Exclusive, Collectively Exhaustive**

- **Mutually exclusive**: No containment or overlap between any two elements at the same level
- **Collectively exhaustive**: Together, the elements cover all judgment dimensions of the legal question

Typical MECE violations:
- Listing "fault" and "intent" as same-level elements (containment)
- Omitting "causation" (not exhaustive)
- Mixing "questions of fact" and "questions of law" at the same level (inconsistent classification)

## IV. Complete Workflow

### Phase 1: Identify Problem Type and Fix the Element Framework

```
Step 1.1 → Identify the type of legal question
         ├── Contract disputes (formation, validity, performance, breach, termination)
         ├── Tort liability (general tort, special tort, product liability, etc.)
         ├── Crime composition (four-element / three-stratum systems)
         ├── Administrative acts (five elements of legality review)
         ├── Procedural matters (jurisdiction, limitation, standing)
         └── Other types (by specific field)

Step 1.2 → Retrieve the corresponding standard element framework
         - Prefer statutory constituent elements
         - If statutory elements unclear, refer to judicial interpretations
         - If neither is clear, refer to prevailing doctrine

Step 1.3 → Confirm hierarchical structure of the framework
         - Level-1 elements: statutory constituent elements (must all be covered)
         - Level-2 elements: refinements of level-1 elements
         - Level-3 elements: concrete factual judgment points (optional, by complexity)
```

### Phase 2: Extract and Fill Elements Item by Item

```
Step 2.1 → Against the framework, extract corresponding facts from raw materials
         - Extract each element independently; do not skip
         - Quote key sentences from raw materials directly
         - Mark unextractable elements as "to be verified"

Step 2.2 → Label status for each element (✅/❌/⚠️/➖/🔶)

Step 2.3 → Record evidence / basis source for each element
         - Fact elements: which part of which material
         - Legal elements: corresponding article numbers
```

### Phase 3: Completeness Check (Triple Check)

```
First check: Framework completeness
  → Ask: Any level-1 element in the standard framework omitted?
  → Method: Compare extraction result with the standard framework item by item
  → If omitted: Supplement and label status

Second check: Fact coverage
  → Ask: Are there important facts in the raw materials not yet "digested" by any element?
  → Method: Re-read raw materials; mark uncited fact fragments
  → If omitted: Assign to an element, or add a new element if needed

Third check: Logical coherence
  → Ask: Are there logical contradictions among elements?
  → Method: Check logical relations (e.g., consistency of causation and damage elements)
  → If contradiction: Label conflict points and note need for further analysis
```

### Phase 4: Output and Handoff

```
Step 4.1 → Output structured element checklist per standard template
Step 4.2 → Attach completeness declaration (passed / failed triple check)
Step 4.3 → Label overall confidence
Step 4.4 → List items to be verified (if any)
Step 4.5 → Confirm ready for next stage / need more information before continuing
```

## V. Common Fields and Legal Sources

### 5.1 Contract Dispute Element Framework

| Level-1 element | Legal source | Level-2 elements |
|---|---|---|
| Proper contractual parties | Civil Code Art. 143 | Capacity for civil acts, agency authority, subject qualification |
| Genuine expression of intent | Civil Code Art. 143 | No fraud, duress, major misunderstanding, or obvious unfairness |
| Lawful content | Civil Code Arts. 143, 153 | No violation of mandatory provisions; no breach of public order and good morals |
| Contract formation | Civil Code Arts. 471–495 | Offer, acceptance, meeting of minds, form requirements |
| Contract performance | Civil Code Arts. 509–534 | Performing party, content, manner, time, place |
| Breach facts | Civil Code Art. 577 | Non-performance, incomplete performance, delayed performance, defective performance |
| Breach remedies | Civil Code Arts. 577–594 | Specific performance, remedial measures, damages, liquidated damages |
| Exemptions | Civil Code Art. 590 etc. | Force majeure, exemption clauses, counterparty fault |

### 5.2 General Tort Liability Element Framework

| Level-1 element | Legal source | Level-2 elements |
|---|---|---|
| Injurious act | Civil Code Art. 1165 | Act / omission; unlawfulness of conduct |
| Damage | Civil Code Art. 1165 | Personal, property, mental harm; certainty of damage |
| Causation | Civil Code Art. 1165 | Factual causation (condition theory); legal causation (adequate causation) |
| Subjective fault | Civil Code Art. 1165 | Intent / negligence; degree of fault; standard of care |

### 5.3 Crime Composition Framework (Four-Element System)

| Level-1 element | Level-2 elements |
|---|---|
| Object of the crime | Direct object, indirect object, object of the act |
| Objective aspect | Harmful act, harmful result, causation, time/place/method (for specific crimes) |
| Subject | Age of criminal responsibility, capacity, special identity |
| Subjective aspect | Intent (direct/indirect), negligence (carelessness/overconfidence), purpose, motive |

### 5.4 Administrative-Act Legality Review Framework

| Level-1 element | Legal source | Explanation |
|---|---|---|
| Authority basis | Administrative Litigation Law Art. 70 | Whether there is statutory authority |
| Fact-finding | Administrative Litigation Law Art. 70 | Whether primary evidence is sufficient |
| Application of law | Administrative Litigation Law Art. 70 | Whether laws and regulations are correctly applied |
| Procedural legality | Administrative Litigation Law Art. 70 | Whether statutory procedure is followed |
| Reasonable discretion | Administrative Litigation Law Art. 70 | Abuse of power or manifest inappropriateness |

### 5.5 Labor Dispute Element Framework

| Level-1 element | Legal source | Level-2 elements |
|---|---|---|
| Establishment of labor relationship | MOLSS Fa [2005] No. 12 | Proper parties; personal, economic, and organizational subordination |
| Facts of employment | Labor Contract Law Art. 7 | Actual start date, work content, work location |
| Written contract | Labor Contract Law Art. 10 | Whether signed, signing time, term, mandatory clauses |
| Wages and remuneration | Labor Contract Law Art. 30 | Wage standard, payment method, cycle, whether below minimum wage |
| Termination | Labor Contract Law Arts. 36–50 | Type of termination, grounds, procedure, economic compensation |

## VI. Verification and Screening Rules

### 6.1 Five Verification Rules for Element Extraction

| Rule ID | Name | Content | Consequence of failure |
|---|---|---|---|
| V-01 | Legal-source anchoring | Each level-1 element must have a clear statutory or doctrinal basis | May not serve as analysis basis; must reconfirm |
| V-02 | Atomicity test | Lowest-level elements cannot be further meaningfully subdivided | Continue subdividing to atomic level |
| V-03 | MECE test | Same-level elements: no overlap, no omission | Adjust element structure |
| V-04 | Status labeling | Each element must have exactly one status label | Supplement labels before continuing |
| V-05 | Source tracing | Each "satisfied" element must cite a fact source | Downgrade to "to be verified" |

### 6.2 Priority Rules for Element Screening

When raw materials are insufficient, proceed by priority:

1. **Must elements**: Every statutory constituent element — must be listed even if marked "to be verified"
2. **Should elements**: Elements affecting severity of legal consequences — should be listed
3. **May elements**: Auxiliary but not essential — may be listed
4. **Exclude elements**: Irrelevant to the case — do not list, but briefly record exclusion reasons

## VII. Output Format Templates

### Template A: Standard Element Checklist

```markdown
## Structured Element Checklist

**Legal question:** [brief description]
**Question type:** [contract / tort / crime composition / administrative act / other]
**Applicable framework:** [framework name and legal source]
**Extraction date:** [YYYY-MM-DD]

### Element Checklist

| No. | Level | Element name | Status | Fact summary | Source / basis | Notes |
|------|------|----------|------|----------|-----------|------|
| 1 | L1 | [Level-1 element 1] | ✅/❌/⚠️/➖/🔶 | [corresponding facts] | [article] | [notes] |
| 1.1 | L2 | [Level-2 element 1.1] | ✅/❌/⚠️/➖/🔶 | [corresponding facts] | [article] | [notes] |
| ... | ... | ... | ... | ... | ... | ... |

### Completeness Check Results

| Check item | Result | Explanation |
|--------|------|------|
| Framework completeness | ✅ Pass / ❌ Fail | [explanation] |
| Fact coverage | ✅ Pass / ❌ Fail | [explanation] |
| Logical coherence | ✅ Pass / ❌ Fail | [explanation] |

### Items to Be Verified

1. [Element X]: Need to supplement [specific information]
2. [Element Y]: Need to confirm [specific issue]

### Overall confidence: [High/Medium/Low] — [brief reason]

### Conclusion: [May enter next stage / Need more information before continuing]
```

### Template B: Concise Element Checklist (Quick Verification)

```markdown
## Element Checklist — [brief legal question]

**Framework:** [name] | **Legal source:** [core articles]

- [ ] Element 1: [name] — [status] — [one-sentence note]
- [ ] Element 2: [name] — [status] — [one-sentence note]
- [ ] Element 3: [name] — [status] — [one-sentence note]
- [ ] Element 4: [name] — [status] — [one-sentence note]

**Omission check:** ✅ None / ⚠️ Omissions: [explanation]
**May continue:** ✅ Yes / ❌ No, reason: [explanation]
```

## VIII. Confidence Labeling System

### 8.1 Single-Element Confidence

| Confidence | Standard | Labeling |
|---|---|---|
| **High** | Facts clear + legal source clear + no dispute | Status ✅ or ❌ |
| **Medium** | Facts basically clear but details fuzzy, or legal source admits multiple readings | Status 🔶 |
| **Low** | Facts unclear or legal source unclear | Status ⚠️ |

### 8.2 Overall Checklist Confidence

| Overall confidence | Criteria |
|---|---|
| **High** | All level-1 elements ✅ or ❌, no ⚠️, triple check all passed |
| **Medium** | 1–2 ⚠️ or 🔶 elements that do not affect core judgment; triple check basically passed |
| **Low** | 3+ ⚠️ elements, or core element is ⚠️, or triple check failed |

### 8.3 Confidence and Next Actions

| Overall confidence | Allowed next action |
|---|---|
| **High** | Proceed directly to legal reasoning / application of law |
| **Medium** | May proceed, but must clearly label uncertainties in the analysis |
| **Low** | **Must not enter next stage**; first supplement information or request user confirmation |

## IX. Common Errors and Prevention

### 9.1 Fatal Error Table

| Error ID | Name | Description | Severity | Prevention |
|---|---|---|---|---|
| F-01 | **Omitting statutory elements** | Failure to list a statutory constituent element | ⭐⭐⭐⭐⭐ Fatal | Fix complete statutory framework first; compare item by item |
| F-02 | **Confused element levels** | Listing level-2 elements alongside level-1 | ⭐⭐⭐⭐ Serious | Strict hierarchy; same level uses same classification standard |
| F-03 | **Skipping check before output** | Delivering without triple completeness check | ⭐⭐⭐⭐⭐ Fatal | Make check mandatory; results must appear in output |
| F-04 | **Missing status labels** | Elements listed without satisfaction status | ⭐⭐⭐⭐ Serious | Exactly one status per element |
| F-05 | **Fact–element mismatch** | Assigning a fact to the wrong element | ⭐⭐⭐⭐ Serious | After extraction, back-check: does this fact prove this element? |
| F-06 | **Forcing ahead on low confidence** | Entering reasoning when overall confidence is "Low" | ⭐⭐⭐⭐⭐ Fatal | Strictly follow confidence–action table |

### 9.2 Common Traps

| Trap | Manifestation | Correct approach |
|---|---|---|
| **Conclusion instead of elements** | Writing "constitutes tort" without splitting four elements | Split into each independent element |
| **Omitting negative elements** | Focusing only on "establishment," ignoring exemptions/defenses | Exemptions and defenses are also necessary elements |
| **Mixing fact and legal evaluation** | Putting legal conclusions in the fact-summary column | Fact summary records objective facts only; legal evaluation goes in notes |
| **Over-splitting** | Splitting a simple element into a dozen sub-items | Split to "independently decidable"; do not pursue extreme granularity |
| **Rigid frameworks** | Applying one framework to all cases | Choose framework by question type |
| **Ignoring time dimension** | Ignoring element changes from statutory amendments | Confirm applicable law version; label time nodes |
| **Omitting procedural elements** | Focusing only on substantive elements; ignoring limitation, jurisdiction | List procedural elements as a separate group |

## X. Special Scenario Handling

### 10.1 Intersecting Legal Relationships

**Scenario:** Same facts involve multiple legal relationships (e.g., concurrent contract breach and tort)

**Handling:**
1. Build an independent element checklist for each legal relationship
2. Cross-reference shared fact elements between checklists
3. Explicitly state "This case involves N legal relationships; separate checklists established"
4. If claim concurrence exists, note the concurrence relationship

### 10.2 Vague or Blank Law

**Scenario:** Legal standard for an element is unclear; no direct provision to cite

**Handling:**
1. Label legal source as "prevailing doctrine" or "similar-case adjudicative rules"
2. List at least two reference cases or scholarly views
3. Mark element confidence as Medium or Low
4. Note the specific source of uncertainty

### 10.3 Severely Insufficient Facts

**Scenario:** User information extremely limited; many elements cannot be judged

**Handling:**
1. Still list the complete element framework (do not omit for lack of information)
2. Mark all undecidable elements as ⚠️
3. Generate an "information supplementation request list" by priority
4. Overall confidence Low; expressly state next stage must not begin

### 10.4 Multiple Time Nodes for Applicable Law

**Scenario:** Facts span before and after a statutory amendment

**Handling:**
1. Fix the time of each fact element
2. Fix the effective law version for each time point
3. If different versions apply at different times, build separate checklists
4. Clearly label the temporal dividing line for applicable law

### 10.5 Party Dispute Focus Not Fully Aligned with Framework

**Scenario:** Parties dispute something outside the core elements of the standard framework

**Handling:**
1. Still complete full extraction under the standard framework (no omission)
2. Add a "dispute-focus elements" section for issues actually disputed
3. Note the relationship between dispute focus and standard elements

## XI. Quality Checklist

Before outputting a structured element checklist, the AI agent must complete:

### Pre-extraction Checks

- [ ] Legal question type clearly identified
- [ ] Correct element framework selected
- [ ] Applicable law version (time node) confirmed
- [ ] All raw materials read at least once

### Extraction Process Checks

- [ ] Every level-1 element listed (no omission)
- [ ] Every element status-labeled (✅/❌/⚠️/➖/🔶)
- [ ] Every "satisfied" element has fact summary and source citation
- [ ] Same-level elements have no overlap (MECE–exclusive)
- [ ] All level-1 elements together cover all judgment dimensions (MECE–exhaustive)
- [ ] Exemptions / defenses and other negative elements considered
- [ ] Procedural elements considered (limitation, jurisdiction, etc., if applicable)

### Pre-output Checks

- [ ] Triple completeness check executed and results recorded
- [ ] Overall confidence labeled
- [ ] Items to be verified listed (if any)
- [ ] Explicitly labeled "may enter next stage" or "need more information"
- [ ] Output format matches standard template
- [ ] Fact summaries do not mix in legal conclusions

## XII. Complete Examples

### Example 1: Simple Scenario — General Tort Element Extraction

**Raw materials:**

> On 15 March 2024, while reversing in a shopping-mall parking lot, Zhang San failed to observe behind and knocked down Li Si who was walking through. Li Si was taken to hospital, diagnosed with a right-leg fracture, hospitalized 20 days, medical expenses RMB 32,000. Traffic police issued an accident determination finding Zhang San fully liable. Li Si lost RMB 15,000 in wages during hospitalization.

---

## Structured Element Checklist

**Legal question:** Zhang San reversed into Li Si; can Li Si require Zhang San to bear tort damages?
**Question type:** Tort liability (general tort — fault liability)
**Applicable framework:** Four elements of general tort (Civil Code Art. 1165(1))
**Extraction date:** 2024-03-20

### Element Checklist

| No. | Level | Element name | Status | Fact summary | Source / basis | Notes |
|------|------|----------|------|----------|-----------|------|
| 1 | L1 | Injurious act | ✅ | Zhang San knocked down Li Si while reversing | Civil Code Art. 1165 | Injurious act in form of commission |
| 1.1 | L2 | Manner of act | ✅ | Driving in reverse (commission) | — | — |
| 1.2 | L2 | Unlawfulness | ✅ | Failed to observe behind; breached safe-driving duty | Road Traffic Safety Law Art. 22 | Police found Zhang San fully liable |
| 2 | L1 | Damage | ✅ | Li Si right-leg fracture; 20 days hospitalization | Civil Code Art. 1165 | — |
| 2.1 | L2 | Personal injury | ✅ | Right-leg fracture | Civil Code Art. 1179 | — |
| 2.2 | L2 | Property damage | ✅ | Medical RMB 32,000 + lost wages RMB 15,000 | Civil Code Art. 1179 | Total RMB 47,000 |
| 2.3 | L2 | Mental harm | ⚠️ | Materials do not mention mental harm | Civil Code Art. 1183 | Fracture may support mental damages claim; to verify |
| 3 | L1 | Causation | ✅ | Reverse collision directly caused fracture | Civil Code Art. 1165 | Factual causation clear; police determination corroborates |
| 3.1 | L2 | Factual causation | ✅ | Collision was direct cause of fracture | — | Condition theory: no collision, no fracture |
| 3.2 | L2 | Legal causation | ✅ | Fracture from reverse collision is ordinarily foreseeable | — | Adequate causation established |
| 4 | L1 | Subjective fault | ✅ | Failed to observe behind; negligence | Civil Code Art. 1165 | Police full liability |
| 4.1 | L2 | Type of fault | ✅ | Negligence (carelessness) | — | Ought to have foreseen but did not |
| 4.2 | L2 | Degree of fault | ✅ | Full fault (police full liability) | Accident determination | — |
| 5 | L1 | Exemptions | ❌ | No exemption shown | Civil Code Arts. 1174–1177 | — |
| 5.1 | L2 | Victim fault | ❌ | Materials do not show Li Si at fault | Civil Code Art. 1173 | Police found Zhang San fully liable |
| 5.2 | L2 | Third-party cause | ❌ | No third-party intervention shown | Civil Code Art. 1175 | — |
| 5.3 | L2 | Force majeure | ❌ | None | Civil Code Art. 180 | — |
| 5.4 | L2 | Self-defense / necessity | ➖ | Not involved | — | — |
| 6 | L1 | Procedural elements | — | — | — | — |
| 6.1 | L2 | Limitation | ✅ | Accident 15 March 2024; within 3-year limitation | Civil Code Art. 188 | Expires 14 March 2027 |
| 6.2 | L2 | Jurisdiction | ⚠️ | Materials do not name a court | Civil Procedure Law Art. 29 | Court of place of tort or defendant’s domicile |

### Completeness Check Results

| Check item | Result | Explanation |
|--------|------|------|
| Framework completeness | ✅ Pass | Four elements + exemptions + procedural elements covered |
| Fact coverage | ✅ Pass | All facts in raw materials assigned to elements |
| Logical coherence | ✅ Pass | No logical contradiction among elements |

### Items to Be Verified

1. **Mental harm (element 2.3):** Confirm whether Li Si claims mental damages; disability rating from fracture
2. **Forum (element 6.2):** Confirm place of accident and defendant’s domicile for jurisdiction

### Overall confidence: High

Core four elements (injurious act, damage, causation, subjective fault) all "satisfied"; facts clear; legal sources clear. Items to verify do not affect the basic judgment that tort liability is established.

### Conclusion: ✅ May enter next stage (application of law and liability determination)

---

### Example 2: Complex Scenario — Labor Relationship Confirmation + Unlawful Termination

**Raw materials:**

> Wang joined a tech company on 1 June 2022 as a software engineer, monthly salary RMB 20,000; the company did not sign a written labor contract. Wang worked at the company office during company hours (9:00–18:00), used company computer and workstation, and accepted project-manager assignments and appraisals. Wages paid monthly by bank transfer.
>
> On 10 August 2023, the company orally told Wang "due to business adjustment, no need to come tomorrow," without stating specific termination grounds, without 30 days’ advance notice, and without any economic compensation. Wang asked for a written termination notice; the company refused.
>
> Wang had no disciplinary record; performance appraisals were all "合格" (合格) or above. The company did not pay social insurance for Wang.
>
> On 1 September 2023 Wang applied to the local labor arbitration commission seeking: (1) confirmation of labor relationship; (2) double-wage differential for failure to sign a written contract; (3) compensation for unlawful termination; (4) make-up of social insurance.

---

## Structured Element Checklist

**Legal question:** Is there a labor relationship between Wang and the tech company? Was termination unlawful? Can Wang’s claims be supported?
**Question type:** Labor dispute (relationship confirmation + unlawful termination + multiple claims)
**Applicable framework:** Labor-relationship confirmation elements + legality of labor-contract termination
**Extraction date:** 2024-03-20

> **Note:** Multiple legal issues; separate element checklists established.

---

### Checklist 1: Labor Relationship Confirmation

**Applicable framework:** MOLSS Fa [2005] No. 12, Art. 1

| No. | Level | Element name | Status | Fact summary | Source / basis | Notes |
|------|------|----------|------|----------|-----------|------|
| 1 | L1 | Proper parties | ✅ | — | MOLSS Fa [2005] No. 12 Art. 1(1) | — |
| 1.1 | L2 | Employer qualification | ✅ | "A tech company" has employer capacity | — | Company form to confirm further (LLC / sole prop., etc.) |
| 1.2 | L2 | Worker qualification | ✅ | Wang natural person, software engineer | — | Age not stated; presumed statutory working age |
| 2 | L1 | Personal subordination | ✅ | — | MOLSS Fa [2005] No. 12 Art. 1(2) | — |
| 2.1 | L2 | Observe rules | ✅ | Worked company hours (9:00–18:00) | — | Fixed hours |
| 2.2 | L2 | Accept management | ✅ | Accepted project-manager assignments and appraisals | — | Clear managerial hierarchy |
| 2.3 | L2 | Designated workplace | ✅ | Worked at company office | — | — |
| 3 | L1 | Economic subordination | ✅ | — | MOLSS Fa [2005] No. 12 Art. 1(3) | — |
| 3.1 | L2 | Remuneration | ✅ | RMB 20,000/month by bank transfer | — | Fixed salary, not project settlement |
| 3.2 | L2 | Means of production | ✅ | Company provided computer and workstation | — | Tools provided by employer |
| 4 | L1 | Organizational subordination | ✅ | Wang’s work part of company business | MOLSS Fa [2005] No. 12 Art. 1(3) | Software engineer is core business role for a tech company |

---

### Checklist 2: Double Wages for Unsigned Written Contract

**Applicable framework:** Labor Contract Law Arts. 10, 82; Implementing Regulations Arts. 6, 7

| No. | Level | Element name | Status | Fact summary | Source / basis | Notes |
|------|------|----------|------|----------|-----------|------|
| 1 | L1 | Labor relationship established | ✅ | See Checklist 1 | — | Prerequisite confirmed |
| 2 | L1 | No written contract | ✅ | "Company did not sign a written labor contract" | Labor Contract Law Art. 10 | — |
| 3 | L1 | Beyond statutory signing period | ✅ | Hired 1 June 2022 to termination 10 Aug 2023; over one month | Labor Contract Law Art. 82 | Over one month from start of employment |
| 4 | L1 | Double-wage calculation period | 🔶 | 1 July 2022 to 31 May 2023 (11 months) | Labor Contract Law Arts. 82, 14(3) | After one year deemed open-ended; double wage max 11 months |
| 5 | L1 | Arbitration limitation | 🔶 | Arbitration filed 1 Sept 2023 | Labor Dispute Mediation and Arbitration Law Art. 27 | Whether double-wage claims subject to 1-year arbitration limitation is disputed; July 2022 portion may be time-barred; depend on local adjudicative practice |
| 6 | L1 | Fault for non-signing | ⚠️ | Materials do not say whether company failed to offer or Wang refused | — | Usually employer bears signing duty; different if worker refused |

---

### Checklist 3: Unlawful Termination

**Applicable framework:** Labor Contract Law Arts. 36–43, 48, 87

| No. | Level | Element name | Status | Fact summary | Source / basis | Notes |
|------|------|----------|------|----------|-----------|------|
| 1 | L1 | Fact of termination | ✅ | 10 Aug 2023 oral notice "no need to come tomorrow" | — | Unilateral employer termination |
| 2 | L1 | Lawfulness of termination grounds | ❌ | Only "business adjustment"; no specific statutory ground | Labor Contract Law Arts. 39–41 | — |
| 2.1 | L2 | Fault-based dismissal (Art. 39) | ❌ | No disciplinary record; performance合格 or above | Labor Contract Law Art. 39 | Fits none |
| 2.2 | L2 | Non-fault dismissal (Art. 40) | ❌ | No proof of incompetence / major change of objective circumstances, etc. | Labor Contract Law Art. 40 | "Business adjustment" may relate to objective change, but no evidence |
| 2.3 | L2 | Economic layoff (Art. 41) | ⚠️ | Only oral "business adjustment"; no layoff plan, etc. | Labor Contract Law Art. 41 | Even if layoff, statutory procedure not followed |
| 3 | L1 | Lawfulness of termination procedure | ❌ | — | — | — |
| 3.1 | L2 | Advance notice | ❌ | No 30 days’ written notice or payment in lieu | Labor Contract Law Art. 40 | — |
| 3.2 | L2 | Written form | ❌ | Oral notice; refused written termination notice | Labor Contract Law Art. 50 | — |
| 3.3 | L2 | Union procedure | ⚠️ | Materials silent on whether union exists / was notified | Labor Contract Law Art. 43 | To verify |
| 4 | L1 | Economic compensation / damages | — | — | — | — |
| 4.1 | L2 | Length of service | ✅ | 1 June 2022 to 10 Aug 2023 ≈ 1 year 2 months | Labor Contract Law Art. 47 | Count as 1.5 months (≥6 months <1 year counts as 1 year) |
| 4.2 | L2 | Monthly wage standard | ✅ | RMB 20,000/month | Labor Contract Law Art. 47 | Confirm whether includes overtime, bonuses, etc. |
| 4.3 | L2 | Unlawful-termination damages | ✅ | Twice economic compensation standard | Labor Contract Law Art. 87 | 2 × 1.5 × 20000 = RMB 60,000 |
| 5 | L1 | Prohibited-termination situations | ⚠️ | Materials silent on medical period, pregnancy, etc. | Labor Contract Law Art. 42 | To verify; if present, further aggravates unlawfulness |

---

### Checklist 4: Social Insurance Make-up

| No. | Level | Element name | Status | Fact summary | Source / basis | Notes |
|------|------|----------|------|----------|-----------|------|
| 1 | L1 | Period of labor relationship | ✅ | 1 June 2022 to 10 Aug 2023 | — | — |
| 2 | L1 | Non-payment of social insurance | ✅ | "Company did not pay social insurance for Wang" | Social Insurance Law Art. 58 | — |
| 3 | L1 | Arbitration acceptance scope | 🔶 | Whether social-insurance make-up is within labor arbitration acceptance | — | Most localities treat make-up as administrative; complain to social-insurance authority; some localities’ arbitration may accept |

---

### Completeness Check Results

| Check item | Result | Explanation |
|--------|------|------|
| Framework completeness | ✅ Pass | Four legal issues each have independent complete checklists |
| Fact coverage | ✅ Pass | All facts assigned; performance records under Checklist 3 item 2.1 |
| Logical coherence | ✅ Pass | Checklists consistent; Checklist 1 conclusions are prerequisites for 2–4 |

### Items to Be Verified (by priority)

1. **[High] Fault for non-signing (Checklist 2–element 6):** Confirm whether company failed to offer or Wang refused
2. **[High] Union procedure (Checklist 3–element 3.3):** Confirm whether company has a union
3. **[Medium] Prohibited-termination situations (Checklist 3–element 5):** Medical period, pregnancy, etc.
4. **[Medium] Double-wage arbitration limitation (Checklist 2–element 5):** Local arbitration practice on double-wage limitation
5. **[Medium] Social-insurance make-up acceptance (Checklist 4–element 3):** Whether local arbitration accepts make-up claims
6. **[Low] Employer form (Checklist 1–element 1.1):** Specific organizational form
7. **[Low] Monthly wage composition (Checklist 3–element 4.2):** Whether RMB 20,000 is all remuneration

### Overall confidence: Medium

**Reasons:** Checklist 1 (relationship confirmation) high confidence; all four elements satisfied. Checklist 3 (unlawful termination) core judgment high confidence (grounds and procedure both unlawful). But double-wage limitation and social-insurance acceptance vary by locality and need confirmation. Overall, core claims (confirm relationship + unlawful-termination damages) have a sufficient analytical basis to enter the next stage, with uncertainties labeled.

### Conclusion: ✅ May enter next stage (application of law and claim assessment), but keep the 7 items to be verified labeled, and recommend the user supplement high-priority information.
