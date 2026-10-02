---
name: legal-terminology
description: |
  Trigger this skill when an AI agent, in generating, reviewing, or revising any legal text (including but not limited to contracts, pleadings, legal opinions, judicial documents, statutory commentaries, legal memoranda, etc.), must ensure that legal terminology is accurate, unambiguous, and consistent with legal stylistic requirements. Trigger scenarios include:
  1. Drafting or revising legal instruments and needing to select correct legal terms;
  2. Reviewing legal text and finding nonstandard, confused, or ambiguous terminology;
  3. Converting everyday language into standardized legal expression;
  4. Translating or aligning Chinese and foreign legal terms;
  5. The user expressly requests terminology standardization of legal text;
  6. Precisely defining or explaining legal concepts.
  This skill is a foundational atomic capability for legal writing and runs through all legal-text production stages.
---

> **Chinese source (authoritative):** [`../../skills/legal-terminology/SKILL.md`](../../skills/legal-terminology/SKILL.md)

# Standardized Legal Terminology

## I. Overview Table

| Item | Content |
|---|---|
| **Capability Name** | Standardized Legal Terminology |
| **Capability Type** | Foundational atomic capability (text layer) |
| **Applicable Scenarios** | Generation, review, revision, and translation of all legal texts |
| **Core Objective** | Ensure legal terminology is accurate, unambiguous, and consistent with legal stylistic norms |
| **Input** | Text segments containing (or that should contain) legal terminology |
| **Output** | Terminology-standardized text, with a terminology correction note |
| **Upstream Dependencies** | Basic familiarity with the relevant area of law |
| **Downstream Capabilities** | Contract drafting, pleading writing, legal opinion writing, statutory commentary, and all other legal writing capabilities |
| **Risk Level** | High (terminology errors may cause defects in legal effect, distorted rights and obligations, or loss of litigation) |

## II. Legal Disclaimer

> **Important notice:** This skill file provides only operational guidance on standardized legal terminology for AI agents and does not constitute legal advice. Final confirmation of legal terms shall be based on currently effective statutes and regulations, judicial interpretations, and official terminology standards. In legal instruments involving major rights and interests, terminology use should be reviewed and confirmed by a practicing lawyer. Different jurisdictions and different branches of law may use different terms for the same concept; the agent should select appropriate expression according to the specific context.

## III. Core Concepts

### 3.1 What Is Standardized Legal Terminology

Standardized legal terminology means using, in legal texts, **professional vocabulary and fixed expressions recognized by the legal community and having determinate legal meaning**, so as to achieve precision, rigor, and uniformity of legal texts.

### 3.2 Three Dimensions of Standardized Expression

```
┌─────────────────────────────────────────────┐
│     Three Dimensions of Standardized Legal Terminology │
├───────────────┬──────────────┬───────────────┤
│   Accuracy    │ Consistency  │ Formality     │
│ (Accuracy)    │ (Consistency)│ (Formality)   │
├───────────────┼──────────────┼───────────────┤
│ Term meanings │ Same concept │ Conform to    │
│ correspond    │ uses the same│ solemn,       │
│ precisely to  │ term within  │ rigorous      │
│ legal rules;  │ the same     │ legal-document│
│ no ambiguity  │ text; do not │ style; avoid  │
│               │ freely swap  │ colloquial or │
│               │ near-synonyms│ literary tone │
└───────────────┴──────────────┴───────────────┘
```

### 3.3 Hierarchy of Sources for Terminology Norms

The normative force of legal terms shall be determined by the following priority:

| Priority | Source | Notes |
|---|---|---|
| 1 | **Original text of statutes and regulations** | Terms used in the Constitution, laws, and administrative regulations have the highest authority |
| 2 | **Judicial interpretations** | Terms in judicial interpretations issued by the Supreme People’s Court and the Supreme People’s Procuratorate |
| 3 | **Official terminology standards** | E.g., legal terminology norms in national standards such as GB/T 15834 |
| 4 | **Authoritative legal scholarship** | Prevailing expressions in mainstream textbooks and legal dictionaries |
| 5 | **Judicial practice conventions** | Expressions long and stably used in judicial documents |

### 3.4 Core Principles of Terminology Standardization

1. **Statutory-priority principle:** Where statutes and regulations provide express wording, that statutory wording must be used
2. **Identity principle:** Within the same text, the same concept is expressed by only one term
3. **Precision principle:** The extension and intension of a term must fully match the legal concept referred to
4. **Context-fit principle:** The same term may have different meanings in different branches of law; choose according to context
5. **Temporal-validity principle:** Terms must remain consistent with currently effective law; note terminology changes from statutory revisions

## IV. Core Terminology Standardization Comparison Tables

### 4.1 High-Frequency Easily Confused Terms (Civil Law)

| No. | ❌ Incorrect / Nonstandard Expression | ✅ Standardized Expression | Legal Source | Notes |
|---|---|---|---|---|
| 1 | 定金 / 订金 (confused) | **定金 (dingjin / deposit as security)** / **订金 (dingjin / advance payment)** | Civil Code Arts. 586–587 | 定金 has security effect (deposit penalty rule applies); 订金 is merely advance payment with no security effect—must be strictly distinguished |
| 2 | 违约金 / 赔偿金 (confused) | **违约金 (liquidated damages)** / **损害赔偿金 (damages)** | Civil Code Arts. 585, 584 | Liquidated damages are agreed liability; damages are compensatory, statutory or agreed |
| 3 | 保证 / 担保 (overly generic use) | **保证 (suretyship)** / **抵押 (mortgage)** / **质押 (pledge)** / **留置 (lien)** / **定金 (deposit)** | Civil Code, Security Part | “担保 (security)” is the umbrella concept; the specific form must be stated |
| 4 | 解除合同 / 终止合同 | **解除 (rescission / termination with possible retrospectivity)** / **终止 (termination)** | Civil Code Arts. 557, 562–566 | 解除 extinguishes going forward and may be retrospective; 终止 means the contractual rights and obligations cease |
| 5 | 不可抗力 / 意外事件 | **不可抗力 (force majeure)** / **意外事件 (unexpected event)** | Civil Code Art. 180 | Force majeure: unforeseeable, unavoidable, and insurmountable; unexpected event is not a statutory exemption ground |
| 6 | 诉讼时效 / 除斥期间 | **诉讼时效 (limitation of actions)** / **除斥期间 (preclusive period)** | Civil Code Arts. 188, 199 | Limitation of actions may be interrupted or suspended; preclusive period is fixed and extinguishes the right upon expiry |
| 7 | 善意 / 恶意 | **善意 (good faith / bona fide)** / **恶意 (bad faith / mala fide)** | Civil Code Art. 311 et al. | In law, 善意 means “did not know and ought not to have known,” not a moral evaluation |
| 8 | 无效 / 可撤销 / 效力待定 | Use separately | Civil Code Arts. 144–157 | Legal consequences differ entirely; must not be confused |
| 9 | 连带责任 / 按份责任 / 补充责任 | Use separately | Civil Code Arts. 177–178 | Different liability forms with major impact on parties’ rights and obligations |
| 10 | 所有权 / 使用权 / 收益权 | State by specific power | Civil Code Art. 240 | Ownership comprises four powers: possession, use, benefit, and disposition |

### 4.2 High-Frequency Easily Confused Terms (Criminal Law)

| No. | ❌ Incorrect / Nonstandard Expression | ✅ Standardized Expression | Legal Source | Notes |
|---|---|---|---|---|
| 11 | 犯罪嫌疑人 / 被告人 (confused) | **犯罪嫌疑人 (criminal suspect)** (investigation / review for prosecution) / **被告人 (defendant)** (trial stage) | Criminal Procedure Law Art. 12 et al. | Different stages use different designations; must not be mixed |
| 12 | 拘留 / 逮捕 / 拘传 | Use separately | Criminal Procedure Law Ch. 6 | Different compulsory measures with different conditions and time limits |
| 13 | 自首 / 坦白 | **自首 (voluntary surrender)** / **坦白 (confession)** | Criminal Law Art. 67 | Voluntary surrender: voluntary appearance + truthful confession; confession: truthful confession after passive apprehension |
| 14 | 主犯 / 从犯 / 胁从犯 | Use separately | Criminal Law Arts. 26–28 | Different roles in joint crime; significant sentencing differences |
| 15 | 故意 / 过失 (overly generic) | **直接故意 (direct intent)** / **间接故意 (indirect intent)** / **疏忽大意的过失 (negligence by oversight)** / **过于自信的过失 (negligence by overconfidence)** | Criminal Law Arts. 14–15 | Four forms of mens rea must be stated precisely |
| 16 | 缓刑 / 假释 / 减刑 | Use separately | Criminal Law Arts. 72–86 | Conditions of application and legal effects differ entirely |
| 17 | 罚金 / 罚款 | **罚金 (criminal fine)** (criminal) / **罚款 (administrative fine)** (administrative) | Criminal Law Art. 52; Administrative Penalty Law | 罚金 is an accessory criminal penalty; 罚款 is an administrative penalty—fundamentally different in nature |
| 18 | 累犯 / 再犯 | **累犯 (recidivist)** / **再犯 (reoffense)** | Criminal Law Arts. 65–66 | Recidivism has strict statutory conditions; reoffense is ordinary language |

### 4.3 High-Frequency Easily Confused Terms (Administrative Law)

| No. | ❌ Incorrect / Nonstandard Expression | ✅ Standardized Expression | Legal Source | Notes |
|---|---|---|---|---|
| 19 | 行政处罚 / 行政处分 | **行政处罚 (administrative penalty)** (external) / **行政处分 (administrative disciplinary sanction)** (internal) | Administrative Penalty Law / Civil Servant Law | Penalties target administrative counterparts; disciplinary sanctions target civil servants |
| 20 | 行政许可 / 行政审批 | **行政许可 (administrative license)** | Administrative Licensing Law Art. 2 | “行政审批 (administrative approval)” is not a strict legal term; normative texts should use “行政许可” |
| 21 | 行政复议 / 行政诉讼 | Use separately | Administrative Reconsideration Law / Administrative Litigation Law | Different remedies; must not be confused |
| 22 | 具体行政行为 / 行政行为 | **行政行为 (administrative act)** | 2014 revision of the Administrative Litigation Law | New law uniformly uses “行政行为”; no longer distinguishes “concrete” vs. “abstract” |
| 23 | 吊销 / 撤销 / 注销 | Use separately | Various special laws | 吊销 is a penalty; 撤销 is error correction; 注销 is procedural termination |

### 4.4 High-Frequency Easily Confused Terms (Litigation Procedure)

| No. | ❌ Incorrect / Nonstandard Expression | ✅ Standardized Expression | Legal Source | Notes |
|---|---|---|---|---|
| 24 | 原告 / 申请人 (confused) | **原告 (plaintiff)** (litigation) / **申请人 (applicant)** (arbitration / non-contentious procedures) | Civil Procedure Law / Arbitration Law | Different procedures use different designations |
| 25 | 上诉 / 申诉 / 申请再审 | Use separately | Relevant chapters of the Civil Procedure Law | Appeal targets judgments not yet effective; application for retrial targets judgments already effective |
| 26 | 裁定 / 判决 / 决定 | Use separately | Civil Procedure Law | Rulings resolve procedural issues; judgments resolve substantive issues; decisions resolve case-management issues |
| 27 | 管辖 / 管辖权 | Use according to context | Civil Procedure Law Ch. 2 | “管辖” refers to the system; “管辖权” refers to a specific court’s authority |
| 28 | 证据 / 证明 / 证明力 | Use separately | Civil Procedure Law Ch. 6 | Evidence is material; proof is an activity; probative force is the strength of evidence |
| 29 | 驳回起诉 / 驳回诉讼请求 | Use separately | Civil Procedure Law | Dismissal of action: fails filing conditions (ruling); dismissal of claims: substantively unfounded (judgment) |
| 30 | 中止 / 终结 / 中断 | Use separately | Various procedure laws | 中止 is suspension; 终结 is termination; 中断 is a limitation-period concept |

### 4.5 High-Frequency Easily Confused Terms (Contract and Commercial Law)

| No. | ❌ Incorrect / Nonstandard Expression | ✅ Standardized Expression | Legal Source | Notes |
|---|---|---|---|---|
| 31 | 甲方 / 乙方 (unclear) | **出租人/承租人 (lessor/lessee)**, **出卖人/买受人 (seller/buyer)**, **委托人/受托人 (principal/agent)**, etc. | Civil Code, Contracts Part | Use statutory designations; on first appearance, parenthetically note the short form |
| 32 | 利息 / 利率 | Use separately | Civil Code Art. 680 | Interest is an amount; interest rate is a ratio |
| 33 | 不可抗力 / 情势变更 | Use separately | Civil Code Arts. 180, 533 | Force majeure causes inability to perform; change of circumstances causes marked unfairness |
| 34 | 要约 / 要约邀请 | Use separately | Civil Code Arts. 472–473 | Offer has legal binding force; invitation to offer does not |
| 35 | 代位权 / 撤销权 | Use separately | Civil Code Arts. 535–542 | Subrogation is asserted against the secondary obligor; revocation targets the obligor’s improper acts |
| 36 | 股东 / 股民 / 投资者 | **股东 (shareholder)** | Company Law | Legal texts should use “股东”; “股民” and “投资者” are non-legal terms |
| 37 | 法定代表人 / 法人代表 | **法定代表人 (legal representative)** | Civil Code Art. 61 | “法人代表” is an erroneous expression; no such legal concept exists |
| 38 | 公章 / 合同专用章 | Use separately and specify | Relevant judicial interpretations | Different seals may have different legal effects |

### 4.6 High-Frequency Easily Confused Terms (Other Important Terms)

| No. | ❌ Incorrect / Nonstandard Expression | ✅ Standardized Expression | Legal Source | Notes |
|---|---|---|---|---|
| 39 | 权利 / 权力 | **权利 (right)** (private law) / **权力 (power)** (public law) | Jurisprudential consensus | Right is enjoyed by private subjects; power is exercised by public authorities |
| 40 | 法人 / 法人代表 / 自然人 | Use separately | Civil Code Art. 57 et al. | A legal person is an organization, not a natural person; do not equate a legal person with its responsible person |
| 41 | 侵权 / 违约 | Use separately | Civil Code, Tort / Contracts Parts | Different claim bases and constitutive elements |
| 42 | 抗辩 / 抗辩权 | Use separately | Jurisprudence / Civil Code | Defense is broad defensive pleading; right of defense is a specific right to resist a claim |
| 43 | 追诉时效 / 诉讼时效 | **追诉时效 (limitation for prosecution)** (criminal) / **诉讼时效 (limitation of actions)** (civil) | Criminal Law Art. 87 / Civil Code Art. 188 | Belong to different branches of law; must not be mixed |
| 44 | 赔偿 / 补偿 | **赔偿 (compensation / damages for wrong)** (unlawful act) / **补偿 (compensation for lawful act)** (lawful act) | State Compensation Law / Land Administration Law, etc. | 赔偿 is based on unlawfulness; 补偿 is based on loss caused by a lawful act |
| 45 | 法律 / 法规 / 规章 | Use by hierarchy of effect | Legislation Law | Laws (NPC and Standing Committee), administrative regulations (State Council), rules (ministries / local governments) |
| 46 | 应当 / 必须 / 可以 | Use by nature of the norm | Legislative drafting norms | “应当” is obligatory; “可以” is empowering; “必须” is the strongest tone |
| 47 | 以上 / 以下 / 以内 | Clarify whether the stated number is included | Civil Code Art. 1259; Criminal Law Art. 99 | In criminal and civil law, “以上,” “以下,” and “以内” ordinarily include the stated number |
| 48 | 日 / 工作日 / 自然日 | Use expressly | Various procedure laws | Period calculation differs; must specify |
| 49 | 生效 / 施行 / 公布 | Use separately | Legislation Law | Promulgation ≠ implementation ≠ taking effect; time points may differ |
| 50 | 知识产权 / 著作权 / 专利权 / 商标权 | Use by specific type | Civil Code Art. 123 | Intellectual property is the umbrella concept; the specific right type must be stated |

## V. Complete Workflow

### 5.1 Terminology Standardization Process

```
Input: Legal text to be processed
         │
         ▼
┌─────────────────────┐
│ Step 1: Identify legal terms │ ← Scan all legal terms and suspected terms in the text
│   and potential terminology issues │
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│ Step 2: Determine legal field │ ← Judge the branch of law (civil / criminal / administrative / commercial, etc.)
│   and document type          │ ← Judge document type (contract / pleading / judgment / opinion, etc.)
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│ Step 3: Verify terms one by one │ ← Verify accuracy against the source hierarchy
│                      │ ← Check whether terms match the branch of law
│                      │ ← Check whether term meanings fit the context
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│ Step 4: Consistency check │ ← Check whether the same concept uses the same term throughout
│                      │ ← Check whether first appearance has necessary definition / explanation
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│ Step 5: Style-fit check │ ← Check whether terminology expression conforms to legal style
│                      │ ← Eliminate colloquial, literary, and vague expressions
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│ Step 6: Temporal-validity check │ ← Confirm terms are consistent with currently effective law
│                      │ ← Watch for obsolete terms from repealed laws
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│ Step 7: Output standardized text │ ← Generate corrected text
│   and correction notes          │ ← Attach terminology correction comparison table and reasons
└─────────────────────┘
```

### 5.2 Detailed Operational Guidance for Each Step

#### Step 1: Identify Legal Terms and Potential Issues

**Operational points:**
- Scan the text sentence by sentence; mark all professional legal terms
- Pay special attention to these high-risk areas:
  - Party designations (plaintiff / defendant / applicant / respondent, etc.)
  - Descriptions of legal acts (rescission / termination / revocation / withdrawal, etc.)
  - Liability forms (joint and several / several / supplementary, etc.)
  - Right types (ownership / use right / creditor’s right / real right, etc.)
  - Procedural terms (jurisdiction / service / periods / limitation, etc.)
  - Quantity and time-limit expressions (above / below / day / business day, etc.)
- Mark everyday language that may need conversion into legal terms

#### Step 2: Determine Legal Field and Document Type

**Operational points:**
- Judge the branch of law from the text content, because the same word may mean different things in different branches
  - Example: “追诉时效” belongs to criminal law; “诉讼时效” belongs to civil law
  - Example: “罚金” belongs to criminal law; “罚款” belongs to administrative law
- Determine stylistic requirements by document type
  - Judicial documents: Strictest; must fully follow statutory terminology
  - Contract texts: Strict, but parties may agree on short forms
  - Legal opinions: Relatively strict; explanatory wording may be used appropriately
  - Legal memoranda: Relatively flexible, but core terms must still be standardized

#### Step 3: Verify Terms One by One

**Verification checklist:**

```
□ Does the term have an express formulation in statutes and regulations?
  → Yes: Must use the statutory formulation
  → No: Use judicial-interpretation or prevailing-doctrine formulation

□ Is the term’s meaning correct in the current branch-of-law context?
  → Example: “违约金 (liquidated damages)” should not appear in a criminal context

□ Does the term’s extension precisely match the referent?
  → Example: Do not use “担保 (security)” generically in place of “抵押 (mortgage)”

□ Is the term used in currently effective law?
  → Example: Do not continue using “经济合同 (economic contract)” (repealed)

□ Does the term have common objects of confusion?
  → Check one by one against the terminology comparison tables in Section IV of this skill
```

#### Step 4: Consistency Check

**Operational points:**
- Build an in-text terminology index; ensure the same concept uses the same term throughout
- If a short form is needed, define it expressly on first appearance
  - Incorrect example: `Party A (hereinafter the "Lessor")` ❌
  - Correct example: `Lessor Zhang San (hereinafter "Party A")` ✅
- Check whether synonym substitution creates ambiguity
  - Example: Earlier text uses “解除 (rescission)”; later text uses “终止 (termination)” for the same act → ambiguity arises

#### Step 5: Style-Fit Check

**Legal stylistic requirements:**

| Expressions to Avoid | Standardized Alternatives | Examples |
|---|---|---|
| Colloquial expressions | Written legal language | “打官司” → “提起诉讼起诉 (file a lawsuit)” |
| Vague qualifiers | Precise limits | “大概 / 左右” → specific amounts / dates |
| Literary rhetoric | Plain, accurate wording | “天价赔偿” → “赔偿金额为人民币XX元 (damages of RMB XX)” |
| Emotionally colored words | Neutral legal terms | “恶劣行径” → “违法行为 (unlawful act)” |
| Colloquial abbreviations | Full statutory names | “交强险” → “机动车交通事故责任强制保险 (compulsory traffic accident liability insurance)” (on first appearance) |
| Internet slang | Formal legal expression | “老赖” → “失信被执行人 (judgment debtor in bad faith)” |

#### Step 6: Temporal-Validity Check

**Key legal changes to watch:**

| Old Term | New Term | Reason for Change |
|---|---|---|
| 经济合同 (economic contract) | 合同 (contract) | Economic Contract Law repealed |
| 具体行政行为 (concrete administrative act) | 行政行为 (administrative act) | 2014 revision of the Administrative Litigation Law |
| 一般法人 / 特别法人 | 营利法人 / 非营利法人 / 特别法人 (for-profit / non-profit / special legal person) | Civil Code reclassification |
| 债权人会议 (creditors’ meeting) | 债权人会议 (retained) | Enterprise Bankruptcy Law continues to use it |
| 民事行为能力 (civil capacity for acts) | 完全 / 限制 / 无民事行为能力 (full / limited / no capacity for civil acts) | Civil Code refinement |
| Two-year limitation of actions | Three-year limitation of actions | Civil Code Art. 188 amendment |

#### Step 7: Output Standardized Text and Correction Notes

Output should include two parts:
1. **Full corrected text**
2. **Terminology correction comparison table** (see output format templates)

## VI. Verification and Screening Rules

### 6.1 Five-Step Method for Verifying Terminology Correctness

```
Step 1: Statutory verification
  → Look up the statutory formulation of the term in currently effective statutes and regulations
  → If found, the statutory formulation controls

Step 2: Context verification
  → Confirm the term’s meaning in the current branch of law / context
  → Exclude cross-branch terminology mixing

Step 3: Collocation verification
  → Confirm whether the term’s modifiers and verbs match customary legal collocations
  → Example: “承担违约责任” ✅  “负担违约责任” ⚠️  “背负违约责任” ❌

Step 4: Logic verification
  → Confirm whether the term’s logical relations in context hold
  → Example: Cannot say both “合同无效 (contract void)” and “解除合同 (rescind the contract)” in the same clause

Step 5: Audience verification
  → Confirm whether terminology use suits the target reader
  → For legal professionals: professional terms may be used directly
  → For non-professionals: a brief explanation may follow core terms
```

### 6.2 Terminology Selection Decision Tree

```
Need to express a legal concept
        │
        ▼
Is there a statutory term in statutes and regulations?
    │           │
   Yes          No
    │           │
    ▼           ▼
Use the statutory term   Is there a common formulation in judicial interpretations?
                    │           │
                   Yes          No
                    │           │
                    ▼           ▼
              Use the judicial-  Is there a recognized term in legal doctrine?
              interpretation          │           │
              formulation            Yes          No
                                   │           │
                                   ▼           ▼
                              Use the doctrinal  Construct a descriptive expression
                              term               and add an explanatory note
```

## VII. Output Format Templates

### 7.1 Terminology Correction Report Template

```markdown
## Legal Terminology Standardization Correction Report

**Text type:** [Contract / Pleading / Legal opinion / Other]
**Field:** [Civil / Criminal / Administrative / Commercial / Other]
**Correction date:** [YYYY-MM-DD]
**Number of corrections:** [N]

### Correction Comparison Table

| No. | Location | Original Expression | Corrected Expression | Correction Type | Reason | Severity |
|------|---------|---------|---------|---------|---------|---------|
| 1    | Art. X  | XXX     | XXX     | Terminology error | XXX     | 🔴 Critical |
| 2    | Art. X  | XXX     | XXX     | Imprecise term | XXX    | 🟡 Warning |
| 3    | Art. X  | XXX     | XXX     | Style defect | XXX     | 🔵 Suggestion |

### Correction Type Notes
- **Terminology error:** Wrong legal term used; may affect legal effect
- **Imprecise term:** Terminology insufficiently precise; may create ambiguity
- **Terminology confusion:** Near-synonyms with different meanings mixed
- **Obsolete term:** Old term from a repealed law used
- **Style defect:** Expression does not meet legal stylistic requirements
- **Consistency issue:** Different terms used for the same concept in the text

### Severity Notes
- 🔴 **Critical:** Must correct; otherwise may cause defects in legal effect or major misunderstanding
- 🟡 **Warning:** Recommended to correct; may create ambiguity or appear unprofessional
- 🔵 **Suggestion:** Optional correction at the stylistic-optimization level
```

### 7.2 Standardized Text Output Template

```markdown
## Standardized Text

[Output the full corrected text here; mark corrections in **bold**]

---
*Note: Bold portions are terminology standardization corrections in this pass.*
```

## VIII. Confidence Annotation System

When standardizing terminology, annotate confidence for each correction:

| Confidence Level | Mark | Meaning | Applicable Scenarios |
|---|---|---|---|
| **Certain** | `[Confidence: Certain]` | Terminology correction supported by express statutory provisions | Statutory-term substitution; correction of obvious errors |
| **High** | `[Confidence: High]` | Supported by judicial interpretations or prevailing doctrine | Standardization of prevailing terms; style corrections |
| **Medium** | `[Confidence: Medium]` | Based on judicial practice conventions | Preferring among multiple acceptable expressions |
| **Low** | `[Confidence: Low]` | Contested or needs further confirmation | Emerging-field terms; local variations |

**Usage rules:**
- Corrections at “Certain” and “High” confidence may be executed directly
- Corrections at “Medium” confidence should attach an explanation and recommend user confirmation
- Corrections at “Low” confidence should be expressly marked as “suggestions” with reasons for uncertainty

## IX. Common Errors and Prevention

### 9.1 Critical Error Table

| Error ID | Error Type | Error Example | Correct Expression | Possible Consequences | Prevention |
|---|---|---|---|---|---|
| F-01 | Wrong party designation | Calling someone “犯罪嫌疑人” at trial stage | “被告人 (defendant)” | Defect in document effect | Determine designation by procedural stage |
| F-02 | Confused liability form | Writing several liability where joint and several is required | Determine per statute | Major harm to parties’ rights | Check liability form in the statutory text |
| F-03 | Wrong contract-validity status | Calling a voidable contract void | Determine per statute | Erroneous legal application | Strictly distinguish void / voidable / pending validity |
| F-04 | Mixing criminal and civil terms | Using “罚金 (criminal fine)” in a civil document | “违约金” or “罚款” | Confusion of legal nature | Confirm the document’s branch of law |
| F-05 | Misnaming legal representative | “法人代表” | “法定代表人 (legal representative)” | Conceptual error; appears unprofessional | Remember “法人代表” is not a legal term |
| F-06 | Confusing 定金 and 订金 | Writing “订金” in a security clause | “定金” (if security effect is needed) | Loss of deposit-penalty protection | Choose based on whether security effect is needed |
| F-07 | Confusing limitation of actions and preclusive period | “撤销权的诉讼时效” | “撤销权的除斥期间 (preclusive period for the right of revocation)” | Fundamentally wrong legal application | Formation rights use preclusive periods; claim rights use limitation of actions |
| F-08 | Wrong judicial-document type | Using a “判决 (judgment)” to dismiss an action | “裁定 (ruling)” | Unlawful document form | Procedural issues → ruling; substantive issues → judgment |
| F-09 | Confusing 赔偿 and 补偿 | Writing expropriation “补偿” as “赔偿” | “补偿” | Implies the act was unlawful; invites dispute | Lawful act → 补偿; unlawful act → 赔偿 |
| F-10 | Confusing right and power | “公民的选举权力” | “公民的选举权利 (citizens’ right to vote)” | Fundamentally wrong jurisprudential concept | Private subject → right; public authority → power |

### 9.2 Common Traps

#### Trap 1: Literal-Meaning Trap
- **Manifestation:** Understanding legal terms by everyday meanings
- **Example:** “善意” in “善意取得 (bona fide acquisition)” ≠ moral goodness; it means “did not know and ought not to have known”
- **Prevention:** Always take the legal definition as controlling; do not infer from everyday meaning

#### Trap 2: Near-Synonym Substitution Trap
- **Manifestation:** Substituting near-synonyms for legal terms to avoid repetition
- **Example:** Replacing “解除合同” with “取消合同” / “废除合同”
- **Prevention:** Legal terminology does not pursue literary lexical variety; the same concept must use the same term

#### Trap 3: Cross-Branch Transplantation Trap
- **Manifestation:** Transplanting a term from one branch of law into another
- **Example:** Writing in a civil contract “甲方应受到处罚” (“处罚 / penalty” is a public-law concept)
- **Prevention:** Confirm the term’s branch of law matches the text’s context

#### Trap 4: Old-Law Inertia Trap
- **Manifestation:** Continuing to use old terms superseded by new law
- **Example:** Continuing to use “具体行政行为” (should be “行政行为”)
- **Prevention:** Track statutory revision developments; periodically update the terminology bank

#### Trap 5: Translation Calque Trap
- **Manifestation:** Literally translating foreign legal terms into Chinese in ways that do not fit the Chinese legal system
- **Example:** Literally rendering “consideration” as “对价” in a Chinese contract-law context
- **Prevention:** Use corresponding terms in the Chinese legal system; add notes where necessary

#### Trap 6: Umbrella-Concept Substitution Trap
- **Manifestation:** Using an umbrella concept generically in place of a specific subordinate concept that should be used precisely
- **Example:** Using “担保” in place of “抵押” or “质押” that should be specified
- **Prevention:** When precise expression is needed, use the most specific subordinate concept

#### Trap 7: Quantity-Boundary Ambiguity Trap
- **Manifestation:** Using “以上 / 以下” without clarifying whether the stated number is included
- **Example:** “三年以上有期徒刑”—does it include three years?
- **Prevention:** Note the rules in different laws on “以上 / 以下” (Criminal Law expressly includes the stated number); annotate expressly where necessary

## X. Special Scenario Handling

### 10.1 Emerging-Field Terminology

For emerging fields such as data compliance, artificial intelligence, and blockchain:

```
Handling strategy:
1. Prefer terms already used in statutes and regulations
   → Example: “个人信息处理者 (personal information handler)” in the Personal Information Protection Law
2. If no statutory term, use formulations in official documents
   → Example: Terms in national standards and departmental rules
3. If neither exists, use industry-prevailing terms and add a definition clause
   → Example: “For purposes of this Agreement, ‘smart contract’ means …”
4. Avoid using pure technical terms without legal definition
   → Example: Do not use “Token” directly; define it as a “digital credential” or other legally intelligible expression
```

### 10.2 Cross-Border Legal Text Terminology

```
Handling strategy:
1. For foreign legal concepts in Chinese legal texts, use corresponding terms in the Chinese legal system
2. If no direct counterpart, use a descriptive expression and annotate the original
   → Example: “信托受益人 (beneficiary)”
3. In bilingual contracts, specify which language version controls
4. Watch for “false friends”—terms that look similar but mean different things
   → Example: Common-law “consideration” ≠ Chinese-law “对价” (Chinese law has no such concept)
```

### 10.3 Party-Defined Custom Terminology

```
Handling strategy:
1. Parties may define custom terms in contracts, but must not conflict with mandatory legal provisions
2. Custom terms should be expressly defined in the contract’s “definitions” clause
3. Custom terms should not create confusion with statutory terms
   → Incorrect example: Defining “违约金” to include the meaning of “定金”
4. Recommend parenthetically annotating the legal nature after a custom term
   → Example: “服务保证金 (in the nature of a deposit / 定金)”
```

### 10.4 Plain-Language Explanation of Legal Terms

```
Handling strategy:
When explaining legal content to non-professionals:
1. First use the standardized legal term
2. Then provide a plain-language explanation in parentheses or a footnote
   → Example: “本案适用诉讼时效（即法律规定的起诉期限）为三年”
3. Plain-language explanation must not replace the legal term itself
4. Plain-language explanation must accurately reflect the term’s meaning and must not oversimplify into misunderstanding
```

## XI. Quality Checklist

After completing terminology standardization, check the following items one by one:

### 11.1 Basic Checks

```
□ Are all legal terms consistent with currently effective statutes and regulations?
□ Are there obsolete terms from repealed laws?
□ Do party designations match the procedural stage / procedure type?
□ Are liability forms accurate (joint and several / several / supplementary)?
□ Are contract-validity statuses accurate (valid / void / voidable / pending validity)?
□ Are right types accurate (real rights / creditor’s rights / IP rights, etc.)?
```

### 11.2 Consistency Checks

```
□ Does the same concept use the same term throughout?
□ Are short forms expressly defined on first appearance?
□ Is terminology use logically consistent before and after?
□ When citing statutory provisions, are terms identical to the original text?
```

### 11.3 Precision Checks

```
□ Is an umbrella concept used in place of a subordinate concept that should be expressed precisely?
□ Are quantity and time-limit expressions clear (including / excluding the stated number)?
□ Is “日 (day)” specified clearly (calendar day / business day)?
□ Are amounts standardized (currency + upper/lower case numerals)?
□ Are there vague qualifiers (“大约 / 左右 / 若干,” etc.)?
```

### 11.4 Style Checks

```
□ Have all colloquial expressions been eliminated?
□ Have all emotionally colored words been eliminated?
□ Have all internet slang / vernacular expressions been eliminated?
□ Has the solemnity of legal documents been preserved?
□ Does use of passive / active voice conform to legal stylistic convention?
```

### 11.5 Special Checks

```
□ Are cross-border terms correctly corresponded?
□ Are emerging-field terms sufficiently defined?
□ Do party-defined custom terms not conflict with statutory terms?
□ Is each correction annotated with confidence?
□ Have all critical-level corrections been addressed?
```

## XII. Complete Examples

### Example 1: Simple Scenario — Contract Clause Terminology Standardization

#### Input Text

```
第五条 违约条款
1. 如甲方未按时交货，乙方有权取消合同，并要求甲方赔偿订金的双倍。
2. 因天灾人祸等意外事件导致不能交货的，甲方不用负责。
3. 双方发生纠纷的，可以打官司解决，诉讼有效期为两年。
4. 甲方的法人代表应在合同上签字盖章。
```

#### Output

**Terminology Correction Report:**

| No. | Location | Original Expression | Corrected Expression | Correction Type | Reason | Severity |
|---|---|---|---|---|---|---|
| 1 | Art. 5.1 | 取消合同 | **解除合同** | Terminology error | “取消” is not a legal term; use “解除” as provided in Civil Code Arts. 562–566 | 🔴 Critical |
| 2 | Art. 5.1 | 订金的双倍 | **定金的双倍** | Terminology confusion | Deposit penalty rule requires “定金” (Civil Code Art. 587); “订金” has no double-return effect | 🔴 Critical |
| 3 | Art. 5.2 | 天灾人祸等意外事件 | **不可抗力** | Imprecise term | Neither “天灾人祸” nor “意外事件” accurately states the statutory exemption ground; use “不可抗力” (Civil Code Art. 180) | 🔴 Critical |
| 4 | Art. 5.2 | 不用负责 | **不承担违约责任** | Style defect | “不用负责” is colloquial; use “不承担违约责任” | 🟡 Warning |
| 5 | Art. 5.3 | 打官司 | **向有管辖权的人民法院提起诉讼** | Style defect | “打官司” is colloquial | 🟡 Warning |
| 6 | Art. 5.3 | 诉讼有效期为两年 | **诉讼时效期间为三年** | Terminology error + content error | ① “诉讼有效期” should be “诉讼时效期间”; ② Civil Code Art. 188 provides a three-year ordinary limitation period, not two years | 🔴 Critical |
| 7 | Art. 5.4 | 法人代表 | **法定代表人** | Terminology error | “法人代表” is not a legal term; it should be “法定代表人” (Civil Code Art. 61) | 🔴 Critical |

**Corrected Text:**

```
第五条 违约责任
1. 如出卖人未按约定期限交付标的物，买受人有权**解除**合同，并要求出卖人
   双倍返还**定金**（《民法典》第五百八十七条）。
2. 因**不可抗力**导致不能交付标的物的，出卖人**不承担违约责任**，但应当
   及时通知买受人并在合理期限内提供证明（《民法典》第五百九十条）。
3. 双方因履行本合同发生争议的，可**向有管辖权的人民法院提起诉讼**。
   本合同项下纠纷的**诉讼时效期间**依照法律规定执行。
4. 出卖人的**法定代表人**或授权代表应在本合同上签字并加盖公章。
```

`[Confidence: Certain]` — All corrections are supported by express statutory provisions.

---

### Example 2: Complex Scenario — Criminal Defense Statement Terminology Standardization

#### Input Text

```
尊敬的审判长、审判员：

    我受犯罪嫌疑人王某的委托，担任其辩护律师。现就本案发表如下辩护意见：

    一、关于犯罪事实
    犯罪嫌疑人王某系初犯，且在被抓获后主动交代了全部犯罪事实，属于自首，
依法可以减轻处罚。

    二、关于量刑
    犯罪嫌疑人王某犯罪情节较轻，建议法院判处缓期执行。王某已向被害方赔偿
了全部损失并取得谅解，具有悔过表现。

    三、关于附带民事赔偿
    犯罪嫌疑人已支付了全部赔偿金，包括医药费、误工费和精神赔偿金共计
十万元左右。

    综上，请求法院对犯罪嫌疑人从轻处罚。

                                        辩护人：李律师
                                        2024年X月X日
```

#### Output

**Terminology Correction Report:**

| No. | Location | Original Expression | Corrected Expression | Correction Type | Reason | Severity |
|---|---|---|---|---|---|---|
| 1 | Entire text (7 places) | 犯罪嫌疑人 | **被告人** | Terminology error | A defense statement is submitted at the trial stage; the designation should be “被告人,” not “犯罪嫌疑人” (Criminal Procedure Law Art. 12: no person shall be determined guilty except by a people’s court judgment according to law) | 🔴 Critical |
| 2 | Part One | 被抓获后主动交代 | **归案后如实供述自己的罪行** | Imprecise term + wrong characterization | Confession after apprehension is “坦白,” not “自首.” Voluntary surrender requires “自动投案” (Criminal Law Art. 67 para. 1); truthful confession after passive apprehension is “坦白” (Art. 67 para. 3) | 🔴 Critical |
| 3 | Part One | 自首 | **坦白** (if truly passive apprehension) | Terminology error | Same as above. If truly passive apprehension, voluntary surrender is not established; characterize as confession | 🔴 Critical |
| 4 | Part One | 可以减轻处罚 | Confession: **可以从轻处罚**; Voluntary surrender: **可以从轻或者减轻处罚** | Imprecise term | The statutory sentencing circumstance for confession is “may be given a lighter punishment,” not “reduced punishment” (Criminal Law Art. 67 para. 3) | 🔴 Critical |
| 5 | Part Two | 缓期执行 | **缓刑** | Terminology confusion | “缓期执行” usually refers to death sentence with suspension of execution (死缓); the context here should be “宣告缓刑” (Criminal Law Art. 72) | 🔴 Critical |
| 6 | Part Two | 悔过表现 | **悔罪表现** | Imprecise term | The legal term is “悔罪表现” (one of the conditions for probation under Criminal Law Art. 72) | 🟡 Warning |
| 7 | Part Three | 附带民事赔偿 | **附带民事诉讼赔偿** or **民事赔偿** | Imprecise term | Clarify whether incidental civil action was instituted (Criminal Procedure Law Art. 101) | 🟡 Warning |
| 8 | Part Three | 精神赔偿金 | **精神损害赔偿** (note: generally not supported in incidental civil action) | Imprecise term + legal-application issue | ① Standardized wording is “精神损害赔偿”; ② Per judicial interpretation, incidental civil actions in criminal cases generally do not entertain claims for mental distress damages | 🔴 Critical |
| 9 | Part Three | 十万元左右 | **人民币壹拾万元（¥100,000.00）** (or specific amount) | Style defect | “左右” is vague; amounts in legal documents must be precise and state the currency | 🟡 Warning |
| 10 | Signature block | 李律师 | **辩护人：李XX，XX律师事务所律师** | Style defect | Defense statement signature block should state the defense counsel’s full name and practicing institution | 🟡 Warning |

**Corrected Text:**

```
尊敬的审判长、审判员：

    北京XX律师事务所接受**被告人**王某的委托，指派我担任其辩护人。
现根据事实和法律，发表如下辩护意见：

    一、关于量刑情节
    **被告人**王某系初犯、偶犯，且在**归案后如实供述自己的罪行**，
依照《中华人民共和国刑法》第六十七条第三款之规定，属于**坦白**，
**可以从轻处罚**。

    二、关于量刑建议
    **被告人**王某犯罪情节较轻，有**悔罪表现**，且已积极赔偿被害人
损失并取得谅解，符合《中华人民共和国刑法》第七十二条规定的**缓刑**
适用条件，建议对**被告人**王某**宣告缓刑**。

    三、关于民事赔偿情况
    **被告人**王某已向被害人赔偿医疗费、误工费等各项经济损失共计
**人民币壹拾万元整（¥100,000.00）**，并已取得被害人出具的谅解书。

    综上所述，辩护人恳请合议庭综合考虑上述情节，依法对**被告人**
王某**从轻处罚**并**适用缓刑**。

                            辩护人：李XX
                            北京XX律师事务所
                            二〇二四年X月X日
```

**Key Correction Notes:**

1. **“犯罪嫌疑人” → “被告人”** `[Confidence: Certain]`
   The statutory designation at the trial stage is “被告人.” This is the most basic terminology norm in criminal procedure; incorrect use severely damages the professionalism of the defense statement.

2. **“自首” → “坦白”** `[Confidence: High]`
   The original text describes “主动交代 after being apprehended”; “被抓获” indicates non-voluntary appearance and does not meet the “自动投案” element of voluntary surrender. If counsel has evidence that Wang XX had intent to surrender and took steps to surrender before apprehension, voluntary surrender may still be established, but factual grounds must be supplemented. This correction is based on the literal meaning of the original text.

3. **“缓期执行” → “缓刑”** `[Confidence: Certain]`
   In criminal law, “缓期执行” specifically means “death sentence with a two-year suspension of execution” (死缓), which is an entirely different institution from “缓刑” (suspension of sentence / probation). Confusing them may cause serious misunderstanding.

4. **Handling of “精神赔偿金”** `[Confidence: High]`
   The corrected text deletes “精神赔偿金” because, under Article 175 paragraph 2 of the Supreme People’s Court Interpretation on the Application of the Criminal Procedure Law of the PRC, incidental civil actions in criminal cases generally do not support claims for mental distress damages. If the victim truly needs to claim mental distress damages, a separate civil action should be filed.

---

## Appendix: Quick Reference Card

```
╔══════════════════════════════════════════════════╗
║   Standardized Legal Terminology · Quick Check Mnemonic ║
╠══════════════════════════════════════════════════╣
║                                                  ║
║  1. Check statute: Does the term have a statutory formulation? ║
║  2. Check branch: Does the term belong to the correct branch of law? ║
║  3. Check context: Does the term’s meaning fit the surrounding text? ║
║  4. Check consistency: Is the same concept worded uniformly throughout? ║
║  5. Check currency: Is the term consistent with currently effective law? ║
║  6. Check style: Does the expression meet legal-document norms? ║
║  7. Check precision: Is there vagueness, overbreadth, or ambiguity? ║
║                                                  ║
║  Critical red lines (never commit):              ║
║  × Mixing 犯罪嫌疑人 / 被告人                     ║
║  × Confusing 定金 / 订金                          ║
║  × Confusing 缓刑 / 死缓                          ║
║  × Confusing 自首 / 坦白                          ║
║  × 法人代表 (should be 法定代表人)                ║
║  × Cross-branch mixing of 罚金 / 罚款             ║
║  × Confusing 赔偿 / 补偿                          ║
║  × Confusing 诉讼时效 / 除斥期间                   ║
║                                                  ║
╚══════════════════════════════════════════════════╝
```
