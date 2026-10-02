---
name: case-retrieval
description: "Trigger this skill when the user needs to find similar cases, related judgments, or adjudicative rules relevant to a current legal issue. Typical triggers include: the user expressly asks to find similar cases or precedents; supporting a legal argument with prior judgments; case outcome prediction that requires reference to like cases; drafting legal documents that need citation of authoritative cases; analyzing judicial practice trends on a legal issue; comparing adjudicative positions of different courts or periods on the same issue. Keywords include, without limitation: similar cases, related judgments, case retrieval, adjudicative rules, like cases, Guiding Cases, typical cases, judicial viewpoints, adjudicative holdings (裁判要旨), etc."
---

> **Chinese source (authoritative):** [`../../skills/case-retrieval/SKILL.md`](../../skills/case-retrieval/SKILL.md)

# Case Retrieval (Finding Similar Cases and Related Judgments)

## Overview Table

| Item | Content |
|------|------|
| **Capability Name** | Case Retrieval |
| **Capability ID** | 09 |
| **Capability Type** | Legal atomic capability |
| **Core Function** | Find similar cases and related judgments relevant to the current legal issue |
| **Input Elements** | Case facts, legal relationship, disputed issues (争议焦点), retrieval purpose |
| **Output Deliverable** | Structured case-retrieval report with case summaries, adjudicative holdings, and relevance assessment |
| **Applicable Stages** | Full stages of case analysis, litigation strategy, legal drafting, and legal research |
| **Related Capabilities** | Legal relationship identification, disputed-issue distillation, statute retrieval, legal argumentation |
| **Risk Level** | Medium–high (omitting or mis-citing cases may skew strategy) |

---

## Legal Disclaimer

> **Important notice:**
> 1. The case-retrieval methodology and structured workflow provided by this skill are for reference only and do not constitute legal advice.
> 2. Mainland China’s legal system is a statute-based (成文法) system; cases generally lack universal binding force (except Guiding Cases (指导性案例)), and retrieval results should be treated as reference material rather than direct legal authority.
> 3. Guiding Cases issued by the Supreme People’s Court (最高人民法院) have “shall be referred to” (应当参照) effect and rank above ordinary cases.
> 4. When an AI system performs case retrieval, it must clearly mark case sources, hierarchical authority, and currency, and avoid citing adjudicative views that have been overturned or are no longer applicable.
> 5. Case-retrieval results should be reviewed by a practicing lawyer or other legal professional before use in actual legal matters.

---

## I. Retrieval Foundations and Mindset

### 1.1 Description of Like-Case Retrieval (类案检索)

Like-case retrieval means searching for and applying cases that are similar to the pending case in basic facts, disputed issues, and legal application, and that have already taken effect as judgments of a people’s court. Under China’s statute-based system, like-case retrieval reflects **integrated statutory and case-law thinking**—using cases to help interpret abstract legal provisions and strengthen the persuasiveness of subsuming the minor premise under the major premise.

### 1.2 Three Retrieval Scenarios

By content, like-case retrieval roughly falls into three types:

| Retrieval Type | Applicable Scenario | Example |
| --------- | ------------------ | ------------------------------------- |
| **Legal-application type** | Retrieve how a statute or judicial interpretation provision is applied | How to identify “persons entrusted to manage or operate State-owned property” under Article 382(2) of the Criminal Law |
| **Fact-finding type** | Retrieve how a specific fact is determined | In loan-fraud cases, how to determine the suspect’s “purpose of illegal possession” |
| **Evidence-admission type** | Retrieve concrete application of evidence rules | Whether interrogation transcripts from continuous questioning beyond a certain duration with no proof that food and rest were ensured should be excluded as illegal evidence |

### 1.3 Purposes of Retrieval

- **Support an argument**: Find adjudicative precedents supporting one’s own position
- **Anticipate risk**: Understand adjudicative trends and win rates in like cases
- **Rebut the opponent**: Find adjudicative views that negate the opponent’s arguments
- **Fill gaps**: Find judicial practice attitudes on issues not clearly provided by statute
- **Unify understanding**: Map the evolution of adjudicative rules on an issue
- **Formulate strategy**: Determine optimal litigation strategy through case analysis
- **Draft documents**: Provide case support for legal opinions / advocacy briefs

---

## II. Pre-Retrieval Preparation: Problem Characterization

### 2.1 Background Information Collection

After preliminary analysis of the case evidence, distill the corresponding **retrieval need**. That need is, in substance, the legal or evidentiary issue the case must resolve.

**Example**: In a construction project dispute, besides claiming against the subcontractor who subcontracted the work to the actual constructor and against the developer as provided by judicial interpretation, may the actual constructor also claim project payment from others—e.g., a contractor who has neither a contractual relationship with the actual constructor nor a statutory obligation?

The retrieval need can be distilled as: **“Must a contractor, by analogy to the developer’s position, pierce privity of contract and bear joint and several liability to the actual constructor? If so, must that liability, by analogy to developer rules, be limited to the unpaid project price?”**

### 2.2 Information-Gathering Channels

When facing unfamiliar case types, drawing on prior research is the most efficient method:

1. **Search-engine retrieval**: Google, Baidu, etc., with keywords such as “XX adjudicative view, XX adjudicative holding, XX big-data report, XX compilation, XX cases, XX practical tips”
2. **WeChat article search**: Almost every specialized legal issue has been analyzed and compiled in WeChat public accounts
3. **Preliminary database search**: “Like-case retrieval” features on platforms such as PKULaw (北大法宝), Wolters Kluwer China Law (威科先行), and Faxin (法信)

**Example**: When handling a case, first distill from the evidence that the retrieval need is “determining authenticity of a company seal (公章).” Then search WeChat for “adjudicative rules on seal authenticity.” From cases cited in articles, extract the court’s terminology in judgments on seal authenticity—greatly helping keyword extraction for deeper retrieval.

### 2.3 Defining the Retrieval Scope

**Case scope**: Mainly typical cases published by higher courts and by the court concerned, and effective judgments rendered by them.

**Time scope**: Different time windows reflect current economic and social conditions and avoid results that diverge from present like-case reality. Except for Guiding Cases, prioritize cases from roughly the past three years.

**Geographic scope**: Besides typical cases and effective judgments of higher courts and of the court concerned, representative typical cases and effective judgments from provincial high courts and intermediate courts in other provinces/municipalities over the past three years may also be included.

---

## III. Retrieval Elements and Keyword Extraction

### 3.1 Retrieval-Element Extraction Checklist

#### A. Basic elements (must extract)
- [ ] Cause of action / dispute type
- [ ] Core legal relationship
- [ ] Main disputed issues
- [ ] Applicable legal provisions

#### B. Factual elements (extract as far as possible)
- [ ] Party types (natural person / legal person / other organization)
- [ ] Nature and pattern of conduct
- [ ] Type and degree of harm
- [ ] Causal features
- [ ] Form of fault

#### C. Limiting elements (extract as needed)
- [ ] Geographic scope (nationwide / specific province / specific court)
- [ ] Time scope (recent years / specific period)
- [ ] Instance requirements (SPC / high court / intermediate / basic-level)
- [ ] Outcome tendency (uphold / dismiss)
- [ ] Amount-in-controversy range

### 3.2 Classification and Extraction of Keywords

Case-retrieval keywords roughly divide into **“normative keywords”** and **“non-normative keywords”**:

| Type | Definition | Examples |
|-----|------|------|
| **Normative keywords** | Concepts, terms, and facts defined or expressed in legal norms | Cause of action (offense), voluntary surrender, meritorious service, State functionary, illegal possession, joint crime, competitive driving |
| **Non-normative keywords** | Natural facts or colloquial expressions outside legal norms | Leading cadre, App, mistress, baking powder, consumer card, counterfeit card |

#### Four methods of keyword extraction:

1.  **Split from statutory text**: For Company Law Article 63 (one-person company), extract “one-person limited liability company,” “shareholder,” “independent property,” “joint and several liability.”
2.  **Extract from case materials**: Extract industry terms from contracts and documents (e.g., “illegal subcontracting,” “delayed completion”).
3.  **Distill from case facts**: Distill keywords from factual fragments (e.g., “nominee shareholding,” “completed dry-share bribery”).


### 3.3 Keyword Combination Examples

Using “piercing the corporate veil among affiliated companies” as an example:

```markdown
Group 1 (core concepts):
- "denial of corporate personality" + "affiliated companies"
- "piercing the corporate veil" + "personality confusion"
- "Company Law Article 20" + "joint and several liability"

Group 2 (types of confusion):
- "personnel confusion" + "affiliated companies"
- "financial confusion" + "independence"
- "business confusion" + "corporate personality"
- "three confusions" + "denial of corporate personality"

Group 3 (horizontal piercing):
- "horizontal piercing" OR "horizontal denial"
- "affiliated companies" + "joint and several liability" + "creditor"
- "actual controller" + "multiple companies" + "confusion"

Group 4 (source retrieval):
- "Nine Minutes" + "denial of corporate personality"
- "Minutes of the National Court Work Conference on Civil and Commercial Trials" + "Article 10"
```

---

## IV. Retrieval Methods and Pathways

### 4.0 Data Sources and Tool-Calling Convention (Mandatory)

> **Core principle: Every case produced by this skill must come from real retrieval; generating cases from memory is strictly forbidden.**

Before executing the pathways below, determine whether the runtime environment has **case-retrieval tools** (e.g., a connected case-library MCP service, retrieval API, or local case library):

1. **If present**: The designed search terms / queries must be submitted to that tool; its returned real results (case number, court, year, cause of action, adjudicative holding, source link) are the sole data source for subsequent similarity assessment and the report. Do not substitute or supplement results with “cases” from memory.
2. **If absent**: Still complete query design and methodological steps, but mark every concrete case reference `[to be retrieved]`, and state clearly in the report: “No case library connected; the following queries must be executed manually.” **Never fabricate case numbers, parties, or adjudicative holdings.**
3. **Tool-agnostic**: This convention depends only on the abstract capability “input search terms → return real cases,” and is not bound to any vendor. Any equivalent case-library tool may be used. Concrete integration (e.g., PKULaw MCP) is described in [`README.md`](./README.md) in this skill’s directory.

### 4.1 Retrieval Pathways


| Retrieval Pathway | Applicable Scenario | Method | Example |
| :-------- | :------------------- | :------------------------------------------------------------------------------------------------------------------------ | :-------------------------------------------------- |
| **Statute → cases** | Legal application is clear; want to know how a provision is applied in practice | Locate the target provision in the database (e.g., Company Law Art. 20) and open cases “citing this provision.” | For validity of contracts ultra vires by the legal representative, review cases citing Contract Law Art. 50 (now Civil Code Art. 504). |
| **Case → cases** | Unfamiliar with the field; need core cases quickly | 1. Find a “seed case” via WeChat articles, etc.<br>2. Close-read it and extract cited statutes and keywords.<br>3. Expand retrieval with those statutes and keywords. | From an article on “seal authenticity adjudicative rules,” find related cases, then analyze the court’s logic and cited statutes for deeper retrieval. |
| **Keyword search** | Most common; fits most scenarios | 1. **Basic search**: enter “construction project delayed completion.”<br>2. **Advanced search**: limit “court’s opinion” to contain “one-person company” and “outcome” to contain “joint and several liability.”<br>3. **Combined search**: normative + non-normative, e.g., “crime of infringing citizens’ personal information + App.” | Whether a briber’s nominee dry shares constitute completed bribery: combine “bribery + dry shares + completed offense.” |
| **Party → cases** | Habitual litigation strategies of a specific party (e.g., large enterprise) | Enter the company’s full name in the database “parties” field and retrieve all judgments naming it as a party. | To understand a known real-estate company’s construction-dispute strategy, search with it as “party.” |


---
## V. Case Similarity Assessment

### 5.1 Definition of Like Cases and Identification Markers

Under Article 1 of the Supreme People’s Court’s *Guiding Opinions on Unifying Legal Application and Strengthening Like-Case Retrieval (for Trial Implementation)*: **“Like cases are cases that are similar to the pending case in basic facts, disputed issues, legal application, and other respects, and that have already taken effect as judgments of a people’s court.”**

Accordingly, determining whether a case is a “like case” requires these three identification markers:

| Identification Marker | Core Content | Judgment Focus |
|:---|:---|:---|
| **Fact identification** | Basic facts should be **key facts** that decisively affect the outcome (key facts matching legal constitutive elements) | Exclude detail facts irrelevant to legal application; focus on element facts |
| **Issue identification** | The disputed issue is the core judgment for resolving the dispute, more often a **legal-application disputed issue** | Focus on the core legal question in dispute, not purely factual disputes |
| **Law identification** | Cases with the same cause of action should, in principle, apply legal norms within the same category | Same cause of action is an important reference but not absolute; combine with specific provisions |

> **Note**: The three markers should be applied **comprehensively**, not in isolation. High similarity on one marker strengthens like-case recognition, but a fundamental difference on any marker may preclude treating the case as a like case.

---

### 5.2 Similarity Assessment Dimensions and Weights

For cases that pass preliminary screening, conduct deep similarity assessment along five dimensions. Each measures how similar the target case is to the retrieved case, and thus the case’s reference value.

| Assessment Dimension | Weight | Assessment Content | Manifestation of High Similarity |
| :--------- | :-- | :------------------------------- | :----------------------------- |
| **Consistency of legal relationship** | 30% | Whether cause of action, parties’ legal status, rights–obligations structure, and underlying legal relationship align | Same cause of action; corresponding party roles; same direction of rights/obligations; same type of underlying relationship |
| **Correspondence of disputed issues** | 25% | Whether the contested questions are the same; whether legal-application disputes are similar; whether norms involved are the same or close | Core dispute identical; same statute or same interpretive question under the same article |
| **Similarity of key facts** | 25% | Whether decisive facts and element facts are similar; whether facts weaken or strengthen probative force | Element facts fully align; decisive circumstances the same; no material differences |
| **Referenceability of adjudicative rules** | 15% | Whether the holding is clear and forms a generally transferable rule-like statement | Holding forms a clear rule “under condition A, B should be found,” transplantable to this case |
| **Procedural-issue linkage** | 5% | Whether trial procedure, evidence rules, and litigation stage are the same or analogous | Same second-instance final judgment; consistent burden-of-proof allocation; same litigation stage |

#### 5.2.1 Dimension One: Consistency of Legal Relationship (Weight 30%)

**Meaning**: Overall consistency between the target case and the retrieved case in the nature of the legal relationship, parties’ legal status, and rights–obligations structure. This is the threshold for treating a case as a “like case.”

**Judgment points**:
- **Cause-of-action consistency**: Same or most similar cause of action (e.g., both “dispute over shareholder liability for harming company creditors’ interests”).
- **Parties’ legal status**: Whether each party’s role corresponds (e.g., both involve a “one-person company shareholder” sued for joint and several liability).
- **Rights–obligations structure**: Whether the direction of core rights and obligations is the same (e.g., both involve a creditor seeking joint and several liability of a shareholder for company debts).
- **Underlying legal relationship**: Whether the underlying relationship generating the core dispute is the same (e.g., both arise from a sales contract creating a goods-payment debt).

**Assessment tip**: This dimension is the **first threshold** for like cases. If the legal relationship differs fundamentally, even high similarity on other dimensions makes the case unsuitable as a core reference.

#### 5.2.2 Dimension Two: Correspondence of Disputed Issues (Weight 25%)

**Meaning**: Whether the core legal questions disputed by the parties are the same. The disputed issue bridges facts and legal application and is a key marker of a “like case.”

**Judgment points**:
- **Identity of the disputed question**: Whether the core legal question is the same (e.g., both concern “whether an audit report submitted by a one-person company shareholder can prove property independence”).
- **Similarity of legal-application disputes**: Whether the norms and interpretive questions align (e.g., both involve burden allocation under Company Law Art. 63).
- **Number and layers of issues**: Whether there is a single core dispute, or multiple disputes with the main one aligned (different secondary issues do not matter).
- **Need for adjudicative guidance**: Whether both sides seek the same type of rule guidance (e.g., both need clarity on “what evidence proves property independence”).

**Assessment tip**: This dimension is the **core hub** of like-case judgment. Even if legal relationships align, different disputed issues make adjudicative rules hard to apply directly. Focus on comparing the court’s listed “disputed issues” with those of the target case.

#### 5.2.3 Dimension Three: Similarity of Key Facts (Weight 25%)

**Meaning**: Whether **key facts** that decisively affect the outcome are similar. Not all facts need match—only “element facts” matching legal constitutive elements are compared.

**Judgment points**:
- **Element facts**: Whether fact elements required by the norm are present (e.g., both involve “shareholder submitted complete annual audit report + bank statements + applied for judicial audit”).
- **Decisive circumstances**: Whether core circumstances affecting the outcome align (e.g., both involve “unblemished audit report; creditor offered no concrete confusion leads”).
- **Factual defects and exceptions**: Whether facts weaken or strengthen proof (e.g., one shareholder refuses original vouchers; the other proactively provides them).
- **Spatiotemporal background similarity**: Whether time, place, and trading customs of the conduct are close.

**How to identify key facts**:
- From the “facts found by the court” section, extract facts the court treated as “materially affecting the outcome.”
- Map to the statute’s constitutive elements to identify element facts.
- Exclude detail facts irrelevant to legal application (e.g., exact signing time or place of a contract).

**Assessment tip**: This is the **most elastic dimension** and must be judged against the specific norm. Subtle differences can reverse outcomes—assess with special care. Use the “substitution method”: replace key facts in the retrieved case with those of the target case and ask whether the outcome would still hold.

#### 5.2.4 Dimension Four: Referenceability of Adjudicative Rules (Weight 15%)

**Meaning**: Whether the holding and legal-application rule distilled from the retrieved case can provide direct, clear guidance for the target case. This determines “usability.”

**Judgment points**:
- **Clarity of the holding**: Whether the court clearly stated a rule (e.g., “under condition A, legal effect B shall be found”).
- **Transplantability**: Whether the rule can apply directly to similar situations in the target case (the rule should be general, not highly fact-bound).
- **Generality**: Whether the rule is confirmed by multiple cases or is a singleton.
- **Value as supplemental interpretation**: Whether it concretizes an ambiguous provision (rather than merely repeating the statute).

**How to extract adjudicative rules**:
- Focus on **rule-like statements** in the “court’s opinion” section; hallmark phrases include: “shall be found to be…,” “shall not be upheld…,” “may refer to…,” “this court finds that … does / does not constitute…”
- Replace case-specific facts with typed descriptions to extract generally applicable standards.
- Rule format: “Under **[condition/scenario]**, the **[act/claim]** of **[subject]** **[shall/may/shall not]** be found to constitute **[legal effect]**.”

**Assessment tip**: This dimension determines **practical persuasive force**. One thoroughly reasoned, clear-rule case outweighs many vague ones. Prefer cases that concretize statutory provisions.

#### 5.2.5 Dimension Five: Procedural-Issue Linkage (Weight 5%)

**Meaning**: Linkage between the target case and the retrieved case in trial procedure, evidence rules, and litigation stage. Procedural differences may affect the premises for applying an adjudicative rule.

**Judgment points**:
- **Procedural consistency**: Same second-instance, retrial, or first-instance procedure (second-instance and retrial cases are usually better reasoned).
- **Evidence-rule application**: Same burden allocation, standard of proof, etc.
- **Litigation stage**: Same stage (e.g., both main actions, or both enforcement-objection suits).
- **Procedural defects and exceptions**: Whether procedural issues affect the judgment’s force.

**Assessment tip**: Weight is low; usually meaningful only when the first four dimensions are highly similar. But procedure (e.g., rules from retrial cases) can markedly strengthen or weaken reference value. Especially: first-instance judgments not yet effective cannot serve as like-case authority; retrial cases (“民再”) are usually the most rigorously reasoned.

---

### 5.3 Comprehensive Assessment and Grouping

After assessing all five dimensions, combine similarity with hierarchical authority and judgment date to grade cases overall.

**Comprehensive assessment points**:
1. **Judge comprehensively; avoid absolutizing one dimension**: Combine all five; do not treat a case as a like case solely because one dimension is highly similar, nor exclude it solely because one dimension differs.
2. **Sensitivity to key-fact differences**: On some legal issues, a slight factual difference can reverse the outcome—pay special attention.
3. **Equal assessment of adverse cases**: Opposite-outcome cases also need assessment on these dimensions to clarify differences for rebuttal or risk forecasting.
4. **Cross-validation across multiple cases**: Single-case assessment may be biased; cross-compare multiple cases to identify mainstream rules and exceptions.
5. **Combine with hierarchical authority**: After similarity assessment, factor in authority level (Guiding Cases, Gazette cases, etc.) to determine final reference value.

**Case grouping standards** (reference):

| Group | Degree of Similarity | Treatment |
| :------------ | :--------------------- | :------------------- |
| **Group A: Core cases** | Highly similar (at least the first three of five dimensions highly consistent) | Analyze in detail; cite heavily; main reference |
| **Group B: Important reference cases** | Moderately similar (first three dimensions basically aligned, with isolated differences) | Format may be simplified; supplemental reference |
| **Group C: General reference cases** | Low similarity (only some dimensions align) | Brief list form; background reference only |
| **Group D: Opposite-outcome cases** | Opposite adjudicative conclusions (regardless of similarity) | List opposite-outcome cases; analyze differences in detail |


---


## VI. Case Screening and Ranking

Case screening is the core step in producing a like-case retrieval report. Scientifically selecting the most valuable cases strengthens persuasiveness and avoids overload. This chapter systematically sets out six screening standards (hierarchy, geography, time, procedure, background, importance) and three verification rules (effectiveness verification, risk verification), and explains judgment methods and application rules for each.

---

### 6.1 Case Screening Standards

| Dimension | Screening / Verification Item | Priority / Pass Standard | Risk Notice / Exclusion |
| :-------- | :--------------- | :-------------------------------------------------------------- | :----------------------------------------- |
| **Hierarchy** | Case authority level | Guiding Cases > Case Library inbound cases > Gazette cases > typical/SPC cases > high-court reference cases > higher-court cases > same-court cases > others | When earlier-tier cases suffice, later-tier cases generally need not be submitted |
| **Geography** | Court territorial nexus | Local court > courts in economically/culturally similar regions > others | If the dispute has clear regional features (e.g., local regulations), prioritize cases from the same jurisdiction |
| **Time** | Judgment date and time facts arose | Closer judgment dates preferred (suggest within 3–5 years) | Match when facts arose with when judgment was rendered; watch for legal change making rules obsolete |
| **Procedure** | Trial procedure type | “民再” (retrial) > “民终” (second instance) > “民初” (first instance) > “民申” (retrial review) | Retrial cases most rigorously reasoned; SPC “民申” cases often only reflect the high court’s view—lower reference value |
| **Background** | Special endorsement | Prefer special endorsement (panel members involved in drafting judicial interpretations / decided after Adjudication Committee discussion) | Cases without special endorsement have ordinary reference value |
| **Importance** | Gravity / difficulty / complexity | Prefer cases that are “four categories of cases” or mandatory-retrieval situations | Reasoning depth and value of ordinary summary-procedure cases are usually lower than major/difficult cases |
| **Effectiveness verification** | Confirm judgment has taken effect | Verify whether second-instance proceedings exist and whether the result conflicts with first instance | **Judgments not yet effective do not qualify as references** |
| **Risk verification** | Confirm not vacated; confirm no risk | Search related cases by main party names; comprehensively review content unrelated to one’s proof purpose | **Risk of vacation via retrial or third-party revocation suit;** avoid adverse views in the case text |


---

#### 6.1.1 Hierarchy Standard (Authority First)

**Meaning**: Authority level determines binding and persuasive force. The higher the level, the stronger the court’s duty to refer.

**Judgment rules**:

| Case Type | Issuing Body | Authority Level | Application Rules |
| :-------------- | :----------- | :--------------- | :--------------------------------------- |
| **Guiding Cases** | SPC Adjudication Committee | **Shall be referred to** (hard constraint) | Courts at all levels shall refer when trying similar cases; reasoning must address whether referral was made |
| **People’s Court Case Library inbound cases** | Supreme People’s Court | **Shall be referred to** | Under Art. 19 of the *Work Rules on Building and Operating the People’s Court Case Library*, if a party submits them, the court must respond in reasoning |
| **Gazette cases** | *Gazette of the Supreme People’s Court* | **Highly authoritative reference** (soft constraint) | Not mandatory, but reflect SPC tendency |
| **Typical / reference cases** | SPC divisions, local high courts | **Important reference** | Mainly unify adjudicative scales within the jurisdiction; de facto guidance for lower courts |
| **Higher-court cases** | Immediately superior people’s court | **De facto constraint** | Given appellate supervision, judgments generally should not conflict with superior-court judgments |
| **Same-court cases** | Prior judgments of the same court | **Soft constraint** | Avoid inconsistent outcomes in like cases; maintain judicial consistency |
| **Out-of-province court cases** | Courts of other provinces/municipalities | **General reference** | Borrow reasoning and methods; no binding force |


**Practice tips**:
- When earlier-tier cases suffice, generally do not submit later-tier cases.
- If earlier-tier cases are insufficient, backfill in order, but explain in the report.
- The report’s core goal is to “persuade by reason”; even only higher-court or same-court cases remain valuable if thoroughly reasoned.

---

#### 6.1.2 Geography Standard (Jurisdictional Nexus)

**Meaning**: Territorial nexus between the adjudicating court and the court seized of the target case affects acceptability of the rule.

**Judgment rules**:
- **Local court cases first**: Cases from the same province, city, or even same court best reflect local adjudicative habits and judicial policy.
- **Economically/culturally similar regions next**: If local cases are insufficient, prefer courts in provinces with similar economic structure, culture, and judicial tradition (e.g., Yangtze River Delta, Pearl River Delta, Chengdu–Chongqing).
- **Other regions last**: General reference only.

**Special notes**:
- If the dispute type or key facts have clear **regional features** (local regulations, local policies, industry customs), prioritize cases from courts in the same jurisdiction; out-of-province value drops sharply.
- Example: rural land-contracting disputes—local regulations differ widely by province; prefer cases from the provincial high court or intermediate courts of the same province.

---

#### 6.1.3 Time Standard (Currency)

**Meaning**: How close the judgment date and the time when facts arose are to the target case affects currency and applicability of the rule.

**Judgment rules**:
- **Closer judgment dates preferred**: Statutes, judicial interpretations, and judicial policy continually update; cases from the past 3–5 years best reflect current scales.
- **Also consider when legal facts arose**: Cases with close judgment dates but distant fact times may have applied different norms (e.g., Contract Law vs. Civil Code). Prefer cases whose fact times are close to the target case.
- **Watch for legal change**: If the target case should apply the Civil Code, but the retrieved case was decided in 2019 (under the Contract Law), confirm whether the Civil Code changed the rule. If unchanged, still usable; if changed, do not rely on it.

**Currency score-reduction reference** (for composite scoring):
- Cases 3–5 years old: modest reduction
- Cases 5–10 years old: larger reduction
- Cases over 10 years: generally do not use unless confirming the law is unchanged

---

#### 6.1.4 Procedure Standard (Instance Rigor)

**Meaning**: Different trial procedures differ in rigor of reasoning and stability of views.

**Judgment rules**:
- **“民再” > “民终” > “民初” > “民申”**
- **民再 (retrial)**: Discussed by the Adjudication Committee or retrial amendment—most rigorous reasoning; highest reference value.
- **民终 (second instance)**: Final judgment; stable force; main reference source.
- **民初 (first instance)**: Judgments not yet effective (e.g., appeal still possible) do not qualify; effective unappealed first-instance judgments have lower value than second instance.
- **民申 (retrial review)**: SPC “民申” cases usually only reflect the original high court’s view without substantive SPC adjudication—lower value; generally not primary references.

**Practice tips**:
- When retrieving a first-instance instrument, always verify whether second-instance proceedings and outcomes exist.
- Prefer cases with “民再” and “民终” case numbers.

---

#### 6.1.5 Background Standard (Special Endorsement)

**Meaning**: Trial background (panel composition, Adjudication Committee discussion) may confer extra authority.

**Judgment rules**:
- **Panel members with legislative background**: If panel members helped draft related judicial interpretations or judicial documents, their reasoning often tracks legislative intent more closely and has higher value.
- **Decided after Adjudication Committee discussion**: Language such as “decided after discussion by this court’s Adjudication Committee” signals professional endorsement and markedly strengthens the rule’s authority.

**Practice tips**:
- When reading judgments, note whether the caption or “court’s opinion” contains such language.
- If present, specially mark it in the report to strengthen persuasiveness.

---

#### 6.1.6 Importance Standard (Gravity / Difficulty / Complexity)

**Meaning**: The case’s gravity, difficulty, and complexity affect typicality of the rule and depth of reasoning. Cases falling within situations that “shall undergo like-case retrieval” usually have higher value.

**Judgment basis** (referencing the SPC *Guiding Opinions on Unifying Legal Application and Strengthening Like-Case Retrieval (for Trial Implementation)* and related rules):

For the following **four categories of cases**, judges **must** conduct like-case retrieval; their judgments are usually more carefully considered and better reasoned:

1. **Major, difficult, complex, or sensitive**: Involving major interests, complex legal relationships, high social attention, strong policy character, etc. Such judgments often go through professional judges’ meetings or the Adjudication Committee; rules are more typical.
2. **Group disputes or matters of wide social concern that may affect social stability**: E.g., involving interests of many workers, owners, or investors. Such judgments often reflect judicial-policy orientation and have important reference value.
3. **Possible conflict with like-case judgments of the same court or a higher court**: Indicates adjudicative divergence; retrieved cases that unify the rule have higher value.
4. **Reports that a judge engaged in unlawful adjudication**: Such cases undergo supervisory review; fairness and reasoning are usually better assured.

Additionally, the following are mandatory or strongly recommended retrieval situations, and related cases likewise have high importance:
- **Cases proposed for professional judges’ meetings or Adjudication Committee discussion**: Rules usually emerge from collective discussion—higher authority.
- **Lack of clear unified rules or no unified rules yet formed**: Reasoning is often more detailed, seeking to fill gaps or clarify ambiguity.
- **Cases where court/division leadership requires retrieval under trial-supervision authority**: Reflects internal emphasis on case quality.

**Practice application**:
- When screening, prefer cases falling within the above. How to tell? Look for features such as:
  - “decided after discussion by this court’s Adjudication Committee”;
  - novel/difficult causes of action (e.g., “first case,” “first nationwide”);
  - many parties or public-interest involvement;
  - lengthy judgments with detailed reasoning.
- In the report, mark such cases (e.g., “This case was decided after Adjudication Committee discussion and has high reference value”).

---

#### 6.1.7 Effectiveness Verification and Risk Verification

Before including any case in the retrieval report, complete the following three verifications. Cases failing any verification should generally not be listed (except opposite-outcome cases, which must be specially explained).

##### 6.8.1 Confirm the Judgment Has Taken Effect

**Method**:
- Verify whether second-instance proceedings exist. If a first-instance judgment is retrieved, search China Judgments Online or related-case search by party name for a second-instance instrument.
- If second instance exists, confirm whether it conflicts with first instance (e.g., amendment or remand). If second instance affirms or only fine-tunes, the first-instance judgment may still be referenced, but preferring the second-instance judgment is better.

**Risk notice**:
- **Judgments not yet effective do not qualify as references**. First-instance judgments still within the appeal period or on appeal and not concluded cannot serve as like-case authority.

##### 6.8.2 Confirm the Judgment Has Not Been Vacated

**Method**:
- Using **main parties’** names as keywords (limit to core parties; avoid adding third parties and other non-core subjects lest results be missed), search related cases on China Judgments Online or databases.
- Check for retrial judgments, transfer-for-trial rulings, or third-party revocation judgments that vacated or amended the original judgment.

**Risk notice**:
- **Risk of vacation via retrial or third-party revocation suit**. If vacated, the adjudicative rule no longer has reference value.

##### 6.8.3 Confirm the Judgment Poses No Risk

**Method**:
- Comprehensively review all content **unrelated to one’s proof purpose**, including:
  - Whether “facts found by the court” contains adverse factual descriptions;
  - Whether “court’s opinion” contains negative evaluations of similar claims;
  - Whether the outcome contains adverse findings (e.g., “the plaintiff was also at fault”).

**Risk notice**:
- **Avoid adverse views in the case text**. If a case overall supports one’s claim but contains an adverse detail (e.g., “although the shareholder was excused here, note that the shareholder and company must have no fund transfers”), opposing counsel may excerpt that part. Identify early and prepare a response, or consider replacing the case.

---
### 6.2 Case Ranking and Conflict-Handling Rules

When multiple like cases exist or conflict, rank and handle them by the **“proximity principle.”** The principle has three layers: **proximity of level first > proximity of specialty first > proximity of time first**.

- **Proximity of level first**: For the adjudicator of the seized court, cases from the **immediate superior court** have the greatest influence and persuasiveness because they directly relate to adjudicative risk (amendment or remand).
- **Proximity of specialty first**: Within the same court, cases from the **specialized trial division hearing this case** (e.g., finance, IP) have more value than those from other divisions of the same court.
- **Proximity of time first**: When conflict arises, the **later-decided** case prevails, because later cases usually reflect new statutes, judicial interpretations, or policy adjustments.

#### 6.2.1 Direct-Line, Collateral, and External Cases (Foundation of Level Proximity)

| Category | Definition | Example | Binding Force |
|:---|:---|:---|:---|
| **Direct-line cases** | Cases from superior courts in a vertical supervisory relationship with the seized court | Basic → intermediate → high → Supreme People’s Court | Strongest (stronger the closer the level) |
| **Collateral cases** | Cases from peer courts under the same superior court as the seized court | Different basic courts under the same intermediate court; different intermediate courts under the same high court | Medium (regional reference) |
| **External cases** | Cases that are neither direct-line nor collateral | Out-of-province court cases | Weaker (reasoning reference only) |

#### 6.2.2 Eight Concrete Handling Rules

**Rule One**: Direct-line cases prevail over collateral cases; collateral prevail over external.

**Rule Two**: Among direct-line cases, if courts at different levels conflict, the case from the **nearest superior court** to the seized court prevails.

**Rule Three**: Among direct-line cases, if the nearest superior court has multiple conflicting cases, the case from the **same specialized trial division** as the one hearing this case prevails.

**Rule Four**: Among direct-line cases, if the nearest superior court’s same specialized division has multiple conflicting cases, the **later-in-time** case prevails.

**Rule Five**: Among direct-line cases, if multiple superior courts at different levels conflict, the **later-in-time** case prevails.

**Rule Six**: Cases of the seized court are used as follows:
- If the handling judge’s or panel’s cases conflict with those of other judges or panels of the seized court, prefer the cases of **this case’s handling judge or same panel**;
- If different specialized divisions of the seized court conflict, prefer the cases of the **specialized division to which the handling judge or panel belongs**;
- If that specialized division has no cases, prefer cases of the **nearest superior court’s same specialized division**;
- If the handling judge, panel, or specialized division has multiple conflicting cases, the **later-in-time** case prevails.

**Rule Seven**: If the same court has no cases and there are no other direct-line cases, draw on **collateral cases** of the seized court, used as follows:
- If multiple collateral cases exist, prefer peer courts located at the seat of the people’s government at the same level as the common nearest superior court; if that priority court has multiple cases, later-in-time prevails;
- Among collateral cases, if specialized divisions conflict, prefer collateral cases from the **same specialized division** as this case;
- Among multiple collateral cases, **later-in-time** prevails.

**Rule Eight**: If there are neither direct-line nor collateral cases, use **external cases** as follows:
- Prefer cases sharing a party with this case and having the same or similar subject matter; if multiple similar cases conflict, later-in-time prevails;
- Prefer peer courts under the same retrial court;
- Prefer peer courts in the same cultural sphere as the seized court; if multiple, prefer the same specialized division as this case; if that division has multiple, later-in-time prevails;
- Otherwise, prefer other peer-court external cases; if multiple, prefer the same specialized division; if that division has multiple, later-in-time prevails.

> **Summary**: These eight rules form a complete case-application system based on “proximity of level, specialty, and time,” for handling adjudicative conflicts among courts on the same legal issue and guiding which like case has the greatest practical reference value.



## VII. Organizing Results and Producing the Report

### 7.1 Case Information Extraction Template

#### Basic information
- Case name:
- Case number:
- Adjudicating court:
- Judgment date:
- Cause of action:
- Instance: (first / second / retrial)
- Case type: (Guiding Case / Gazette case / typical case / ordinary case)
- Instrument type: (judgment / ruling / mediation statement)

#### Party information
- Plaintiff / appellant / applicant:
- Defendant / appellee / respondent:
- Third party (if any):

#### Case-fact summary
- Core facts: (within 200 characters/words)
- Factual correspondence to the target case:

#### Disputed issues
- Issue 1:
- Issue 2:

#### Adjudicative holding
- Core adjudicative rule:
- Legal-application points:
- Summary of reasoning:

#### Applicable law
- Main statutory bases:
- Judicial-interpretation bases:

#### Outcome
- Summary of judgment/ruling operative part:

#### Retrieval assessment
- Similarity score: __/10
- Similarity level: high / medium / low
- Explanation of reference value:
- Key differences from the target case:

### 7.2 Standard Structure of the Retrieval Report

```markdown
## I. Retrieval Statement
### 1.1 Retrieval Question
[State clearly the legal issue this retrieval seeks to resolve]

### 1.2 Retrieval Tools
[List databases and platforms used]

### 1.3 Retrieval Methods
[Describe pathways and keywords used]

## II. Basic Information on the Pending Case
### 2.1 Legal Relationship
[Describe the target case’s legal relationship]

### 2.2 Disputed Issues
- Issue 1: [description]
- Issue 2: [description]

### 2.3 Applicable Law
- [List relevant provisions]

## III. Core Cases (Group A: similarity ≥80%)
[Detailed case information per template]

## IV. Important Reference Cases (Group B: similarity 60–79%)
[Same format; may simplify]

## V. General Reference Cases (Group C: similarity 40–59%)
[Brief list form]

## VI. Opposite-Outcome Cases (Group D)
[List opposite-outcome cases; analyze differences]

## VII. Summary of Adjudicative Rules
### 7.1 Mainstream Adjudicative Rules
[Distill rules reflected by the majority of cases]

### 7.2 Minority / Exception Rules
[Distill minority views]

### 7.3 Trend Analysis
[Analyze evolution of adjudicative rules]

## VIII. Retrieval Conclusions and Recommendations
### 8.1 Retrieval Conclusions
[Summarize findings]

### 8.2 Recommendations for the Target Case
[Propose recommendations based on results]

### 8.3 Limitations of This Retrieval
[State limitations and gaps]
```

### 7.3 Production Tips and Cautions

**1. Organize like cases by layers matching the advocacy brief’s argument structure**

A like-case retrieval report exists to support litigation claims; its organization should track the advocacy brief’s argument structure. When different like cases support rules corresponding to different disputed issues, layered arrangement and logical correspondence among cases become especially necessary.

**2. Use of adverse cases**

Adverse cases are not useless. Retrieving and analyzing them is like viewing the problem from a bird’s-eye perspective:
- Fully assess legal risks one’s side may face and whether the case has representation value
- Break the limits and rigidity of a one-sided advocacy approach; prepare early for likely defenses
- Submitting a comprehensive like-case analysis that explains why adverse cases are inapplicable can relatively increase judicial acceptance of the overall report

**3. Prefer subtraction over addition**

- Do not state retrieval duration, discarded keywords, or the retriever’s name in the report
- Usually keep 3–5 like cases under the same disputed issue or adjudicative point
- Avoid marking the entire text so heavily that key points are obscured

**4. Handling original case texts**

- Append the original retrieval sources after the report
- Highlight reading priorities with a highlighter to reduce the judge’s reading burden
- Prefer versions with China Judgments Online watermarks
- Paginate originals and prepare a table of contents, or note corresponding page numbers in the like-case summaries

---

## VIII. Complete Sample Report: Like-Case Retrieval Report on Horizontal Denial of Corporate Personality

### I. Retrieval Statement

#### 1.1 Retrieval Question
**Core question**: Where affiliated companies have personality confusion, must they bear joint and several liability for each other’s debts? (Conditions for applying horizontal denial of corporate personality)

**Extended questions**:
1. How is personality confusion among affiliated companies determined?
2. What are the standards for finding “personnel confusion, business confusion, and financial confusion”?
3. Must the actual controller bear joint and several liability for affiliated companies’ debts?

#### 1.2 Retrieval Tools
- Faxin platform
- PKULaw
- Wolters Kluwer China Law
- China Judgments Online
- People’s Court Case Library

#### 1.3 Retrieval Methods
**Pathway One (statute linkage)**: Using Company Law Art. 20(3), Art. 23(2) (2023 revision), and Arts. 10–11 of the *Nine Minutes* as base provisions, retrieve related cases

**Pathway Two (keyword combinations)**:
- Group 1: "affiliated companies" AND "personality confusion" AND "joint and several liability"
- Group 2: "horizontal denial" OR "horizontal piercing" AND "denial of corporate personality"
- Group 3: "personnel confusion" OR "financial confusion" OR "business confusion" AND "affiliated companies"

**Pathway Three (case reverse search)**: Starting from *XCMG Construction Machinery Co., Ltd. v. Chengdu Chuanjiao Industry & Trade Co., Ltd. et al.* (sales contract dispute) (Guiding Case No. 15), retrieve subsequent judgments citing that case

### II. Basic Information on the Pending Case

#### 2.1 Legal Relationship
This case is a sales-contract dispute. The plaintiff (creditor) has a sales-contract relationship with Defendant I (debtor); Defendant I failed to pay for goods. Defendants II and III are affiliated companies of Defendant I (controlled by the same actual controller); the three companies are highly confused in personnel, business, and finance. The plaintiff claims personality confusion among the three and seeks joint and several liability of Defendants II and III for Defendant I’s debts.

#### 2.2 Disputed Issues
- **Issue 1**: Do Defendants II and III and Defendant I constitute personality confusion among affiliated companies?
- **Issue 2**: If so, must Defendants II and III bear joint and several liability for Defendant I’s debts? (Application of horizontal denial of corporate personality)
- **Issue 3**: Must the actual controller bear joint and several liability for company debts?

#### 2.3 Applicable Law
- Article 23(2) of the *Company Law of the People’s Republic of China* (2023 revision)
- Article 20(3) of the *Company Law of the People’s Republic of China* (2018 amendment)
- Articles 10 and 11 of the *Minutes of the National Court Work Conference on Civil and Commercial Trials* (*Nine Minutes*)
- Articles 6 (fairness) and 7 (good faith) of the *Civil Code of the People’s Republic of China*

### III. Core Cases (Group A: Similarity ≥80%)

#### Case 1: XCMG Construction Machinery Co., Ltd. v. Chengdu Chuanjiao Industry & Trade Co., Ltd. et al. (sales contract dispute)
- **Case number**: (2011) Su Shang Zhong Zi No. 0107
- **Adjudicating court**: Jiangsu High People’s Court
- **Judgment date**: 19 October 2011
- **Case type**: **Guiding Case No. 15** (issued by the Supreme People’s Court on 31 January 2013)
- **Similarity score**: 9.5/10

**Case-fact summary**:
Chuanjiao Industry & Trade owed XCMG over RMB 10.91 million in goods payment. Chuanjiao Machinery and Ruilu were affiliated with Chuanjiao Industry & Trade; Wang Yongli was the actual controller of all three. All three had Wang Yongli as manager, Ling Xin as financial officer, Lu Xin as cashier-accountant, and Zhang Meng as industrial-commercial formality handler; management positions overlapped. Their business scopes overlapped; external publicity did not clearly distinguish them; they shared sales manuals and special seals for business contracts. Financially, they shared settlement accounts; funds and control could not be distinguished. The plaintiff claimed personality confusion and sought joint and several liability.

**Disputed issues**:
1. Did Chuanjiao Machinery, Ruilu, and Chuanjiao Industry & Trade constitute personality confusion?
2. If so, must they bear joint and several liability for Chuanjiao Industry & Trade’s debts?

**Adjudicative holding**:
1. Where affiliated companies’ personnel, business, finance, etc., cross or confuse so that their respective property cannot be distinguished and independent personality is lost, personality confusion is constituted.
2. Where affiliated companies’ personality is confused and creditors’ interests are seriously harmed, the affiliated companies bear joint and several liability to each other for external debts.

**Summary of reasoning**:
"Independent corporate personality is the premise for a legal person to bear liability independently. Article 3(1) of the Company Law provides: ‘A company is an enterprise legal person that has independent legal-person property and enjoys legal-person property rights. A company shall be liable for its debts with all its property.’ Independent property is the material guarantee of independent liability; independent personality is prominently reflected in property independence. When affiliated companies’ property cannot be distinguished and independent personality is lost, the basis for independent liability is lost. Article 20(3) of the Company Law provides: ‘Where a company’s shareholder abuses the company’s independent legal-person status and shareholders’ limited liability to evade debts and seriously harms the interests of the company’s creditors, the shareholder shall bear joint and several liability for the company’s debts.’ In this case, although the three companies were registered with the industrial and commercial authorities as mutually independent enterprise legal persons, in reality boundaries among them were blurred and personalities confused; Chuanjiao Industry & Trade bore all affiliated companies’ debts yet could not pay, enabling the other affiliated companies to evade huge debts and seriously harming creditors’ interests. Such conduct contradicts the purpose of the legal-person system and the principle of good faith; its essence and harmful result are comparable to the circumstances under Article 20(3) of the Company Law. Therefore, by reference to Article 20(3), Chuanjiao Machinery and Ruilu shall bear joint and several liability to pay Chuanjiao Industry & Trade’s debts."

**Reference value**:
This is **Guiding Case No. 15 of the Supreme People’s Court**, a landmark on horizontal denial of corporate personality. It established standards for finding personality confusion among affiliated companies (personnel, business, and financial confusion) and legal consequences (joint and several liability). It aligns highly with the pending case on basic facts (affiliated-company structure; three-confusion features), disputed issues (application of horizontal denial), and legal application (analogous application of Company Law Art. 20(3)), and has the strongest reference value.

**Key differences**:
When this case was decided, the Company Law did not yet expressly provide for horizontal denial; the court “applied by reference” Article 20(3). After the 2023 Company Law revision, Article 23(2) expressly provides for horizontal denial, making legal application more direct.

---

#### Case 2: China Cinda Asset Management Chengdu Office v. Sichuan Tailai Decoration Engineering Co., Ltd. et al. (loan contract dispute)
- **Case number**: (2008) Min Er Zhong Zi No. 55
- **Adjudicating court**: Supreme People’s Court
- **Judgment date**: 2008
- **Case type**: **Gazette case**
- **Similarity score**: 9/10

**Case-fact summary**:
Sichuan Tailai Decoration Engineering, Sichuan Tailai Housing Development, and Sichuan Tailai Entertainment were affiliated companies, all actually controlled by Shen Huayuan. They exhibited personnel confusion (overlapping management), financial confusion (shared accounts; arbitrary fund transfers), and business confusion (overlapping scopes; mixed external publicity). Cinda claimed personality confusion and sought joint and several liability for the loan debts.

**Disputed issues**:
Where affiliated companies have personality confusion, must they bear joint and several liability for each other’s debts?

**Adjudicative holding**:
Where a controlling shareholder or actual controller controls multiple subsidiaries or affiliated companies and abuses control so that property boundaries among them are unclear, finances are confused, interests are transferred among them, and personality independence is lost—turning them into tools for the controlling shareholder to evade debts, operate illegally, or even commit crimes—the court may, upon comprehensive facts, deny the subsidiaries’ or affiliated companies’ legal-person personality and order joint and several liability.

**Summary of reasoning**:
"As actual controller of the Shen companies, Shen Huayuan arbitrarily disposed of and confused each company’s property and creditor–debtor relations, making personnel, property, etc., indistinguishable, contradicting the purpose of the legal-person system, violating good faith and fairness, and harming creditors’ interests."

**Reference value**:
This is a **Supreme People’s Court Gazette case** that earlier established adjudicative rules on horizontal denial. It is highly similar to the pending case on key facts such as “same actual controller controlling multiple affiliated companies,” “three-confusion features,” and “harm to creditors’ interests.” Reasoning on “contradicting the purpose of the legal-person system” and “violating good faith and fairness” is important for this case.

**Key differences**:
The judgment is earlier; whether Article 20(3) then applied to horizontal denial was contested, and the court ultimately relied on basic civil-law principles. Article 23(2) of the Company Law now expressly provides for horizontal denial.

---

#### Case 3: A bank v. an industrial company et al. (financial loan contract dispute) (Case Library inbound case)
- **Case number**: (2022) Zui Gao Fa Min Zhong No. XXX (illustrative)
- **Adjudicating court**: Supreme People’s Court
- **Judgment date**: 2022
- **Case type**: **People’s Court Case Library inbound case**
- **Similarity score**: 8.5/10

**Case-fact summary**:
(Because the specific case number requires querying the Case Library, a typical scenario is described here.) The debtor company and its affiliates were highly confused: same legal representative, same finance staff, same office premises, shared bank accounts, frequent fund flows with undistinguishable accounts. The creditor sought joint and several liability of the affiliates.

**Disputed issues**:
1. Standards for finding personality confusion among affiliated companies?
2. How is the burden of proof allocated for horizontal denial?

**Adjudicative holding**:
Under Company Law Art. 23(2) (as applicable after the 2023 revision) or by reference to Art. 20(3), where affiliated companies have personality confusion, they shall bear joint and several liability for each other’s debts. Finding personality confusion requires comprehensive consideration of the degree of confusion in personnel, business, and finance, and whether property becomes indistinguishable.

**Reference value**:
As a People’s Court Case Library inbound case, under Art. 19 of the *Work Rules on Building and Operating the People’s Court Case Library*, it **shall be referred to**. It belongs to the same financial-commercial category as the pending case and is highly similar in affiliated-company structure, confusion features, and legal application.

**Key differences**:
This case may involve special diligence duties of a financial institution as creditor, slightly different from the pending case’s ordinary sales-contract relationship.

---

### IV. Important Reference Cases (Group B: Similarity 60–79%)

#### Case 4: Lei Moufu v. Chongqing Lanyu Company et al. (outsider’s objection suit)
- **Case number**: (2020) Zui Gao Fa Min Shen No. XXX
- **Adjudicating court**: Supreme People’s Court
- **Judgment date**: 2020
- **Case type**: Supreme People’s Court judgment
- **Similarity score**: 7/10

**Case-fact summary**:
In enforcement, the creditor discovered personality confusion between the debtor and an affiliate and applied to add the affiliate as a judgment debtor. The court held that horizontal denial may still apply at the enforcement stage to add the affiliate as a judgment debtor.

**Disputed issues**:
May horizontal denial of corporate personality apply at the enforcement stage?

**Adjudicative holding**:
Horizontal denial may still apply at the enforcement stage to protect creditors’ interests.

**Reference value**:
This case resolves the **procedural application** of horizontal denial, confirming that affiliates may also be added as judgment debtors at enforcement. If the pending case enters enforcement, this case is an important reference.

**Key differences**:
This concerns adding judgment debtors in enforcement, slightly different from confirming joint and several liability at the litigation stage in the pending case.

---

#### Case 5: A construction company v. a real-estate development company et al. (construction project contract dispute)
- **Case number**: (2019) XX High Court Min Zhong No. XXX
- **Adjudicating court**: A provincial high people’s court
- **Judgment date**: 2019
- **Case type**: High people’s court judgment
- **Similarity score**: 6.5/10

**Case-fact summary**:
Affiliated real-estate and construction companies had personnel confusion (overlapping management) and financial confusion (fund transfers without clear accounts), but business confusion was low (different business scopes). The court found personality confusion and joint and several liability.

**Disputed issues**:
Where business confusion is low, may personality confusion still be found?

**Adjudicative holding**:
Finding personality confusion does not require all three confusions (personnel, business, finance); it suffices that the degree reaches “property indistinguishable and independent personality lost.”

**Reference value**:
This case clarifies the **flexible standard** for personality confusion and remains useful if one confusion feature is weak in the pending case.

**Key differences**:
This is a construction-project dispute, unlike the pending sales contract; and its lower demand for business confusion does not fully match the pending case’s three-fold confusion features.

---

### V. General Reference Cases (Group C: Similarity 40–59%)

| No. | Case Name | Case Number | Adjudicating Court | Adjudicative Holding | Reference Value |
|-----|---------|------|---------|---------|---------|
| 1 | A trading company v. a group company et al. (sales contract dispute) | (2017) XX Intermediate Min Chu No. XXX | A municipal intermediate people’s court | Personnel confusion alone is insufficient for personality confusion; property must be indistinguishable | Reverse reference: single confusion is not enough |
| 2 | A bank v. an investment company et al. (financial loan contract dispute) | (2021) XX High Court Min Zhong No. XXX | A provincial high people’s court | Inter-affiliate fund lending with clear accounts does not constitute personality confusion | Reverse reference: financial confusion requires “indistinguishability” |
| 3 | A tech company v. a software company et al. (computer software development contract dispute) | (2020) Zui Gao Fa Zhi Min Zhong No. XXX | Supreme People’s Court | Standards for personality confusion among affiliates in IP cases | Different field, but standards may be referenced |

---

### VI. Opposite-Outcome Cases (Group D)

#### Case 6: An industrial company v. a trading company et al. (sales contract dispute) (personality confusion not found)
- **Case number**: (2018) XX Intermediate Min Zhong No. XXX
- **Adjudicating court**: A municipal intermediate people’s court
- **Judgment date**: 2018
- **Case type**: Ordinary case

**Case-fact summary**:
Although the three companies were controlled by the same actual controller and had some overlapping managers, each had an independent finance department, kept separate books, and recorded fund flows clearly; property could be distinguished. The court found no personality confusion.

**Adjudicative holding**:
Personnel overlap among affiliates is insufficient for personality confusion; the key is whether financial confusion makes property indistinguishable.

**Difference analysis**:
The key difference from the pending case is the **degree of financial confusion**. Here defendants had independent finance departments, separate books, and clear fund flows; in the pending case the three companies shared settlement accounts and funds/control could not be distinguished—higher financial confusion. Thus the opposite outcome does not apply to the pending case and instead sideways confirms that the pending case meets the personality-confusion standard.

---

### VII. Summary of Adjudicative Rules

#### 7.1 Mainstream Adjudicative Rules

**Rule One: Standards for finding personality confusion among affiliated companies**
Where affiliated companies’ personnel, business, finance, etc., cross or confuse so that their respective property cannot be distinguished and independent personality is lost, personality confusion is constituted. The three aspects (personnel, business, finance) are main factors, but **all three need not be present**; the core is whether the result is “property indistinguishable and independent personality lost.”

**Rule Two: Legal consequences of horizontal denial**
Where affiliated companies’ personality is confused and creditors’ interests are seriously harmed, the affiliated companies bear joint and several liability to each other for external debts. After the 2023 Company Law revision, Article 23(2) expressly provides: “Where a shareholder uses two or more companies under its control to commit the acts provided in the preceding paragraph, each company shall bear joint and several liability for the debts of any of the companies.”

**Rule Three: Burden of proof**
A creditor claiming personality confusion among affiliates should offer preliminary evidence of confusion facts (personnel, business, financial crossover). Affiliates denying this should prove property independence (e.g., independent books, independent accounting).

**Rule Four: Actual controller’s liability**
Where an actual controller abuses independent legal-person status and shareholders’ limited liability to evade debts and seriously harms creditors’ interests, the controller shall bear joint and several liability for company debts. But **mere knowledge of affiliated companies’ personality confusion is insufficient for joint and several liability**; one must prove confusion between the controller’s own property and company property, or abuse of control.

#### 7.2 Minority / Exception Rules

**Exception One: Single confusion is not enough**
Some courts hold that personnel or business confusion alone, with financial independence and distinguishable property, does not constitute personality confusion.

**Exception Two: Industry-specific considerations**
In industries with group management and centralized finance, moderate fund transfers and personnel sharing may not be treated as confusion.

**Exception Three: Procedural limits**
A few courts held that horizontal denial should be resolved at the litigation stage and that affiliates should not be added as judgment debtors directly at enforcement (but the Supreme People’s Court’s latest trend confirms enforcement-stage application as well).

#### 7.3 Trend Analysis

**Trend One: From “application by reference” to “direct application”**
Guiding Case No. 15 (2013) “applied by reference” Company Law Art. 20(3); *Nine Minutes* Art. 11 (2019) clarified horizontal denial; Company Law Art. 23(2) (2023) formally established it—moving from analogical to direct application.

**Trend Two: Standards from strict to lenient to moderate**
Early cases were strict, requiring all three confusions; after Guiding Case No. 15 the standard eased, emphasizing “property indistinguishable”; recent cases trend toward refinement, focusing on substantive fairness and creditor protection.

**Trend Three: Expanding procedural application**
From confirming joint and several liability at litigation, to adding judgment debtors at enforcement, to substantive consolidation in bankruptcy—procedural pathways for horizontal denial continue to mature.

---

### VIII. Retrieval Conclusions and Recommendations

#### 8.1 Retrieval Conclusions

1. **Legal application**: After the 2023 Company Law revision, Article 23(2) expressly provides for horizontal denial; the pending case may apply that article directly without further “application by reference” of Article 20(3).

2. **Fact finding**: The three defendant companies in the pending case exhibit **personnel confusion** (same actual controller; overlapping management), **business confusion** (overlapping scopes; mixed external publicity), and **financial confusion** (shared settlement accounts; indistinguishable funds), meeting the personality-confusion standard established by Guiding Case No. 15.

3. **Adjudicative trend**: The Supreme People’s Court and local courts tend to apply personality-confusion findings for affiliated companies strictly with creditor protection in mind; the pending case has a relatively high chance of success.

4. **Risk notice**: Collect and fix evidence of financial confusion (bank statements, account books, etc.)—this is key to finding personality confusion.

#### 8.2 Recommendations for the Target Case

**Litigation-strategy recommendations**:

1. **Legal application**: Directly invoke Company Law (2023 revision) Art. 23(2), and cite Guiding Case No. 15 as reasoning support.

2. **Evidence organization**:
   - Personnel confusion: collect industrial-commercial registration info, management appointment documents, social-insurance payment records, etc.
   - Business confusion: collect external publicity materials, business contracts, evidence of overlapping customers, etc.
   - Financial confusion: apply for court retrieval of the three companies’ bank statements and financial books to prove shared accounts and fund confusion

3. **Like-case submission**: Prefer Guiding Case No. 15, Gazette case (2008) Min Er Zhong Zi No. 55, and similar judgments of the local high court or superior courts.

4. **Responding to adverse cases**: Anticipate the opponent may submit “single confusion is not enough” cases; prepare evidence that this case involves severe three-fold confusion and that financial confusion reaches “property indistinguishable.”

**Document-drafting recommendations**:

In the complaint / advocacy brief, argue along the chain “personnel confusion → business confusion → financial confusion → loss of independent personality → serious harm to creditors’ interests → joint and several liability,” citing Guiding Case No. 15’s holding as core support.

#### 8.3 Limitations of This Retrieval

1. **Time limitation**: This retrieval mainly covers cases before 2024; the newest judgments after the 2023 Company Law revision may not be fully included, which may affect grasp of the latest trend.

2. **Geographic limitation**: Focus is on the Supreme People’s Court and provincial high courts; specific adjudicative rules of the court seized of the pending case (e.g., a basic court or a particular intermediate court) may not be fully covered.

3. **Factual differences**: Fine factual details of the pending case (degree of confusion, harm consequences) may differ slightly from retrieved cases; final findings depend on the court’s comprehensive judgment of the evidence on record.

4. **Legal updates**: After the 2023 Company Law revision, some older cases’ “application by reference” reasoning is outdated and must be re-understood alongside the new provisions.

---

**Retrieval date**: XX Month XX Day, 2024  
**Retriever**: XXX  
**Reviewer**: XXX
