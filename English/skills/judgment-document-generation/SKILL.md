---
name: judgment-document-generation
description: Based on a case-fact narrative, coordinate and invoke 8 atomic capabilities to generate a complete criminal judgment that is format-compliant and rigorously reasoned. Covers the full pipeline of fact-finding, legal application, sentencing reasoning, and document output.
---

> **Chinese source (authoritative):** [`../../skills/judgment-document-generation/SKILL.md`](../../skills/judgment-document-generation/SKILL.md)

# Judgment Document Generation (8 Skills)

## I. Capability Overview

This composite capability targets first-instance criminal cases. It takes a case-fact narrative (including prosecution charges, evidence summary, defendant statements, etc.) and outputs a structurally complete, rigorously reasoned, and format-compliant criminal judgment (刑事判决书). Execution strictly follows the mainline: "fact extraction → concept comprehension → dispute identification → statute retrieval → case retrieval → deductive reasoning → format application → terminology standardization," with quality checks and conditional branches at key nodes.

---

## II. Selected Atomic Capabilities

| Step | Capability ID | Capability Name | Rationale |
|:---:|:---:|---|---|
| S1 | 4 | Legal Core Element Extraction | The foundation of a judgment is accurate fact-finding; all core elements—subject, act, object, time, causation, legal consequences, etc.—must be extracted from the case narrative to provide structured input for every subsequent step |
| S2 | 5 | Legal Concept Comprehension | Precise understanding of the statutory constitutive elements of the charged offense, forms of crime (consummated / attempted / discontinued), joint crime, sentencing circumstances, and related concepts (intension and extension) is required to ensure correct legal application |
| S3 | 6 | Dispute Focus and Legal Relationship Identification | The "本院认为" (this Court's opinion) section must address the prosecution–defense dispute foci; the case's core disputed issues and the nature of the legal relationships must be accurately identified |
| S4 | 8 | Legal Provision Retrieval | A judgment must cite specific legal provisions as the basis of adjudication; applicable Criminal Law articles, judicial interpretations, and sentencing norms must be retrieved |
| S5 | 9 | Case Retrieval | Sentencing should reference judicial practice patterns in similar cases to keep the outcome within a reasonable range and strengthen uniformity and persuasiveness |
| S6 | 16 | Deductive Reasoning | The core argumentative logic of a judgment is "major premise (legal norm) → minor premise (case facts) → conclusion (adjudicative result)"; deductive reasoning is the key capability for generating reasons and sentencing conclusions |
| S7 | 49 | Legal Document Format Application | Criminal judgments have strict format norms (caption/header, facts, reasons, operative part / disposition, closing); the document type must be identified and the corresponding format applied |
| S8 | 50 | Legal Terminology Standardization | A judgment is a formal legal instrument; all wording must be accurate, unambiguous, and consistent with legal drafting style throughout the output process |

---

## III. Atomic Capabilities Not Selected

This composite capability uses all 8 available atomic capabilities; there are no exclusions.

**Rationale:** Judgment-document generation is among the most complex end-to-end tasks in legal AI. It requires full-chain coverage from fact-finding through legal application to document output. The 8 atomic capabilities map to indispensable links in that chain—fact layer (AS4), concept layer (AS5), dispute layer (AS6), norm layer (AS8, AS9), reasoning layer (AS16), and output layer (AS49, AS50). Omitting any one would leave a defect in some dimension of the judgment.

---

## IV. Complete Execution Flow

### Flow Overview

```
Input: Case-fact narrative
  │
  ▼
[S1] AS4 Legal Core Element Extraction
  │
  ▼
[S2] AS5 Legal Concept Comprehension
  │
  ├──Quality Checkpoint QC1──→ If fail, backtrack to S1
  ▼
[S3] AS6 Dispute Focus and Legal Relationship Identification
  │
  ▼
[S4] AS8 Legal Provision Retrieval
  │
  ├──Quality Checkpoint QC2──→ If fail, backtrack to S2/S3
  ▼
[S5] AS9 Case Retrieval
  │
  ▼
[S6] AS16 Deductive Reasoning
  │
  ├──Quality Checkpoint QC3──→ If fail, backtrack to S4/S5
  ▼
[S7] AS49 Legal Document Format Application
  │
  ▼
[S8] AS50 Legal Terminology Standardization
  │
  ├──Quality Checkpoint QC4──→ If fail, backtrack to S7
  ▼
Output: Complete criminal judgment
```

---

### S1: Legal Core Element Extraction

| Item | Content |
|---|---|
| **Capability invoked** | AS4 — Legal Core Element Extraction |
| **Input** | Full original case-fact narrative (including prosecution charges, evidence list, defendant's attitude) |
| **Actions** | Extract the following irreducible core elements item by item: ① criminal subject (defendant identity, co-offender information); ② criminal act (specific manner and means); ③ object / target of the offense (legal interest infringed, specific property); ④ purpose / motive; ⑤ criminal result (consummated / attempted, loss amount); ⑥ timeline (offense date, apprehension date, restitution date, etc.); ⑦ causation; ⑧ sentencing-related circumstances (voluntary surrender / 自首, truthful confession / 坦白, restitution of stolen property / 退赃, prior convictions, etc.); ⑨ evidence summary |
| **Output** | Structured element inventory (JSON or table) |
| **Passed to next step** | Complete structured element inventory for S2 to comprehend related legal concepts |

**Case 1 example:**
> Extraction result: subject (Zhang 3), act (forging ID card, impersonating to defraud property), purpose (repaying debts), target amount (RMB 100,000), result (discovered; unsuccessful), time (28 April 2017)

**Case 2 example:**
> Extraction result: subjects (An Xu + Yang jointly), act (forced entry with tools and household theft / 入户盗窃), object (gold and silver jewelry), time (offense 9 May 2016; arrested 15 April 2018), mitigating circumstance (returned RMB 3,000)

---

### S2: Legal Concept Comprehension

| Item | Content |
|---|---|
| **Capability invoked** | AS5 — Legal Concept Comprehension |
| **Input** | Structured element inventory from S1 |
| **Actions** | Based on extracted act features and results, identify possible offenses and, for each, comprehend constitutive elements and intension/extension of: ① statutory constitutive elements of the charged offense (four-element theory or three-tier theory); ② forms of crime (consummated, attempted, discontinued / 中止, preparatory); ③ joint crime concepts (principal / 主犯, accessory / 从犯, coerced accomplice / 胁从犯); ④ sentencing circumstance concepts (statutory lighter / mitigated / heavier circumstances; discretionary circumstances); ⑤ other special concepts involved (e.g., "household theft / 入户盗窃", "huge amount / 数额巨大") |
| **Output** | Legal concept analysis table for the case (each concept with definition, constitutive elements, and applicability conditions) |
| **Passed to next step** | Concept analysis table + S1 element inventory for S3 to identify dispute foci |

**Case 1 example:**
> Comprehend fraud (诈骗罪) constitutive elements—purpose of illegal appropriation, fabricating facts or concealing the truth, obtaining another's property by deception, relatively large amount; criminal attempt—having begun to commit the crime, failing to complete it for reasons independent of the actor's will

**Case 2 example:**
> Comprehend theft "household theft / 入户盗窃"—criminalized regardless of amount; joint crime; criteria for distinguishing principal and accessory

---

### 🔍 Quality Checkpoint QC1: Element–Concept Match Verification

| Check Item | Verification Logic | On Failure |
|---|---|---|
| Element completeness | Whether elements extracted in S1 cover all facts corresponding to the offense's constitutive elements in S2 | Backtrack to S1; supplement omitted elements |
| Concept coverage | Whether S2 covers legal concepts corresponding to all act features in S1 | Supplement omitted concepts in S2 |
| Preliminary offense characterization reasonableness | Whether the preliminarily identified offense matches act features (e.g., violent taking of property should not be characterized as theft) | Backtrack to S2; re-analyze offense direction |

---

### S3: Dispute Focus and Legal Relationship Identification

| Item | Content |
|---|---|
| **Capability invoked** | AS6 — Dispute Focus and Legal Relationship Identification |
| **Input** | S1 structured element inventory + S2 legal concept analysis table |
| **Actions** | ① Identify the nature of legal relationships among the parties (criminal prosecution relationship, joint-offender relationship, victim–defendant relationship, etc.); ② Identify possible prosecution–defense dispute foci, including but not limited to: offense characterization disputes; form-of-crime disputes (consummated vs. attempted); co-offender status disputes (principal vs. accessory); sentencing circumstance disputes (recognition of voluntary surrender / truthful confession); amount determination disputes; ③ For each dispute focus, mark priority for response in the "本院认为" section |
| **Output** | Dispute focus list (priority-ranked) + legal relationship map |
| **Passed to next step** | Dispute focus list to guide precise statute retrieval in S4 |

**Case 1 example:**
> Dispute foci: ① whether fraud was consummated or attempted; ② characterization of "huge amount" (which sentencing tier under Article 266 applies to RMB 100,000)

**Case 2 example:**
> Dispute foci: ① An Xu's status in the joint crime (principal or accessory); ② effect of returning RMB 3,000 on sentencing

---

### S4: Legal Provision Retrieval

| Item | Content |
|---|---|
| **Capability invoked** | AS8 — Legal Provision Retrieval |
| **Input** | S2 offense and concept analysis + S3 dispute focus list |
| **Actions** | Retrieve applicable legal norms by layer: ① **Conviction provisions:** Criminal Law Special Part articles for the offense (including sentencing ranges); ② **Form-of-crime provisions:** General Part articles such as attempt (Art. 23), discontinuation (Art. 24); ③ **Joint-crime provisions:** e.g., joint crime (Art. 25), principal/accessory (Arts. 26–29); ④ **Sentencing circumstance provisions:** e.g., voluntary surrender (Art. 67), truthful confession (Art. 67 para. 3), meritorious service (Art. 68); ⑤ **Penalty enforcement provisions:** fine (Arts. 52, 53), restitution (Art. 64), etc.; ⑥ **Judicial interpretations:** amount thresholds for the offense, sentencing guidelines, etc. |
| **Output** | Applicable provision list (full text, applicability rationale, corresponding dispute focus IDs) |
| **Passed to next step** | Provision list to constrain S5 case retrieval scope and to serve as major premises for S6 deductive reasoning |

**Case 1 example:**
> Retrieval: Criminal Law Art. 266 (fraud and sentencing ranges), Art. 23 (criminal attempt), Art. 67 para. 3 (truthful confession → lighter punishment)

**Case 2 example:**
> Retrieval: Criminal Law Arts. 264, 25, 67 para. 3, 52, 53, 64

---

### 🔍 Quality Checkpoint QC2: Provision–Dispute Coverage Verification

| Check Item | Verification Logic | On Failure |
|---|---|---|
| Full dispute-focus coverage | Whether each dispute focus in S3 has supporting provisions | Backtrack to S4; supplement retrieval |
| Offense provision accuracy | Whether retrieved offense provisions match the offense determined in S2 | Backtrack to S2 to reconfirm offense, or backtrack to S4 to correct retrieval |
| Sentencing circumstance provision completeness | Whether each sentencing circumstance extracted in S1 has a corresponding provision | Backtrack to S4; supplement sentencing-circumstance provisions |
| Judicial interpretation currency | Whether retrieved judicial interpretations were in force at the time of the offense | Replace with the version effective at the time of the offense |

---

### S5: Case Retrieval

| Item | Content |
|---|---|
| **Capability invoked** | AS9 — Case Retrieval |
| **Input** | S1 structured elements (offense, manner of act, amount, circumstances) + S3 dispute foci + S4 provision list |
| **Actions** | ① Using offense + manner of act + form of crime as keywords, retrieve judgments in similar cases; ② Focus on: sentencing ranges under similar amounts/circumstances; adjudicative tendencies on dispute foci (e.g., practical grasp of accessory criteria); sentencing habits of courts in the same locality; ③ Extract comparable-case sentencing baselines and adjustment factors |
| **Output** | Comparable-case retrieval report (3–5 reference cases with offense, circumstances, sentence, and adjudicative gist / 裁判要旨) |
| **Passed to next step** | Comparable-case sentencing range and adjudicative tendencies to calibrate the sentencing conclusion in S6 |

**Conditional branches:**
- If highly similar cases are found (manner of act, amount, and circumstances substantially consistent): extract sentencing reference values directly
- If no highly similar cases are found: broaden the search (relax amount range or manner of act) and mark limited reference value

**Case 1 example:**
> Find sentencing patterns in similar attempted-fraud cases to assess reasonableness of a seven-month sentencing range

**Case 2 example:**
> Induce Shanghai-area judicial practice sentencing patterns from similar household-theft cases; find precedents on accessory determination criteria

---

### S6: Deductive Reasoning

| Item | Content |
|---|---|
| **Capability invoked** | AS16 — Deductive Reasoning |
| **Input** | S1 structured elements (minor premise) + S4 provision list (major premise) + S3 dispute foci (argumentation targets) + S5 comparable-case references (sentencing calibration) |
| **Actions** | Reason layer by layer along the following chain; each layer uses the syllogistic structure "major premise → minor premise → conclusion": **Layer 1: Conviction reasoning** — Map case facts item by item against constitutive elements → conclude whether the offense is established; **Layer 2: Form-of-crime reasoning** (conditionally triggered) — If attempt/discontinuation etc. are disputed, map facts against form requirements → conclude on form; **Layer 3: Joint-crime reasoning** (conditionally triggered) — If joint crime exists, argue each defendant's status and role → conclude principal/accessory; **Layer 4: Sentencing circumstance reasoning** — Argue item by item whether statutory/discretionary lighter, mitigated, or heavier circumstances are established; **Layer 5: Sentencing conclusion reasoning** — Combine conviction + form + co-offender status + sentencing circumstances + comparable-case references → derive specific term of imprisonment and additional penalties; **Layer 6: Ancillary matters reasoning** — Derive restitution, confiscation, restraining orders, and other ancillary dispositions |
| **Output** | Complete reasoning chain (major premise, minor premise, and conclusion for each layer) + final adjudicative conclusions (principal penalty + additional penalties + ancillary dispositions) |
| **Passed to next step** | Reasoning-chain text (for the "本院认为" section) + adjudicative conclusions (for the operative part / 判决主文) |

**Case 1 example:**
> ① Fraud constitutive elements satisfied item by item → fraud established; ② discovered and unsuccessful for reasons independent of will → attempt established; ③ RMB 100,000 falls in the "huge amount" sentencing tier; attempt may be punished more lightly or mitigated by reference to consummated offense; ④ plus truthful confession for lighter punishment → derive fixed-term imprisonment of seven months + fine of RMB 30,000

**Case 2 example:**
> ① Household-theft constitutive elements satisfied → theft established; ② two persons plotted and jointly committed → joint crime established; ③ defense claim of accessory status lacks sufficient evidence → not accepted; ④ truthful confession + return of funds for lighter punishment → derive fixed-term imprisonment of six months + fine of RMB 2,000 + restitution order

---

### 🔍 Quality Checkpoint QC3: Reasoning-Chain Completeness and Consistency Verification

| Check Item | Verification Logic | On Failure |
|---|---|---|
| Full constitutive-element coverage | Whether conviction reasoning argued every constitutive element of the offense | Backtrack to S6 Layer 1; supplement omitted-element argument |
| Full dispute-focus response | Whether each dispute focus in S3 received a clear response in the reasoning chain | Backtrack to S6; supplement argument on omitted dispute foci |
| Sentencing reasonableness | Whether the derived sentence falls within the statutory range in S4 and is broadly consistent with the S5 comparable-case range | If outside statutory range → backtrack to S4 to confirm provision application; if large deviation from comparable cases → backtrack to S5 to broaden retrieval or supplement special-circumstance reasoning in S6 |
| Logical coherence | Whether conclusions across layers contradict (e.g., finding attempt but sentencing as consummated) | Backtrack to S6; correct contradictory links |

---

### S7: Legal Document Format Application

| Item | Content |
|---|---|
| **Capability invoked** | AS49 — Legal Document Format Application |
| **Input** | S1 structured elements + S6 reasoning chain and adjudicative conclusions + S4 provision list |
| **Actions** | ① Identify document type as "first-instance criminal judgment"; ② Per Supreme People's Court criminal judgment format norms, assemble prior outputs into: **Header / 首部** — court name, case number, prosecuting organ, defendant basic information, defense counsel information, case origin and trial process; **Facts / 事实部分** — "经审理查明" (facts found after trial) paragraph (restating facts based on S1 elements) + evidence enumeration; **Reasons / 理由部分** — "本院认为" paragraph (expanding argument from S6 reasoning chain, responding to each dispute focus); **Operative part / 判决主文** — conviction and sentence + additional penalties + restitution and other ancillary dispositions (from S6 conclusions); **Closing / 尾部** — sentence credit calculation, appeal rights notice, panel signatures, date; **Appendix** — full text of cited legal provisions (from S4 provision list) |
| **Output** | Formatted judgment draft (all structural sections) |
| **Passed to next step** | Full judgment draft for S8 terminology standardization and polishing |

**Case 1 example:**
> Criminal judgment format, stating in order: party information, prosecution charges, fact-finding, this Court's opinion, operative part, sentence calculation, appeal notice, appended legal provisions

---

### S8: Legal Terminology Standardization

| Item | Content |
|---|---|
| **Capability invoked** | AS50 — Legal Terminology Standardization |
| **Input** | Full judgment draft from S7 |
| **Actions** | Sentence-by-sentence review and standardization: ① **Terminological accuracy:** Ensure offense names, forms of crime, and sentencing circumstances use statutory terms (e.g., "犯罪未遂" / criminal attempt rather than "未遂犯"; "如实供述自己的罪行" / truthfully confessing one's crimes rather than colloquial "坦白交代"); ② **Operative-part norms:** Ensure formulations such as "判处有期徒刑X年/月" (sentenced to fixed-term imprisonment of X years/months), "并处罚金人民币X元" (and a fine of RMB X), "责令退赔" (ordered to make restitution) conform to judicial drafting practice; ③ **Citation norms:** Ensure correct format "依照《中华人民共和国刑法》第X条第X款" (pursuant to Article X, paragraph X of the Criminal Law of the PRC); ④ **Stylistic consistency:** Third-person narration, legal-document sentence patterns, no colloquial expression; ⑤ **Logical connective norms:** Proper use of "鉴于" (whereas/in light of), "综上" (in sum), "据此" (accordingly), etc. |
| **Output** | Final judgment after terminology standardization |
| **Passed to final output** | Complete criminal judgment |

**Case 1 example:**
> Ensure formulations such as "犯罪未遂", "比照既遂犯从轻或者减轻处罚" (punished more lightly or mitigated by reference to a consummated offender), "判处有期徒刑", "并处罚金" conform to criminal-document norms

---

### 🔍 Quality Checkpoint QC4: Final-Draft Completeness Verification

| Check Item | Verification Logic | On Failure |
|---|---|---|
| Structural completeness | Whether the judgment includes header, facts, reasons, operative part, and closing in full | Backtrack to S7; supplement missing sections |
| Operative part–reasons consistency | Whether offense, term, and fine in the operative part fully match conclusions in "本院认为" | Backtrack to S7; correct inconsistencies |
| Provision citation completeness | Whether all cited provisions are appended at the end | Backtrack to S7; supplement omitted provisions |
| Terminology zero-defect | Whether colloquial expressions, terminological errors, or format irregularities remain | Backtrack to S8; re-polish |
| Sentence calculation accuracy | Whether start/end dates of the sentence (including pretrial detention credit / 羁押折抵) are correct | Backtrack to S7; correct date calculation |

---

## V. Conditional Branches and Backtracking

### 5.1 Form-of-Crime Branch

```
In S1 extraction results, check the "criminal result" element:
├── Result is "unsuccessful / failed / attempted" → S2 must comprehend "criminal attempt"
│                                                  → S3 must list "consummated vs. attempted" as a dispute focus
│                                                  → S4 must retrieve Criminal Law Art. 23
│                                                  → S6 must add a "form-of-crime reasoning" layer
├── Result is "discontinued / 中止" → similar path, substitute Art. 24
└── Result is "consummated / successful" → skip form-of-crime–related steps
```

**Case 1 triggers this branch:** Zhang 3 "discovered and unsuccessful" → attempt path → S2 comprehends criminal attempt → S4 retrieves Art. 23 → S6 argues attempt established and applies lighter/mitigated punishment

**Case 2 does not trigger this branch:** An Xu "stole gold/silver jewelry and fled" → consummated → skip form-of-crime steps

### 5.2 Joint-Crime Branch

```
In S1 extraction results, check the "criminal subject" element:
├── Multiple subjects → S2 must comprehend "joint crime" and "principal/accessory"
│                     → S3 must list "each defendant's status" as a dispute focus
│                     → S4 must retrieve Criminal Law Arts. 25–29
│                     → S6 must add a "joint-crime reasoning" layer
└── Single subject → skip joint-crime–related steps
```

**Case 2 triggers this branch:** An Xu "together with Yang" → joint-crime path → S2 comprehends joint crime → S3 identifies principal/accessory dispute → S6 argues that accessory defense is not accepted

**Case 1 does not trigger this branch:** Zhang 3 acted alone → skip joint-crime steps

### 5.3 Defense-Opinion Response Branch

```
In S1 extraction results, check whether defense counsel opinions exist:
├── Defense opinions present → S3 must list issues raised as dispute foci
│                            → S6 must respond to each opinion (accept / reject with reasons)
│                            → S7 "本院认为" must include commentary on defense opinions
└── No defense opinions → skip defense-opinion response; respond only to prosecution charges
```

### 5.4 Sentencing Anomaly Backtracking

```
In QC3, check sentencing reasonableness:
├── Sentence outside statutory range → backtrack to S4 to confirm sentencing tier
│                                    → backtrack to S6 to recalculate sentence
├── Deviation from comparable cases >50% → backtrack to S5 to broaden case retrieval
│                                        → backtrack to S6 to supplement special-circumstance reasoning
└── Sentence within reasonable range → continue to S7
```

### 5.5 Offense-Change Backtracking

```
In S6 conviction reasoning, constitutive elements not satisfied:
├── A given element clearly not satisfied → backtrack to S2 to re-analyze possible offenses
│                                        → backtrack to S3 to re-identify dispute foci
│                                        → backtrack to S4 to re-retrieve provisions
│                                        → restart reasoning from S6
└── All elements satisfied → continue subsequent reasoning layers
```

---

## VI. Complete Examples

### Example 1: Attempted Fraud Case (Case 1)

**Input:** Case-fact narrative of the prosecution charging Zhang 3 with forging an ID card, impersonating another to defraud RMB 100,000, being discovered, and failing to obtain the funds.

**Execution process:**

| Step | Capability | Key Operation | Output Summary |
|:---:|:---:|---|---|
| S1 | AS4 | Extract subject (Zhang 3), act (forge ID, impersonate to defraud), purpose (repay debts), target amount (RMB 100,000), result (discovered; unsuccessful), time (28 April 2017) | Structured element inventory |
| S2 | AS5 | Comprehend four constitutive elements of fraud; comprehend definition and elements of criminal attempt | Concept analysis table |
| QC1 | — | Verify: elements cover all fraud constitutive elements ✓; "unsuccessful" maps to criminal attempt ✓ | Pass |
| S3 | AS6 | Identify dispute foci: ① consummated vs. attempted; ② which sentencing tier for RMB 100,000 | Dispute focus list |
| S4 | AS8 | Retrieve Criminal Law Arts. 266, 23, 67 para. 3 | Provision list |
| QC2 | — | Verify: both dispute foci have provision coverage ✓; sentencing-circumstance provisions complete ✓ | Pass |
| S5 | AS9 | Retrieve sentencing patterns in similar attempted-fraud cases; confirm reasonableness of seven-month range | Comparable-case report |
| S6 | AS16 | Four-layer reasoning: ① elements satisfied → fraud established; ② discovered for reasons independent of will → attempt; ③ "huge amount" tier + attempt lighter/mitigated; ④ truthful confession lighter → seven months + fine RMB 30,000 | Reasoning chain + adjudicative conclusions |
| QC3 | — | Verify: sentence within statutory range ✓; consistent with comparable cases ✓; all dispute foci addressed ✓ | Pass |
| S7 | AS49 | Assemble per criminal judgment format: header → fact-finding → this Court's opinion → operative part → sentence calculation → appeal notice → appended provisions | Judgment draft |
| S8 | AS50 | Standardize formulations such as "犯罪未遂", "比照既遂犯从轻或者减轻处罚", "判处有期徒刑", "并处罚金" | Final judgment |
| QC4 | — | Verify: structure complete ✓; operative part consistent with reasons ✓; terminology standard ✓; sentence calculation correct (2017.4.28–2017.11.27) ✓ | Pass |

**Output:** Complete criminal judgment sentencing Zhang 3 for fraud to fixed-term imprisonment of seven months and a fine of RMB 30,000.

**Conditional branches triggered:** Form-of-crime branch (attempt path) ✓; joint-crime branch not triggered (acted alone).

---

### Example 2: Household Theft Joint-Crime Case (Case 2)

**Input:** Case-fact narrative of the prosecution charging An Xu, together with Yang, with forced entry and household theft of gold and silver jewelry, and return of RMB 3,000.

**Execution process:**

| Step | Capability | Key Operation | Output Summary |
|:---:|:---:|---|---|
| S1 | AS4 | Extract subjects (An Xu + Yang), act (forced entry with tools; household theft), object (gold/silver jewelry), timeline (offense 2016.5.9 → arrest 2018.4.15), mitigating circumstance (returned RMB 3,000) | Structured element inventory |
| S2 | AS5 | Comprehend special criminalization standard for "household theft"; comprehend joint crime and principal/accessory criteria | Concept analysis table |
| QC1 | — | Verify: elements cover household-theft constitutive elements ✓; joint-crime concepts comprehended ✓ | Pass |
| S3 | AS6 | Identify dispute foci: ① An Xu's status in joint crime (principal vs. accessory); ② sentencing effect of returning RMB 3,000 | Dispute focus list |
| S4 | AS8 | Retrieve Criminal Law Arts. 264, 25, 67 para. 3, 52, 53, 64 | Provision list |
| QC2 | — | Verify: co-offender status dispute covered by Arts. 25–27 ✓; return-of-funds circumstance covered by Art. 64 ✓ | Pass |
| S5 | AS9 | Retrieve Shanghai-area household-theft sentencing patterns; retrieve precedents on accessory determination | Comparable-case report |
| S6 | AS16 | Four-layer reasoning: ① household-theft elements satisfied → theft established; ② plotted and jointly committed → joint crime established; ③ accessory claim lacks sufficient evidence → not accepted; ④ truthful confession + return lighter → six months + fine RMB 2,000 + restitution | Reasoning chain + adjudicative conclusions |
| QC3 | — | Verify: sentencing reasonable ✓; accessory defense addressed ✓; logically coherent ✓ | Pass |
| S7 | AS49 | Assemble per criminal judgment format; operative part includes two items (conviction/sentence + restitution order) | Judgment draft |
| S8 | AS50 | Standardize formulations such as "入户盗窃", "共同犯罪", "责令退赔违法所得后发还被害人" | Final judgment |
| QC4 | — | Verify: structure complete ✓; both operative items consistent with reasons ✓; defense-opinion response included ✓ | Pass |

**Output:** Complete criminal judgment sentencing An Xu for theft to fixed-term imprisonment of six months and a fine of RMB 2,000; ordered to make restitution of illegal gains to be returned to victim Gong; defense accessory opinion not accepted.

**Conditional branches triggered:** Joint-crime branch ✓; defense-opinion response branch ✓; form-of-crime branch not triggered (consummated).

---

## VII. Exception Handling and Fallback Mechanisms

| Exception Scenario | Handling |
|---|---|
| Case-fact narrative too brief; S1 cannot extract sufficient elements | Mark "facts unclear" in output, list missing elements, request supplementation, then re-execute |
| S2 cannot determine a unique offense (concurrence of offenses / 罪名竞合) | In S3, list offense selection as the primary dispute focus; in S6, argue constitutive elements for each candidate offense separately, choose one with reasoned justification |
| S5 finds no comparable cases | Mark "no direct comparable-case reference"; S6 sentencing reasoning relies only on statutory sentencing ranges and strengthens reasoned argumentation in the judgment |
| Logical contradiction appears in S6 reasoning chain | Trigger full-chain backtracking; re-examine from S1 whether element extraction is accurate; locate contradiction source step by step |
| Case involves multiple offenses with concurrent sentencing / 数罪并罚 | Run the full S2–S6 flow for each offense; at the end of S6 add a "concurrent sentencing reasoning" layer; in S7 assemble using multi-offense judgment format |

---

## VIII. Capability Call Dependency Summary

```
AS4 ──→ AS5 ──→ AS6 ──→ AS8 ──→ AS9 ──→ AS16 ──→ AS49 ──→ AS50
 │        │        │        │        │        │         │         │
 │        │        │        │        │        │         │         └─ Final output
 │        │        │        │        │        │         └─ Format assembly
 │        │        │        │        │        └─ Core reasoning (depends on AS4+AS8+AS6+AS9)
 │        │        │        │        └─ Sentencing calibration
 │        │        │        └─ Major premises supplied
 │        │        └─ Argumentation targets set
 │        └─ Conceptual framework established
 └─ Factual foundation laid
```

**Key dependency notes:**
- AS16 (deductive reasoning) is the core hub of the entire flow; it depends simultaneously on outputs of four upstream capabilities: AS4 (minor premise), AS8 (major premise), AS6 (argumentation targets), and AS9 (sentencing calibration)
- AS49 (format application) and AS50 (terminology standardization) are sequential output-layer capabilities: AS49 handles structure, AS50 handles wording; together they ensure formal quality of the final document
- AS5 (concept comprehension), though early in the flow, permeates all subsequent steps and is the foundational capability ensuring accuracy of legal application
