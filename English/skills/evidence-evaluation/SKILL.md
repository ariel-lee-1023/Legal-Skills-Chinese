---
name: evidence-evaluation
description: |
  Trigger this skill when evidence materials in a case need to be assessed for authenticity, legality, and relevance (the “three attributes” of evidence / 三性), as well as for probative value.
  Typical trigger scenarios include, but are not limited to:
  - After a party or counsel submits evidence, assessing whether the court is likely to admit it
  - Responding to and analyzing the opposing party’s cross-examination / challenge opinions on one’s own evidence
  - Conducting a comprehensive evaluation of all evidence in the case to determine whether facts to be proved are established
  - Determining whether evidence meets the applicable standard of proof (e.g., high degree of probability, beyond reasonable doubt)
  - Identifying weak links in the chain of evidence and proposing reinforcement recommendations
  - Assessing the validity of special forms of evidence such as electronic data, expert opinions, and witness testimony
  - Identifying and arguing exclusion of illegally obtained evidence
---

> **Chinese source (authoritative):** [`../../skills/evidence-evaluation/SKILL.md`](../../skills/evidence-evaluation/SKILL.md)

# Evidentiary Validity Evaluation

## Overview Table

| Item | Content |
|------|------|
| **Capability name** | Evidentiary Validity Evaluation |
| **Capability ID** | 12 |
| **Core function** | Assess evidence authenticity, legality, relevance, and probative value |
| **Applicable domains** | Civil litigation, criminal litigation, administrative litigation, arbitration |
| **Key legal sources** | Provisions on evidence in the *Civil Procedure Law*, *Criminal Procedure Law*, and *Administrative Litigation Law*, and their respective judicial interpretations; *Several Provisions of the Supreme People’s Court on Evidence in Civil Litigation* (2019 Amendment); evidence chapters of the *Interpretation of the Supreme People’s Court on the Application of the Criminal Procedure Law of the People’s Republic of China*; *Provisions of the Supreme People’s Court on Several Issues Concerning Evidence in Administrative Litigation* |
| **Output** | Evidentiary validity evaluation report (including item-by-item conclusions, overall probative-value judgment, and reinforcement recommendations) |
| **Risk level** | High (evidence evaluation directly affects fact-finding and outcomes) |

---

## Legal Disclaimer

> **Important notice:** The evidentiary validity evaluation provided by this skill is assistive legal analysis and does not constitute a formal legal opinion. Whether evidence is ultimately admitted is decided by the court in accordance with law. Users should note:
> 1. Evidence evaluation depends heavily on specific case facts and examination of originals/original objects; AI cannot directly perceive physical evidence
> 2. Authenticity determinations often require courtroom cross-examination, expert examination, and similar procedures; AI evaluation is preliminary analysis only
> 3. Evidence rules and standards of proof differ substantially across litigation types (civil / criminal / administrative)
> 4. AI evaluation results should be reviewed by a practicing lawyer or legal professional before use

---

## I. Core Conceptual Framework

### 1.1 The “Three Attributes” of Evidence (三性) Framework

```
Evidentiary Validity Evaluation
├── Evidentiary competence (admissibility)
│   ├── Authenticity (真实性 / Authenticity)
│   │   ├── Formal authenticity: whether the evidence medium itself is genuine and untampered
│   │   └── Substantive authenticity: whether the content reflected by the evidence accords with objective facts
│   ├── Legality (合法性 / Legality)
│   │   ├── Subject legality: whether the party collecting the evidence was qualified
│   │   ├── Formal legality: whether the form of the evidence meets statutory requirements
│   │   ├── Procedural legality: whether collection procedures were lawful
│   │   └── Content legality: whether the content does not violate prohibitory legal rules
│   └── Relevance (关联性 / Relevance)
│       ├── Direct relevance: a direct proving relationship between the evidence and the fact to be proved
│       └── Indirect relevance: an indirect inferential relationship between the evidence and the fact to be proved
└── Probative value (证明力 / Probative Value)
    ├── Probative value of a single item: the degree to which one item proves the fact to be proved
    ├── Corroboration among items: mutual corroboration or contradiction among multiple items
    └── Completeness of the evidence chain: whether all evidence forms a complete chain of proof
```

### 1.2 Types of Evidence and Statutory Forms

| Litigation type | Statutory types of evidence | Legal basis |
|----------|-------------|---------|
| **Civil litigation** | Party statements, documentary evidence, physical evidence, audiovisual materials, electronic data, witness testimony, expert opinions, inspection records | Art. 66, *Civil Procedure Law* |
| **Criminal litigation** | Physical evidence, documentary evidence, witness testimony, victim statements, confessions and defenses of criminal suspects/defendants, expert opinions, records of inspection/examination/identification/investigative experiments, etc., audiovisual materials/electronic data | Art. 50, *Criminal Procedure Law* |
| **Administrative litigation** | Documentary evidence, physical evidence, audiovisual materials, electronic data, witness testimony, party statements, expert opinions, inspection records / on-site records | Art. 33, *Administrative Litigation Law* |

### 1.3 Standards of Proof

| Standard of proof | Applicable scenarios | Specific requirements |
|----------|---------|---------|
| **Beyond reasonable doubt** | Conviction in criminal cases (prosecution’s burden) | Evidence is reliable and sufficient; reasonable doubt is excluded; evidence used for adjudication has been verified as true through statutory procedures; all case evidence forms a complete system of proof |
| **High degree of probability** | Ordinary facts in civil cases | The probative value of one party’s evidence is clearly greater than the other’s; the judge is inwardly convinced that the probability the fact exists exceeds the probability it does not (commonly understood as above ~75%) |
| **Elevated standard of proof** | Civil matters such as fraud, coercion, malicious collusion, oral wills, gifts, etc. | Higher than high degree of probability; below beyond reasonable doubt but clearly above the ordinary civil standard |
| **Preponderance of evidence** | Procedural facts and similar matters in civil cases | Relatively greater probative value is sufficient |
| **Clear preponderance** | Administrative litigation (agency’s burden) | Evidence of the legality of the administrative act should meet a clear-preponderance standard |

### 1.4 Allocation of the Burden of Proof

| Litigation type | General rule | Special rules |
|----------|---------|---------|
| **Civil litigation** | “He who asserts must prove” (Art. 67, *Civil Procedure Law*) | Reversal of the burden of proof (e.g., medical harm, environmental pollution, product liability); legal presumptions |
| **Criminal litigation** | In public prosecutions, the prosecuting authority bears the burden of proof | Burden shifting in special offenses such as possessing a huge amount of property from unidentified sources; the defendant bears limited rebuttal responsibility |
| **Administrative litigation** | The defendant (administrative agency) bears the burden of proving the legality of the administrative act | The plaintiff bears the burden on standing/conditions for suit, damages claimed, etc. |

---

## II. Complete Workflow

### Stage One: Evidence Information Collection and Classification

**Step 1: Identify basic information for each item of evidence**

For each evidence material, extract the following:

```
- Evidence number / name
- Type of evidence (documentary / physical / electronic data / witness testimony / expert opinion, etc.)
- Source of evidence (who provided it, how obtained)
- Form of evidence (original / copy / duplicate / reproduction)
- Time of submission
- Fact intended to be proved (purpose of proof)
- Litigation type (civil / criminal / administrative)
```

**Step 2: Determine the facts to be proved**

```
- List all facts to be proved in the case
- Map each fact to corresponding evidence
- Label the allocation of the burden of proof for each fact
- Determine the applicable standard of proof
```

**Step 3: Classify and organize evidence**

```
Classify along the following dimensions:
├── By type of evidence
├── By fact to be proved
├── By submitting party (plaintiff / defendant / third party / court-obtained)
└── By nature of evidence (direct / indirect; original / hearsay-derived; affirmative / rebuttal)
```

### Stage Two: Item-by-Item Review of the “Three Attributes” (三性)

**Step 4: Authenticity review**

```
Review checklist:
□ Is documentary evidence an original? Has a copy been checked against the original?
□ Is physical evidence the original object? Is there damage, deterioration, or contamination?
□ Does electronic data have complete generation, storage, and transmission records? Has it been notarized or preserved on a blockchain?
□ Is witness testimony based on the witness’s personal perception? Is there hearsay?
□ Are the materials submitted for expert examination authentic and complete?
□ Are audiovisual materials on the original medium? Are there signs of editing or splicing?
□ Are there internal contradictions in the content of the evidence?
□ Does the evidence contradict other known facts?
□ Is there contrary evidence showing the item is not authentic?
□ Does the time the evidence was formed align with the case timeline?
```

**Step 5: Legality review**

```
Review checklist:
□ Was the collecting subject qualified?
  - Civil: parties, agents, notarial offices, etc.
  - Criminal: investigative organs and their personnel (compliance with recusal rules)
  - Administrative: collected by the agency when making the administrative act (post-act collection generally not permitted)
□ Were collection procedures lawful?
  - Was there torture to extract confession, violence, threats, or other illegal means?
  - Were search and seizure conducted with lawful formalities?
  - Were technical investigation measures approved?
  - Were others’ lawful rights and interests infringed (e.g., illegal wiretapping, secret filming)?
□ Is the form of the evidence lawful?
  - Does documentary evidence meet statutory formal requirements?
  - Was the expert opinion issued by a qualified institution and qualified experts?
  - Does the witness have capacity to testify?
  - Does the inspection record bear witness signatures?
□ Does it fall within illegally obtained evidence that must be excluded?
  - Criminal: confessions collected by torture or other illegal methods (absolute exclusion)
  - Criminal: witness testimony and victim statements collected by violence, threats, or other illegal methods (absolute exclusion)
  - Criminal: physical or documentary evidence collected in violation of statutory procedure that may seriously affect judicial fairness and cannot be cured or reasonably explained (discretionary exclusion)
  - Civil: evidence formed or obtained by methods that seriously infringe others’ lawful rights and interests, violate prohibitory legal rules, or seriously violate public order and good morals
```

**Step 6: Relevance review**

```
Review checklist:
□ Is there a logical connection between the evidence and the fact to be proved?
□ Is the connection direct or indirect?
  - Direct evidence: can alone and directly prove the fact to be proved
  - Indirect evidence: must be combined with other evidence to prove the fact to be proved
□ How strong is the relevance? (strong / medium / weak)
□ Is the evidence related to the disputed focus of the case?
□ Is the inferential chain for indirect evidence reasonable and complete?
□ Is relevance so weak that the item lacks evidentiary value?
```

### Stage Three: Probative Value Assessment

**Step 7: Probative value of a single item**

Apply different assessment rules by type of evidence:

**7.1 Documentary evidence — probative value rules**

| Assessment factor | High probative value | Low probative value |
|----------|---------|---------|
| Medium / form | Original | Copy (cannot be checked against original) |
| Maker | State organs, notarial institutions | Privately made |
| Manner of formation | Formed in the ordinary course of business | Made specifically for litigation |
| Nature of content | Statements adverse to the maker | Statements favorable to the maker |
| Signatures / seals | Complete signature, seal, and date | No signature or signature in doubt |

**7.2 Witness testimony — probative value rules**

| Assessment factor | High probative value | Low probative value |
|----------|---------|---------|
| Mode of perception | Personal perception | Hearsay / speculation / comment |
| Interest | No interest in relation to the parties | Interest with one party |
| Appearance in court | Appeared and submitted to cross-examination | Written testimony only, no appearance |
| Cognitive capacity | Normal cognition, memory, and expression | Limited capacity (young age, mental disorder, etc.) |
| Consistency | Consistent statements over time | Contradictions or repeated changes |
| Level of detail | Rich and specific detail | Vague and general |

**7.3 Electronic data — probative value rules**

| Assessment factor | High probative value | Low probative value |
|----------|---------|---------|
| Preservation method | Notarial preservation / blockchain preservation / original records of a third-party platform | Printed screenshots |
| Integrity | Complete data chain (generation–storage–transmission–extraction) | Fragmented excerpts lacking context |
| Anti-tampering | Hash verification / timestamp | Cannot prove absence of tampering |
| Extraction procedure | Extracted lawfully by a professional institution | Extracted by the party themselves |
| Proof of linkage | Can link to a specific subject (e.g., real-name authentication) | Cannot confirm the user’s identity |

**7.4 Expert opinions — probative value rules**

| Assessment factor | High probative value | Low probative value |
|----------|---------|---------|
| Expert institution | Statutory qualification, good reputation | Qualification in doubt or examination beyond scope |
| Expert | Corresponding professional competence and practice qualification | Unqualified or recusal grounds exist |
| Examined materials | Clear source, complete chain of custody | Unclear source or broken chain of custody |
| Methodology | National standards or industry-recognized methods | Nonstandard or outdated methods |
| Process | Complete records, reproducible verification | Missing process records |
| Formulation of conclusion | Clear and specific | Vague or overly conditional |

**7.5 Party statements — probative value rules**

| Assessment factor | High probative value | Low probative value |
|----------|---------|---------|
| Nature of content | Adverse to the stating party (admission) | Favorable to the stating party |
| Consistency | Consistent over time | Contradictory over time |
| Corroboration | Corroborated by other evidence | Lone evidence, no corroboration |
| Specificity | Concrete and detailed | Vague or evasive |

**Step 8: Analysis of corroboration among items of evidence**

```
Analytical framework:
1. Draw an evidence-relationship map
   - Mark the fact each item points to
   - Mark corroboration relationships among items (consistent / contradictory / complementary)
   
2. Identify corroboration patterns
   - Full corroboration: multiple items fully consistent on key facts
   - Partial corroboration: consistent on main facts, differences in detail
   - Mutual contradiction: irreconcilable contradictions among items
   
3. Contradiction analysis and handling
   - Analyze causes (memory bias / different positions / fabricated evidence)
   - Judge whether contradictions affect core fact-finding
   - Determine rules for accepting or rejecting contradictory evidence
```

**Step 9: Completeness of the evidence chain**

```
Assessment criteria:
□ Does the evidence chain cover all key links of the facts to be proved?
□ Are there breaks in the chain (a key link lacking evidentiary support)?
□ Do indirect items form a complete logical chain?
□ Is the conclusion from the chain unique (criminal cases) or at a high degree of probability (civil cases)?
□ Are there reasonable alternative explanations that have not been excluded?
```

### Stage Four: Comprehensive Judgment and Conclusions

**Step 10: Overall probative-value judgment**

```
1. For each fact to be proved, aggregate assessment results for all related evidence
2. Weigh the probative value of supporting and opposing evidence
3. Against the applicable standard of proof, judge whether the fact is established
4. Clearly flag uncertain facts and explain why
```

**Step 11: Form evaluation conclusions**

```
Types of conclusions:
- Evidence sufficient: the fact meets the standard of proof and may be found established
- Evidence basically sufficient: main facts are supported; individual details need reinforcement
- Evidence insufficient: the standard of proof is not met; the fact is difficult to find established
- Evidence contradictory: supporting and opposing evidence are roughly equal; further investigation needed
```

**Step 12: Propose reinforcement recommendations**

```
For weak links, propose:
- Types and content of evidence that need to be supplemented
- Recommendations for fixing and preserving existing evidence
- Cross-examination strategy recommendations (e.g., apply for witness appearance, apply for expert examination)
- Reminders on proof deadlines and procedures
```

---

## III. Common Domains and Legal-Source Cross-Reference

### 3.1 Civil Litigation Evidence Rules

| Rule | Legal basis | Core content |
|------|---------|---------|
| Documentary evidence submission | Arts. 47–49, *Civil Evidence Provisions* | Where a party controlling documentary evidence refuses without justified reason to produce it, the court may find the opposing party’s claim established |
| Admission (自认) | Arts. 3–9, *Civil Evidence Provisions* | One party’s admission of an adverse fact relieves the other of the burden of proof; in joint actions, one person’s admission does not automatically bind others |
| Evidence preservation | Art. 84, *Civil Procedure Law* | Where evidence may be destroyed or become difficult to obtain later, preservation may be applied for |
| Time limit for producing evidence | Arts. 51–56, *Civil Evidence Provisions* | Legal consequences of late submission (admonition, fine; exclusion is not lightly applied) |
| Electronic data rules | Arts. 14–15, *Civil Evidence Provisions* | Scope of electronic data and factors for authenticity review |
| Evidence formed abroad | Art. 16, *Civil Evidence Provisions* | Evidence formed outside the territory should go through notarization and authentication formalities |

### 3.2 Criminal Litigation Evidence Rules

| Rule | Legal basis | Core content |
|------|---------|---------|
| Exclusion of illegally obtained evidence | Art. 56, *Criminal Procedure Law*; *Provisions on Several Issues Concerning Strict Exclusion of Illegally Obtained Evidence in Handling Criminal Cases* | Confessions obtained by torture are absolutely excluded; illegal real evidence is subject to discretionary exclusion |
| Reliable and sufficient evidence standard | Art. 55, *Criminal Procedure Law* | Facts for conviction and sentencing are all proved by evidence; evidence used for adjudication has been verified as true through statutory procedures; considering all evidence, reasonable doubt is excluded |
| Witness appearance | Arts. 252–256, *Criminal Procedure Law Interpretation* | Where the prosecutor, party, or defender objects to witness testimony that has major impact on conviction or sentencing, the witness shall appear |
| Evidence standard in death-penalty cases | *Provisions on Several Issues Concerning Examining and Judging Evidence in Death-Penalty Cases* | Death-penalty cases apply the strictest evidence standards |
| Technical investigation evidence | Art. 152, *Criminal Procedure Law* | Materials collected through technical investigation may be used as evidence, subject to approval |
| Curing defective evidence | Related articles of the *Criminal Procedure Law Interpretation* | Evidence with collection-procedure defects that can be cured or reasonably explained may be used |

### 3.3 Administrative Litigation Evidence Rules

| Rule | Legal basis | Core content |
|------|---------|---------|
| Defendant’s burden of proof | Art. 34, *Administrative Litigation Law* | The defendant bears the burden of proving the legality of the administrative act |
| Limits on defendant evidence collection | Art. 35, *Administrative Litigation Law* | The defendant may not, during litigation, on its own collect evidence from the plaintiff or witnesses |
| Defendant’s time limit for producing evidence | Art. 67, *Administrative Litigation Law* | The defendant shall submit evidence within 15 days of receiving a copy of the complaint |
| Court investigation for evidence | Art. 40, *Administrative Litigation Law* | The court may obtain evidence from relevant administrative agencies and other organizations or citizens |
| Review of normative documents | Art. 53, *Administrative Litigation Law* | Normative documents below the level of rules may be reviewed incidentally |

### 3.4 Special Rules for Particular Types of Evidence

| Type of evidence | Key rules | Points of attention |
|----------|---------|---------|
| **Notarial instruments** | Notarized instruments have preferential probative value, unless contrary evidence is sufficient to overturn them | Check whether notarial procedure was lawful; whether the notarial certificate remains valid |
| **Evidence formed abroad** | Must be notarized by the competent notarial authority of the place of formation and authenticated by the Chinese embassy or consulate there | Special rules apply to evidence from Hong Kong, Macao, and Taiwan |
| **Audiovisual materials** | Doubtful audiovisual materials cannot alone serve as the basis for finding facts | Check lawful acquisition; whether technical examination has been conducted |
| **Electronic data** | Review integrity and reliability of generation, storage, transmission, and extraction | Note the probative-value difference between original platform records and screenshots |
| **Expert-assistant opinions** | Expert assistants appear to opine on expert opinions or specialized issues | Not a statutory type of evidence, but may affect whether expert opinions are accepted |

---

## IV. Verification and Screening Rules

### 4.1 Admissibility Screening (Threshold Review)

```
Gate 1: Formal review
├── Is it a statutory type of evidence? → No → Do not admit
├── Was it submitted within the proof time limit? → No → Review whether there is justified reason
├── Does it meet statutory formal requirements? → No → Review whether it can be cured
└── Pass → Proceed to Gate 2

Gate 2: Legality review
├── Are there grounds for exclusion of illegally obtained evidence? → Yes → Initiate exclusion procedure
├── Are there defects in collection procedure? → Yes → Review whether they can be cured / reasonably explained
├── Did collection methods infringe lawful rights and interests? → Yes → Review severity
└── Pass → Proceed to Gate 3

Gate 3: Relevance review
├── Is there a logical connection to the fact to be proved? → No → Do not admit
├── Is relevance strong enough to have evidentiary value? → No → Do not admit
└── Pass → Proceed to probative-value assessment

Gate 4: Authenticity review
├── Is the evidence medium authentic? → In doubt → Apply for expert examination / reinforcement
├── Is the content authentic? → In doubt → Judge comprehensively with other evidence
└── Pass → Determine the level of probative value
```

### 4.2 Preferential Probative-Value Rules (Civil Litigation)

Under the *Civil Evidence Provisions* and judicial practice, probative value generally follows this preferential order:

```
1. Official documentary evidence made by state organs or social organizations pursuant to authority > other documentary evidence
2. Physical evidence, archives, expert opinions, inspection records, and notarized or registered documentary evidence > other documentary evidence, audiovisual materials, and witness testimony
3. Original evidence > hearsay-derived / transmitted evidence
4. Direct evidence > indirect evidence
5. Testimony of a witness with an interest in one party < other witness testimony
6. Testimony of a witness who appeared > written testimony of a witness who did not appear
7. Several items of different types that are consistent in content > a single isolated item
```

### 4.3 Evidence That Cannot Alone Serve as the Basis for Finding Facts

The following cannot alone serve as the basis for finding case facts and require reinforcement by other evidence:

```
In civil litigation:
- Testimony by a minor that does not match the minor’s age and intellectual condition
- Testimony by a witness with an interest in one party or that party’s agent
- Audiovisual materials or electronic data with doubts
- Copies or reproductions that cannot be checked against originals or original objects
- Testimony of a witness who failed to appear without justified reason

In criminal litigation:
- Statements, testimony, and confessions by victims, witnesses, and defendants who have physiological or mental defects that create some difficulty in perceiving and expressing case facts, but who have not lost the capacity for correct perception and expression
- Testimony favorable to the defendant by a witness with an interest in the defendant
- Defendant confessions that require corroboration by other evidence (principle that lone evidence cannot alone establish guilt)
```

---

## V. Output Format Templates

### 5.1 Single-Item Evidence Evaluation Form

```markdown
## Evidence Evaluation Form

### Basic Information
| Item | Content |
|------|------|
| Evidence number | [Number] |
| Evidence name | [Name] |
| Type of evidence | [Documentary / physical / electronic data / witness testimony / expert opinion / ...] |
| Submitting party | [Plaintiff / defendant / third party] |
| Form of evidence | [Original / copy / ...] |
| Fact intended to be proved | [Specific fact to be proved] |

### Three-Attribute Review (三性)

#### Authenticity assessment
- **Conclusion:** [Authentic / in doubt / not authentic]
- **Basis:** [Specific analysis]
- **Risk points:** [If any]

#### Legality assessment
- **Conclusion:** [Lawful / defective / unlawful]
- **Basis:** [Specific analysis]
- **Risk points:** [If any]

#### Relevance assessment
- **Conclusion:** [Direct relevance / indirect relevance / insufficient relevance]
- **Basis:** [Specific analysis]
- **Degree of relevance:** [Strong / medium / weak]

### Probative Value Assessment
- **Single-item probative value level:** [High / medium / low]
- **Reinforcement needed:** [Yes / no]
- **Reinforcement recommendation:** [If needed]

### Overall Assessment
- **Admissibility conclusion:** [Admissible / conditionally admissible / not admissible]
- **Confidence:** [★★★★★/★★★★☆/★★★☆☆/★★☆☆☆/★☆☆☆☆]
- **Special notes:** [If any]
```

### 5.2 Full-Case Comprehensive Evidence Evaluation Report

```markdown
# Full-Case Comprehensive Evidence Evaluation Report

## I. Basic Case Information
| Item | Content |
|------|------|
| Case type | [Civil / criminal / administrative] |
| Cause of action | [Specific cause] |
| Applicable standard of proof | [Beyond reasonable doubt / high degree of probability / ...] |
| Total number of evidence items | [X] |
| Evaluation date | [Date] |

## II. Facts to Be Proved and Burden Allocation
| No. | Fact to be proved | Party bearing burden | Standard of proof |
|------|---------|-----------|---------|
| 1 | [Fact 1] | [Plaintiff / defendant] | [Standard] |
| 2 | [Fact 2] | [Plaintiff / defendant] | [Standard] |

## III. Summary of Item-by-Item Evaluations
| No. | Name | Type | Authenticity | Legality | Relevance | Probative value | Admissibility |
|----------|---------|------|--------|--------|--------|--------|--------|
| 1 | [Name] | [Type] | [Conclusion] | [Conclusion] | [Conclusion] | [Level] | [Conclusion] |

## IV. Evidence-Chain Analysis
### 4.1 Evidence-relationship map
[Describe corroboration / contradiction among items]

### 4.2 Completeness of the evidence chain
| Fact to be proved | Supporting evidence | Opposing evidence | Chain status | Meets standard of proof? |
|---------|---------|---------|-----------|----------------|

## V. Overall Evaluation Conclusions
### 5.1 Findings on each fact to be proved
| Fact to be proved | Finding | Confidence | Notes |
|---------|---------|--------|------|

### 5.2 Overall assessment
[Comprehensive evaluation of all evidence in the case]

## VI. Reinforcement Recommendations
| Priority | Recommendation | Purpose | Feasibility |
|--------|---------|------|--------|

## VII. Risk Warnings
[List main evidentiary risks and response recommendations]
```

---

## VI. Confidence Annotation System

### 6.1 Confidence for a Single Item of Evidence

| Level | Symbol | Meaning | Typical situations |
|------|------|------|---------|
| **Very high** | ★★★★★ | All three attributes are beyond doubt; strong probative value | Original official documentary evidence issued by a state organ; notarized original contract; original bank transaction records |
| **Relatively high** | ★★★★☆ | Three attributes basically beyond doubt; relatively strong probative value | Signed/sealed original documentary evidence; disinterested witness who appeared and was cross-examined; expert opinion from a qualified institution |
| **Medium** | ★★★☆☆ | Some defects that can be cured; ordinary probative value | Copy corroborated by other evidence; written testimony of a witness who did not appear for justified reasons; evidence with cured procedural defects |
| **Relatively low** | ★★☆☆☆ | Clear defects; weak probative value | Copy that cannot be checked against the original; interested-witness testimony; electronic-data screenshots of unclear origin |
| **Very low** | ★☆☆☆☆ | Serious problems in the three attributes; basically no probative value | Suspected forged evidence; illegally obtained evidence; evidence unrelated to the fact to be proved |

### 6.2 Confidence for Overall Conclusions

| Level | Meaning | Explanation |
|------|------|------|
| **Certain** | Evaluation conclusion highly reliable | Legal rules are clear; evidence situation is clear; little room for dispute |
| **Relatively certain** | Evaluation conclusion fairly reliable | Main bases are clear, but some factors require judicial discretion |
| **Ordinary** | Evaluation conclusion has some reference value | Involves more subjective judgment; different judges may find differently |
| **Uncertain** | Evaluation conclusion for reference only | Evidence situation is complex; multiple reasonable explanations exist; conclusion may change with new evidence |
| **Highly uncertain** | Low reliability of evaluation conclusion | Key information missing; effective evaluation not possible; recommend re-evaluation after supplementation |

---

## VII. Common Errors and Prevention

### 7.1 Fatal Error Table

| ID | Error type | Description | Consequences | Prevention |
|------|---------|---------|------|---------|
| F-01 | **Confusing evidence rules across litigation types** | Applying civil evidence rules to a criminal case, or vice versa | Evaluation conclusions wholly wrong; may cause serious legal consequences | Before evaluation, confirm litigation type and apply the corresponding evidence-rule system |
| F-02 | **Confusing standards of proof** | Applying “beyond reasonable doubt” in a civil case, or “high degree of probability” in a criminal case | Wrong findings on facts to be proved | Clearly label the applicable standard and judge conclusions against it |
| F-03 | **Omitting exclusion-of-illegal-evidence review** | Failing to identify illegally obtained evidence that should be excluded | Inadmissible evidence pollutes the overall conclusion | Conduct legality review for every item; pay special attention to collection means and procedure |
| F-04 | **Ignoring burden-of-proof allocation** | Misidentifying who bears the burden, leading to favorable findings for the party with insufficient evidence | Directional error in fact-finding | Before evaluation, clarify burden allocation for each fact to be proved |
| F-05 | **Conflating evidentiary competence with probative value** | Assessing probative value of evidence that lacks competence (is inadmissible) | Confused logic; unreliable conclusions | Strictly follow “competence first, then probative value” |
| F-06 | **Lone-evidence adjudication** | Finding key facts on a single item without checking need for reinforcement | Violates reinforcement rules; unreliable conclusions | Always check for reinforcing evidence on key facts, especially in criminal cases |
| F-07 | **Ignoring the temporal dimension of evidence** | Failing to review the relationship between when evidence was formed and when case facts occurred | May admit post-hoc fabricated or unrelated evidence | Place evidence on the case timeline and review temporal reasonableness |

### 7.2 Common Traps

| ID | Trap description | How to identify | Response strategy |
|------|---------|---------|---------|
| T-01 | **Copy trap**: party submits only a copy, claiming the original is lost | Check for records of checking against the original; whether there is a reasonable loss explanation | Review whether the copy is corroborated by other evidence; warn that a copy alone cannot serve as the basis for adjudication |
| T-02 | **Electronic-data screenshot trap**: only chat screenshots rather than original data | Check for complete conversational context; whether notarized preservation was done | Recommend providing original electronic data or complete notarized records; lower the probative-value level in assessment |
| T-03 | **Expert-opinion authority trap**: over-relying on expert opinions without reviewing their foundation | Check institution qualification, expert qualification, material source, and methodology | Conduct full review of expert opinions; do not relax standards because of “professionalism” |
| T-04 | **Admission-withdrawal trap**: a party admits then tries to withdraw | Check whether withdrawal was agreed by the other side; whether there is sufficient evidence that the admission is inconsistent with facts | Strictly apply admission rules; review whether withdrawal conditions are met |
| T-05 | **Hidden witness interest**: witness appears disinterested but has concealed interest ties | Deeply review the witness’s relationship with the parties (relatives, friends, colleagues, business partners, etc.) | Fully investigate the witness’s background; lower probative value where interest may exist |
| T-06 | **Post-act evidence collection in administrative litigation**: agency supplements evidence during litigation | Check whether evidence was formed before the administrative act | Evidence collected by the agency during litigation generally cannot support the legality of the administrative act |
| T-07 | **Evidence ambush**: a party suddenly submits new evidence at hearing | Check whether within the proof time limit; whether it qualifies as “new evidence” | Review whether late-production exceptions apply; whether the other side has an adequate chance to cross-examine |
| T-08 | **Selective production**: party submits only favorable evidence and conceals unfavorable evidence | Review completeness of evidence; whether there are obvious information gaps | Flag possible concealment risk; recommend applying for court investigation or requiring the other side to produce |

---

## VIII. Special Scenario Handling

### 8.1 Exclusion Procedure for Illegally Obtained Evidence

```
Trigger conditions:
- In a criminal case, the defense applies to exclude illegally obtained evidence
- In a civil case, one party asserts the other’s evidence was illegally obtained

Handling process:
1. Review whether the exclusion application provides relevant clues or materials
2. Distinguish absolute exclusion from discretionary exclusion
   - Absolute exclusion (criminal): confessions obtained by torture or other illegal methods; witness testimony and victim statements obtained by violence or threats
   - Discretionary exclusion (criminal): physical or documentary evidence collected in violation of procedure that may seriously affect judicial fairness and cannot be cured or reasonably explained
   - Civil exclusion: seriously infringing others’ lawful rights and interests, violating prohibitory legal rules, or seriously violating public order and good morals
3. Review the prosecuting authority’s / collecting party’s proof of legality
4. Judge whether the exclusion standard is met
5. Assess the impact of exclusion on the full-case evidence system

Points of attention:
- The “fruit of the poisonous tree” rule has limited application in China; derivative evidence from illegal evidence is not automatically excluded
- Exclusion of repeated confessions requires case-specific analysis (confessions after change of interrogators may not be excluded)
- Distinguish defective evidence from illegally obtained evidence: defective evidence may be cured; illegally obtained evidence must be excluded
```

### 8.2 Special Review of Electronic Data

```
Review framework:
1. Generation
   - Was the system that generated the electronic data operating normally?
   - Was there human interference in the generation process?
   
2. Storage
   - Is the storage medium safe and reliable?
   - Are there anti-tampering measures (e.g., blockchain, timestamps)?
   - Was modification possible during storage?
   
3. Transmission
   - Was transmission complete?
   - Was there data loss or damage?
   
4. Extraction
   - Was the extracting subject qualified?
   - Was the extraction method scientific and standardized?
   - Was an extraction record made?
   - Were there witnesses?
   
5. Presentation
   - Is the presented content consistent with the original data?
   - Did format conversion affect content integrity?

Special review points for common electronic-data types:
- WeChat/QQ chat records: real-name authentication status; whether the conversation is complete; whether notarized
- Email: header information; send/receive server records; whether digitally signed
- Web content: whether notarially preserved; whether the page could have been modified
- Electronic contracts: whether electronic signatures comply with the *Electronic Signature Law*
- Surveillance video: device operating status; time calibration; integrity of storage medium
```

### 8.3 Special Handling of Evidence Formed Abroad

```
Handling rules:
1. Evidence formed outside the territory of the People’s Republic of China:
   - Shall be certified by the notarial authority of the place of formation
   - And authenticated by the embassy or consulate of the People’s Republic of China in that country
   - Or shall undergo certification formalities provided in a treaty between the PRC and that country

2. Evidence from Hong Kong, Macao, and Taiwan:
   - Hong Kong: notarized by Hong Kong lawyers entrusted by the Ministry of Justice
   - Macao: notarized by China Legal Service (Macao) Company
   - Taiwan: notarized by local notarial authorities and confirmed by institutions such as SEF / ARATS

3. Evidence in a foreign language:
   - Shall be accompanied by a Chinese translation
   - The translation shall be made by a qualified translation institution

Review checklist:
□ Are notarization and authentication formalities complete?
□ Is the notarization–authentication chain complete?
□ Is the translation accurate? (If disputed, re-translation may be applied for)
□ Does the content of overseas evidence meet substantive requirements of PRC law?
```

### 8.4 Urgent Handling of Evidence Preservation

```
Trigger conditions:
- Evidence may be destroyed
- Evidence may become difficult to obtain later
- The opposing party may destroy evidence

Handling recommendations:
1. Pre-suit preservation: apply to the court at the place where the evidence is located, the respondent’s domicile, or a court with jurisdiction over the case
2. In-suit preservation: apply to the court hearing the case
3. Notarial preservation: notarial preservation of electronic data, on-site conditions, etc.
4. Lawyer witnessing: in emergencies, first fix evidence through lawyer witnessing

Points of attention:
- For pre-suit preservation, suit must be filed within 30 days after the court takes preservation measures
- The application should state basic information about the evidence and the necessity of preservation
- Security may be required
```

### 8.5 Handling Contradictory Evidence

```
Types of contradiction and handling methods:

1. Same witness’s contradictory statements over time
   → Review reasons for change; take hearing statements as controlling (unless reasonably explained)
   → Lower the overall probative value of that witness’s testimony

2. Contradictions among different witnesses’ testimony
   → Review each witness’s conditions of perception, interests, and cognitive capacity
   → Apply preferential probative-value rules to decide acceptance or rejection
   → Where necessary, apply for confrontation among witnesses

3. Contradiction between documentary evidence and witness testimony
   → Documentary evidence generally has greater probative value than witness testimony
   → But authenticity and formation background of the documentary evidence must still be reviewed

4. Contradiction among expert opinions (multiple examinations)
   → Review materials, methods, and expert qualifications for each examination
   → Where necessary, apply for re-examination or supplemental examination
   → The court may organize experts to appear for cross-examination

5. Contradiction between party statements and objective evidence
   → Objective evidence (physical, documentary, electronic data, etc.) generally prevails over party statements
   → Contradiction with objective evidence may affect the credibility of the party’s statements as a whole
```

---

## IX. Quality Checklists

### 9.1 Pre-Evaluation Checklist

```
□ Has the litigation type (civil / criminal / administrative) been confirmed?
□ Has the applicable evidence-rule system been confirmed?
□ Have all facts to be proved been clarified?
□ Has the burden of proof been correctly allocated?
□ Has the applicable standard of proof been determined?
□ Has information on all evidence materials to be evaluated been collected?
□ Have the disputed focuses of the case been understood?
```

### 9.2 In-Evaluation Checklist

```
□ Has every item undergone three-attribute (三性) review?
□ Has evaluation strictly followed “competence first, then probative value”?
□ Have special review rules for different types of evidence been observed?
□ Has the possibility of excluding illegally obtained evidence been reviewed?
□ Have corroboration and contradiction among items been analyzed?
□ Has completeness of the evidence chain been assessed?
□ Has attention been paid to evidence needing reinforcement?
□ Have possible opposing cross-examination opinions been considered?
□ Have uncertain judgments been annotated with confidence levels?
```

### 9.3 Post-Evaluation Checklist

```
□ Are evaluation conclusions checked against the applicable standard of proof?
□ Is there a clear finding opinion for each fact to be proved?
□ Are confidence levels annotated for evaluation conclusions?
□ Have reinforcement recommendations been proposed?
□ Have major evidentiary risks been identified?
□ Is the output format complete and standardized?
□ Are there logical contradictions or omissions?
□ Has the limitation of AI evaluation been disclosed?
□ Has review by professionals been recommended?
```

---

## X. Complete Examples

### Example One: Simple Scenario — Evaluation of Evidence in a Private Lending Dispute

#### Case Background

Plaintiff Zhang sued defendant Li in a private lending dispute, alleging that on 15 March 2023 Li borrowed RMB 500,000 from Zhang, with an agreed annual interest rate of 12% and a one-year term, and that Li failed to repay when due.

#### Evidence Submitted by the Plaintiff

| No. | Evidence name | Type of evidence | Form |
|------|---------|---------|------|
| Evidence 1 | IOU / promissory note | Documentary evidence | Original |
| Evidence 2 | Bank transfer record | Documentary evidence / electronic data | Original transaction details issued by the bank |
| Evidence 3 | Screenshots of WeChat chat records | Electronic data | Printouts (not notarized) |
| Evidence 4 | Written testimony of witness Wang | Witness testimony | Written testimony (witness did not appear) |

#### Defendant’s Cross-Examination Opinions

- On Evidence 1: Admits authenticity of the signature on the IOU, but asserts that RMB 300,000 has already been repaid
- On Evidence 2: No objection
- On Evidence 3: Disputes authenticity; asserts screenshots may have been tampered with
- On Evidence 4: Disputes; witness did not appear, and Wang is the plaintiff’s colleague

#### Evaluation Process

**I. Determine the evaluation framework**

- Litigation type: Civil litigation
- Cause of action: Private lending dispute
- Applicable evidence rules: *Civil Procedure Law* and *Civil Evidence Provisions*
- Standard of proof: High degree of probability
- Burden of proof: Plaintiff bears the burden of proving establishment of the lending relationship and delivery of the loan; defendant bears the burden of proving repayment of RMB 300,000

**II. Facts to be proved**

| No. | Fact to be proved | Party bearing burden |
|------|---------|-----------|
| 1 | Existence of lending consensus (parties agreed on a RMB 500,000 loan, 12% annual interest, one-year term) | Plaintiff |
| 2 | Actual delivery of the loan (RMB 500,000 actually delivered to defendant) | Plaintiff |
| 3 | Defendant has repaid RMB 300,000 | Defendant |

**III. Item-by-item evidence evaluation**

---

**Evidence 1: IOU (original)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ✅ Authentic | Defendant admits signature authenticity; IOU is an original; content includes complete elements of amount, interest rate, and term |
| **Legality** | ✅ Lawful | Voluntarily signed by the parties; form lawful; content does not violate prohibitory rules; 12% annual rate does not exceed the statutory ceiling |
| **Relevance** | ✅ Direct relevance | Directly proves existence of lending consensus; directly related to Fact 1 |
| **Probative value** | **High** | Original documentary evidence; defendant admits signature authenticity; directly proves lending consensus |
| **Confidence** | ★★★★★ | Defendant’s admission of signature authenticity; original documentary evidence; extremely strong |

---

**Evidence 2: Bank transfer record (original)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ✅ Authentic | Original transaction details issued by the bank; defendant has no objection |
| **Legality** | ✅ Lawful | Lawfully issued by the bank; form lawful |
| **Relevance** | ✅ Direct relevance | Shows that on 15 March 2023 the plaintiff’s account transferred RMB 500,000 to the defendant’s account, consistent with the date and amount on the IOU; directly proves delivery |
| **Probative value** | **High** | Original record issued by a national financial institution; strong objectivity; high probative value |
| **Confidence** | ★★★★★ | Original bank record; defendant has no objection; extremely strong |

---

**Evidence 3: WeChat chat screenshots (printouts, not notarized)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ⚠️ In doubt | Only screenshot printouts; no notarial preservation; defendant disputes authenticity; tampering cannot be excluded; complete conversational context lacking |
| **Legality** | ✅ Basically lawful | Ordinary communications between parties; manner of obtaining not unlawful |
| **Relevance** | ✅ Indirect relevance | Chat content involves debt collection; related to the lending relationship, but is indirect evidence |
| **Probative value** | **Low** | Screenshot printouts are transmitted evidence; defendant disputes; not notarially preserved; cannot alone serve as the basis for finding facts |
| **Confidence** | ★★☆☆☆ | Authenticity in doubt; reinforcement needed |

**Reinforcement recommendations:**
1. Recommend that the plaintiff provide original chat records on the phone and display them in court
2. Or apply for notarial preservation of the WeChat chat records
3. Or obtain original communication records from the WeChat operator (Tencent)

---

**Evidence 4: Written testimony of witness Wang (witness did not appear)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ⚠️ In doubt | Witness did not appear for cross-examination; authenticity cannot be verified |
| **Legality** | ⚠️ Defective | Defendant objects to the testimony; the witness should have appeared but did not; review whether there was a justified reason for non-appearance |
| **Relevance** | ✅ Indirect relevance | Witness claims to have witnessed the lending process; related to facts to be proved |
| **Probative value** | **Low** | Witness is the plaintiff’s colleague (interest exists); did not appear; falls within types that cannot alone serve as the basis for finding facts (interested-witness testimony + non-appearing written testimony) |
| **Confidence** | ★★☆☆☆ | Two diminishing factors combined; relatively weak |

**Reinforcement recommendations:**
1. Apply for witness Wang to appear and submit to cross-examination
2. If the witness truly cannot appear for justified reasons, submit supporting materials
3. Seek other disinterested witnesses

---

**IV. Evidence-chain analysis**

**Fact 1 (lending consensus):**
- Evidence 1 (original IOU): direct proof, high probative value ★★★★★
- Evidence 3 (WeChat screenshots): indirect corroboration, low ★★☆☆☆
- Evidence 4 (witness testimony): indirect corroboration, low ★★☆☆☆
- **Conclusion:** The original IOU already fully proves lending consensus; even without Evidence 3 and 4, Fact 1 meets the high-degree-of-probability standard. ✅ **Fact established**

**Fact 2 (loan delivery):**
- Evidence 2 (bank transfer record): direct proof, high ★★★★★
- Evidence 1 (IOU): indirect corroboration (IOUs are typically issued after receipt of funds)
- **Conclusion:** Bank transfer record and IOU corroborate each other; fully prove that RMB 500,000 was actually delivered. ✅ **Fact established**

**Fact 3 (defendant has repaid RMB 300,000):**
- Defendant asserts repayment of RMB 300,000 but submitted no evidence (e.g., transfer records, receipts)
- Burden rests on the defendant
- **Conclusion:** Defendant has not discharged the burden of proof. ❌ **Fact not established (until defendant supplements evidence)**

**V. Overall evaluation conclusions**

| Fact to be proved | Finding | Confidence | Notes |
|---------|---------|--------|------|
| Lending consensus exists | ✅ Established | Certain | Original IOU + defendant’s admission of signature; evidence sufficient |
| RMB 500,000 loan delivered | ✅ Established | Certain | Bank transfer record + IOU corroboration; evidence sufficient |
| Defendant has repaid RMB 300,000 | ❌ Not established (for now) | Relatively certain | Defendant has not produced evidence; watch whether defendant supplements within the proof time limit |

**VI. Reinforcement recommendations**

| Priority | Recommendation | Purpose | Feasibility |
|--------|------|------|--------|
| High | Notarially preserve WeChat chat records or display original records in court | Reinforce proof of debt-collection facts | High |
| Medium | Apply for witness Wang to appear | Enhance probative value of witness testimony | Medium |
| Low | Watch whether defendant submits evidence of RMB 300,000 repayment | Prepare rebuttal | — |

**VII. Risk warnings**

1. **Primary risk:** Defendant may, within the proof time limit, supplement evidence of repayment of RMB 300,000 (e.g., transfer records); prepare a response plan in advance
2. **Secondary risk:** If WeChat chat records are not reinforced, they may not be admitted under strong challenge, but this does not affect core fact-finding
3. **Overall assessment:** Plaintiff’s core evidence (original IOU + bank transfer record) has strong probative value and a complete chain; likelihood of success is relatively high

---

### Example Two: Complex Scenario — Evaluation of Evidence in a Criminal Case (Intentional Injury)

#### Case Background

The prosecuting authority charges that on the evening of 20 January 2024, at a bar, defendant Zhao quarreled with victim Qian over a trivial matter and struck Qian’s head with a beer bottle, causing Qian second-degree serious injury. After coming into custody, Zhao first confessed to the crime, then retracted and claimed self-defense (正当防卫).

#### Evidence Submitted by the Prosecuting Authority

| No. | Evidence name | Type of evidence |
|------|---------|---------|
| Evidence 1 | Defendant Zhao’s confession (first, guilty confession) | Confessions and defenses of the defendant |
| Evidence 2 | Defendant Zhao’s confession (second and thereafter, retracted; claims self-defense) | Confessions and defenses of the defendant |
| Evidence 3 | Victim Qian’s statement | Victim statement |
| Evidence 4 | Testimony of witness Sun (bar server) | Witness testimony |
| Evidence 5 | Testimony of witness Zhou (Zhao’s friend) | Witness testimony |
| Evidence 6 | Bar surveillance video (partial; critical period footage blurred) | Audiovisual materials |
| Evidence 7 | Forensic expert opinion (Qian’s injury is second-degree serious injury) | Expert opinion |
| Evidence 8 | On-site inspection record and photographs | Inspection record |
| Evidence 9 | Beer bottle (instrument of the offense) | Physical evidence |
| Evidence 10 | Explanation of how Zhao came into custody | Documentary evidence |

#### Issues Raised by the Defense

1. Zhao’s first confession was made after continuous interrogation exceeding 24 hours, suspected fatigue interrogation
2. Surveillance video shows Qian first pushed and shoved Zhao
3. Witness Zhou’s testimony supports Zhao’s claim of self-defense

#### Evaluation Process

**I. Determine the evaluation framework**

- Litigation type: Criminal litigation
- Charge: Intentional injury (causing serious injury)
- Applicable evidence rules: *Criminal Procedure Law* and *Criminal Procedure Law Interpretation*
- Standard of proof: Beyond reasonable doubt (evidence reliable and sufficient)
- Burden of proof: Prosecuting authority bears the burden of proving the criminal facts

**II. Facts to be proved**

| No. | Fact to be proved | Party bearing burden | Importance |
|------|---------|-----------|---------|
| 1 | Zhao struck Qian’s head with a beer bottle | Prosecuting authority | Core |
| 2 | Zhao had intent to injure | Prosecuting authority | Core |
| 3 | Qian’s injury is second-degree serious injury | Prosecuting authority | Core |
| 4 | Causal link between Zhao’s conduct and Qian’s injury | Prosecuting authority | Core |
| 5 | Whether there was a premise for self-defense (Qian first committed an unlawful infringement) | Raised by defense; prosecuting authority must exclude | Key dispute |
| 6 | If defensive conduct existed, whether it exceeded necessary limits | Depends on circumstances | Key dispute |

**III. Item-by-item evidence evaluation**

---

**Evidence 1: Zhao’s first confession (guilty confession)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ⚠️ In doubt | Defendant has retracted; review whether content is corroborated by other evidence |
| **Legality** | ⚠️ **Seriously in doubt** | Defense asserts continuous interrogation exceeding 24 hours, suspected fatigue interrogation. Under Art. 120 of the *Criminal Procedure Law*, summons or forced appearance shall not exceed 24 hours, and the suspect’s meals and necessary rest shall be guaranteed. **Need to review:** ① start and end times recorded in interrogation transcripts; ② contemporaneous audio-video recording (if any); ③ detention-facility entry/exit records; ④ explanations by interrogators |
| **Relevance** | ✅ Direct relevance | Confession content directly concerns the criminal facts |
| **Probative value** | **Pending** | Depends on legality review outcome |
| **Confidence** | ★★☆☆☆ | Major legality doubts; resolve first |

**⚠️ Analysis of exclusion of illegally obtained evidence:**

```
1. Review points:
   - Do times recorded in interrogation transcripts exceed the statutory limit?
   - Is there contemporaneous audio-video recording? Is it complete?
   - Were meals and rest guaranteed during interrogation?
   - Can the prosecuting authority prove lawful collection?

2. Legal application:
   - If fatigue interrogation is confirmed, the confession may be one collected by illegal methods
   - Under Art. 2 of the *Provisions on Several Issues Concerning Strict Exclusion of Illegally Obtained Evidence in Handling Criminal Cases*,
     confessions collected by illegal methods such as illegally restricting personal liberty shall be excluded
   - In judicial practice, fatigue interrogation is generally treated as a disguised illegal collection method

3. Preliminary judgment:
   - If the prosecuting authority cannot adequately prove interrogation legality, there is a substantial risk of exclusion
   - Even if not excluded, probative value is greatly reduced by retraction
```

---

**Evidence 2: Zhao’s second and subsequent confessions (retracted; claims self-defense)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ⚠️ Needs comprehensive judgment | Retraction content must be checked against other evidence |
| **Legality** | ✅ No illegality found | Confession after change of interrogators; procedure lawful |
| **Relevance** | ✅ Direct relevance | Defense of self-defense is directly related to the core dispute |
| **Probative value** | **Medium** | Defendant’s defense needs corroboration; but if the first confession is excluded, stable post-retraction confessions have some reference value |
| **Confidence** | ★★★☆☆ | Judge comprehensively with other evidence |

---

**Evidence 3: Victim Qian’s statement**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ⚠️ Needs cautious assessment | As an interested party, the victim’s statement may be biased; review consistency over time and consistency with objective evidence |
| **Legality** | ✅ Lawful | Lawfully obtained; procedure lawful |
| **Relevance** | ✅ Direct relevance | Directly describes the incident process |
| **Probative value** | **Medium-high** | Victim personally experienced the incident, but note: ① victim claims Zhao struck first without cause, which may contradict surveillance (showing Qian first pushed); ② victim’s head injury may affect memory of details |
| **Confidence** | ★★★☆☆ | Check against surveillance and other objective evidence |

**Key contradiction:** Victim’s statement that “Zhao struck first without cause” contradicts surveillance showing “Qian first pushed Zhao”—this is the core dispute.

---

**Evidence 4: Testimony of witness Sun (bar server)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ✅ Relatively credible | Witness is bar staff who was present; no interest with either side |
| **Legality** | ✅ Lawful | Lawfully collected; procedure lawful |
| **Relevance** | ✅ Direct relevance | Eyewitness to the incident |
| **Probative value** | **Relatively high** | Disinterested third-party witness; but review: ① witness’s position and angle; ② whether who struck first could be clearly seen; ③ specific content of the testimony |
| **Confidence** | ★★★★☆ | Disinterested witness; relatively strong |

**Key information:** Pay special attention to Sun’s description of the key fact of “who struck first.”

---

**Evidence 5: Testimony of witness Zhou (Zhao’s friend)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ⚠️ Needs cautious assessment | Witness is the defendant’s friend; interest exists |
| **Legality** | ✅ Lawful | Lawfully collected; procedure lawful |
| **Relevance** | ✅ Direct relevance | Eyewitness; supports self-defense claim |
| **Probative value** | **Relatively low** | Testimony favorable to the defendant by an interested witness has relatively low probative value; cannot alone serve as the basis for finding facts |
| **Confidence** | ★★☆☆☆ | Interest lowers probative value, but corroboration by other evidence can strengthen it |

---

**Evidence 6: Bar surveillance video (partial; critical period footage blurred)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ✅ Basically authentic | Automatically recorded by the bar’s surveillance system; strong objectivity; but critical-period footage is blurred, affecting fact-finding |
| **Legality** | ✅ Lawful | Public-place surveillance; lawfully obtained |
| **Relevance** | ✅ Direct relevance | Records part of the incident process |
| **Probative value** | **Medium** | Objective evidence that should have high value, but limited by blur in the critical period. **Identifiable content:** shows Qian first pushing Zhao; **blurred portion:** specific process of Zhao striking with the bottle is insufficiently clear |
| **Confidence** | ★★★☆☆ | Some content clear; some blur must be combined with other evidence |

**Key finding:** The identifiable portion shows Qian first pushing, which contradicts the victim’s claim that “Zhao struck first without cause” and supports the defense’s self-defense claim.

**Recommendation:** Apply for technical enhancement of the surveillance video to obtain clearer images.

---

**Evidence 7: Forensic expert opinion (second-degree serious injury)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ✅ Authentic | Institution has statutory qualification; experts have practice qualifications |
| **Legality** | ✅ Lawful | Entrustment procedure lawful; methodology complies with national standards |
| **Relevance** | ✅ Direct relevance | Directly proves the injury result |
| **Probative value** | **High** | Forensic expert opinion; strong professionalism; standardized procedure |
| **Confidence** | ★★★★★ | Standardized examination procedure; clear conclusion |

**Review points confirmed:**
- ✅ Expert institution: has judicial appraisal qualification
- ✅ Expert: has forensic clinical appraisal practice qualification
- ✅ Examined materials: the victim personally; clear source
- ✅ Appraisal standard: based on the *Standards for Assessing the Degree of Human Injury*
- ✅ Conclusion: clearly second-degree serious injury

---

**Evidence 8: On-site inspection record and photographs**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ✅ Authentic | Made by investigators in accordance with law; bears witness signatures |
| **Legality** | ✅ Lawful | Inspection procedure lawful; records complete |
| **Relevance** | ✅ Relevant | Records on-site conditions related to case facts |
| **Probative value** | **Relatively high** | Objective record of on-site conditions |
| **Confidence** | ★★★★☆ | Inspection record with standardized procedure |

---

**Evidence 9: Beer bottle (instrument of the offense)**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ✅ Authentic | Lawfully extracted from the scene; extraction record and seizure inventory exist |
| **Legality** | ✅ Lawful | Extraction and seizure procedure lawful |
| **Relevance** | ✅ Direct relevance | Instrument of the offense; directly related to the injury conduct |
| **Probative value** | **Relatively high** | Physical evidence; strong objectivity; fingerprint identification would further raise value |
| **Confidence** | ★★★★☆ | Complete chain of custody |

**Recommendation:** Confirm whether fingerprint extraction and comparison were conducted.

---

**Evidence 10: Explanation of how the defendant came into custody**

| Review item | Evaluation conclusion | Analysis |
|----------|---------|------|
| **Authenticity** | ✅ Authentic | Issued by the public security organ |
| **Legality** | ✅ Lawful | Form lawful |
| **Relevance** | ✅ Relevant | Related to how the defendant came into custody; may involve voluntary surrender findings |
| **Probative value** | **Medium** | Proves the custody process; reference value for sentencing |
| **Confidence** | ★★★★☆ | — |

---

**IV. Evidence-chain analysis and core disputes**

**4.1 Evidence chain for undisputed facts**

| Fact to be proved | Supporting evidence | Chain status | Conclusion |
|---------|---------|-----------|------|
| Zhao struck Qian’s head with a beer bottle | Evidence 1 (if not excluded), Evidence 2 (admits striking), Evidence 3, Evidence 4, Evidence 6 (partly visible), Evidence 9 | Complete | ✅ May be found |
| Qian’s injury is second-degree serious injury | Evidence 7 | Complete | ✅ May be found |
| Causation between Zhao’s conduct and the injury | Evidence 7 + Evidence 8 + Evidence 9 | Complete | ✅ May be found |

**4.2 Core dispute: whether self-defense is constituted**

```
Evidence supporting self-defense:
├── Evidence 2 (Zhao’s stable post-retraction confession) — medium probative value
├── Evidence 5 (Zhou’s testimony, but interested) — relatively low
└── Evidence 6 (surveillance shows Qian first pushing) — medium (critical period blurred)

Evidence opposing self-defense:
├── Evidence 1 (Zhao’s first guilty confession) — legality in doubt; may be excluded
└── Evidence 3 (victim states Zhao struck first) — contradicts surveillance; value reduced

Neutral evidence:
└── Evidence 4 (Sun’s testimony) — need to confirm Sun’s specific description of “who struck first”
```

**4.3 Key contradiction analysis**

```
Contradiction 1: Victim statement vs. surveillance video
- Victim claims Zhao struck first without cause
- Surveillance shows Qian first pushed
- Analysis: Objective evidence (surveillance) generally prevails over party statements
- Conclusion: Credibility of the victim’s statement on “who struck first” is reduced

Contradiction 2: Zhao’s first confession vs. post-retraction confession
- First confession admits intentional injury
- After retraction, claims self-defense
- Analysis: Legality of the first confession is in doubt; post-retraction confession partly matches surveillance
- Conclusion: If the first confession is excluded, the post-retraction confession combined with surveillance has some credibility

Contradiction 3: Witness Sun vs. witness Zhou (assuming differences)
- Need concrete comparison of their descriptions of key facts
- Sun is disinterested; preferential probative value
- Zhou is interested; relatively low value
```

**V. Overall evaluation conclusions**

| Fact to be proved | Finding | Confidence | Notes |
|---------|---------|--------|------|
| Zhao struck Qian’s head with a bottle | ✅ May be found | Certain | Multiple items consistently prove |
| Qian’s second-degree serious injury | ✅ May be found | Certain | Forensic expert opinion is clear |
| Causation | ✅ May be found | Certain | Evidence chain complete |
| Zhao had intent to injure | ⚠️ Disputed | Uncertain | If self-defense is found, no intent to injure |
| Qian first committed an unlawful infringement | ⚠️ Some supporting evidence | Uncertain | Surveillance shows Qian first pushing, but footage is blurred; judge comprehensively with Sun’s testimony |
| Whether defense was excessive | ⚠️ Needs further analysis | Highly uncertain | Even if unlawful infringement is found, whether striking the head with a beer bottle causing serious injury exceeded necessary limits still requires argument |

**VI. Key issues and recommendations**

| Priority | Issue / recommendation | Purpose |
|--------|---------|------|
| **Highest** | Initiate exclusion of illegally obtained evidence; review legality of Zhao’s first confession | Determine whether it can serve as a basis for adjudication |
| **Highest** | Apply for technical enhancement of the surveillance video | Obtain clear images of the critical period |
| **High** | Apply for witness Sun to appear; focus questioning on “who struck first” | Obtain disinterested third-party testimony on the core dispute |
| **High** | Review contemporaneous audio-video of Zhao’s first confession | Verify whether fatigue interrogation occurred |
| **Medium** | Confirm whether Zhao’s fingerprints were extracted from the beer bottle | Reinforce linkage between physical evidence and the defendant |
| **Medium** | Review whether the bar has surveillance from other angles | Obtain a more complete record of the incident |

**VII. Risk warnings**

```
1. [Risk of exclusion of illegally obtained evidence] If Zhao’s first confession is excluded, the prosecuting authority loses its only guilty confession
   and must rely entirely on other evidence to prove the criminal facts.

2. [Risk regarding self-defense findings] Surveillance shows Qian first pushed Zhao; if that fact is found,
   the premise for self-defense exists. But even if unlawful infringement is found,
   whether striking the head with a beer bottle causing serious injury constitutes excessive defense remains a key dispute.

3. [Risk regarding the standard of proof] Criminal cases apply “beyond reasonable doubt.”
   On the key fact of “who struck first,” existing evidence is contradictory
   and may fail to exclude the reasonable doubt that “Qian first committed an unlawful infringement.”

4. [Sentencing impact] Even if self-defense is not found, if the victim is found at fault (struck first),
   sentencing may still be affected.

5. [Overall assessment] Evidence is sufficient on the criminal conduct and injury result,
   but there is major dispute on subjective intent and self-defense;
   the final conclusion highly depends on:
   (a) the legality review outcome of the first confession
   (b) content of the surveillance after technical enhancement
   (c) witness Sun’s testimony on the core facts
```

---

## Appendix: Quick Reference Card

### Quick Lookup Table for Three-Attribute (三性) Review of Evidence

```
┌─────────────────────────────────────────────┐
│         Evidentiary Validity Evaluation Quick Lookup        │
├─────────────────────────────────────────────┤
│                                               │
│  Step 1: Confirm litigation type → Select evidence-rule system │
│  Step 2: Clarify facts to be proved → Allocate burden of proof │
│  Step 3: Determine the standard of proof                           │
│                                               │
│  Item-by-item review:                                    │
│  ┌─ Authenticity: Original? Untampered? Content credible?            │
│  ├─ Legality: Subject? Procedure? Form? Illegal exclusion?         │
│  ├─ Relevance: Logical link to the fact to be proved? Degree?         │
│  └─ Probative value: Type-specific rules? Reinforcement needed?                │
│                                               │
│  Comprehensive judgment:                                    │
│  ┌─ Corroboration / contradiction among items                       │
│  ├─ Completeness of the evidence chain                              │
│  ├─ Whether the standard of proof is met                           │
│  └─ Reinforcement recommendations                                  │
│                                               │
│  ⚠️ Fatal checks:                                │
│  □ Is the litigation type correct?                          │
│  □ Is the standard of proof correct?                          │
│  □ Has illegally obtained evidence been screened?                        │
│  □ Has the burden of proof been clarified?                          │
│  □ Has lone evidence been flagged?                            │
└─────────────────────────────────────────────┘
```
