---
name: legal-document-summarization
description: |
  Trigger this skill when a structured summary is needed for judgments, rulings, mediation statements, arbitral awards, administrative penalty decisions, and other legal instruments.
  Typical trigger scenarios include, but are not limited to:
  - The user asks for a summary of a legal instrument, extraction of key points, or generation of a holding / ratio abstract
  - The user needs to convert multiple legal instruments into standardized summaries that are comparable and searchable
  - The user asks to extract case information, issues in dispute, legal authorities, or reasoning
  - The user needs summary materials for case studies, litigation analysis, or teaching preparation
  - The user asks to distinguish summary emphases across document types (judgment / ruling / mediation / arbitration / administrative penalty)
  Core value of this skill: On the basis of fidelity to the original text, convert lengthy legal instruments into concise, objective, structured summaries that highlight core content and avoid restating the full text or offering subjective evaluation.
---

> **Chinese source (authoritative):** [`../../skills/legal-document-summarization/SKILL.md`](../../skills/legal-document-summarization/SKILL.md)

# Legal Document Summarization

## Overview Table

| Item | Content |
|------|------|
| **Capability ID** | 15 |
| **Capability Name** | Legal Document Summarization |
| **Capability Type** | Information extraction and structuring |
| **Core Function** | Identify document type, extract elements, organize logic, and produce structured output for various legal instruments |
| **Input** | Full text of judgments, rulings, mediation statements, arbitral awards, administrative penalty decisions, and similar legal instruments |
| **Output** | Structured summary customized by document type (case information, facts, issues, authorities, conclusions, reasoning) |
| **Related Capabilities** | Legal document formatting (ensure normative output format); statutory retrieval (verify accuracy of legal authorities); legal reasoning (analyze reasoning logic) |
| **Key Principles** | Fidelity to the original; objectivity and neutrality; highlight the core; distinguish by type |

## Legal Disclaimer

> **Important notices:**
> 1. The summary must be faithful to the original text and must not add facts, views, or conclusions not stated in the original.
> 2. The summary must not contain subjective evaluative language (e.g., "the court wisely held," "the penalty was reasonable," "the defendant acted in bad faith").
> 3. For scanned or image-based instruments, OCR may introduce errors; uncertainties should be marked in the summary.
> 4. Summary conclusions reflect only what the instrument records and do not constitute legal opinions on the merits of the case.
> 5. For cases still pending, the summary must not disclose non-public procedural information or trade secrets.

## I. Core Concepts

### 1.1 Document Types and Summary Emphases

Different types of legal instruments have different core functions and information structures; summary emphases must adjust accordingly:

| Document Type | Core Function | Summary Emphases | Key Elements Distinguishing It from Other Types |
|----------|----------|----------|------------------------|
| **Judgment** (*panjueshu*) | Resolve substantive disputes | Fact findings, application of law, reasons for decision, disposition | The court's "findings" of fact (not parties' allegations) |
| **Ruling** (*caidingshu*) | Resolve procedural matters | Procedural background, application / objection content, ruling authorities, procedural conclusion | Does not address substantive disputes; only procedural issues |
| **Mediation statement** (*tiaojieshu*) | Confirm the parties' agreement | Matters in dispute, content of the mediation agreement, performance arrangements | Reflects mutual consent, not a coercive court adjudication |
| **Arbitral award** (*zhongcai caijueshu*) | Final award by the arbitral tribunal | Arbitration claims, fact findings, tribunal opinions, award disposition | Finality of one award; based on an arbitration agreement |
| **Administrative penalty decision** (*xingzheng chufa juedingshu*) | Administrative sanction | Unlawful facts, penalty basis, type and measure of penalty | Unilateral administrative act; subject to reconsideration and litigation |

### 1.2 Summary vs. Abridgment vs. Evaluation

```
Original text ──────────────────────────────────────→

  Summary: Extract core elements, reorganize structurally, omit non-critical details
  
  Abridgment: Compress the original proportionally, retaining a slimmed version of all information points
  
  Evaluation: Add subjective judgments and value commentary (prohibited in summaries)
```

**Essence of summarization:** Not merely shortening the original, but identifying core information, removing irrelevant details, and reorganizing information by logical structure.

### 1.3 Six-Element Extraction Framework

All legal-instrument summaries should center on the following six elements:

```
┌─────────────────────────────────────────────────┐
│  1. Case information: who, when, where, which body issued it │
│  2. Factual background: what happened (facts relevant to the conclusion) │
│  3. Issues in dispute: core legal questions to be resolved │
│  4. Legal authorities: which norms were cited │
│  5. Disposition / result: how the matter was finally handled │
│  6. Reasoning: how the conclusion was derived from facts + norms │
└─────────────────────────────────────────────────┘
```

## II. Complete Workflow

### Phase One: Preparation and Identification

#### Step 1: Identify Document Type

First determine which type the legal instrument belongs to:

| Judgment Criterion | Judgment | Ruling | Mediation Statement | Arbitral Award | Administrative Penalty Decision |
|----------|--------|--------|--------|-----------|---------------|
| **Title keywords** | "Civil Judgment," "Criminal Judgment," "Administrative Judgment" | "Civil Ruling," "Enforcement Ruling" | "Civil Mediation Statement," "Mediation Agreement" | "Arbitral Award" | "Administrative Penalty Decision" |
| **Core function** | Substantive adjudication | Procedural disposition | Confirm agreement | Arbitral adjudication | Administrative sanction |
| **Issuing body** | Court | Court | Court (confirming the parties' agreement) | Arbitration commission / tribunal | Administrative agency |

**Judgment principle:** Do not apply a format before identifying the document type; otherwise the true emphases of that document type are easily missed.

#### Step 2: Extract Case Information

Extract complete citation information from the caption or title section:

| Extraction Item | Source Location | Example |
|--------|----------|------|
| **Case name** | Caption | Meijing Co. v. Ant Co. unfair competition dispute |
| **Case / document number** | Below the title | (2024) Jing 0108 Min Chu No. 1234 |
| **Date** | End of the instrument | 7 December 2024 |
| **Issuing body** | Caption / end | Beijing Haidian District People's Court |
| **Parties** | Caption | Plaintiff: Meijing Co.; Defendant: Ant Co. |

**Requirement:** This section should retain original wording as far as possible to support retrieval and citation.

### Phase Two: Content Extraction

#### Step 3: Distill Key Facts or Procedural Background

According to document type, distill facts or procedural matters directly related to the conclusion:

**Judgments / arbitral awards / administrative penalty decisions:**
- Distill facts related to the substantive dispute
- Distinguish "facts alleged by the parties" from "facts found by the instrument"
- Retain only key facts that affect the conclusion; omit irrelevant details

**Rulings:**
- Distill procedural background (e.g., after the plaintiff sued, the defendant raised a jurisdictional objection)
- Distill the content of the application or objection
- Do not include facts of the substantive dispute

**Mediation statements:**
- Distill matters in dispute and the background of reaching mediation
- Main points of divergence between the parties
- Key factors facilitating mediation (if mentioned)

#### Step 4: Summarize Issues in Dispute

Distill the disputes in the instrument into one or more clear legal questions:

**Requirements:**
- Phrase as legal questions (answerable interrogatives)
- Capture the problems the decision truly resolved
- Avoid overly broad background descriptions

| Poor Issue Framing | Good Issue Framing |
|-------------|-------------|
| "The parties had a dispute" | "Whether Meijing Co.'s scraping of data from Ant's platform constitutes unfair competition" |
| "There is a controversy" | "Whether the defendant's jurisdictional objection is established" |
| "The compensation issue" | "Whether the plaintiff's claimed RMB 5 million in damages has factual and legal basis" |

#### Step 5: Extract the Disposition or Result

Accurately summarize the instrument's final disposition:

| Document Type | Manner of Stating the Conclusion | Example |
|----------|-------------|------|
| **Judgment** | Grant / dismiss / confirm / modify | "Judgment that the defendant cease the unfair competition at issue and compensate the plaintiff RMB 2 million for economic losses" |
| **Ruling** | Grant / dismiss / transfer / stay / terminate | "Ruling dismissing the defendant's jurisdictional objection" |
| **Mediation statement** | The parties reached the following agreement | "The parties voluntarily reached the following mediation agreement: 1. The defendant shall pay the plaintiff RMB XX by [date]..." |
| **Arbitral award** | Awards that... | "Awards that the respondent pay the claimant RMB 1 million in goods price plus overdue interest" |
| **Administrative penalty decision** | Decides to impose... | "Decides to order the party to correct the unlawful conduct and imposes a fine of RMB 500,000" |

**Key principle:** Accurately distinguish "parties' claims" from "the instrument's conclusions." Do not misstate the plaintiff's claims as the court's judgment.

#### Step 6: Extract Legal Authorities

List the legal norms cited in the instrument:

- **Statutes:** Civil Code Art. X; Criminal Law Art. X
- **Judicial interpretations:** SPC Interpretation on ... Art. X
- **Administrative regulations / departmental rules**
- **Contract clauses** (if a contract dispute)
- **Arbitration rules** (arbitral awards)
- **Administrative discretion benchmarks** (administrative penalty decisions)

**Notes:**
- Prioritize norms directly cited and used as the basis for judgment / award / penalty
- If a cited provision has been repealed or amended, that may be noted in the summary
- Norms that are "referred to" or "consulted" may be listed separately

#### Step 7: Summarize the Reasoning

Outline in concise language the logical process by which the conclusion was reached:

**The reasoning summary should show:**
1. Which facts the instrument accepted (evidence assessment)
2. How legal norms were applied (interpretation and application of provisions)
3. How main disputes and defenses were addressed (responses to opposing arguments)
4. How the conclusion was derived from facts + norms (logical chain)

**Requirements:**
- Not a mere abridgment of the original, but a demonstration of "how facts were found → how norms were applied → how the conclusion was reached"
- Concise language highlighting the causal chain
- Avoid restating the full pleadings history

### Phase Three: Output

#### Step 8: Format Output by Document Type

According to the identified document type, select the corresponding structured template for output (see output format templates in Part III).

## III. Output Format Templates

### Template A: General Six-Element Summary (Applicable to Any Legal Instrument)

```markdown
## Case Summary

### I. Case Information
- **Case name:** [name]
- **Case number:** [number]
- **Date:** [date]
- **Issuing body:** [body]
- **Parties:** [plaintiff / claimant / sanctioned party] vs [defendant / respondent / sanctioning authority]

### II. Case Facts (or Procedural Background)
[Concise statement of fact points directly related to the conclusion; use third person; retain only key information]

### III. Issues in Dispute
1. [Issue 1, phrased as a legal question]
2. [Issue 2, if any]

### IV. Conclusion
- [Conclusion on Issue 1 is...]
- [Conclusion on Issue 2 is...]

### V. Legal Authorities
- [XXX Law] Art. X
- [judicial interpretation / regulation / contract clause / arbitration rule]

### VI. Reasoning
[Outline the logical path from fact findings through application of law to the conclusion; highlight the causal chain]
```

### Template B: Judgment Summary

```markdown
## Judgment Summary

### I. Case Information
- **Case name:** [...]
- **Case number:** [...]
- **Court:** [...]
- **Decision date:** [...]

### II. Case Facts
[Cause of action, parties' identities and main claims; retain only key facts affecting the judgment]

### III. Issues in Dispute
1. [...]

### IV. Facts Found by the Court
[The court's findings on key facts (as distinct from parties' allegations)]

### V. Legal Authorities
- [...]

### VI. Disposition
- [Specific content of grant / dismissal / confirmation / modification]

### VII. Reasoning
[The court's logical chain from evidence → fact findings → application of law → conclusion]
```

### Template C: Ruling Summary

```markdown
## Ruling Summary

### I. Case Information
- **Case name:** [...]
- **Case number:** [...]
- **Court:** [...]
- **Ruling date:** [...]

### II. Procedural Background
[Procedural stage of the case, e.g., after the plaintiff sued, the defendant raised a jurisdictional objection]

### III. Content of the Application or Objection
[Specific requests or assertions of the applicant / objector]

### IV. Issues in Dispute
[Procedural question to be resolved]

### V. Legal Authorities
- [...]

### VI. Ruling Result
- [Grant / dismiss / transfer / stay / terminate]

### VII. Reasoning
[The court's analytical logic on the procedural question]
```

### Template D: Mediation Statement Summary

```markdown
## Mediation Statement Summary

### I. Case Information
- **Case name:** [...]
- **Case number:** [...]
- **Court:** [...]
- **Mediation date:** [...]

### II. Case Background
[Matters in dispute and the background of reaching mediation]

### III. Mediation Matters
[Core matters in dispute between the parties]

### IV. Content of the Mediation Agreement
- Article 1: [...]
- Article 2: [...]
- [Manner of performance, deadlines, liability for breach, etc.]

### V. Legal Authorities
- [Legal basis confirming the validity of the mediation agreement]

### VI. Result
[The mediation agreement is confirmed by the court and has legal effect]
```

### Template E: Arbitral Award Summary

```markdown
## Arbitral Award Summary

### I. Case Information
- **Case name:** [...]
- **Case number:** [...]
- **Arbitration institution:** [...]
- **Award date:** [...]
- **Tribunal composition:** [sole arbitrator / three-member tribunal]

### II. Case Facts
[Arbitration claims and disputed facts; retain only content related to the award]

### III. Issues in Dispute
[Core questions the tribunal needed to resolve]

### IV. Facts Found by the Tribunal
[The tribunal's findings of fact]

### V. Legal Authorities
- [arbitration agreement / arbitration rules]
- [substantive legal norms]

### VI. Award Disposition
- [...]
- [Note on finality of one award]

### VII. Reasoning
[The tribunal's analytical logic]
```

### Template F: Administrative Penalty Decision Summary

```markdown
## Administrative Penalty Decision Summary

### I. Case Information
- **Penalty decision document number:** [...]
- **Issuing authority:** [...]
- **Date:** [...]

### II. Party Information
- **Sanctioned party:** [name]
- **Unified social credit code / ID number:** [...]

### III. Unlawful Facts
[Unlawful facts found upon investigation; state objectively]

### IV. Issues in Dispute (if statements or defenses were made)
[The party's defense and the agency's response]

### V. Legal Authorities
- [Basis for finding unlawfulness]
- [Basis for the penalty]
- [Discretion benchmarks for the penalty]

### VI. Penalty Result
- [Type of penalty: fine / order to correct / revoke license, etc.]
- [Measure / amount]
- [Manner and deadline for performance]

### VII. Reasoning
[The agency's explanation of fact findings, application of law, and discretion as to the penalty measure]

### VIII. Remedies
- **Administrative reconsideration:** [deadline, authority]
- **Administrative litigation:** [deadline, court with jurisdiction]
```

## IV. Examples

### Example 1: Civil Judgment Summary

**Input (key points from the original):**
> Beijing Haidian District People's Court Civil Judgment (2024) Jing 0108 Min Chu No. 1234. Plaintiff Meijing Co. sued defendant Ant Co. for unfair competition. Plaintiff alleged that Ant Co. scraped data from plaintiff's "XX Data Platform" by technical means for use in its own product operations, constituting unfair competition. Defendant argued that it scraped publicly available data and had taken reasonable measures, and thus did not constitute unfair competition. Court findings: Defendant scraped plaintiff's platform data without permission; although some of the data was public, substantial cost was required to collect and organize it; defendant's conduct substantially substituted for plaintiff's data product, harmed plaintiff's lawful rights and interests, and disrupted market competition order. Judgment: (1) Defendant shall immediately cease the unfair competition at issue; (2) Defendant shall compensate plaintiff RMB 2 million for economic losses and RMB 100,000 for reasonable expenses.

**Output:**

```markdown
## Judgment Summary

### I. Case Information
- **Case name:** Meijing Co. v. Ant Co. unfair competition dispute
- **Case number:** (2024) Jing 0108 Min Chu No. 1234
- **Court:** Beijing Haidian District People's Court
- **Decision date:** [date in original]

### II. Case Facts
Plaintiff Meijing Co. operates the "XX Data Platform" and invested substantial cost to collect and organize data. Defendant Ant Co. scraped data from plaintiff's platform by technical means for use in its own product operations. Plaintiff sued, alleging that defendant's conduct constituted unfair competition.

### III. Issues in Dispute
1. Whether defendant's scraping of plaintiff's platform data constitutes unfair competition?
2. If it constitutes unfair competition, how should the amount of damages be determined?

### IV. Facts Found by the Court
- Defendant scraped plaintiff's platform data without permission
- Although some of the data at issue was public, substantial cost was required to collect and organize it
- Defendant's conduct substantially substituted for plaintiff's data product
- Defendant's conduct harmed plaintiff's lawful rights and interests and disrupted market competition order

### V. Legal Authorities
- Anti-Unfair Competition Law Art. 2 (general clause)
- Anti-Unfair Competition Law Art. 12 (internet-specific clause)

### VI. Disposition
1. Defendant shall immediately cease the unfair competition at issue
2. Defendant shall compensate plaintiff RMB 2 million for economic losses
3. Defendant shall compensate plaintiff RMB 100,000 for reasonable expenses

### VII. Reasoning
The court found that plaintiff enjoyed competitive interests in its platform data; defendant's scraping without permission and substantial substitution for plaintiff's data product violated the principle of good faith and recognized commercial ethics, disrupted market competition order, and constituted unfair competition. As to the amount of damages, the court comprehensively considered the market value of plaintiff's data product, the nature and duration of defendant's infringement, and other factors, and assessed damages at RMB 2 million.
```

### Example 2: Ruling Summary

**Input (key points from the original):**
> Beijing No. 1 Intermediate People's Court Civil Ruling. Plaintiff Meijing Co. sued defendant Ant Co. for unfair competition in Haidian District Court. Within the answer period, defendant raised a jurisdictional objection, asserting that the case should be heard by the court at defendant's domicile (Chaoyang District, Beijing). Haidian District Court held that this was an unfair competition dispute and that the court at the place of infringement (Haidian District) had jurisdiction, and ruled to dismiss the defendant's jurisdictional objection. Defendant appealed. The Intermediate Court held that the alleged infringement occurred in Haidian District, and Haidian District Court, as the court at the place of infringement, had jurisdiction. Ruling: appeal dismissed; original ruling affirmed.

**Output:**

```markdown
## Ruling Summary

### I. Case Information
- **Case name:** Meijing Co. v. Ant Co. unfair competition dispute (appeal on jurisdictional objection)
- **Case number:** [case number]
- **Court:** Beijing No. 1 Intermediate People's Court
- **Ruling date:** [date]

### II. Procedural Background
Plaintiff sued in Haidian District Court; defendant raised a jurisdictional objection; the court of first instance ruled to dismiss. Defendant appealed.

### III. Content of the Application or Objection
Appellant (defendant at first instance) asserted that the case should be heard by the court at defendant's domicile (Chaoyang District Court).

### IV. Issues in Dispute
Should the case be heard by the court at the defendant's domicile, or by the court at the place of infringement?

### V. Legal Authorities
- Civil Procedure Law Art. 29 (jurisdiction at the place of infringement)
- Civil Procedure Law Art. 130 (review of jurisdictional objections)

### VI. Ruling Result
Ruling dismissing the appeal and affirming the original ruling (Haidian District Court has jurisdiction over this case).

### VII. Reasoning
The appellate court held that this was an unfair competition dispute and that the alleged infringement occurred in Haidian District. Under Civil Procedure Law Art. 29, actions arising from infringement are heard by the court at the place of infringement or at the defendant's domicile. Haidian District, as the place of infringement, has jurisdiction. The first-instance ruling was correct and should be affirmed.
```

### Example 3: Administrative Penalty Decision Summary

**Input (key points from the original):**
> Beijing Municipal Administration for Market Regulation Administrative Penalty Decision. Party: a certain technology company Ltd. Upon investigation, the party collected users' clipboard information in its operated App without user consent, for identifying user acquisition channels. This violated Personal Information Protection Law Arts. 13 and 16. The party defended that it collected information to optimize user experience and had applied anonymization. The agency held that clipboard information is personal information; collection without prior user consent violated the minimum-necessity principle; the anonymization defense failed. Penalty decision: order correction of the unlawful conduct and impose a fine of RMB 500,000.

**Output:**

```markdown
## Administrative Penalty Decision Summary

### I. Case Information
- **Penalty decision document number:** [number]
- **Issuing authority:** Beijing Municipal Administration for Market Regulation
- **Date:** [date]

### II. Party Information
- **Sanctioned party:** a certain technology company Ltd.
- **Unified social credit code:** [...]

### III. Unlawful Facts
In its operated App, the party collected users' clipboard information without user consent for identifying user acquisition channels.

### IV. Issues in Dispute
1. Is clipboard information personal information subject to protection?
2. Do the party's defenses based on "optimizing user experience" and "anonymization" succeed?

### V. Legal Authorities
- **Basis for finding unlawfulness:** Personal Information Protection Law Art. 13 (processing personal information requires the individual's consent); Art. 16 (may not refuse to provide products or services on the ground that the individual does not consent to processing or withdraws consent)
- **Basis for penalty:** Personal Information Protection Law Art. 66

### VI. Penalty Result
- Order correction of the unlawful conduct
- Fine of RMB 500,000

### VII. Reasoning
The agency found: clipboard information can identify a specific natural person and constitutes personal information. The party collected it without obtaining user consent beforehand, and the collection exceeded what was necessary to achieve product functions, violating the minimum-necessity principle. The purpose of "optimizing user experience" does not exempt the consent obligation, and the "anonymization" defense was inconsistent with the facts. Comprehensively considering the nature, circumstances, and degree of harm of the unlawful conduct, a fine of RMB 500,000 was imposed.

### VIII. Remedies
- **Administrative reconsideration:** Apply to [reconsideration authority] within 60 days of receipt of the decision
- **Administrative litigation:** File with [court of jurisdiction] within 6 months of receipt of the decision
```

## V. Common Errors and Prevention

| Error Type | Error Description | Consequences | Preventive Measures |
|----------|----------|------|----------|
| **Wrong document-type identification** | Summarizing a ruling in judgment format and extracting lengthy substantive disputes | Summary emphases completely off; true procedural issues missed | Identify document type first, then select the matching template |
| **Confusing allegations with findings** | Writing facts alleged by the plaintiff as "facts found by the court" | Inaccurate summary; misleads readers | Strictly distinguish "parties' allegations" from "instrument findings"; mark the source of the latter |
| **Overly broad issues** | "The parties had a dispute" / "there is a controversy" | Fails to reveal the legal questions the case truly needed to resolve | Phrase issues as answerable legal questions |
| **Mixing in subjective evaluation** | "The court wisely held" / "the penalty was quite reasonable" | Violates objectivity and neutrality | Delete all evaluative adjectives; state only facts and conclusions |
| **Restating rather than summarizing** | Long quotations from the original with only light cuts | Loses the value of a summary; remains lengthy | Extract core elements, then reorganize in summarizing language |
| **Omitting legal authorities** | Writing only "pursuant to relevant legal provisions" | Cannot trace the normative basis of the decision / penalty | List specific provisions cited, item by item |
| **Empty reasoning** | "The court rendered judgment according to law" | No logical chain; readers cannot see how the conclusion was reached | Show the full chain "fact findings → application of norms → derivation of conclusion" |
| **Ignoring procedural boilerplate** | Retaining lengthy service history, hearing notices, and collegial panel composition | Inflates length; core information is buried | Compress or omit procedural content that does not affect the conclusion |

## VI. Special Scenario Handling

### 6.1 Multi-Defendant / Multi-Plaintiff Cases

- Clearly list all parties' litigation status in the "Parties" section
- Distinguish each party's different claims and conduct in "Case Facts"
- Separately list dispositions as to each party in "Disposition"

### 6.2 Series / Related Cases

- At the start of the summary, mark the relationship between this case and related cases
- If the disposition depends on another case's judgment, state that
- For batch litigation (e.g., securities misrepresentation series), simplify common facts and highlight case-specific differences

### 6.3 Second-Instance / Retrial Instruments

- **Second-instance judgment summary:** Focus on differences between first-instance findings and second-instance modification / affirmance, and the appellate court's reasons for modification
- **Retrial instrument summary:** Focus on the parties' grounds for applying for retrial and the court's review conclusions regarding the prior proceedings
- Explain the instance history in "Procedural Background"

### 6.4 Scanned / OCR-Recognized Instruments

- Where recognition of text is uncertain, mark with `[?]` in the summary
- Especially mark critical numbers (amounts, dates, case numbers) if unclear
- Advise the user to verify against the original, especially article numbers of legal authorities

### 6.5 Foreign-Related / Hong Kong–Macao–Taiwan Cases

- Note the applicable law (Chinese law, foreign law, international treaties)
- If conflict-of-laws rules are involved, state the governing law chosen by the court
- For rulings involving service abroad, taking of evidence abroad, and similar procedural issues, extract these as emphases

### 6.6 Class Actions / Representative Actions

- In "Parties," explain the litigation representatives and the represented plaintiff group
- In "Case Facts," summarize the common factual basis
- In "Disposition," state the scope of effect of the judgment

## VII. Quality Checklist

```markdown
□ 1. Has the document type been accurately identified (judgment / ruling / mediation / arbitration / administrative penalty)?
□ 2. Is case information complete (name, case number, date, issuing body, parties)?
□ 3. Does the facts section retain only information directly related to the conclusion?
□ 4. Have "parties' allegations" and "instrument findings" been strictly distinguished?
□ 5. Have issues in dispute been distilled into clear legal questions?
□ 6. Does the conclusion accurately reflect the instrument's final disposition?
□ 7. Have legal authorities been listed with specific provisions (statute name + article number)?
□ 8. Does the reasoning show the logical chain "facts → norms → conclusion"?
□ 9. Is the summary free of any subjective evaluative language?
□ 10. Does the output format match the document type (correct template used)?
□ 11. Has procedural boilerplate been appropriately compressed?
□ 12. Have uncertainties from scanned / OCR recognition been marked?
```

## VIII. Related Skills

| Related Skill | Relationship | Notes |
|----------|------|------|
| Legal document formatting | Complementary | Ensure normative summary format and clean layout |
| Statutory retrieval | Upstream / parallel | Verify that legal authorities extracted in the summary remain currently in force |
| Legal reasoning | Downstream | Further analyze reasoning logic and argumentative structure on the basis of the summary |
| Legal concept comprehension | Upstream | Understand key legal concepts appearing in the summary (e.g., "public order and good morals," "good faith") |
| Similar-case retrieval and analysis | Downstream | Compare and analyze after summarizing multiple instruments |
| Multi-document summarization | Extension | When batch summarization and comparison of multiple instruments are needed |

## IX. Limitations and Risk Notices

- **Dependence on information completeness:** Summary quality depends entirely on the completeness and clarity of the original. If the original is logically confused or insufficiently reasoned, the summary cannot cure that.
- **OCR recognition risk:** OCR of scans may misrecognize characters, numbers, or punctuation; for critical information, advise the user to verify against the original.
- **Subjective understanding bias:** Although summaries require objectivity and neutrality, selecting "key facts" and distilling "issues in dispute" still inevitably involve judgment; different persons may emphasize different points.
- **Format limits:** Standardized templates cannot cover all special document types; for novel or uncommon instruments, flexibly adjust on the basis of the general six-element framework.
- **Currency:** The currency of legal authorities is judged as of the instrument's issuance; provisions cited in the summary may later have been amended; if used for current legal analysis, verify separately.
- **Confidential information:** For cases involving closed hearings, trade secrets, or personal privacy, the summary must observe disclosure limits and, where necessary, redact sensitive information.
