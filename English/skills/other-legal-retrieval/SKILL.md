---
name: other-legal-retrieval
description: "Trigger this skill when the agent needs to retrieve auxiliary legal information beyond statutes, judicial interpretations, and typical cases. Includes but is not limited to: legislative background materials (draft explanations, deliberation reports, legislature press conferences), regulatory cases and administrative penalty decisions, local guiding opinions and meeting minutes, drafting notes and policy interpretations of departmental rules, industry standards and technical norms, reports on law implementation, NPC Standing Committee law-enforcement inspection reports, white papers and policy documents, prevailing academic views and authoritative textbook positions, and comparative foreign-law materials. Trigger when the user’s question involves contexts such as 'why is it so provided,' 'what is the legislative purpose,' 'how do regulators handle this in practice,' 'what special local rules exist,' or 'what is industry practice.'"
---

> **Chinese source (authoritative):** [`../../skills/other-legal-retrieval/SKILL.md`](../../skills/other-legal-retrieval/SKILL.md)

# Other Legal Retrieval

> Systematic retrieval of legislative background, regulatory cases, local guiding opinions, and other auxiliary legal information

## I. Overview Table

| Item | Content |
|------|------|
| **Capability name** | Other Legal Retrieval |
| **Capability type** | Atomic capability — information retrieval |
| **Core function** | Retrieve auxiliary legal information beyond statutes and typical cases |
| **Typical triggers** | Exploring legislative purpose; finding regulatory enforcement approaches; obtaining special local rules; understanding industry practice; comparative-law research |
| **Upstream dependencies** | Legal-issue identification; characterization of legal relationships |
| **Downstream handoff** | Legal interpretation and argumentation; legal opinion drafting; compliance-scheme design |
| **Deliverable** | Structured auxiliary legal-information retrieval report |
| **Risk level** | Medium (auxiliary information is not direct adjudicative authority, but erroneous citation may mislead legal judgment) |

## II. Legal Disclaimer

⚠️ **Important**

1. Information retrieved by this skill mostly belongs to **informal legal sources** or **auxiliary materials**, with hierarchical effect lower than statutes, administrative regulations, judicial interpretations, and other formal sources. When citing, clearly label nature and hierarchical effect.
2. Legislative background materials reflect the legislator’s **subjective intent** and, in interpretation, are materials for **historical interpretation**; they cannot replace the foundational role of textual interpretation.
3. Local guiding opinions, meeting minutes, and similar documents have **territorial scope**; do not apply them across regions without distinction.
4. Regulatory cases and administrative penalty decisions **lack precedential binding force**; they are only references for understanding enforcement approaches.
5. When citing academic views, note the distinction between **prevailing and minority views**; do not present individual scholars’ views as settled conclusions.
6. Foreign-law materials are for **comparative reference** only and do not constitute legal authority under Chinese law.

## III. Core Concepts

### 3.1 Scope of "Other Retrieval"

"Other retrieval" is **supplementary retrieval** relative to **statutory retrieval** (retrieving currently effective legal norms) and **case retrieval** (retrieving judgments and guiding cases). Retrieval targets fall into ten categories:

| No. | Category | Explanation | Typical carriers |
|------|------|------|----------|
| 1 | **Legislative background materials** | Explanatory documents in enactment and amendment | Draft explanations, deliberation reports, amendment briefings, press Q&A |
| 2 | **Regulatory cases** | Administrative enforcement cases and penalty decisions | Administrative penalty decisions, regulatory circulars, typical-case compilations |
| 3 | **Local guiding opinions** | Guiding documents of local judicial or administrative organs | High-court trial minutes, local implementing measures, local normative documents |
| 4 | **Departmental-rule interpretations** | Official interpretations by rule-making organs | Drafting notes, policy interpretations, press Q&A, FAQs |
| 5 | **Meeting minutes** | Consensus from internal meetings of judicial or administrative organs | Minutes of the National Court Civil and Commercial Trial Work Conference (九民纪要 / Jiumin Minutes), etc. |
| 6 | **Industry standards and technical norms** | Technical standards relevant to application of law | National standards (GB), industry standards, association standards |
| 7 | **Policy documents** | Policy documents of Party and state organs | State Council opinions, ministry notices, white papers |
| 8 | **Law-enforcement inspection reports** | NPC Standing Committee inspections of law implementation | Enforcement-inspection reports, special research reports |
| 9 | **Prevailing academic views** | Mainstream views in legal scholarship | Authoritative textbooks, law-journal articles, writings of legislative participants |
| 10 | **Foreign-law materials** | Related legal systems of other jurisdictions | Foreign statutory texts, comparative-law literature |

### 3.2 Hierarchy of Effect

```
Formal sources (directly applicable)
├── Constitution
├── Statutes (法律)
├── Administrative regulations (行政法规)
├── Local regulations (地方性法规)
├── Autonomous and separate regulations (自治条例和单行条例)
├── Judicial interpretations (司法解释)
└── Departmental rules / local government rules (部门规章 / 地方政府规章)

Informal sources / auxiliary materials (reference use)  ← this skill’s retrieval scope
├── Tier 1: Quasi-normative documents
│   ├── Meeting minutes (e.g., Jiumin Minutes)
│   ├── Local high-court trial guiding opinions
│   └── Departmental normative documents
├── Tier 2: Official interpretive materials
│   ├── Legislative background (draft explanations, etc.)
│   ├── Departmental-rule drafting notes and policy interpretations
│   └── Law-enforcement inspection reports
├── Tier 3: Enforcement-practice materials
│   ├── Regulatory cases / administrative penalty decisions
│   ├── Regulatory Q&A / window guidance
│   └── Industry standards and technical norms
├── Tier 4: Doctrinal materials
│   ├── Prevailing academic views
│   ├── Personal writings of legislative participants
│   └── Comparative foreign-law materials
└── Tier 5: Other reference
    ├── Policy documents
    ├── White papers
    └── News reports and public information
```

### 3.3 Classification by Retrieval Purpose

| Purpose | Explanation | Priority categories |
|----------|------|-------------|
| **Explore legislative purpose** | Understand enactment background and normative intent | Legislative background, enforcement-inspection reports, prevailing academic views |
| **Determine enforcement approach** | Understand regulators’ actual standards and calibration | Regulatory cases, departmental-rule interpretations, regulatory Q&A |
| **Grasp local differences** | Understand special local rules and practices | Local guiding opinions, local normative documents |
| **Fill normative gaps** | Find reference rules when law is silent | Meeting minutes, prevailing academic views, foreign-law materials |
| **Confirm technical standards** | Fix technical judgment standards in application of law | Industry standards, technical norms, departmental normative documents |
| **Assess policy trends** | Anticipate amendment direction and regulatory trends | Policy documents, white papers, legislative plans |

## IV. Complete Workflow

### 4.1 Overall Flow

```
[Step 1] Need identification and classification
        │
        ▼
[Step 2] Retrieval-strategy design
        │
        ▼
[Step 3] Multi-source information retrieval
        │
        ▼
[Step 4] Screening and verification
        │
        ▼
[Step 5] Hierarchical-effect labeling
        │
        ▼
[Step 6] Integration and output
        │
        ▼
[Step 7] Confidence assessment and risk warnings
```

### 4.2 Step Details

#### Step 1: Need Identification and Classification

**Goal:** Accurately identify which subcategory of "other retrieval" the user’s need falls into.

**Operational points:**

1. **Parse the user question** for key signal words:
   - "Why is it provided…" → legislative background
   - "How do regulators view…" / "Will we be penalized…" → regulatory cases
   - "How does Region XX provide…" / "Locally…" → local guiding opinions
   - "Industry practice is…" / "Usual practice…" → industry standards, regulatory practice
   - "How do foreign laws provide…" / "In comparative law…" → foreign-law materials
   - "How does scholarship view…" / "In theory…" → prevailing academic views
   - "Policy direction…" / "Future trends…" → policy documents

2. **Confirm retrieval purpose** (see §3.3 classification table).

3. **Clarify time range:**
   - Legislative background: enactment/amendment time of the corresponding law
   - Regulatory cases: usually recent 3–5 years
   - Local guiding opinions: confirm still effective
   - Policy documents: focus on latest releases

4. **Clarify territorial scope:**
   - Nationwide vs. specific province/city
   - Whether cross-regional comparison is needed

#### Step 2: Retrieval-Strategy Design

**Goal:** Design targeted retrieval plans by need category.

**Category strategies:**

| Category | Main retrieval path | Key sources | Techniques |
|------|-------------|-----------|----------|
| Legislative background | Law name + "草案说明" / "审议报告" / "修改情况" | NPC website, China NPC Magazine, Law Press legislative compilations | Trace legislative timeline; distinguish first/second/third reading drafts |
| Regulatory cases | Regulator name + violation type + "行政处罚" / "典型案例" | Regulator websites (CSRC, former CBIRC, SAMR, etc.), Credit China | Focus on grounds, legal basis, and penalty range |
| Local guiding opinions | Province/city + court/agency + legal field + "指导意见" / "纪要" | Local high-court websites, local government rules databases | Check release date and whether superseded |
| Departmental-rule interpretations | Rule name + "解读" / "起草说明" / "答记者问" | Making organ websites, State Council policy library | Prefer official interpretations; distinguish official vs. unofficial |
| Meeting minutes | Meeting/minutes name + issue keywords | SPC website, legal databases | Note scope of application and temporal effect |
| Industry standards | Standard number/name + industry field | National standards full-text system, industry standards platforms | Distinguish mandatory (GB) vs. recommended (GB/T) |
| Policy documents | Issuing organ + policy field + document type | gov.cn, ministry websites | Note document level (State Council vs. ministry vs. local) |
| Prevailing academic views | Legal-issue keywords + authoritative scholar / textbook names | CNKI, PKULaw journals, authoritative textbooks | Prefer legislative participants’ writings and national textbooks |
| Foreign law | Legal-institution name + country/region | Comparative-law journals, Westlaw, government law databases | Note civil-law vs. common-law system differences |

#### Step 3: Multi-Source Information Retrieval

**Goal:** Execute retrieval per strategy and obtain original information.

**Operational points:**

1. **Priority order:** Official channels > authoritative databases > academic literature > other sources
2. **Cross-verification:** Confirm the same information through at least two independent sources
3. **Full text:** Prefer full documents over abstracts or second-hand paraphrases
4. **Currency:** Check whether still effective, amended, or repealed

**Source priority matrix:**

```
Priority 1 (official authoritative)
├── NPC and Standing Committee websites
├── State Council and ministry websites
├── SPC / SPP websites
├── Provincial people’s congress / government / high-court websites
└── National standards full-text disclosure system

Priority 2 (professional legal databases)
├── PKULaw (北大法宝)
├── Wolters Kluwer China (威科先行)
├── China Judgments Online
└── Credit China

Priority 3 (academic resources)
├── CNKI
├── Authoritative law textbooks
└── Core law journals

Priority 4 (other reference)
├── Law-firm research reports
├── Industry-association materials
└── News reports
```

#### Step 4: Screening and Verification

**Goal:** Verify authenticity, relevance, and currency of retrieved information.

**Verification checklist:**

- [ ] **Source authenticity:** From official or authoritative channels? Original source findable?
- [ ] **Content completeness:** Full text obtained? Risk of taking out of context?
- [ ] **Currency / validity:** Still effective? Amended, replaced, or repealed?
- [ ] **Relevance match:** Truly related to the user question? "Similar in form, different in substance"?
- [ ] **Territorial applicability:** Do local documents apply to the user’s territory?
- [ ] **Version accuracy:** Latest version? Multiple versions to distinguish?

**Special verification scenarios:**

| Scenario | Verification focus |
|------|----------|
| Legislative background | Confirm which draft version the explanation matches; final enacted text may differ substantially from the draft |
| Regulatory cases | Confirm whether the penalty was overturned on administrative reconsideration or litigation |
| Local guiding opinions | Confirm still effective; after higher-law amendment, local documents may have lapsed without express repeal |
| Meeting minutes | Confirm scope (nationwide vs. particular case types); later minutes amending related content |
| Academic views | Confirm prevailing view; whether author later changed position |

#### Step 5: Hierarchical-Effect Labeling

**Goal:** Label hierarchical legal effect and reference value for each retrieved item.

**Labeling system:**

| Effect level | Tag | Explanation | Suggested citation style |
|----------|------|------|-------------|
| A | `[Quasi-normative]` | Meeting minutes, local high-court guiding opinions, etc.; strong practical binding force | "According to Article X of the XX Minutes…" |
| B | `[Official interpretation]` | Legislative explanations, departmental-rule interpretations, etc. | "According to the legislature’s explanation…" / "According to XX department’s interpretation…" |
| C | `[Enforcement practice]` | Regulatory cases, administrative penalty decisions, etc. | "From regulatory practice…" / "In XX case, the regulator held…" |
| D | `[Doctrinal reference]` | Prevailing academic views, authoritative textbook positions | "Prevailing scholarship holds…" / "According to Professor XX…" |
| E | `[General reference]` | Policy documents, foreign law, news reports, etc. | "From a policy orientation…" / "In comparative law…" |

#### Step 6: Integration and Output

**Goal:** Integrate retrieved information in a structured format.

**Integration principles:**

1. **Order by hierarchical effect:** Higher-effect information first
2. **Order by relevance:** Most directly related to the user question first
3. **Cite sources:** Each item must have full citation (document name, issuing organ, date, document number)
4. **Distinguish fact from evaluation:** Present retrieved content objectively, clearly separated from the agent’s own analysis
5. **Reveal contradictions:** If sources conflict, expressly state and analyze causes

#### Step 7: Confidence Assessment and Risk Warnings

**Goal:** Overall reliability assessment of results and potential-risk warnings.

**Assessment dimensions:**

| Dimension | High confidence | Medium confidence | Low confidence |
|------|---------|---------|---------|
| Source reliability | Official original text | Authoritative database reprint | Second-hand paraphrase / non-authoritative |
| Currency | Within 1 year | 1–5 years | Over 5 years |
| Consistency | Multi-source consistent | Basically consistent with minor differences | Clear contradictions |
| Coverage | Fully covers user question | Partial coverage | Only indirectly related |

## V. Common Fields and Source Mapping

### 5.1 Civil and Commercial

| Retrieval need | Recommended materials | Typical document examples |
|----------|-------------|-------------|
| Contract-law legislative background | Legislative explanations, commentaries | Civil Code Contracts Book (Draft) Explanation; NPCSC Legal Affairs Commission Civil Law Office, Civil Code Contracts Book Commentary |
| Corporate-governance disputes | Meeting minutes | Minutes of the National Court Civil and Commercial Trial Work Conference (Jiumin Minutes) |
| Understanding the security system | Judicial-interpretation understanding & application | SPC Civil Division II, Understanding and Application of the Security-System Judicial Interpretation |
| IP damages | Local guiding opinions | Local high-court guiding opinions on IP damages |

### 5.2 Financial Regulation

| Retrieval need | Recommended materials | Typical document examples |
|----------|-------------|-------------|
| Securities-violation penalty standards | Regulatory cases | CSRC administrative penalty decisions; typical-case circulars |
| Banking compliance requirements | Regulatory Q&A | Former CBIRC Q&A; window guidance |
| Private-fund regulation | Industry self-regulation rules | AMAC self-regulation rules; filing notices |
| Fintech innovation compliance boundary | Policy documents | Financial Stability and Development Committee meeting spirit; joint PBOC/CSRC/CBIRC documents |

### 5.3 Administrative Law

| Retrieval need | Recommended materials | Typical document examples |
|----------|-------------|-------------|
| Administrative-penalty discretion benchmarks | Local normative documents | Local administrative-penalty discretion benchmarks |
| Administrative-licensing implementation standards | Departmental-rule interpretations | Ministry licensing service guides |
| Scope of government information disclosure | Enforcement-inspection reports | NPCSC enforcement-inspection report on the Government Information Disclosure Law |

### 5.4 Criminal Law

| Retrieval need | Recommended materials | Typical document examples |
|----------|-------------|-------------|
| Criminal Law Amendment legislative background | Legislative explanations | Criminal Law Amendment (XI) (Draft) Explanation |
| Local sentencing differences | Local sentencing guiding opinions | Provincial high-court implementing rules on Sentencing Guiding Opinions for Common Crimes |
| Standards for new-type crimes | Meeting/symposium minutes | Two Supremes and Ministry of Public Security opinions on telecom-network fraud and related crimes |

### 5.5 Labor Law

| Retrieval need | Recommended materials | Typical document examples |
|----------|-------------|-------------|
| Arbitration–trial linkage in labor disputes | Local guiding opinions | Local minutes on arbitration–trial linkage in labor disputes |
| Social-insurance contribution base standards | Local normative documents | Local HRSS annual contribution-base notices |
| New-form employment relationship characterization | Policy documents | Eight-department Guiding Opinions on Protecting Labor Rights of Workers in New Employment Forms |

## VI. Verification and Screening Rules

### 6.1 Admission Rules (all must be met)

| ID | Rule | Explanation |
|------|------|------|
| V-01 | **Traceable source** | Must trace to specific issuing organ, document name, and release date |
| V-02 | **Verifiable content** | Must verify accuracy via original channel or authoritative database |
| V-03 | **Confirmable currency** | Must confirm status (currently effective / amended / repealed) |
| V-04 | **Clear relevance** | Must have direct or reasonably indirect nexus with the user question |

### 6.2 Exclusion Rules (any one triggers exclusion)

| ID | Rule | Explanation |
|------|------|------|
| E-01 | **Unknown source** | Cannot confirm issuing organ or origin |
| E-02 | **Clearly ineffective** | Expressly repealed with no historical reference value |
| E-03 | **Content conflict** | Lower-level document clearly conflicts with currently effective higher law |
| E-04 | **Uncorroborated single source** | Only one non-authoritative source and cannot cross-verify |
| E-05 | **Severely outdated** | Legal environment fundamentally changed; information has lost all reference value |

### 6.3 Special Screening Rules

**Legislative background screening:**
- Prefer explanations corresponding to the **final deliberation draft**, not first-reading explanations
- If provisions were substantially amended during deliberation, present pre- and post-amendment legislative explanations to reveal reasons for change
- Clearly distinguish legislative participants’ **personal writings** from **official legislative explanations**

**Regulatory-case screening:**
- Prefer cases from the **recent 3 years**
- Prefer cases **most factually similar** to the user question
- Watch whether the penalty was **changed/revoked** on administrative reconsideration or litigation

**Local guiding-opinion screening:**
- Confirm **territorial match** with user need
- Confirm still effective **after higher-law amendment**
- If localities differ, present **comparatively**

## VII. Output Format Templates

### 7.1 Standard Output Template

```markdown
## Other Legal Retrieval Report

### I. Retrieval Summary

| Item | Content |
|------|------|
| Retrieval question | [precise statement of user question] |
| Retrieval purpose | [explore legislative purpose / determine enforcement approach / grasp local differences / ...] |
| Retrieval category | [legislative background / regulatory cases / local guiding opinions / ...] |
| Time range | [specific range] |
| Territorial range | [nationwide / specific province-city] |

### II. Retrieval Results

#### Result 1: [document / material name]

| Item | Content |
|------|------|
| Effect tag | [Quasi-normative] / [Official interpretation] / [Enforcement practice] / [Doctrinal reference] / [General reference] |
| Issuing organ | [specific organ] |
| Release date | [YYYY-MM-DD] |
| Document number | [if any] |
| Currency status | Currently effective / Amended / Repealed |
| Scope of application | [nationwide / specific territory / specific industry] |

**Core content excerpt:**
> [original quotation]

**Relevance analysis to user question:**
[how this material responds to the user question]

---

#### Result 2: [document / material name]
[same format]

---

### III. Comprehensive Analysis

[synthesis of all results; reveal consistency or contradictions]

### IV. Confidence Assessment

| Dimension | Rating | Explanation |
|------|------|------|
| Source reliability | ★★★★☆ | [explanation] |
| Currency | ★★★★★ | [explanation] |
| Consistency | ★★★☆☆ | [explanation] |
| Coverage | ★★★★☆ | [explanation] |
| **Overall confidence** | **★★★★☆** | [overall evaluation] |

### V. Risk Warnings

1. [warning 1]
2. [warning 2]
3. [matters needing further verification]

### VI. Suggested Next Steps

1. [suggestion 1]
2. [suggestion 2]
```

### 7.2 Brief Output Template (quick-reply scenarios)

```markdown
**Retrieval result:** [brief overview]

**Key materials:**
1. [name] ([effect tag], [issuing organ], [date]): [core points]
2. [name] ([effect tag], [issuing organ], [date]): [core points]

**Confidence:** [High/Medium/Low] — [brief note]

**Note:** [key risk warning]
```

## VIII. Confidence Labeling System

### 8.1 Single-Item Confidence

| Level | Symbol | Meaning | Typical scenario |
|------|------|------|----------|
| Certain | ✅ | Authoritative source, verifiable content, confirmed currency | Currently effective original text from official website |
| Higher | 🟢 | Reliable source, basically verifiable | Database-collected document not word-checked against official original |
| Medium | 🟡 | Fairly reliable source, some uncertainty | Content cited in scholarship; non-latest version |
| Lower | 🟠 | Limited authority or hard to fully verify | Second-hand meeting spirit; internal documents from unofficial channels |
| Doubtful | 🔴 | Unclear source or clear red flags | Circulating online with unconfirmed origin; contradicts known information |

### 8.2 Overall Retrieval Confidence

| Level | Description | Criteria |
|------|------|----------|
| **High** | Reliable; usable directly for legal analysis | Core items ✅ or 🟢; multi-source cross-verified; currency confirmed |
| **Medium** | Basically reliable; further verification advised | Core items 🟡 or above; most cross-verifiable; some uncertain factors |
| **Low** | Reference only; must further verify | Core items 🟠 or 🔴; lack of cross-verification; clear currency or source doubts |

## IX. Common Errors and Prevention

### 9.1 Fatal Error Table

| ID | Error type | Description | Consequence | Prevention |
|------|----------|----------|------|----------|
| F-01 | **Citing informal sources as formal** | Citing meeting minutes, local guiding opinions, etc. as legal authority without labeling nature | Wrong foundation for legal argument; may lose case or fail compliance scheme | Strictly label effect tags; use "refer to / take reference from," not "pursuant to" |
| F-02 | **Citing ineffective documents** | Not checking currency; citing repealed or superseded documents | Analysis based on outdated rules; conclusions may be wholly wrong | Confirm currency for every item; after higher-law amendment, recheck lower documents |
| F-03 | **Wrong cross-territorial application** | Applying Region A’s local guiding opinion to Region B’s case | Wrong application of law | Label each local document’s territory; when citing cross-territorially, state for reference only |
| F-04 | **Confusing draft explanations with final law** | Citing legislative explanation matching draft text that was substantially amended in final law | Misunderstanding of legislative purpose vs. actual law | Compare draft text with final law; label which reading the explanation matches |
| F-05 | **Presenting individual views as prevailing** | Citing minority or personal views without labeling academic status | Misleads understanding of the legal issue | Label "prevailing / majority / minority"; compare multiple scholars |
| F-06 | **Ignoring subsequent change in regulatory cases** | Citing a penalty later revoked on reconsideration or litigation | Analysis based on wrong enforcement approach | Check subsequent status of the penalty; watch related administrative litigation |

### 9.2 Common Traps

| ID | Trap | Explanation | Response |
|------|------|------|----------|
| T-01 | **"Press Q&A" trap** | Press-Q&A wording may be broader or narrower than the statute; not equivalent to the law itself | Use as an aid to understanding, not independent legal authority |
| T-02 | **"Window guidance" trap** | Window guidance may change anytime and usually lacks formal records | Label informal nature; advise user to confirm directly with the regulator |
| T-03 | **"Meeting minutes" effect trap** | Effect of different minutes varies enormously (Jiumin Minutes vs. local court internal minutes) | Distinguish issuance level and scope of application |
| T-04 | **"Authoritative textbook" edition trap** | Authoritative textbooks may have multiple editions with different views | Cite latest edition; if views changed, explain the change |
| T-05 | **"Foreign law" transplant trap** | Foreign institutions depend on their own legal systems and social backgrounds | State institutional-background differences in comparative analysis; do not simply analogize |
| T-06 | **"Policy document" normalization trap** | Misreading policy language as legally binding norms | Distinguish policy orientation from legal norms; label non-normative nature |
| T-07 | **"Industry standard" mandatory trap** | Confusing legal effect of mandatory vs. recommended standards | Label standard type (GB vs. GB/T); explain different legal consequences of breach |
| T-08 | **"Commentary book" authority trap** | Equating statutory commentaries (even by Legal Affairs Commission) with legislative or judicial interpretation | Commentaries are doctrinal interpretation without legal binding force; label as reference |

## X. Special Scenario Handling

### 10.1 Information-Conflict Scenarios

**Description:** Contradictions among auxiliary legal information from different sources.

**Handling rules:**

1. **Hierarchical-effect priority:** Higher-effect information prevails over lower
   - Meeting minutes > local guiding opinions (same issue)
   - SPC documents > local-court documents
   - Newer documents > older (same organ)

2. **Temporal priority:** Newer information usually prevails over older
   - But note: new local documents cannot overturn older nationwide documents

3. **Specialty priority:** Special rules on a specific issue prevail over general rules

4. **Presentation:**
   ```
   ⚠️ Information-conflict warning:
   - [Source A] holds: [View A]
   - [Source B] holds: [View B]
   - Conflict analysis: [causes]
   - Suggested reliance: [suggestion and reasons]
   ```

### 10.2 Information-Gap Scenarios

**Description:** No directly related auxiliary legal information found for the user question.

**Handling rules:**

1. **Expand retrieval scope:**
   - From exact match to similar issues
   - From specific field to adjacent fields
   - From domestic to comparative foreign law

2. **Downgrade substitutes:**
   - No legislative background → scholarly analysis of legislative purpose
   - No regulatory cases → related administrative-litigation cases
   - No local guiding opinions → neighboring regions’ rules as reference

3. **Expressly inform:**
   ```
   ℹ️ Retrieval note:
   For [specific issue], no directly related [material type] was retrieved.
   Alternative: [results of substitute retrieval]
   Suggestion: [user next steps]
   ```

### 10.3 Sensitive-Information Scenarios

**Description:** Retrieved information involves internal documents, unpublished information, or sensitive policy.

**Handling rules:**

1. **Cite only public information:** Do not cite documents marked "internal," "confidential," or "secret"
2. **Label information nature:** If from informal channels (e.g., industry rumor), must clearly label
3. **Advise formal confirmation:** Advise confirmation via formal channels (e.g., information-disclosure request, regulatory consultation)

### 10.4 Legal Transition-Period Scenarios

**Description:** During old–new law transition, auxiliary materials may exist in both systems.

**Handling rules:**

1. **Clarify time nodes:** Label new-law effective date and transition arrangements
2. **Distinguish application:**
   - Conduct before new law effective → refer to old-system auxiliary materials
   - Conduct after new law effective → refer to new-system auxiliary materials
   - Transition-period conduct → refer to both
3. **Warn of risk:** Right after new-law effectiveness, supporting auxiliary materials (implementing rules, guiding opinions) may not yet exist

### 10.5 Cross-Field Retrieval Scenarios

**Description:** User question intersects multiple legal fields; need auxiliary materials from multiple fields.

**Handling rules:**

1. **Identify intersection points:** Clarify which legal fields are involved
2. **Retrieve by field:** Execute retrieval separately by field
3. **Integrate analysis:** Analyze whether auxiliary materials across fields conflict
4. **Label fields:** In output, clearly label each item’s legal field

## XI. Quality Checklist

### 11.1 Pre-Retrieval Checks

- [ ] Accurately identified the user’s retrieval-need category?
- [ ] Clarified time and territorial ranges?
- [ ] Formulated reasonable retrieval strategy and priorities?
- [ ] Confirmed the issue truly needs "other retrieval," not statutory or case retrieval?

### 11.2 Mid-Retrieval Checks

- [ ] Used multiple sources for cross-verification?
- [ ] Prioritized official authoritative channels?
- [ ] Obtained full text rather than relying only on abstracts?
- [ ] Checked documents’ currency status?

### 11.3 Post-Retrieval Checks

- [ ] Each item fully cited (organ, name, date, document number)?
- [ ] Each item labeled with effect-level tag?
- [ ] Each item’s currency confirmed?
- [ ] Information conflicts revealed and analyzed if any?
- [ ] Information gaps explained with alternatives if any?
- [ ] Local documents labeled with applicable territory?
- [ ] Academic views distinguished prevailing vs. minority?
- [ ] Foreign-law materials explained with institutional-background differences?

### 11.4 Output Checks

- [ ] Output format matches template?
- [ ] Confidence assessment provided?
- [ ] Risk warnings provided?
- [ ] Next steps suggested?
- [ ] Citation style appropriate ("refer to" not "pursuant to")?
- [ ] All fatal errors (F-01 to F-06) avoided?

## XII. Complete Examples

### Example 1: Simple Scenario — Finding Legislative Background Materials

**User question:** What is the legislative purpose of Civil Code Art. 1176 on "assumption of risk" (自甘风险)? Why was this rule newly added?

---

#### Other Legal Retrieval Report

##### I. Retrieval Summary

| Item | Content |
|------|------|
| Retrieval question | Legislative purpose and reasons for adding Civil Code Art. 1176 "assumption of risk" |
| Retrieval purpose | Explore legislative purpose |
| Retrieval category | Legislative background materials; prevailing academic views |
| Time range | 2018–2020 (Civil Code compilation period) |
| Territorial range | Nationwide |

##### II. Retrieval Results

**Result 1: NPCSC Legal Affairs Commission explanation of the Civil Code (Draft)**

| Item | Content |
|------|------|
| Effect tag | `[Official interpretation]` 🟢 |
| Issuing organ | Constitution and Law Committee of the NPC |
| Release date | 2020-05-22 |
| Document number | — |
| Currency status | Historical document (corresponding law already in force) |
| Scope of application | Nationwide |

**Core content excerpt:**
> On the basis of summarizing practical experience, the Tort Liability Book draft improved rules such as assumption of risk. It provides that a person who voluntarily participates in a cultural or sports activity with certain risks and is harmed by another participant’s conduct may not request that other participant to bear tort liability, except where the other participant intentionally or with gross negligence caused the harm.

**Relevance analysis:**
The explanation positions adding assumption of risk as a result of "summarizing practical experience"—related adjudicative rules already existed in practice; the Civil Code elevated them to statutory law.

---

**Result 2: NPCSC Legal Affairs Commission Civil Law Office, Commentary on the Tort Liability Book of the PRC Civil Code**

| Item | Content |
|------|------|
| Effect tag | `[Doctrinal reference]` 🟡 |
| Issuing organ | Compiled by NPCSC Legal Affairs Commission Civil Law Office |
| Release date | July 2020 |
| Document number | ISBN 978-7-5197-4638-5 |
| Currency status | Currently effective |
| Scope of application | Nationwide |

**Core content excerpt:**
> This article provides for assumption of risk. As society develops, cultural and sports activities enrich people’s lives, and related disputes increase. In football, basketball, mountaineering, rock climbing, and other activities with certain risks, personal injury among participants sometimes occurs. Mechanically applying fault liability and requiring the injuring participant to pay damages would hinder normal cultural and sports activities and conflict with the public’s ordinary understanding. Therefore it is necessary to establish assumption of risk and reasonably allocate damage risk in such activities.

**Relevance analysis:**
Written by the Legal Affairs Commission Civil Law Office (legislative participants), detailing legislative purpose: (1) respond to rising cultural/sports disputes; (2) avoid mechanical fault liability chilling normal activities; (3) align with ordinary public understanding and fairness.

---

**Result 3: Prevailing academic views**

| Item | Content |
|------|------|
| Effect tag | `[Doctrinal reference]` 🟡 |
| Source | Wang Liming, Research on the Tort Liability Book of the Civil Code (Renmin University Press, 2020); Cheng Xiao, Tort Liability Law (Law Press, 3d ed. 2021) |
| Currency status | Currently effective |

**Core content excerpt:**
> Prevailing scholarship holds that theoretical bases of assumption of risk include: (1) **assumption of risk principle** — those who voluntarily join dangerous activities should bear the inherent risks; (2) **victim consent theory** — participants’ knowledge and acceptance of inherent risks constitute implied consent; (3) **policy consideration of promoting social activities** — avoid excessive liability hindering beneficial cultural and sports activities.

**Relevance analysis:**
Prevailing scholarship supplements the doctrinal foundation not fully developed in the legislative explanation, aiding deeper understanding of the rule’s justifications.

---

##### III. Comprehensive Analysis

The legislative purpose of Civil Code Art. 1176 "assumption of risk" may be understood on three levels:

1. **Practical response:** Rising cultural/sports disputes; adjudicative rules already formed in practice need statutory confirmation and unification.
2. **Value balancing:** Balance victim protection and normal cultural/sports activities; avoid a "chilling effect" from mechanical fault liability.
3. **Doctrinal foundation:** Supported by assumption-of-risk and victim-consent theory, reflecting the principle of self-responsibility.

##### IV. Confidence Assessment

| Dimension | Rating | Explanation |
|------|------|------|
| Source reliability | ★★★★★ | Legislative explanation is official; commentary by legislative participants |
| Currency | ★★★★★ | Materials from compilation period and after effectiveness |
| Consistency | ★★★★★ | Three sources highly consistent |
| Coverage | ★★★★☆ | Fully covers legislative purpose; comparative-law background not covered |
| **Overall confidence** | **★★★★★** | **High confidence; retrieval results reliable** |

##### V. Risk Warnings

1. Although the Legal Affairs Commission Civil Law Office commentary is highly authoritative, strictly speaking it is **doctrinal interpretation**, not legislative interpretation, and has no legal binding force.
2. The concrete scope of assumption of risk (e.g., whether limited to "cultural and sports activities") remains disputed in scholarship and practice; legislative background materials do not fully eliminate that dispute.

##### VI. Suggested Next Steps

1. For judicial application after effectiveness, conduct **case retrieval** for judgments applying Art. 1176.
2. For comparative background, research common-law "assumption of risk" and civil-law "victim consent" theories.

---

### Example 2: Complex Scenario — Cross-Category Retrieval (Regulatory Cases + Local Guiding Opinions + Policy Documents)

**User question:** Our company is an internet platform planning to add personal-information cross-border transfer clauses to the user agreement. Please help us understand: (1) How severe are regulatory penalties for illegal cross-border personal-information transfers? (2) Do local cyberspace authorities have special requirements? (3) What is the future regulatory trend?

---

#### Other Legal Retrieval Report

##### I. Retrieval Summary

| Item | Content |
|------|------|
| Retrieval question | Penalty severity, local special requirements, and regulatory trends for cross-border personal-information transfers |
| Retrieval purpose | Determine enforcement approach + grasp local differences + assess policy trends |
| Retrieval category | Regulatory cases; local guiding opinions/normative documents; policy documents |
| Time range | From 2021 to present (after PIPL effectiveness) |
| Territorial range | Nationwide + focus on Beijing, Shanghai, Shenzhen, Hainan, etc. |

##### II. Retrieval Results

**【Part 1: Regulatory Cases — Penalty Severity】**

**Result 1: Cyberspace Administration of China administrative penalty decision against DiDi Global**

| Item | Content |
|------|------|
| Effect tag | `[Enforcement practice]` ✅ |
| Issuing organ | Cyberspace Administration of China |
| Release date | 2022-07-21 |
| Document number | — |
| Currency status | Executed |
| Scope of application | Nationwide (individual case) |

**Core content excerpt:**
> Pursuant to the Cybersecurity Law, Data Security Law, Personal Information Protection Law, and other laws and regulations, CAC imposed a fine of RMB 8.026 billion on DiDi Global. Investigation found illegal processing of personal information, data-processing activities endangering national security, and related violations, including illegal provision of data overseas.

**Relevance analysis:**
The most emblematic post-PIPL penalty, with a historically high fine. Although the case’s violations far exceed pure cross-border transfer (also involving national security, etc.), it fully shows regulators’ **zero-tolerance attitude** and **heavy-penalty tendency** toward illegal data outbound transfers.

---

**Result 2: Typical cases of data outbound security assessments published by CAC**

| Item | Content |
|------|------|
| Effect tag | `[Enforcement practice]` 🟢 |
| Issuing organ | Cyberspace Administration of China |
| Release date | 2023 (continuously updated) |
| Currency status | Currently effective |
| Scope of application | Nationwide |

**Core content excerpt:**
> CAC has successively published multiple batches of approval results and typical cases for data outbound security assessments. From disclosed information, regulators focus on: (1) whether necessity of outbound transfer is adequately demonstrated; (2) whether the overseas recipient’s data-protection capacity meets standards; (3) whether separate consent of personal-information subjects was validly obtained; (4) whether assessment filing materials are complete and accurate.

**Relevance analysis:**
These typical cases reveal regulators’ **review priorities** in data outbound security assessment, with direct guidance for designing cross-border transfer clauses.

---

**Result 3: Compiled administrative penalty cases of local cyberspace authorities**

| Item | Content |
|------|------|
| Effect tag | `[Enforcement practice]` 🟢 |
| Source | Administrative penalty information published on provincial CAC websites |
| Currency status | Continuously updated |
| Scope of application | Various localities |

**Core content excerpt:**
> From local cyberspace authorities’ published cases, personal-information protection penalties show: increasing frequency since 2023 vs. 2022; targets expanding from large platforms to SMEs; measures including warning, fines, ordered remediation, and suspension of related business; in outbound-transfer cases, failure to conduct security assessment or obtain separate consent are the most common grounds.

**Relevance analysis:**
Shows enforcement shifting from "catch big, release small" to "full coverage"; mid-sized internet platforms also face high enforcement risk.

---

**【Part 2: Local Special Requirements】**

**Result 4: Hainan Free Trade Port data outbound related rules**

| Item | Content |
|------|------|
| Effect tag | `[Quasi-normative]` 🟢 |
| Issuing organ | Hainan Provincial People’s Government / CAC |
| Related documents | Overall Plan for Hainan Free Trade Port Construction — cross-border data flow content |
| Currency status | Currently effective (continuously advancing) |
| Scope of application | Hainan Free Trade Port |

**Core content excerpt:**
> Hainan FTP enjoys pilot advantages for cross-border data flows. Related policies explore more convenient outbound mechanisms in specific fields (e.g., cross-border e-commerce, international healthcare), including innovative systems such as negative-list management.

**Relevance analysis:**
If the company has Hainan operations or considers using Hainan policy advantages, watch FTP data-outbound facilitation measures. Note policies are still advancing; detailed implementing rules may not be fully in place.

---

**Result 5: Shanghai Data Regulations related provisions**

| Item | Content |
|------|------|
| Effect tag | `[Quasi-normative]` ✅ |
| Issuing organ | Standing Committee of Shanghai Municipal People’s Congress |
| Release date | 2021-11-25 |
| Document number | — |
| Currency status | Currently effective |
| Scope of application | Shanghai Municipality |

**Core content excerpt:**
> The Shanghai Data Regulations make local provisions on cross-border data flows, further refining data classification and grading under the national legal framework, and exploring facilitation mechanisms in specific areas such as Lingang New Area.

**Relevance analysis:**
As a pioneer in data legislation, Shanghai’s refinements on cross-border data flows deserve attention, especially Lingang special policies.

---

**Result 6: Shenzhen SEZ Data Regulations related provisions**

| Item | Content |
|------|------|
| Effect tag | `[Quasi-normative]` ✅ |
| Issuing organ | Standing Committee of Shenzhen Municipal People’s Congress |
| Release date | 2021-06-29 |
| Document number | — |
| Currency status | Currently effective |
| Scope of application | Shenzhen (SEZ legislation) |

**Core content excerpt:**
> The Shenzhen SEZ Data Regulations are the country’s first comprehensive data-field legislation, setting concrete requirements for cross-border personal-data transfers, including data-protection impact assessments. As SEZ legislation, the regulations may make adaptive provisions on specific matters relative to higher law.

**Relevance analysis:**
Shenzhen SEZ legislation has a special legal status; if the company operates in Shenzhen, pay special attention to its distinctive requirements.

---

**【Part 3: Regulatory Trends】**

**Result 7: Provisions on Promoting and Regulating Cross-border Data Flows**

| Item | Content |
|------|------|
| Effect tag | `[Quasi-normative]` ✅ |
| Issuing organ | Cyberspace Administration of China |
| Release date | 2024-03-22 |
| Currency status | Currently effective |
| Scope of application | Nationwide |

**Core content excerpt:**
> The Provisions optimize and adjust systems such as data outbound security assessment, standard contracts for personal-information outbound transfers, and personal-information protection certification; clarify circumstances exempt from security-assessment filing; and reflect a policy orientation balancing security and development. Main changes include: clarifying scenarios not requiring security-assessment filing; optimizing filing procedures; and facilitation arrangements for cross-border e-commerce, international cooperation, and similar scenarios.

**Relevance analysis:**
Among the most important documents for judging future regulatory trends, showing a shift from "strict control" toward "classified management and precise measures." The company should focus on whether its business falls within exemption scenarios.

---

**Result 8: State Council policy documents on digital-economy development**

| Item | Content |
|------|------|
| Effect tag | `[General reference]` 🟢 |
| Source | 14th Five-Year Plan for Digital Economy Development (Guo Fa [2021] No. 29), etc. |
| Issuing organ | State Council |
| Currency status | Currently effective |
| Scope of application | Nationwide |

**Core content excerpt:**
> National digital-economy development plans expressly call for "actively participating in formulating international rules on cross-border data flows" and "exploring mechanisms for managing cross-border data flows," reflecting a policy direction of promoting orderly outbound flows while ensuring data security.

**Relevance analysis:**
At the macro-policy level, the regulatory trend is **"security and development in parallel,"** not pure restriction—leaving policy space for enterprise compliance.

---

##### III. Comprehensive Analysis

**(1) Penalty-severity analysis**

From regulatory cases, illegal cross-border personal-information transfers show:
1. **Strong willingness to impose maximum penalties:** DiDi’s RMB 8.026 billion fine shows regulators will use the harshest means against serious violations
2. **Expanding enforcement scope:** From large platforms to SMEs
3. **Common violation grounds:** No security assessment, no separate consent, inadequate security measures

**(2) Local-difference analysis**

| Region | Special policy | Focus points |
|------|----------|----------|
| Hainan | Cross-border data-flow facilitation pilot | Negative-list management (advancing) |
| Shanghai (Lingang) | Cross-border data-flow facilitation exploration | Special policies in specific areas |
| Shenzhen | SEZ data legislation | May make adaptive provisions relative to higher law |
| Beijing | Digital-economy promotion regulations | Watch FTZ policies |

**(3) Regulatory-trend assessment**

1. **Short term (1–2 years):** Implementation of the Provisions on Promoting and Regulating Cross-border Data Flows will be key; clearer exemption scenarios will lower compliance costs for some enterprises
2. **Medium term (3–5 years):** Management of cross-border data flows will become more refined; classification and grading will be the norm; local pilot experience may rise to nationwide institutions
3. **Long term:** China will more actively join international rule-making on cross-border data flows and build bilateral or multilateral mechanisms with major trading partners

##### IV. Confidence Assessment

| Dimension | Rating | Explanation |
|------|------|------|
| Source reliability | ★★★★☆ | Core information from official channels; some local policy details may not be fully public |
| Currency | ★★★★☆ | Most information within ~2 years; field changes fast; continuous monitoring needed |
| Consistency | ★★★★☆ | Sources basically consistent; local–national linkage details not fully clear |
| Coverage | ★★★★☆ | Fairly complete coverage of three sub-questions; public disclosure of regulatory cases limited |
| **Overall confidence** | **★★★★☆** | **Higher confidence; core conclusions reliable; further verify some details** |

##### V. Risk Warnings

1. ⚠️ **Rapid policy-change risk:** Regulation of cross-border personal-information transfers is evolving quickly; information in this report may change shortly; update retrieval regularly.
2. ⚠️ **Uncertainty of local-policy implementation:** Facilitation policies in Hainan, Shanghai Lingang, etc. are still advancing; detailed implementing rules may not be fully issued; do not rely too early.
3. ⚠️ **Limited public disclosure of regulatory cases:** Not all administrative penalties are published; actual enforcement may be stricter than public cases suggest.
4. ⚠️ **Case specificity:** DiDi involved national-security and other special factors; its penalty severity cannot simply be analogized to ordinary enterprises’ outbound-transfer violations.
5. ⚠️ **Window-guidance changes:** Regulators’ window guidance and review approaches may adjust anytime; advise pre-communication with competent authorities before formal security-assessment filing.

##### VI. Suggested Next Steps

1. **Statutory retrieval:** Systematically retrieve currently effective provisions of PIPL Chapter III (rules on cross-border provision of personal information), Measures for Data Outbound Security Assessment, Measures for Standard Contracts for Outbound Transfer of Personal Information, Provisions on Promoting and Regulating Cross-border Data Flows, etc.
2. **Compliance-path assessment:** Based on the company’s concrete business scenarios (data type, volume, recipient country, etc.), assess whether to choose security assessment, standard contract, or protection certification.
3. **Local-policy confirmation:** If the company has operations in Hainan, Shanghai Lingang, Shenzhen, etc., advise consulting local cyberspace authorities on the latest facilitation policies.
4. **Continuous monitoring:** Establish continuous monitoring of cross-border personal-information transfer regulatory policy.
5. **Professional advice:** Given the field’s complexity and rapid change, advise engaging specialized data-compliance counsel for targeted compliance assessment.

---

*This retrieval report generated: [current date]*
*Disclaimer: Information in this report is auxiliary reference only and does not constitute formal legal advice. For specific legal issues, rely on currently effective laws and regulations and consult a licensed attorney.*
