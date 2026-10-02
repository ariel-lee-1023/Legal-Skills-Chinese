---
name: evidence-argument-chain
description: |
  Trigger this skill when multiple pieces of evidence in a case must be systematically mapped to legal argumentative claims.
  Typical trigger scenarios include: preparing litigation documents (complaint, answer, counsel's brief) that require a complete evidence–claim correspondence; organizing the evidence list before trial and clarifying the purpose of proof for each item; reorganizing the evidence chain after the opposing party raises rebuttals; cases with multiple disputed issues where evidence must be grouped under different argumentative claims; assessing whether existing evidence sufficiently supports all claims and identifying weak links and gaps in the evidence chain.
  The core of this skill is to build a complete mapping of "claim → elements → evidence → probative-value assessment," ensuring every legal claim is adequately supported by evidence, every piece of evidence has a clear purpose of proof, and the overall argumentative chain is logically rigorous and hierarchically clear.
---

> **Chinese source (authoritative):** [`../../skills/evidence-argument-chain/SKILL.md`](../../skills/evidence-argument-chain/SKILL.md)

# Organizing the Evidence–Argument Chain

## Overview Table

| Item | Content |
|------|---------|
| **Capability Name** | Organizing the Evidence–Argument Chain |
| **Capability ID** | 35 |
| **Capability Type** | Evidence organization and argument construction |
| **Core Function** | Systematically map evidence to argumentative claims and build a complete evidence–claim correspondence |
| **Input Elements** | Case facts, parties' claims, existing evidentiary materials, legal grounds, disputed issues |
| **Output Deliverable** | A structured evidence–argument chain map, including complete claim–element–evidence correspondence and probative-value assessment |
| **Applicable Stages** | Full litigation process: pre-suit preparation, filing, production of evidence, trial, appeal, etc. |
| **Related Capabilities** | Review of the three attributes of evidence (三性审查), legal-element analysis, disputed-issue identification, legal drafting |
| **Difficulty Level** | ★★★★☆ |

## Legal Disclaimer

> **Important notice:** This skill file provides only methodological guidance for AI agents on organizing evidence and building argument chains; it does not constitute legal advice on any specific case. Final determination of evidence rests with the People's Court (人民法院). In actual cases, evidence organization should be professionally judged by a practicing lawyer based on the specific facts. When using this skill, the AI agent should clearly label its output as auxiliary analysis and advise the user to consult a qualified legal professional.

---

## I. Core Concepts

### 1.1 Definition of the Evidence–Argument Chain

An evidence–argument chain means decomposing a legal claim into its constituent elements (构成要件), then mapping concrete evidence item-by-item onto each element, forming a complete logical chain of "**claim → elements → evidence → probative value**."

```
┌─────────────────────────────────────────────────────┐
│                 Ultimate Legal Claim                  │
│         (e.g., defendant shall compensate loss)       │
├─────────┬─────────┬─────────┬───────────┤
│ Element A│ Element B│ Element C│ Element D  │
│ Breach   │ Damage   │ Causation│ Grounds for│
│ of fact  │ result   │          │ liability  │
├─────────┼─────────┼─────────┼───────────┤
│ Evid. A1 │ Evid. B1 │ Evid. C1 │ Evid. D1   │
│ Evid. A2 │ Evid. B2 │ Evid. C2 │ (to be     │
│ Evid. A3 │          │          │  supplemented)│
├─────────┼─────────┼─────────┼───────────┤
│ Probative│ Probative│ Probative│ Probative │
│ value:   │ value:   │ value:   │ value:    │
│ Strong   │ Strong   │ Medium   │ Weak      │
└─────────┴─────────┴─────────┴───────────┘
```

### 1.2 Key Terms

| Term | Definition | Notes |
|------|------------|-------|
| **Argumentative claim (论证主张)** | The legal conclusion the party seeks the court to find | e.g., "defendant breached the contract"; "plaintiff is entitled to rescind the contract" |
| **Constituent elements (构成要件)** | The legal conditions that must be satisfied for a claim to be established | Determined by substantive-law norms |
| **Object of proof (证明对象)** | The specific fact that must be proved by evidence | Each element may correspond to one or more objects of proof |
| **Evidentiary materials (证据材料)** | Materials used to prove case facts | Documentary evidence, physical evidence, witness testimony, electronic data, etc. |
| **Purpose of proof (证明目的)** | The specific factual proposition an item of evidence is intended to prove | One item of evidence may have multiple purposes of proof |
| **Probative value (证明力)** | The degree to which evidence proves the fact to be proved | Assessed as strong / medium / weak, or more finely graded |
| **Evidence chain (证据链)** | A system of proof formed by multiple items of evidence corroborating one another | Needed when a single item of evidence is insufficient |
| **Evidence gap (证据缺口)** | A state in which an element lacks adequate evidentiary support | Requires supplemental evidence or adjustment of argumentative strategy |
| **Burden of proof (举证责任)** | The duty to produce evidence and prove a particular fact | Determines who bears the adverse consequences if evidence is insufficient |

### 1.3 Hierarchical Structure of the Evidence–Argument Chain

```
Layer 1: Ultimate Claim
  │
  ├── Layer 2: Sub-claims / Disputed Issues
  │     │
  │     ├── Layer 3: Legal Elements (构成要件)
  │     │     │
  │     │     ├── Layer 4: Facts to Prove (待证事实)
  │     │     │     │
  │     │     │     ├── Layer 5: Evidence (证据材料)
  │     │     │     │     │
  │     │     │     │     └── Layer 6: Probative-Value Assessment (证明力评估)
```

---

## II. Complete Workflow

### Stage One: Claim Inventory and Element Decomposition

**Goal:** Clarify all legal claims and decompose each claim into its legal constituent elements.

#### Step 1: Identify and List All Legal Claims

- Start from the party's claims for relief or grounds of defense
- Distinguish primary claims from auxiliary (fallback / 备位) claims
- Clarify the legal basis of each claim (basis of the right of claim / basis of the right of defense — 请求权基础 / 抗辩权基础)

```
【Operational Template】
Claim ID: C-01
Claim content: Defendant shall pay plaintiff liquidated damages of RMB 500,000
Legal basis: Civil Code (《民法典》) Arts. 577, 585
Claim type: □ Primary claim / □ Fallback claim (备位主张)
Party bearing burden of proof: Plaintiff
```

#### Step 2: Decompose Legal Constituent Elements

- Extract elements from the legal norm (the claim-basis norm — 请求权基础规范)
- Distinguish positive elements (to be proved by the asserting party) from negative elements (requiring contrary proof by the other party)
- Annotate allocation of the burden of proof

```
【Operational Template】
Element decomposition for Claim C-01:
┌──────┬──────────────────────┬──────────────┬────────────────┐
│ Elem.│    Element content    │ Burden bearer│ Element nature │
│  ID  │                       │              │                │
├──────┼──────────────────────┼──────────────┼────────────────┤
│ E-01 │ Valid formation of    │   Plaintiff  │ Positive element│
│      │ the contract          │              │                │
│ E-02 │ Defendant's breach    │   Plaintiff  │ Positive element│
│ E-03 │ Liquidated-damages    │   Plaintiff  │ Positive element│
│      │ clause is valid       │              │                │
│ E-04 │ Liquidated-damages    │ Defendant    │ Negative element│
│      │ amount is reasonable  │ (contrary    │                │
│      │                       │  proof)      │                │
└──────┴──────────────────────┴──────────────┴────────────────┘
```

#### Step 3: Determine Facts to Be Proved

- Convert each element into concrete propositions of fact to be proved
- Distinguish undisputed facts from disputed facts
- Annotate the degree of dispute for disputed facts

```
【Operational Template】
Facts to be proved for Element E-02 "Defendant's breach":
  F-02-1: Defendant failed to deliver goods by the agreed deadline
          (30 June 2024) [Disputed — High]
  F-02-2: Goods delivered by defendant did not meet contractual quality
          standards [Disputed — Medium]
  F-02-3: Defendant unilaterally changed the place of delivery without
          plaintiff's consent [Undisputed]
```

### Stage Two: Evidence Inventory and Classification

**Goal:** Fully inventory existing evidentiary materials and classify them systematically.

#### Step 4: Compile the Evidence List

- Register every item of evidentiary material one by one
- Annotate basic attributes (type, source, form, original / copy)
- Preliminarily assess authenticity, lawfulness, and relevance (the "three attributes" — 三性)

```
【Evidence Registration Template】
┌──────┬────────────────┬──────┬──────┬──────┬──────────────────┐
│ Evid.│ Evidence name  │ Type │Source│ Form │ Three-attribute  │
│  ID  │                │      │      │      │ preliminary      │
├──────┼────────────────┼──────┼──────┼──────┼──────────────────┤
│ P-01 │ Purchase       │ Doc. │ Both │ Orig.│ Auth✓ Law✓ Rel✓ │
│      │ contract       │      │parties│     │                  │
│ P-02 │ Delivery note  │ Doc. │ Pl.  │ Copy │ Auth? Law✓ Rel✓ │
│ P-03 │ QC inspection  │ Doc. │ Third│ Orig.│ Auth✓ Law✓ Rel✓ │
│      │ report         │      │party │      │                  │
│ P-04 │ WeChat chat    │ Elec.│ Pl.  │ Screen│ Auth? Law? Rel✓│
│      │ records        │ data │      │ shot │                  │
│ P-05 │ Witness Zhang  │ Wit. │ Pl.'s│ Writ-│ Auth? Law✓ Rel✓ │
│      │ testimony      │ test.│ side │ ten  │                  │
└──────┴────────────────┴──────┴──────┴──────┴──────────────────┘
```

#### Step 5: Group Evidence

Group evidence preliminarily by direction of proof:

- **Positive evidence:** Supports one's own claims
- **Adverse evidence:** May be used by the other side against oneself
- **Neutral evidence:** Proves background facts
- **Corroborating evidence (补强证据):** Used to strengthen the probative value of other evidence

### Stage Three: Evidence–Claim Linkage (Core Step)

**Goal:** Establish precise correspondence between evidence and constituent elements.

#### Step 6: Match Evidence Element by Element

This is the core operation of the entire process. For each constituent element, retrieve available evidence one by one:

```
【Linkage Operation Rules】
1. One item of evidence may be linked to multiple elements (one evidence, multiple uses)
2. One element should preferably be supported by multiple items of evidence (multiple evidence, one element)
3. When linking, the specific purpose of proof of that evidence for that element must be stated
4. Annotate the mode of proof for that element (direct / indirect / corroborating)
```

```
【Evidence–Element Linkage Matrix】

              │ E-01       │ E-02       │ E-03            │ E-04
              │ Contract   │ Breach     │ Liquidated-     │ Amount
              │ formation  │            │ damages clause  │ reasonable
──────────────┼────────────┼────────────┼─────────────────┼────────
P-01 Purchase │ ★ Direct   │ ○ Indirect │ ★ Direct        │ ○ Indirect
     contract │            │            │                 │
P-02 Delivery │            │ ★ Direct   │                 │
     note     │            │            │                 │
P-03 QC report│            │ ★ Direct   │                 │
P-04 WeChat   │ ○ Corrob.  │ ★ Direct   │                 │
     records  │            │            │                 │
P-05 Witness  │            │ ○ Corrob.  │                 │
     testimony│            │            │                 │

Legend: ★ Direct proof  ○ Indirect proof / corroboration  Blank = no link
```

#### Step 7: Draft Purpose-of-Proof Statements

Write a concrete purpose of proof for each linkage:

```
【Purpose-of-Proof Statement Template】
Evidence P-04 (WeChat chat records) → Element E-02 (breach)
  Purpose of proof: To prove that on 5 July 2024 the defendant admitted
                    in WeChat that "the goods have indeed not been shipped yet,"
                    directly proving failure to deliver by the agreed deadline.
  Mode of proof: Direct proof
  Key content: On 5 July 2024 at 14:23, Li Mou, legal representative of the
               defendant, sent: "Sorry, there was a problem at the factory;
               the goods have indeed not been shipped yet"
  Strength of proof: Strong (party's admission — 当事人自认)
```

#### Step 8: Build Evidence Chains

When a single item of evidence is insufficient to fully prove an element, build an evidence chain:

```
【Evidence-Chain Construction Template】
Evidence chain for Element E-02 (defendant failed to deliver goods on time):

  P-01 (Purchase contract) ──→ Establishes delivery deadline as 30 June 2024
        │
        ↓
  P-02 (Delivery note) ──→ Shows actual shipment date as 15 July 2024
        │
        ↓
  P-04 (WeChat records) ──→ Defendant admitted on 5 July that goods not yet shipped
        │
        ↓
  P-05 (Witness testimony) ──→ Warehouse manager confirms goods received only on 15 July

  Chain logic: Contractual deadline (P-01) + Defendant's admission of delay (P-04)
               + Actual shipment record (P-02) + Witness corroboration (P-05)
               = Fully proves defendant delivered 15 days late

  Evidence-chain completeness assessment: ★★★★★ (Complete; multiple items corroborate)
```

### Stage Four: Probative-Value Assessment and Gap Analysis

**Goal:** Assess the strength of evidentiary support for each element and identify weak links.

#### Step 9: Assess Probative Value Element by Element

```
【Probative-Value Assessment Criteria】

Grade   │ Standard                                          │ Notes
────────┼───────────────────────────────────────────────────┼──────────────
★★★★★ │ Multiple direct evidence items corroborate; no    │ Extremely strong
        │ contradictions                                    │
★★★★☆ │ Direct evidence + corroboration; essentially no   │ Strong
        │ contradictions                                    │
★★★☆☆ │ Direct evidence without corroboration, or only an │ Medium
        │ indirect evidence chain                           │
★★☆☆☆ │ Only a single indirect item, or evidence has      │ Relatively weak
        │ defects                                           │
★☆☆☆☆ │ Almost no evidence or severe insufficiency        │ Extremely weak
```

```
【Element Probative-Value Summary】
┌──────┬──────────────────────┬──────────┬──────┬──────────────────────┐
│ Elem.│    Element content    │ # support│ Prob.│    Risk notice        │
│  ID  │                       │  items   │value │                      │
├──────┼──────────────────────┼──────────┼──────┼──────────────────────┤
│ E-01 │ Valid contract        │    2     │★★★★★│ No material risk      │
│      │ formation             │          │      │                      │
│ E-02 │ Defendant's breach    │    4     │★★★★★│ Delivery note is a    │
│      │                       │          │      │ copy                 │
│ E-03 │ Liquidated-damages    │    1     │★★★★☆│ Check standard-form   │
│      │ clause valid          │          │      │ clause issues         │
│ E-04 │ Liquidated-damages    │    1     │★★☆☆☆│ ⚠ Evidence weak       │
│      │ amount reasonable     │          │      │                      │
└──────┴──────────────────────┴──────────┴──────┴──────────────────────┘
```

#### Step 10: Identify Evidence Gaps and Remedial Recommendations

```
【Evidence-Gap Analysis Template】
┌──────────────────────────────────────────────────────────────┐
│ ⚠ Evidence-Gap Warning                                        │
├──────────────────────────────────────────────────────────────┤
│ Gap location: Element E-04 (liquidated-damages amount        │
│               reasonable)                                    │
│ Gap description: Lack of direct evidence proving the amount  │
│                  of actual loss                              │
│ Risk level: High (defendant may apply to reduce liquidated   │
│             damages)                                         │
│ Remedial options:                                            │
│   Option A: Supplement financial loss calculation sheet and  │
│             related vouchers                                 │
│   Option B: Apply for judicial appraisal of actual loss      │
│   Option C: Submit loss-reference data from similar industry │
│             breach cases                                     │
│   Option D: Adjust litigation strategy; reduce the claimed   │
│             liquidated-damages amount                        │
│ Priority: Option A > Option B > Option C > Option D          │
│ Deadline reminder: Complete supplementation before the end   │
│                    of the evidence-production period         │
│                    (举证期限)                                 │
└──────────────────────────────────────────────────────────────┘
```

### Stage Five: Argument-Chain Integration and Optimization

**Goal:** Integrate scattered evidence–element correspondences into a complete argument chain and optimize it.

#### Step 11: Draw the Argument-Chain Panorama

Integrate all claims, elements, and evidence into one complete argument-chain panorama (see Output Format Templates below).

#### Step 12: Optimize Argumentative Sequence

```
【Principles for Optimizing Argumentative Sequence】
1. Strong before weak: Put the best-supported elements first to build credibility
2. Simple before complex: Clear, straightforward facts first; complex disputes later
3. Chronological thread: Organize by the order in which facts occurred for ease of understanding
4. Logical progression: Arrange according to the progressive relationships of legal logic
5. Offense and defense together: Anticipate the other side's likely rebuttals and pre-position responsive evidence
```

#### Step 13: Anticipate Opposing Rebuttals and Prepare Responses

```
【Offense–Defense Anticipation Template】
┌──────────────┬────────────────┬────────────────────┬──────────┐
│ Own claim    │ Likely opposing│ Responsive evidence│ Response │
│              │ rebuttal       │ / strategy         │ strength │
├──────────────┼────────────────┼────────────────────┼──────────┤
│ Defendant    │ Force majeure  │ P-04 WeChat shows  │ Strong   │
│ late delivery│ (pandemic)     │ factory's own      │          │
│              │                │ problem            │          │
├──────────────┼────────────────┼────────────────────┼──────────┤
│ Liquidated   │ Amount too     │ Supplement actual- │ Medium   │
│ damages      │ high; should   │ loss evidence      │ (to be   │
│ RMB 500,000  │ be reduced     │                    │  suppl.) │
└──────────────┴────────────────┴────────────────────┴──────────┘
```

### Stage Six: Output and Delivery

#### Step 14: Generate Structured Output Documents

Generate the final evidence–argument chain document according to the "Output Format Templates" below.

#### Step 15: Quality Check

Verify item by item against the "Quality Checklist" below.

---

## III. Common Fields and Sources of Law

### 3.1 Element-Decomposition Reference by Case Type

| Case type | Typical claim | Core constituent elements | Principal sources of law |
|-----------|---------------|---------------------------|--------------------------|
| **Contract breach** | Seek breach liability | ① Valid contract formation ② Breach ③ Damage ④ Causation | Civil Code Arts. 577–585 |
| **Tort (general)** | Seek compensation for loss | ① Tortious act ② Damage ③ Causation ④ Fault | Civil Code Art. 1165 |
| **Tort (special)** | Seek compensation for loss | ① Tortious act ② Damage ③ Causation (burden reversed) | Civil Code Arts. 1169–1178, etc. |
| **Labor dispute** | Seek economic compensation | ① Employment relationship ② Grounds for termination ③ Compensation base ④ Years of service | Labor Contract Law (《劳动合同法》) Arts. 46–47 |
| **Intellectual property** | Seek cessation of infringement | ① Valid right ② Defendant's infringing acts ③ Without authorization | Copyright Law, Patent Law, Trademark Law |
| **Private lending (民间借贷)** | Seek repayment of loan | ① Lending agreement ② Delivery of funds ③ Maturity of repayment period ④ Non-repayment | Civil Code Arts. 667–680 |
| **Marriage & family** | Seek division of property | ① Marital relationship ② Property is joint marital property ③ Division plan is reasonable | Civil Code Arts. 1062–1066 |
| **Company dispute** | Shareholder harming company interests | ① Shareholder status ② Harmful act ③ Company interests damaged ④ Causation | Company Law (《公司法》) Arts. 20–21 |

### 3.2 Sources of Law for Burden-of-Proof Allocation

| Rule | Source of law | Applicable scenarios |
|------|---------------|----------------------|
| He who asserts must prove (谁主张谁举证) | Civil Procedure Law (《民事诉讼法》) Art. 67 | General principle |
| Reversal of burden of proof (举证责任倒置) | Relevant judicial interpretations | Medical damage, environmental pollution, product liability, etc. |
| Presumption from obstruction of proof (举证妨碍推定) | Interpretation of the Civil Procedure Law (《民诉法解释》) Art. 112 | One party controls evidence and refuses to produce it |
| Admission rules (自认规则) | Provisions on Civil Evidence (《民事证据规定》) Arts. 3–5 | Party's admission of facts adverse to itself |
| Order to produce documentary evidence (书证提出命令) | Provisions on Civil Evidence Arts. 45–48 | Documentary evidence under the other party's control |
| Standard of proof (证明标准) | Provisions on Civil Evidence Art. 86 | High degree of probability (高度盖然性) |

---

## IV. Validation and Screening Rules

### 4.1 Validity Validation of Evidence Linkages

Each evidence–element linkage must pass the following five validations:

| Validation item | Content | Pass criterion | If not passed |
|-----------------|---------|----------------|---------------|
| **Relevance validation** | Whether the evidence is logically linked to the element | Can reasonably support inference of the fact to be proved | Remove the linkage |
| **Direction-of-proof validation** | Whether the evidence supports (rather than rebuts) the element | Direction of proof is consistent | Mark as adverse evidence and prepare a response |
| **Clarity of purpose of proof** | Whether the purpose can be stated in one sentence | Purpose is concrete and clear | Redraft the purpose of proof |
| **Three-attribute validation (三性)** | Whether authenticity, lawfulness, and relevance are satisfied | No material defects in any of the three | Mark risk and prepare corroboration plan |
| **Non-duplication validation** | Whether it entirely duplicates other already-linked evidence | Provides incremental probative value | Mark as corroborating evidence or remove |

### 4.2 Completeness Screening Rules for Evidence Chains

```
【Completeness Check Rules】

Rule 1: Each positive element has at least 1 item of direct evidence
  → If not met: Mark as "Evidence gap — Severe"

Rule 2: Key elements (those corresponding to disputed issues) have at least 2 items of evidence
  → If not met: Mark as "Evidence gap — Medium"

Rule 3: Each item of direct evidence has at least 1 corroborating item
  → If not met: Mark as "Evidence weak — Needs corroboration"

Rule 4: No logical breaks in the evidence chain
  → If not met: Mark as "Logical break — Needs repair"

Rule 5: No "orphaned evidence" left unlinked
  → If not met: Re-examine that item's probative value or remove it
```

### 4.3 Logical Validation of the Argument Chain

```
【Logical Validation Checklist】
□ Whether claims match legal grounds (whether the claim basis — 请求权基础 — is correct)
□ Whether element decomposition is complete (whether necessary elements are omitted)
□ Whether facts to be proved cover the full meaning of the elements
□ Whether evidence proves the facts to be proved (and not other facts)
□ Whether contradictions exist among items of evidence (self-contradiction in one's own evidence)
□ Whether the argument chain contains circular reasoning
□ Whether the reasoning process contains jumps (missing intermediate links)
□ Whether burden-of-proof allocation is correct
```

---

## V. Output Format Templates

### 5.1 Complete Output Document Structure

```markdown
# Evidence–Argument Chain Analysis Report

## Basic Information
- Case name: [Case name]
- Cause of action: [Cause of action]
- Analysis date: [Date]
- Client's position: [Plaintiff / Defendant / Third party]

## I. Claim System

### Claim C-01: [Claim content]
- Legal basis: [Statute]
- Burden of proof: [Plaintiff / Defendant]
- Claim type: [Primary / Fallback]

### Claim C-02: [Claim content]
- ...

## II. Element Decomposition

### Constituent elements of Claim C-01
| Element ID | Element content | Burden bearer | Degree of dispute |
|------------|-----------------|---------------|-------------------|
| E-01 | ... | ... | High / Medium / Low / Undisputed |

## III. Evidence List
| Evidence ID | Evidence name | Type | Source | Form | Three-attribute assessment |
|-------------|---------------|------|--------|------|----------------------------|
| P-01 | ... | ... | ... | ... | ... |

## IV. Evidence–Element Linkage Matrix
[Matrix table]

## V. Detailed Evidence Chains by Element

### Element E-01: [Element content]
#### Facts to be proved
- F-01-1: ...
- F-01-2: ...

#### Corresponding evidence and purposes of proof
| Evidence | Purpose of proof | Mode of proof | Strength of proof |
|----------|------------------|---------------|-------------------|
| P-xx | ... | Direct / Indirect / Corroborating | Strong / Medium / Weak |

#### Evidence-chain diagram
[Chain description]

#### Probative-value assessment: ★★★★☆
#### Risk notice: [If any]

## VI. Evidence-Gap Analysis
| Gap location | Gap description | Risk level | Remedial options |
|--------------|-----------------|------------|------------------|

## VII. Offense–Defense Anticipation
| Own claim | Likely opposing rebuttal | Response plan | Response strength |
|-----------|--------------------------|---------------|-------------------|

## VIII. Recommended Argumentative Sequence
[Suggested order of developing the argument and reasons]

## IX. Overall Assessment
- Overall evidentiary sufficiency: [Rating]
- Strongest link: [Explanation]
- Weakest link: [Explanation]
- Key recommendations: [1–3 core recommendations]

## Confidence Statement
[See Confidence Annotation System]
```

---

## VI. Confidence Annotation System

### 6.1 Overall Analysis Confidence

| Confidence level | Marker | Meaning | Applicable conditions |
|------------------|--------|---------|------------------------|
| **High confidence** | 🟢 | Analytical conclusions are highly reliable | Facts clear, evidence sufficient, legal relationships clear |
| **Medium confidence** | 🟡 | Conclusions have reference value but involve uncertainty | Some facts unclear, evidence defective, legal application disputed |
| **Low confidence** | 🔴 | Conclusions for reference only; further professional judgment needed | Facts severely unclear, key evidence missing, legal issues complex |

### 6.2 Item-Level Linkage Confidence

Annotate confidence for each evidence–element linkage:

```
【Confidence Annotation Format】
P-01 → E-02 [Confidence: High 🟢]
  Reason: Original contract directly states the delivery deadline; authenticity undisputed

P-04 → E-02 [Confidence: Medium 🟡]
  Reason: WeChat screenshot not notarized; other side may challenge authenticity
  Suggestion: Recommend notarized preservation or blockchain evidence preservation

P-05 → E-02 [Confidence: Low 🔴]
  Reason: Witness is an employee of plaintiff's company; interest relationship may weaken
          probative value
  Suggestion: Seek a disinterested third-party witness
```

### 6.3 Factors Affecting Confidence

```
Factors that raise confidence:
  + Evidence is an original
  + Evidence has been notarized
  + Multiple items corroborate one another
  + Admission by the opposing party
  + Documents issued by state organs
  + Legal relationships simple and clear
  + Clear judicial interpretation or guiding case

Factors that lower confidence:
  - Evidence is a copy / screenshot
  - Single source of evidence
  - Witness has an interest relationship with a party
  - Electronic data not preserved
  - Legal application is disputed
  - Fact-finding relies on inference rather than direct evidence
  - Contrary evidence exists
  - Case involves novel legal issues
```

---

## VII. Common Errors and Prevention

### 7.1 Fatal-Error Table

| ID | Error type | Description | Consequences | Prevention |
|----|------------|-------------|--------------|------------|
| **F-01** | Omitted elements | Incomplete decomposition of legal elements; key elements omitted | Entire claim fails for lack of evidence on a necessary element | Strictly extract elements against the statute; refer to authoritative treatises' element breakdowns; cross-validate |
| **F-02** | Misallocated burden of proof | Mistakenly treating the other side's burden as one's own, or vice versa | Wasted proof resources or omitted necessary proof | Consult statutory and interpretive rules on burden allocation; distinguish positive from negative elements |
| **F-03** | Wrong evidence–element link | Linking evidence to an unrelated element | Key elements actually unsupported without being noticed | Validate relevance of each link; write clear purposes of proof |
| **F-04** | Ignoring adverse evidence | Focusing only on favorable evidence; overlooking adverse content in one's own materials | Exploited by the other side at trial; caught off guard | Analyze each item from both sides; view evidence from the opponent's perspective |
| **F-05** | Broken evidence chain | Lack of logical connection among items; cannot form complete proof | Judge cannot form inner conviction (心证); standard of proof not met | Draw evidence-chain diagrams; check logical links at each step |
| **F-06** | Misjudged standard of proof | Wrong judgment of the required standard (e.g., applying criminal standard in a civil case) | Over-proving wastes resources, or under-proving | Clarify the applicable standard (civil: high degree of probability — 高度盖然性) |

### 7.2 Common Traps

| ID | Trap name | Description | How to identify | Response strategy |
|----|-----------|-------------|-----------------|-------------------|
| **T-01** | Evidence-dumping trap | Submitting large volumes without clear purposes of proof; judge cannot grasp the focus | Check whether every item has a clear purpose-of-proof statement | Select core evidence; clearly annotate purposes; arrange in logical order |
| **T-02** | Lone-evidence dependency trap | Key element rests on a single item; collapse if that item is excluded | Check whether key elements have backup evidence | Prepare at least two independent evidence paths for key elements |
| **T-03** | Self-contradiction trap | Contradictions among one's own items weaken overall credibility | Cross-compare dates, amounts, persons, and other key information across all evidence | Explain or adjust the evidence combination promptly upon discovering contradictions |
| **T-04** | Over-inference trap | Jump from evidence to fact to be proved is too large; missing intermediate links | Check whether each inference step has adequate basis | Supplement intermediate evidence, or reduce the size of the inferential jump |
| **T-05** | Formal-defect trap | Content is sufficient but form fails requirements (e.g., no notarization, no original) | Check formal requirements item by item | Notarize/preserve in advance; prepare originals; perfect evidence form |
| **T-06** | Confused timeline trap | Timeline presented by evidence is unclear or contradictory | Arrange all evidence chronologically; check temporal logic | Produce a case timeline; ensure chronological coherence |
| **T-07** | Ignoring procedural evidence | Focusing only on substantive evidence; overlooking evidence of procedural matters (service, notice, etc.) | Check whether procedural elements need proof | Include procedural elements in the element decomposition |

---

## VIII. Special-Scenario Handling

### 8.1 Concurrent / Alternative Claims (多主张竞合)

When multiple alternative claim bases exist (e.g., concurrence of breach liability and tort liability):

```
Handling method:
1. Build an independent evidence–argument chain for each claim basis
2. Compare evidentiary sufficiency across chains
3. Annotate shared evidence (items that can support multiple claims)
4. Recommend the best-supported claim basis as the primary claim
5. Treat other claim bases as fallback claims (备位主张)

【Concurrence Analysis Template】
┌─────────────────┬──────────────────┬──────────────────┐
│                 │ Breach-liability │ Tort-liability   │
│                 │ path             │ path             │
├─────────────────┼──────────────────┼──────────────────┤
│ # of elements   │        4         │        4         │
│ Existing evidence│      100%       │       75%        │
│ coverage        │                  │                  │
│ Weakest element │ Loss amount (★★★)│ Fault proof (★★) │
│ Difficulty of   │     Medium       │       High       │
│ proof           │                  │                  │
│ Scope of        │ Foreseeability   │ Full compensation│
│ recovery        │ limit            │                  │
│ Recommendation  │ ★ Primary claim  │ Fallback claim   │
└─────────────────┴──────────────────┴──────────────────┘
```

### 8.2 Burden-of-Proof Reversal Scenarios

```
Handling method:
1. Clearly identify which elements are subject to burden reversal
2. For reversed elements, analyze contrary evidence the other side may submit
3. Prepare evidence to re-rebut the other side's contrary evidence
4. Note: Even with burden reversal, one's own side must still provide preliminary evidence

【Reversal Example: Medical Damage Liability】
  Patient must prove: ① Fact of treatment ② Damage consequence
  Medical provider must prove: ③ Treatment was without fault ④ No causation between
                               treatment and damage

  → Focus of patient's evidence chain: medical records, damage appraisal
  → Anticipate medical provider's contrary evidence: medical charts, treatment norms,
    expert opinions
  → Prepare re-rebuttal: authenticity challenges to charts; third-party appraisal
```

### 8.3 Electronic-Evidence Scenarios

```
Handling method:
1. Pay special attention to proof of authenticity of electronic data
2. Recommend notarized preservation or blockchain evidence preservation
3. Attend to integrity of electronic data (do not clip fragments)
4. Prepare explanations of generation, storage, and transmission of the electronic data

【Electronic-Evidence Corroboration Checklist】
□ Has notarized preservation been performed?
□ Is there hash-value verification?
□ Has the full context been preserved?
□ Can the generating subject of the electronic data be proved?
□ Is there other evidence corroborating the electronic data content?
□ Does it comply with the Electronic Signature Law (《电子签名法》) and related rules?
```

### 8.4 Lost / Hard-to-Obtain Evidence Scenarios

```
Handling method:
1. Apply for court investigation and evidence collection (Civil Procedure Law Art. 67(2))
2. Apply for an order to produce documentary evidence (Provisions on Civil Evidence Art. 45)
3. Invoke presumption from obstruction of proof (Interpretation of the Civil Procedure Law Art. 112)
4. Substitute an indirect evidence chain for direct evidence
5. Use empirical rules (经验法则) and factual presumptions

【Alternative Proof-Path Template】
Original evidence: [Lost / unobtainable evidence]
Alternative options:
  Path A: Apply for court collection → Feasibility [High/Med/Low] → Est. time [X days]
  Path B: Indirect evidence chain → Evidence needed [list] → Probative value [assess]
  Path C: Obstruction presumption → Preconditions [met?] → Success rate [assess]
  Path D: Factual presumption → Presumption basis [explain] → Risk of opposing
          rebuttal [assess]
```

### 8.5 Collective Litigation / Multi-Party Scenarios

```
Handling method:
1. Distinguish common evidence from individual evidence
2. Build an independent evidence sub-chain for each party
3. Annotate sharing relationships among items of evidence
4. Note how conflicts of interest among parties affect use of evidence

【Multi-Party Evidence Matrix】
              │ Party A │ Party B │ Party C │ Shared
──────────────┼─────────┼─────────┼─────────┼──────
P-01 Contract │   ✓     │   ✓     │         │  ✓
P-02 Payment  │   ✓     │         │         │
     voucher  │         │         │         │
P-03 Meeting  │         │   ✓     │   ✓     │
     minutes  │         │         │         │
P-04 Appraisal│   ✓     │   ✓     │   ✓     │  ✓
     report   │         │         │         │
```

---

## IX. Quality Checklist

### 9.1 Completeness Check

```
【Must-Complete Items】
□ 1. All legal claims have been listed
□ 2. Legal basis for each claim has been annotated
□ 3. Constituent elements of each claim have been fully decomposed
□ 4. Burden of proof has been correctly allocated
□ 5. All evidence has been registered in the list
□ 6. Three attributes of each item have been preliminarily assessed
□ 7. Evidence–element linkage matrix has been completed
□ 8. Purpose of proof for each linkage has been drafted
□ 9. Probative value of each element has been assessed
□ 10. Evidence gaps have been identified and remedial options proposed
```

### 9.2 Quality Check

```
【Quality Validation Items】
□ 11. No omitted constituent elements
□ 12. No incorrect burden-of-proof allocation
□ 13. No incorrect evidence–element linkages
□ 14. No self-contradictory evidence
□ 15. No orphaned unlinked evidence (or reasons explained)
□ 16. Key elements supported by multiple items of evidence
□ 17. No logical breaks in evidence chains
□ 18. Likely opposing rebuttals have been considered
□ 19. Argumentative sequence is reasonable
□ 20. Confidence annotations are accurate
```

### 9.3 Formal Check

```
【Formal Norm Items】
□ 21. Evidence IDs are uniformly standardized
□ 22. Element IDs are uniformly standardized
□ 23. Purposes of proof are clear and concrete
□ 24. Risk notices are prominently marked
□ 25. Output document structure is complete
```

---

## X. Complete Examples

### Example One: Simple Scenario — Private Lending Dispute (民间借贷纠纷)

#### Case Brief

On 15 March 2023, Zhang San borrowed RMB 100,000 from Li Si, agreeing on an annual interest rate of 8% and a one-year term, to be repaid by 15 March 2024. Zhang San issued an IOU (借条); Li Si paid the loan by bank transfer. After maturity, Zhang San did not repay. Li Si sued seeking repayment of principal RMB 100,000 plus interest.

#### Evidence–Argument Chain Analysis

**I. Claim System**

```
Claim C-01: Defendant Zhang San shall repay plaintiff Li Si loan principal of RMB 100,000
  Legal basis: Civil Code Art. 675
  Burden of proof: Plaintiff
  Claim type: Primary claim

Claim C-02: Defendant Zhang San shall pay loan interest (calculated at 8% per annum)
  Legal basis: Civil Code Arts. 674, 680
  Burden of proof: Plaintiff
  Claim type: Primary claim
```

**II. Element Decomposition**

```
Constituent elements of Claim C-01:
┌──────┬──────────────────────────────┬──────────────┬────────┐
│ Elem.│      Element content          │ Burden bearer│ Dispute│
│  ID  │                               │              │ degree │
├──────┼──────────────────────────────┼──────────────┼────────┤
│ E-01 │ Lending agreement (parties    │   Plaintiff  │  Low   │
│      │ reached agreement to lend)    │              │        │
│ E-02 │ Delivery of funds (loan       │   Plaintiff  │  Low   │
│      │ actually delivered)           │              │        │
│ E-03 │ Repayment period has matured  │   Plaintiff  │  None  │
│ E-04 │ Defendant has not repaid      │   Plaintiff  │  Low   │
└──────┴──────────────────────────────┴──────────────┴────────┘

Constituent elements of Claim C-02:
┌──────┬──────────────────────────────┬──────────────┬────────┐
│ Elem.│      Element content          │ Burden bearer│ Dispute│
│  ID  │                               │              │ degree │
├──────┼──────────────────────────────┼──────────────┼────────┤
│ E-05 │ Interest agreement is clear   │   Plaintiff  │  Low   │
│ E-06 │ Rate does not exceed statutory│   Plaintiff  │  None  │
│      │ cap                           │              │        │
└──────┴──────────────────────────────┴──────────────┴────────┘
```

**III. Evidence List**

```
┌──────┬────────────────┬──────┬──────┬──────┬──────────────────┐
│ Evid.│ Evidence name  │ Type │Source│ Form │ Three-attribute  │
│  ID  │                │      │      │      │ assessment       │
├──────┼────────────────┼──────┼──────┼──────┼──────────────────┤
│ P-01 │ Original IOU   │ Doc. │ Def. │ Orig.│ Auth✓ Law✓ Rel✓ │
│ P-02 │ Bank transfer  │ Doc. │ Bank │ Orig.│ Auth✓ Law✓ Rel✓ │
│      │ record         │      │      │      │                  │
│ P-03 │ Collection     │ Elec.│ Pl.  │ Screen│ Auth✓ Law✓ Rel✓│
│      │ WeChat records │ data │      │ shot │                  │
│ P-04 │ Collection SMS │ Elec.│ Pl.  │ Screen│ Auth✓ Law✓ Rel✓│
│      │ records        │ data │      │ shot │                  │
└──────┴────────────────┴──────┴──────┴──────┴──────────────────┘
```

**IV. Evidence–Element Linkage Matrix**

```
              │ E-01    │ E-02    │ E-03    │ E-04    │ E-05    │ E-06
              │ Lending │ Funds   │ Period  │ Non-    │ Interest│ Rate
              │ agreement│delivery│ matured │repayment│ agreed  │ lawful
──────────────┼─────────┼─────────┼─────────┼─────────┼─────────┼────────
P-01 IOU      │ ★ Direct│ ○ Indir.│ ★ Direct│         │ ★ Direct│ ★ Direct
P-02 Transfer │ ○ Corrob│ ★ Direct│         │         │         │
     record   │         │         │         │         │         │
P-03 WeChat   │         │         │         │ ★ Direct│         │
     collection│        │         │         │         │         │
P-04 SMS      │         │         │         │ ○ Corrob│         │
     collection│        │         │         │         │         │
```

**V. Detailed Evidence Chains by Element**

```
Element E-01 (Lending agreement):
  Fact to prove: Zhang San and Li Si agreed on 15 March 2023 to a loan of RMB 100,000
  Evidence chain:
    P-01 (IOU) → States "Borrowed from Li Si RMB One Hundred Thousand Yuan only";
                 Zhang San signed and affixed fingerprint
    P-02 (Transfer record) → Transfer remark "loan"; corroborates lending relationship
  Probative-value assessment: ★★★★★
  Risk notice: None

Element E-02 (Delivery of funds):
  Fact to prove: Li Si actually delivered the RMB 100,000 loan to Zhang San
  Evidence chain:
    P-02 (Bank transfer record) → Shows Li Si transferred RMB 100,000 to Zhang San
                                  on 15 March 2023
    P-01 (IOU) → States "now borrowed," indicating funds received
  Probative-value assessment: ★★★★★
  Risk notice: None (bank transfer record is the strongest delivery evidence)

Element E-03 (Repayment period matured):
  Fact to prove: Agreed repayment deadline of 15 March 2024 has matured
  Evidence chain:
    P-01 (IOU) → States "to be repaid by 15 March 2024"
    + Filing date later than 15 March 2024 (court may take judicial notice)
  Probative-value assessment: ★★★★★
  Risk notice: None

Element E-04 (Defendant has not repaid):
  Fact to prove: Zhang San has not repaid any of the loan to date
  Evidence chain:
    P-03 (WeChat collection records) → On 20 March 2024 Li Si demanded payment;
                                       Zhang San replied "give me a few more days"
    P-04 (SMS collection records) → On 5 April 2024 Li Si demanded again;
                                    Zhang San did not reply
  Probative-value assessment: ★★★★☆
  Risk notice: If defendant asserts partial repayment, watch for repayment vouchers

Elements E-05 (Interest agreement clear) + E-06 (Rate lawful):
  Fact to prove: Parties agreed on 8% per annum, not exceeding the statutory cap
  Evidence chain:
    P-01 (IOU) → States "annual interest rate 8%"
    + 8% does not exceed four times the one-year LPR (a question of legal application)
  Probative-value assessment: ★★★★★
  Risk notice: None
```

**VI. Evidence-Gap Analysis**

```
Evidence-gap analysis in this case: No severe gaps
Minor risk points:
  - P-03 and P-04 are screenshots; recommend notarized preservation
  - If defendant asserts repayment already made, prepare to respond
    (require defendant to prove)
```

**VII. Overall Assessment**

```
Overall evidentiary sufficiency: ★★★★★ (Extremely sufficient)
Strongest link: Lending agreement + delivery of funds
  (original IOU + bank transfer record — ironclad)
Weakest link: Non-repayment fact (relies on defendant's admission, but burden of
  proving repayment is on defendant)
Key recommendations:
  1. Recommend notarized preservation of WeChat and SMS records
  2. Prepare to respond to defendant's possible "already repaid" defense
Confidence: 🟢 High confidence
```

---

### Example Two: Complex Scenario — Product Quality Tort Dispute

#### Case Brief

Consumer Wang Mou purchased an electric kettle manufactured by Company A on an e-commerce platform in January 2024. In March 2024, while in use, the kettle suddenly burst, severely scalding Wang Mou's right hand. Wang was hospitalized for 15 days, incurred medical expenses of RMB 32,000, and missed 30 days of work. Wang asserts the kettle had a product defect and seeks joint and several compensation of RMB 150,000 total from Company A (producer) and E-commerce Platform B (seller) for medical expenses, lost wages, nursing care, mental distress damages, etc. Company A defends that the product had no defect and that the incident resulted from Wang's improper use. Platform B defends that it is merely a platform provider, not a seller.

#### Evidence–Argument Chain Analysis

**I. Claim System**

```
Claim C-01: Company A (producer) shall bear product liability and compensate plaintiff's loss
  Legal basis: Civil Code Arts. 1202, 1203
  Burden of proof: Plaintiff proves defect + damage + causation; defendant proves
                   exemption grounds
  Claim type: Primary claim

Claim C-02: E-commerce Platform B shall bear joint and several liability
  Legal basis: Civil Code Art. 1203; E-Commerce Law (《电子商务法》) Art. 38
  Burden of proof: Plaintiff proves Platform B is the seller or failed to fulfill
                   review duties
  Claim type: Primary claim

Claim C-03: Items and amounts of compensation
  Legal basis: Civil Code Arts. 1179, 1183
  Burden of proof: Plaintiff
  Claim type: Primary claim

  C-03-1: Medical expenses RMB 32,000
  C-03-2: Lost wages RMB 15,000 (monthly salary RMB 15,000 × 1 month)
  C-03-3: Nursing care RMB 6,000
  C-03-4: Nutritional expenses RMB 3,000
  C-03-5: Mental distress damages RMB 50,000
  C-03-6: Transportation RMB 2,000
  C-03-7: Follow-up treatment RMB 42,000
```

**II. Element Decomposition**

```
Constituent elements of Claim C-01 (Product liability — producer):
┌──────┬────────────────────────────────┬──────────────┬────────┐
│ Elem.│        Element content          │ Burden bearer│ Dispute│
│  ID  │                                 │              │ degree │
├──────┼────────────────────────────────┼──────────────┼────────┤
│ E-01 │ Product has a defect            │   Plaintiff  │  High  │
│ E-02 │ Plaintiff suffered personal     │   Plaintiff  │  Low   │
│      │ injury                          │              │        │
│ E-03 │ Causation between defect and    │   Plaintiff  │  High  │
│      │ damage                          │              │        │
│ E-04 │ Company A is the producer of    │   Plaintiff  │  Low   │
│      │ the product                     │              │        │
│ E-05 │ No statutory exemption grounds  │ Defendant    │  High  │
│      │ exist                           │ (contrary    │        │
│      │                                 │  proof)      │        │
└──────┴────────────────────────────────┴──────────────┴────────┘

Constituent elements of Claim C-02 (Platform liability):
┌──────┬────────────────────────────────┬──────────────┬────────┐
│ Elem.│        Element content          │ Burden bearer│ Dispute│
│  ID  │                                 │              │ degree │
├──────┼────────────────────────────────┼──────────────┼────────┤
│ E-06 │ Platform B is the seller or     │   Plaintiff  │  High  │
│      │ failed to fulfill review duties │              │        │
│ E-07 │ Platform B knew or should have  │   Plaintiff  │  High  │
│      │ known of the product defect     │              │        │
└──────┴────────────────────────────────┴──────────────┴────────┘

Constituent elements of Claim C-03 (Damages):
┌──────┬────────────────────────────────┬──────────────┬────────┐
│ Elem.│        Element content          │ Burden bearer│ Dispute│
│  ID  │                                 │              │ degree │
├──────┼────────────────────────────────┼──────────────┼────────┤
│ E-08 │ Actual occurrence and amount of │   Plaintiff  │ Medium │
│      │ each item of loss               │              │        │
│ E-09 │ Mental distress reached a       │   Plaintiff  │ Medium │
│      │ serious degree                  │              │        │
└──────┴────────────────────────────────┴──────────────┴────────┘
```

**III. Evidence List**

```
┌──────┬────────────────────────┬──────┬──────┬──────┬──────────────────┐
│ Evid.│    Evidence name        │ Type │Source│ Form │ Three-attribute  │
│  ID  │                         │      │      │      │ assessment       │
├──────┼────────────────────────┼──────┼──────┼──────┼──────────────────┤
│ P-01 │ Platform order          │ Elec.│ Pl.  │ Screen│ Auth✓ Law✓ Rel✓│
│      │ screenshots             │ data │      │ shot │                  │
│ P-02 │ Electronic invoice      │ Doc. │ Plat.│ Elec. │ Auth✓ Law✓ Rel✓ │
│ P-03 │ Burst kettle (physical) │ Phys.│ Pl.  │ Phys. │ Auth✓ Law✓ Rel✓ │
│ P-04 │ Accident-scene photos   │ Elec.│ Pl.  │ Photos│ Auth? Law✓ Rel✓│
│      │ (12)                    │ data │      │      │                  │
│ P-05 │ Product quality         │ Doc. │ Third│ Orig. │ Auth✓ Law✓ Rel✓ │
│      │ appraisal report        │      │party │      │                  │
│ P-06 │ Hospital diagnosis      │ Doc. │ Hosp.│ Orig. │ Auth✓ Law✓ Rel✓ │
│      │ certificate             │      │      │      │                  │
│ P-07 │ Inpatient medical       │ Doc. │ Hosp.│ Copy  │ Auth✓ Law✓ Rel✓ │
│      │ records                 │      │      │      │                  │
│ P-08 │ Medical expense         │ Doc. │ Hosp.│ Orig. │ Auth✓ Law✓ Rel✓ │
│      │ invoices (17)           │      │      │      │                  │
│ P-09 │ Certificate of lost     │ Doc. │ Empl.│ Orig. │ Auth✓ Law✓ Rel✓ │
│      │ work time               │      │oyer │      │                  │
│ P-10 │ Salary bank statements  │ Doc. │ Bank │ Orig. │ Auth✓ Law✓ Rel✓ │
│ P-11 │ Nursing-care receipts   │ Doc. │ Care │ Orig. │ Auth✓ Law✓ Rel✓ │
│      │                         │      │ co.  │      │                  │
│ P-12 │ Judicial appraisal      │ Doc. │ Appr.│ Orig. │ Auth✓ Law✓ Rel✓ │
│      │ opinion                 │      │ body │      │                  │
│ P-13 │ Product manual /        │ Doc. │ Prod.│ Orig. │ Auth✓ Law✓ Rel✓ │
│      │ certificate of conformity│     │      │      │                  │
│ P-14 │ Same-model product      │ Elec.│ Web  │ Screen│ Auth? Law? Rel✓│
│      │ complaint records       │ data │      │ shot │                  │
│ P-15 │ Family-member witness   │ Wit. │ Pl.'s│ Writ- │ Auth? Law✓ Rel✓ │
│      │ testimony at time of    │ test.│ side │ ten  │                  │
│      │ incident                │      │      │      │                  │
│ P-16 │ Transportation receipts │ Doc. │ Pl.  │ Orig. │ Auth✓ Law✓ Rel✓ │
│ P-17 │ Follow-up treatment     │ Doc. │ Hosp.│ Orig. │ Auth✓ Law✓ Rel✓ │
│      │ plan and cost estimate  │      │      │      │                  │
│ P-18 │ Screenshot of platform  │ Elec.│ Pl.  │ Screen│ Auth? Law? Rel?│
│      │ merchant onboarding     │ data │      │ shot │                  │
│      │ agreement               │      │      │      │                  │
└──────┴────────────────────────┴──────┴──────┴──────┴──────────────────┘
```

**IV. Evidence–Element Linkage Matrix**

```
              │E-01 │E-02 │E-03 │E-04 │E-05 │E-06 │E-07 │E-08 │E-09
              │Prod.│Pers.│Caus.│Prod-│Exem.│Plat.│Plat.│Loss │Mental
              │def. │inj. │ation│ucer │ption│role │fault│amt. │distress
──────────────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────
P-01 Order    │     │     │     │○Ind.│     │○Ind.│     │     │
     screenshots│   │     │     │     │     │     │     │     │
P-02 E-invoice│     │     │     │★Dir.│     │○Ind.│     │     │
P-03 Kettle   │★Dir.│     │○Ind.│     │     │     │     │     │
     physical │     │     │     │     │     │     │     │     │
P-04 Scene    │○Cor.│★Dir.│★Dir.│     │     │     │     │     │○Ind.
     photos   │     │     │     │     │     │     │     │     │
P-05 Quality  │★Dir.│     │★Dir.│     │★Dir.│     │     │     │
     appraisal│     │     │     │     │     │     │     │     │
P-06 Diagnosis│     │★Dir.│○Cor.│     │     │     │     │     │○Ind.
     cert.    │     │     │     │     │     │     │     │     │
P-07 Inpatient│     │★Dir.│     │     │     │     │     │○Ind.│○Ind.
     records  │     │     │     │     │     │     │     │     │
P-08 Medical  │     │     │     │     │     │     │     │★Dir.│
     invoices │     │     │     │     │     │     │     │     │
P-09 Lost-work│     │     │     │     │     │     │     │★Dir.│
     cert.    │     │     │     │     │     │     │     │     │
P-10 Salary   │     │     │     │     │     │     │     │★Dir.│
     statements│    │     │     │     │     │     │     │     │
P-11 Nursing  │     │     │     │     │     │     │     │★Dir.│
     receipts │     │     │     │     │     │     │     │     │
P-12 Appraisal│     │★Dir.│     │     │     │     │     │○Ind.│★Dir.
     opinion  │     │     │     │     │     │     │     │     │
P-13 Manual   │○Ind.│     │     │★Dir.│     │     │     │     │
P-14 Complaint│○Cor.│     │     │     │     │     │★Dir.│     │
     records  │     │     │     │     │     │     │     │     │
P-15 Witness  │     │○Cor.│★Dir.│     │     │     │     │     │
     testimony│     │     │     │     │     │     │     │     │
P-16 Transport│     │     │     │     │     │     │     │★Dir.│
     receipts │     │     │     │     │     │     │     │     │
P-17 Follow-up│     │     │     │     │     │     │     │★Dir.│
     treatment│     │     │     │     │     │     │     │     │
P-18 Onboarding│    │     │     │     │     │★Dir.│○Ind.│     │
     agreement│     │     │     │     │     │     │     │     │
```

**V. Detailed Evidence Chains for Key Elements**

```
═══════════════════════════════════════════════════
Element E-01 (Product has a defect) — Core disputed issue
═══════════════════════════════════════════════════

Facts to prove:
  F-01-1: The electric kettle at issue had a design defect or manufacturing defect
  F-01-2: The defect caused the product not to meet national or industry standards
          for personal safety

Evidence chain:
  P-03 (Burst kettle — physical)
    │ Purpose of proof: Show the physical state of the burst kettle; provide
    │                   specimen for appraisal
    │ Mode of proof: Direct proof
    │ Strength of proof: Strong
    ↓
  P-05 (Product quality appraisal report)
    │ Purpose of proof: Appraisal concludes welding process of the inner tank was
    │                   defective and did not meet GB4706.1-2005 requirements
    │ Mode of proof: Direct proof
    │ Strength of proof: Strong (authoritative third-party appraisal)
    ↓
  P-13 (Product manual / certificate of conformity)
    │ Purpose of proof: Contrast labeled standards with actual quality
    │ Mode of proof: Indirect proof
    │ Strength of proof: Medium
    ↓
  P-14 (Same-model complaint records)
    │ Purpose of proof: Show batch quality issues with this model, not an isolated case
    │ Mode of proof: Corroboration
    │ Strength of proof: Weak (web screenshots; authenticity pending verification)

  Chain logic: Physical display of defect state (P-03) + Professional appraisal
               confirming defect (P-05) + Label vs. actual mismatch (P-13) + Similar
               complaints corroborating (P-14)
               = Fully proves product defect

  Probative-value assessment: ★★★★☆
  Risk notice:
    ⚠ Authenticity of P-14 web complaint records may be challenged; recommend notarization
    ⚠ Defendant may apply for re-appraisal; prepare a response
    ⚠ Defendant may assert the product was conforming when shipped and the defect
      arose during use

═══════════════════════════════════════════════════
Element E-03 (Causation) — Core disputed issue
═══════════════════════════════════════════════════

Facts to prove:
  F-03-1: The kettle's defect caused the burst
  F-03-2: The burst directly caused Wang Mou's scalds

Evidence chain:
  P-05 (Quality appraisal report)
    │ Purpose of proof: Appraisal concludes welding defect caused uneven pressure
    │                   bearing of the inner tank during heating — direct cause of burst
    │ Mode of proof: Direct proof (causation: defect → burst)
    │ Strength of proof: Strong
    ↓
  P-04 (Accident-scene photos)
    │ Purpose of proof: Show scene after burst; spatial relationship between kettle
    │                   fragments and burn location; prove causation burst → scalds
    │ Mode of proof: Direct proof (causation: burst → scalds)
    │ Strength of proof: Medium
    ↓
  P-15 (Family-member witness testimony)
    │ Purpose of proof: Witness observed the burst and Wang Mou's injury process
    │ Mode of proof: Direct proof
    │ Strength of proof: Medium (witness is family; interest relationship)
    ↓
  P-06 (Diagnosis certificate)
    │ Purpose of proof: Diagnosis of "second-degree burn of right hand," consistent
    │                   with injury characteristics from kettle burst
    │ Mode of proof: Corroboration
    │ Strength of proof: Strong

  Chain logic: Defect caused burst (P-05) + Scene state after burst (P-04)
               + Eyewitness confirms course of events (P-15) + Injury consistent
               with accident (P-06)
               = Proves complete causal chain: defect → burst → scalds

  Probative-value assessment: ★★★★☆
  Risk notice:
    ⚠ Defendant may assert improper use by Wang Mou (e.g., dry boiling, overfilling)
      caused the burst
    ⚠ Witness is family; probative value may be weakened
    ⚠ Recommend supplementing: evidence of use environment at the time (e.g., residual
      water volume testing inside the kettle)

═══════════════════════════════════════════════════
Element E-06 (Platform B is seller or failed review duties) — Disputed issue
═══════════════════════════════════════════════════

Facts to prove:
  F-06-1: Platform B's role in the transaction was as seller, not merely platform
          service provider
  or
  F-06-2: Platform B failed to fulfill review duties regarding merchant qualifications
          and product quality

Evidence chain:
  P-18 (Screenshot of platform merchant onboarding agreement)
    │ Purpose of proof: Analyze legal relationship between platform and merchant;
    │                   determine whether platform participated in sales (e.g.,
    │                   unified collection, unified shipping)
    │ Mode of proof: Direct proof
    │ Strength of proof: Medium (requires legal interpretation)
    ↓
  P-01 (Order screenshots)
    │ Purpose of proof: Show degree of platform participation on the order page
    │                   (e.g., labels such as "platform self-operated," "platform
    │                   shipping")
    │ Mode of proof: Indirect proof
    │ Strength of proof: Medium
    ↓
  P-02 (Electronic invoice)
    │ Purpose of proof: Issuer information on the invoice to identify the selling entity
    │ Mode of proof: Indirect proof
    │ Strength of proof: Medium
    ↓
  P-14 (Same-model complaint records)
    │ Purpose of proof: Show multiple quality complaints about the product on the
    │                   platform; platform should have known of the defect
    │ Mode of proof: Direct proof (as to F-06-2)
    │ Strength of proof: Weak (authenticity pending verification)

  Probative-value assessment: ★★★☆☆
  Risk notice:
    ⚠ This is the weakest link in the case
    ⚠ If the platform is merely an information intermediary, it may not bear joint liability
    ⚠ Further investigation of the platform's actual role in the transaction is needed
```

**VI. Evidence-Gap Analysis**

```
┌──────────────────────────────────────────────────────────────┐
│ ⚠ Evidence-Gap Warning #1                                     │
├──────────────────────────────────────────────────────────────┤
│ Gap location: Element E-05 (no statutory exemption grounds)  │
│ Gap description: Defendant Company A may assert improper use │
│                  by Wang Mou (e.g., dry boiling); need        │
│                  rebuttal evidence                           │
│ Risk level: High                                             │
│ Remedial options:                                            │
│   Option A: Supplement evidence of Wang Mou's normal use     │
│             (e.g., use-habit statement; residue testing      │
│             inside kettle)                                   │
│   Option B: Add appraisal opinion "excluding improper use"   │
│             to the appraisal report                          │
│   Option C: Rely on burden allocation — exemption grounds    │
│             are for defendant to prove                       │
│ Priority: Option C (legal strategy) > Option B > Option A    │
└──────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────┐
│ ⚠ Evidence-Gap Warning #2                                     │
├──────────────────────────────────────────────────────────────┤
│ Gap location: Element E-06 (Platform B liability)            │
│ Gap description: Insufficient evidence that Platform B is    │
│                  the seller or was at fault                  │
│ Risk level: High                                             │
│ Remedial options:                                            │
│   Option A: Apply for court collection of complete           │
│             cooperation agreement between platform and       │
│             merchant                                         │
│   Option B: Obtain platform's review records for the merchant│
│   Option C: Collect platform handling records of similar     │
│             complaints                                       │
│   Option D: If evidence remains insufficient, consider       │
│             adjusting strategy to pursue only Company A      │
│ Priority: Option A > Option B > Option C > Option D          │
└──────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────┐
│ ⚠ Evidence-Gap Warning #3                                     │
├──────────────────────────────────────────────────────────────┤
│ Gap location: Element E-09 (seriousness of mental distress)  │
│ Gap description: RMB 50,000 mental distress damages requires │
│                  proof that harm reached a serious degree    │
│ Risk level: Medium                                           │
│ Remedial options:                                            │
│   Option A: Supplement disability-grade appraisal (verify    │
│             whether P-12 already includes it)                │
│   Option B: Supplement psychological treatment records       │
│   Option C: Submit scar photos to prove impact on appearance │
│ Priority: Option A > Option C > Option B                     │
└──────────────────────────────────────────────────────────────┘
```

**VII. Offense–Defense Anticipation**

```
┌────────────────┬────────────────────┬────────────────────┬────────┐
│ Own claim      │ Likely opposing    │ Responsive evidence│Response│
│                │ rebuttal           │ / strategy         │strength│
├────────────────┼────────────────────┼────────────────────┼────────┤
│ Product has a  │ Product passed     │ P-05 appraisal     │ Strong │
│ defect         │ factory inspection;│ takes priority over│        │
│                │ submit factory     │ factory inspection;│        │
│                │ inspection report  │ defect may be a    │        │
│                │                    │ latent batch defect│        │
├────────────────┼────────────────────┼────────────────────┼────────┤
│ Defect caused  │ Improper use by    │ Burden on          │ Medium │
│ burst          │ Wang Mou (dry      │ defendant; P-15    │        │
│                │ boiling, overfill, │ witness confirms   │        │
│                │ modification, etc.)│ normal use;        │        │
│                │                    │ appraisal excludes │        │
│                │                    │ improper use       │        │
├────────────────┼────────────────────┼────────────────────┼────────┤
│ Platform B     │ Platform is merely │ Obtain evidence of │ Weak   │
│ should be      │ an information     │ platform's         │ ⚠ To be│
│ liable         │ intermediary, not  │ participation in   │  suppl.│
│                │ a seller           │ the transaction;   │        │
│                │                    │ assert failure of  │        │
│                │                    │ review duties      │        │
├────────────────┼────────────────────┼────────────────────┼────────┤
│ Mental distress│ Amount too high;   │ P-12 disability    │ Medium │
│ RMB 50,000     │ scalds are not     │ grade; scar photos;│        │
│                │ permanent injury   │ reference awards   │        │
│                │                    │ in similar cases   │        │
├────────────────┼────────────────────┼────────────────────┼────────┤
│ Lost wages     │ Lost-work period   │ P-09 lost-work     │ Strong │
│ RMB 15,000     │ too long or income │ cert. + P-10 salary│        │
│                │ proof inaccurate   │ statements         │        │
│                │                    │ corroborate        │        │
└────────────────┴────────────────────┴────────────────────┴────────┘
```

**VIII. Recommended Argumentative Sequence**

```
Suggested order of developing the argument:

Step 1: Establish product purchase relationship (E-04 producer identity)
  → P-01 order + P-02 invoice + P-13 manual
  → Simple and clear; establish foundational facts

Step 2: Prove product defect (E-01 core element)
  → P-03 physical + P-05 appraisal report + P-14 complaint records
  → Core dispute; lead with the appraisal report

Step 3: Prove damage facts (E-02 personal injury)
  → P-04 scene photos + P-06 diagnosis certificate + P-07 medical records
  → Facts clear; advance quickly

Step 4: Establish causation (E-03 causal chain)
  → P-05 appraisal + P-04 photos + P-15 witness + P-06 diagnosis
  → Comprehensive argument forming a complete causal chain

Step 5: Argue damages amounts (E-08 items of loss)
  → P-08 through P-17 various expense vouchers
  → Itemize clearly with clean figures

Step 6: Claim mental distress damages (E-09 mental distress)
  → P-12 appraisal opinion + P-07 medical records
  → Raise last; balance law and equity

Step 7: Argue platform liability (E-06, E-07)
  → P-18 onboarding agreement + P-01 order + P-14 complaints
  → Weakest link last; adjust flexibly based on trial developments
```

**IX. Overall Assessment**

```
Overall evidentiary sufficiency: ★★★★☆ (Relatively sufficient, but with weak links)

Strongest links:
  - Product purchase relationship (ironclad)
  - Personal injury facts (hospital evidence sufficient)
  - Medical and other economic losses (vouchers complete)

Weakest links:
  - Platform B liability (insufficient evidence; needs corroboration) ★★☆☆☆
  - Mental distress damages amount (need disability appraisal supplement) ★★★☆☆

Key recommendations:
  1. [Urgent] Promptly obtain notarized preservation of P-14 web complaint records
  2. [Important] Apply for court collection of Platform B's cooperation agreement
     and review records with the merchant
  3. [Important] Confirm whether P-12 appraisal opinion includes disability-grade
     assessment; if not, apply for supplemental disability appraisal
  4. [Recommended] Prepare supplemental evidence "excluding improper use" to
     forestall defendant's improper-use defense
  5. [Strategy] If Platform B liability evidence remains insufficient, consider
     focusing the litigation on Company A to reduce risk of loss

Confidence: 🟡 Medium confidence
  Reason: Core claims (product defect + damages) are well supported, but platform
          liability involves substantial uncertainty; defendant's "improper use"
          defense requires focused prevention.
```

---

## Appendix: Quick Reference Card

```
┌─────────────────────────────────────────────┐
│   Evidence–Argument Chain Construction ·    │
│            Quick Reference Card             │
├─────────────────────────────────────────────┤
│                                             │
│  Six-step method:                           │
│  ① List claims → ② Split elements →         │
│  ③ Inventory evidence                       │
│  ④ Make linkages → ⑤ Assess strength →      │
│  ⑥ Fill gaps                                │
│                                             │
│  Core formula:                              │
│  Claim = Element1(evidence set) +           │
│          Element2(evidence set) + ...       │
│                                             │
│  Key checks:                                │
│  ✓ Each element has ≥1 direct evidence item │
│  ✓ Key elements have ≥2 evidence items      │
│  ✓ One's own evidence has no self-          │
│    contradiction                            │
│  ✓ Opposing rebuttals anticipated and       │
│    responses prepared                       │
│  ✓ Evidence gaps identified with remedial   │
│    options                                  │
│                                             │
│  Fatal errors — quick lookup:               │
│  ✗ Omitted constituent elements             │
│  ✗ Wrong burden-of-proof allocation         │
│  ✗ Evidence linked to wrong element         │
│  ✗ Ignoring adverse evidence                │
│  ✗ Logical break in the evidence chain      │
│                                             │
└─────────────────────────────────────────────┘
```
