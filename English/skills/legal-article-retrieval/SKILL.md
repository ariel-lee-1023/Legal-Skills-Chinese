---
name: legal-article-retrieval
description: Generate standardized legal research reports for case retrieval, statutory research, similar-case analysis, and related legal research scenarios. Use when the user needs industry or professional analysis, prediction of adjudication outcomes, verification of the validity of legal authorities, confirmation of legal bases for claims or defenses, or analysis of judicial practice tendencies. Supports litigation strategy assessment, trial preparation, compliance review, legal training, and other legal practice scenarios.
---

> **Chinese source (authoritative):** [`../../skills/legal-article-retrieval/SKILL.md`](../../skills/legal-article-retrieval/SKILL.md)

## Overall Retrieval Process Map

```
Preparation Stage → Thinking Stage → Execution Stage → Review Stage → Deliverable Stage
    ↓                    ↓                ↓               ↓                ↓
Clarify purpose    Hierarchy of     Systematic      Cross-validation   Report presentation
Tool configuration   sources         retrieval      Subsumption test    Conclusion formation
                   Legal relations   Keyword method Retrieval loop      Risk warnings
                   Claim-based       Case reverse-
                     thinking          lookup
                   Validity screening
                   Conflict handling
```


## Stage 1: Retrieval Preparation and Information Confirmation

### 1.1 Defining the Retrieval Purpose

Law is abstract. Statutory text may present unclear major-premise semantics or indeterminate word meaning and scope. In practice, parties often dispute the specific meaning of a provision. Therefore, before citing a legal rule, counsel should not only understand the provision’s literal meaning and logical structure, but also consider its application requirements and consult authoritative interpretations by relevant bodies.

**Typical retrieval scenarios**:
1. Determining the legal basis for litigation claims
2. Reviewing the law applied by the opposing party
3. Rechecking the law applied in an adjudication

> **[Case Study] Highway and Residential Area Distance Case**
> **Retrieval purpose**: Ascertain restrictive rules on how far a highway under construction must be kept from residential areas

### 1.2 Prerequisite Information Confirmation (Mandatory Process)

**Before entering legal retrieval, confirm that all of the following information has been obtained:**

| Information Category | Content That Must Be Confirmed |
| :--- | :----------------------------- |
| Dispute type | Labor dispute / contract dispute / tort liability / marriage & family / administrative, etc. |
| Party information | You (worker / consumer / plaintiff, etc.) vs. the other party (employer / seller / defendant, etc.) |
| Core facts | What happened? Time, place, conduct |
| Issues in dispute | What do you want? (compensation / rights protection / liability determination, etc.) |
| Geographic information | If local rules may apply, the province/city must be known |
| Legal relationship | The legal relationship between the user and the other party (e.g., employment contract / sales contract) |

**Questioning template**:

```
Please supplement the following information so I can accurately retrieve legal authorities:

1. [Dispute type] What kind of legal issue are you facing?
   - Labor dispute (overtime pay, resignation, work injury, etc.)
   - Contract dispute (sale, lease, loan, etc.)
   - Tort liability (traffic accident, personal injury, etc.)
   - Marriage & family (divorce, inheritance, property, etc.)
   - Other (please specify)

2. [Party information] What is your status?
   - Worker / consumer / citizen / enterprise, etc.

3. [Core facts] Briefly describe what happened (time, course of events, relief sought)

4. [Geography] Does a specific locality apply? (e.g., Beijing, Shanghai, Guangzhou, Shenzhen, or other places with special rules)

5. [Legal relationship] Have you and the other party signed a contract? (e.g., employment contract / service contract)
```

**[Strictly Prohibited]**
- Do not call any legal retrieval tool before the user has confirmed the facts
- Do not perform inferential legal analysis based on assumptions
- Do not include legal conclusions in the fact summary

**Process requirements**:
1. Output a “Fact Summary” covering: parties (you vs. the other party), timeline (what happened), conduct (specific acts), issues in dispute (what you want), geography (localities involved)
2. Explicitly ask for confirmation: “Are the above facts accurate? Please state any supplements or corrections.”
3. Enter the legal retrieval stage only after the user confirms

> **[Case Study] Highway and Residential Area Distance Case**
> - **Parties**: Highway construction entity vs. owners of adjacent residential properties
> - **Core facts**: Highway construction is too close to the residential area; owners claim their rights and interests are harmed
> - **Issue in dispute**: Whether law clearly restricts the distance between a highway and residential areas
> - **Geography**: Consider national laws and local rules (e.g., Guangdong Province Highway Regulations)

---

## Stage 2: Retrieval Tool Configuration and Database Selection

Classified by types of sources of law:

| Type | Sources | Effect | Application Requirements |
| :----- | :----- | :------- | :--------- |
| Formal sources | Constitution, statutes (laws), administrative regulations, local regulations, departmental rules, international treaties | Have expressly provided legal effect; must be considered | May be used directly as adjudicative authority |
| Informal sources | Custom, policy, Guiding Cases, legal theory, moral principles | Lack express legal force, but have legal persuasive force; may be considered | Assist application of formal sources or fill gaps |


### 2.1 Baseline Databases (Primary Legal Resources)

**Definition**: Normative legal resources, mainly laws, administrative regulations, legal interpretations, and similar instruments enacted by state legislative bodies and government. In common-law jurisdictions these also include judicial precedents and decisions. Such resources have legal effect and are normative.

**Characteristics**:
1. Mandatory and normative
2. Different levels of hierarchical effect
3. Legal documents have temporal validity
4. Large volume of legal literature
5. Accessed and used through particular methods

**Commonly used baseline databases**:
- PKULaw (北大法宝) (including English version)
- Lawyee (北大法意)
- Angle Knowledge Base (月旦知识库)
- Westlaw China (万律网)
- WestlawNext
- Lexis Advance
- HeinOnline
- Max Planck Encyclopedia of Public International Law
- Kluwer Law Online
- Beck-online (German)
- China Judgments Online (中国裁判文书网)

> **[Case Study] Highway and Residential Area Distance Case**
> **Retrieval tools**: PKULaw (北大法宝), China Judgments Online

### 2.2 Auxiliary Databases (Secondary Legal Resources)

**Definition**: Non-normative legal resources—all literature and information that interprets, researches, discusses, or comments on law, such as law review articles, monographs, textbooks, and explanations or commentaries on statutes and cases. Such resources do not have legal force.

**Characteristics**:
- Multiple publication types, large volume, widely used
- Retrieved by literature type (books, journals, theses, etc.)
- Includes self-media, WeChat official accounts, and other new-media resources

**Types of auxiliary resources**:
- **Secondary materials**: Textbooks, practice guides, monographs, WeChat official accounts, Wolters Kluwer China professional commentary, firm work product, government websites, case analyses, academic articles, online discussion, legislative developments, etc.
- **Global search**: Search engines (Google, Baidu, Sogou WeChat) to retrieve articles for background
- **AI assistance**: AI for fuzzy retrieval and preliminary analysis, **but results may be used only after verification against baseline databases**

**Important note**: Titles of laws and regulations, category, issuing authority, issuance date, effective date, and validity status are of particular importance.

### 2.3 Proprietary Databases

- The user’s local databases
- The law firm’s accumulated case-handling experience

---

## Stage 3: Retrieval Thinking and Methodological Framework

### 3.1 Hierarchy-of-Sources Retrieval

**Retrieval order**: Constitution → statutes (laws) → administrative regulations → local regulations → departmental rules → judicial interpretations

**Contemporary Chinese system of sources of law**:

| Rank | Enacting Body | Characteristics | Examples |
|------|---------|------|------|
| **Constitution** | National People’s Congress (NPC) | Fundamental law; supreme effect | Constitution of the People’s Republic of China |
| **Statutes (laws)** | NPC and its Standing Committee | Effect second only to the Constitution | Civil Code; Labor Law |
| **Administrative regulations** | State Council | Effect below statutes | Regulations on the Implementation of the Labor Contract Law |
| **Local regulations** | People’s congresses and standing committees of provinces / cities divided into districts | Apply within the administrative region | Guangdong Province Highway Regulations |
| **Departmental rules** | Ministries and commissions under the State Council | Specific fields of administrative management | Interim Provisions on Wage Payment |
| **Judicial interpretations** | Supreme People’s Court (SPC) / Supreme People’s Procuratorate (SPP) | Have legal effect | Fa Shi 〔2020〕 No. 17 |

**Hierarchy-of-effect rules** (as provided in the Legislation Law):
- The Constitution has the highest legal effect
- Statutes have higher effect than administrative regulations, local regulations, and rules
- Administrative regulations have higher effect than local regulations and rules
- Local regulations have higher effect than local government rules at the same level and below
- Rules of provincial/autonomous-region governments have higher effect than rules of governments of cities divided into districts and autonomous prefectures within that administrative region

**Application rules**:
- Normative documents enacted by the same body: where a special provision conflicts with a general provision, apply the special provision; where a new provision conflicts with an old provision, apply the new provision
- Conflict adjudication procedures: conflicts between statutes are decided by the NPC Standing Committee; conflicts between administrative regulations by the State Council; conflicts between departmental rules and local government rules by the State Council

**Operational points**:
- Record invalid retrieval paths (to understand legislative gaps)
- Excerpt effective provisions and keep the original text intact
- Identify the relationship between jurisdiction and the rank of the issuing body
- Flag documents from bodies without authority (e.g., internal meeting minutes cannot be used directly as adjudicative authority)

> **[Case Study] Highway and Residential Area Distance Case**
> **Hierarchy-of-sources retrieval process**:
> - **Invalid retrieval** (record the path): Road Traffic Safety Law; Regulations on the Implementation of the Road Traffic Safety Law; Detailed Rules for the Implementation of the Measures for Completion (Handover) Acceptance of Highway Engineering Projects (no specific distance rules)
> - **Valid retrieval**:
>   - **Statutes**: General Principles of the Civil Law Art. 83 (neighboring relations), Art. 106 (tort liability); Property Law Art. 91 (safety of immovable property)
>   - **Administrative regulations**: Regulations on Highway Safety Protection Art. 11 (highway building control zone of no less than 30 meters), Arts. 13 and 28
>   - **Local regulations**: Guangdong Province Highway Regulations Arts. 5 and 9 (highway and building clusters no less than 200 meters)
>   - **Other normative documents**: Technical Standard of Highway Engineering Art. 3.0.1

### 3.2 Legal-Relationship Thinking

**Core logic**: Examine legal relationships in the chronological order in which case facts arose; treat legal relationships as the focus of examination; determination of legal facts and legal relationships precedes the search for norms.

| Logical Dimension | Updated Content |
| :------- | :--------------------------------------------------- |
| **Temporal logic** | Refined into the full life cycle of legal relationship: formation → validity → performance → change |
| **Subject logic** | Subject types; capacity for rights / capacity for acts; distinction between absolute and relative legal relationships; structure of rights and obligations (dominion rights / claim rights / defenses / formative rights) |
| **System logic** | **General Provisions–Specific Provisions–Exceptions structure**; clarify the application order “specific provisions before general provisions”; examine principle–exception–proviso layers |


**Retrieval process**

| Step | Description | Logical Dimension |
| :--------- | :------------------ | :--- |
| 1. Determine the legal relationship | Labor / contract / tort / neighboring relations | Subject logic |
| 2. Determine the type of right | Dominion / claim / defense / formative right | Content logic |
| 3. Determine the governing law | Special provisions → specific-part provisions → general-part provisions | System logic |
| 4. Break down constitutive elements | Subject, object, content, liability | Structural logic |
| 5. Compare elements item by item | Fact subsumption | Temporal logic |
| 6. Examine defenses and exceptions | Grounds that defeat liability | Exception logic |
| 7. Hierarchical retrieval | Higher rank → lower rank | Hierarchy logic |
| 8. Case verification | Guiding Cases | Practice logic |
* Retrieval content

| Knowledge of Civil Legal Relationships | Reflection in Retrieval Thinking |
| :-------------------- | :-------------------- |
| **General Provisions subject system** | Subject-qualification review (capacity for rights, capacity for acts) |
| **Distinction between absolute and relative rights** | Different retrieval paths for absolute vs. relative legal relationships |
| **Classification of rights (dominion / claim / defense / formative)** | Methods for breaking down constitutive elements by right type |
| **Legislative technique combining general and specific parts** | Retrieval order “specific provisions before general provisions” |
| **Principles and exceptions** | Priority examination of proviso clauses |
| **Correspondence of rights and obligations** | Bidirectional retrieval: one party’s right → the other party’s obligation |

> **[Case Study] Highway and Residential Area Distance Case**
> **Characterization of the legal relationship**: Neighboring-relations dispute + tort-liability dispute
> - Subject qualification: Highway construction entity (holder of rights in immovable property) vs. neighboring residents (holders of rights in adjacent immovable property)
> - Rights and obligations: The construction entity must not endanger the safety of adjacent immovable property; residents enjoy neighboring-rights protection
> - Applicable law: Neighboring-relations rules in the General Principles of the Civil Law; Property Law Art. 91; Tort Liability Law
>
1. Application relationship between General Provisions and Specific Provisions

| Application Layer | Retrieval Order | Functional Role | Application in the Highway Case |
| :------- | :--- | :--- | :------------------ |
| **Special provisions** | Retrieve first | Specialized rules | Regulations on Highway Safety Protection Art. 11 (30 meters) |
| **Specific-part provisions** | Retrieve next | General rules | Civil Code, Book on Real Rights, Chapter 7 (neighboring relations) |
| **General-part provisions** | Supplementary retrieval | Catch-all application | Civil Code Art. 8 (public order and good morals) |

Principle–exception structure analysis

```plain
30-meter rule (mandatory norm; floor)
    └── 200-meter rule (planning norm; ceiling)
            └── Proviso: “determined according to requirements such as safe sight distance”
```

**System-logic conclusion**:

- <30 meters: Directly unlawful
- 30–200 meters: Need further examination of whether safety is “endangered”
- ≥200 meters: Conforms to planning; generally not a tort    
Structure of rights and obligations content
```plain
Rights system
├── Dominion rights (real rights, personality rights) → absolute rights → erga omnes
├── Claim rights (obligatory rights) → relative rights → inter partes
├── Defenses (against claim rights)
└── Formative rights (unilaterally change a legal relationship)

Obligations system
├── Duties to act (affirmative conduct)
└── Duties to forbear (non-infringement)
```
### 3.3 Claim-Based Thinking Retrieval

**Core logic**: Start from the claim basis; examine whether the plaintiff’s litigation claims can be established; the search for norms precedes determination of legal facts.

#### 1. Retrieval order

1. Whether the claim has already arisen
2. Whether the claim has not been extinguished
3. Whether the claim may be exercised

```
Tier 1: Contractual claims (priority of private autonomy)
    └── Detailed reasons table for priority over negotiorum gestio, real rights, tort, and unjust enrichment
    
Tier 2: Claims from unilateral juristic acts (bequests, reward advertisements)

Tier 3: Quasi-contractual claims (culpa in contrahendo, unauthorized agency)
    └── Priority reason: related to contracting; good-faith duties higher than in ordinary relations

Tier 4: Claims under status law (maintenance, child support, parental support)

Tier 5: Negotiorum gestio claims (lawful justification)
    └── Justifying character + alignment with Core Socialist Values (avoid the adverse effects of the “Peng Yu case”)

Tier 6: Real-rights claims (priority of real-rights protection)
    └── Three reasons for priority over obligatory rights (priority of effect, no limitation period, no fault required)
    └── Four-type table (return of the original thing, elimination of obstruction, elimination of danger, restoration to original condition)

Tier 7: Possession-protection claims (protection of factual status)
    └── Four types + 1-year preclusive period (除斥期间)

Tier 8: Unjust enrichment claims (correction of benefit shifts)
    └── Reason for priority over tort (fault not required)

Tier 9: Tort claims (catch-all protection)
    └── Four types (general, presumed fault, no-fault, joint)
    └── Reason for placing last (not a premise for other claims)
```

#### 2. Concurrence and choice of claims (highway case)

| Claim Basis | Application Conditions | Advantages | Disadvantages | Recommendation |
| ----------------- | --------- | ---------- | ------- | -------- |
| **Real-rights claim** (Art. 236) | Obstruction or possible obstruction of a real right | No fault required; limitation periods do not apply | Does not support damages | **Assert first** |
| **Tort claim** (Art. 1165) | Fault-based tort | Supports damages | Must prove fault | **Assert in parallel** |

**Litigation strategy**:
- Assert real-rights claim + tort claim together (aggregation of claims)
- First seek elimination of obstruction and elimination of danger
- Concurrently seek damages

#### 3. Three-layer structure for examining claims

```
Has the claim arisen?
    ├── Tatbestand (符合构成要件 / fits the constitutive elements)
    ├── Unlawfulness (whether justifying grounds exist)
    └── Culpability (whether fault exists)
        ↓
Has the claim not been extinguished?
    ├── Performance, deposit, set-off, release, merger
    ├── Expiry of the limitation period
    └── Right-holder’s waiver
        ↓
May the claim be exercised?
    ├── Do defenses exist?
    └── Are there other obstacles to exercise?
```

#### 4. Supplementary doctrinal explanations

| Block | Content |
| -------- | ----------------------------------------------------- |
| **Legislative purpose** | Contract (private autonomy); real rights (protect dominion status); tort (make good loss); unjust enrichment (correct imbalance) |
| **Scholarly views** | Medicus (economy of thought); Wang Zejian (claim basis as cornerstone of civil-law thinking); Wang Liming (legal methodology); Zhu Qingyu (validity system of juristic acts) |
| **Methods of interpretation** | Textual, systematic, purposive, historical, comparative |


>5. Case: Nine-tier examination table for the highway case

| Order | Claim Type | Examination Conclusion | Reason |
| --- | --------- | -------- | ------------ |
| 1 | Contractual claim | ❌ Not established | No contractual relationship |
| 2 | Unilateral act | ❌ Not established | No bequest or reward advertisement |
| 3 | Quasi-contract | ❌ Not established | No culpa in contrahendo |
| 4 | Status law | ❌ Not established | Not a status relationship |
| 5 | Negotiorum gestio | ❌ Not established | Construction entity managing its own affairs |
| 6 | **Real-rights claim** | ✅ **Established** | May seek elimination of obstruction and elimination of danger |
| 7 | Possession protection | △ May be established | But real-rights claim is preferable |
| 8 | Unjust enrichment | ❌ Not established | Has legal basis (approvals) |
| 9 | **Tort claim** | ✅ **Established** | May seek damages |

### 3.4 Screening the Validity of Statutory Provisions

Operational process

| Step | Review Content | Checking Method |
| ------------- | ------------------------------------------ | -------------------- |
| **Step 1: Formal review** | Authenticity / accuracy | Cross-verify in two or more authoritative databases |
| **Step 2: Substantive review** | Validity (repealed, amended, pending effectiveness) | Query validity status; judge the nature of the document |
| **Step 3: Applicability review** | Subject-matter effect (personal + spatial) | Judge party status, geographic scope, nature of conduct |
| **Step 4: Temporal review** | Temporal effect (effectiveness, termination, retroactivity). Substantive law does not apply retroactively; substantive judicial interpretations have practical retroactive effect; procedural law applies immediately | Build a case timeline; note first-/second-/retrial application scope |
| **Step 5: Hierarchical review** | Level of effect | Check enacting body; judge conflict; resolve conflicts |


 Theoretical framework of legal effect

| Type of Effect | Core Question | Integration Points |
| --------- | ------ | ------------------------------ |
| **Personal effect** | To whom does the law apply? | Point 3: subject-matter effect (personality / territoriality / protective / hybrid principles) |
| **Spatial effect** | Where does the law apply? | Point 3: subject-matter effect (central legislation / local legislation; extraterritorial effect) |
| **Temporal effect** | When does the law apply? | Point 4: temporal effect (effectiveness, termination, retroactivity) |
| **Level of effect** | Hierarchical relations among norms | Point 5: level of effect (higher-level law > lower-level law) |



#### 3.4.1 Personal Effect: Four Principles

| Knowledge Point | Application Scenario | Operational Steps | Judgment Standard | Common Errors | Case Example |
|--------|---------|---------|---------|---------|---------|
| **Personality principle** | Chinese citizens engaging in legal acts abroad | 5 steps: confirm nationality → confirm place of act → retrieve Chinese law → retrieve lex loci actus → compare conflict rules | Criminal Law Art. 7 | Mistakenly thinking “acts abroad are not subject to Chinese law” | Chinese citizen investing in and building a highway abroad |
| **Territoriality principle** | Foreigners engaging in legal acts within China | 4 steps: confirm place of act → confirm “within the territory” extensions → retrieve Chinese law → judge exceptions | Civil Code Art. 12 | Ignoring “territorial extensions” such as embassies/consulates and vessels | Foreign construction entity building a highway within China |
| **Protective principle** | Acts abroad harming Chinese national or citizen interests | 5 steps: confirm act abroad → confirm harm → retrieve jurisdictional rules → judge “minimum sentence” → retrieve lex loci actus | Criminal Law Art. 8 | Ignoring the “minimum sentence of three years or more” limit | Foreigner building a road abroad causing death or injury to Chinese citizens |
| **Hybrid principle** | Ordinary foreign-related civil cases | 5 steps: judge territoriality → personality → protection → retrieve treaties → retrieve conflict rules | Generally adopted in China | Applying only one principle | Comprehensive judgment of a foreign-related highway contract dispute |

**Operational flowchart**:
```
Does the case involve foreign-related elements?
    ├── Yes → Judge the type of connecting factor
    │           ├── Act/result within Chinese territory? → Territoriality first
    │           ├── Is one party a Chinese citizen? → Personality as supplement
    │           └── Harm to major Chinese national or citizen interests? → Protection as supplement
    └── No → Apply territoriality directly
```

#### 3.4.2 Spatial Effect of Law: Concrete Application of Levels and Scope

| Knowledge Point | Application Scenario | Operational Steps | Judgment Standard | Common Errors | Case Example |
| ------------- | -------------- | --------------------------------------- | ------------ | ---------- | ---------------- |
| **Levels of spatial effect** | Determine retrieval scope (nationwide or local) | 5 steps: confirm case locality → confirm enacting body → retrieve central legislation → retrieve local legislation → judge conflict | Legislation Law Art. 81 | Citing local regulations across regions | Retrieve Guangdong rules; do not retrieve Shanghai rules |
| **Extraterritorial effect** | Cross-border investment; overseas acts affecting China | 5 steps: confirm act abroad → confirm domestic impact → retrieve extraterritorial application rules → retrieve treaties → judge conditions | Criminal Law Art. 6(3) | Ignoring the “effects principle” | Overseas road construction pollution affecting China |
| **Territorial extension** | Cases on embassies/consulates, vessels, aircraft | 4 steps: confirm place → confirm “territorial extension” → retrieve legal rules → judge jurisdiction | Criminal Law Art. 6(2) | Ignoring territorial-extension rules | Construction-contract dispute on a Chinese-flagged vessel |
| **Autonomy regulations and separate regulations** | Cases in ethnic autonomous areas | 5 steps: confirm autonomous locality → retrieve regulations → confirm adaptations → confirm authority → confirm approval documents | Legislation Law Art. 90 | Failing to verify whether adaptations were approved | Autonomous prefecture adaptation of highway construction compensation standards |
| **Special economic zone (SEZ) regulations** | Cases within SEZs | 5 steps: confirm within SEZ → retrieve SEZ regulations → confirm authorization → confirm adaptations → adjudicate if needed | Legislation Law Art. 95(2) | Failing to verify the authorizing decision | Shenzhen SEZ adaptations for highway management |

**Hierarchical retrieval flowchart**:
```
Determine where the case arose
    ↓
Layer 1: Retrieve central legislation (nationwide effect)
    ├── Constitution → statutes → administrative regulations → departmental rules
    ↓
Layer 2: Retrieve local legislation (effect within the administrative region)
    ├── Provincial local regulations → local regulations of cities divided into districts → provincial government rules → municipal government rules of cities divided into districts
    ↓
Layer 3: Retrieve special-region legislation (may adapt)
    ├── Autonomy regulations, separate regulations → SEZ regulations
    ↓
Layer 4: Judge conflicts and application
```

#### 3.4.3 Temporal Effect of Law: Effectiveness, Termination, Retroactivity

| Knowledge Point | Application Scenario | Operational Steps | Judgment Standard | Common Errors | Case Example |
| ------------ | ------------ | ---------------------------------------- | ----------- | ------------- | ------------------- |
| **Three forms of effective time** | Determine whether a law has taken effect | 4 steps: retrieve implementation date → judge form of effectiveness → build timeline → compare time of act | Legislation Law Art. 57 | Confusing “publication date” with “implementation date” | Civil Code implemented 1 Jan 2021 |
| **Express repeal** | Confirm whether old law was expressly repealed | 4 steps: retrieve repeal clause → retrieve repeal notice → check database labels → confirm temporal scope of repeal | Civil Code Art. 1260 | Citing repealed law | Marriage Law and Inheritance Law expressly repealed |
| **Implied repeal** | Confirm whether old law was impliedly repealed | 4 steps: compare old and new law → judge conflict → confirm old-law application after new law takes effect → retrieve judicial application | Legislation Law Art. 92 | Ignoring implied repeal | General Principles of the Civil Law impliedly repealed |
| **Non-retroactivity of law** | Application of new law to prior acts | 5 steps: confirm time of act → confirm law’s effective time → judge sequence → generally apply old law → retrieve special rules | Legislation Law Art. 93 | Applying new law wholesale to prior acts | Civil Code does not apply to acts before 2021 |
| **Favorable-retroactivity exception** | Criminal law: old law with lighter penalty if favorable | 4 steps: compare impact of old and new law → judge favorability → retrieve judicial interpretations → judge permissibility | Criminal Law Art. 12 | Wrongly applying in civil law | Criminal field: apply new law when it punishes more lightly |
| **Procedural “new law” principle** | Procedural law changes during litigation | 5 steps: confirm procedural stage → confirm procedural-law change → judge whether “ongoing” → retrieve application rules → judge application | Legislation Law Art. 93 proviso | Confusing substance and procedure | Second-instance procedure applies new Civil Procedure Law |
| **Substantive “old law” principle** | Law applicable to substantive rights and obligations | 4 steps: distinguish substance and procedure → confirm time of act → generally apply law at time of act → retrieve retroactivity rules | Legislation Law Art. 93 | Confusing substance and procedure | Contract-validity determination applies old substantive law |
| **Handling acts spanning time** | Conduct continuing across a legal change | 4 steps: confirm start/end times → confirm legal change → judge whether “continuing” → generally apply new law | General legal principle | Mechanically applying old-law principle | Highway construction spanning 2020–2021; apply new law |

**Temporal-effect operational flowchart**:
```
Build a case timeline
    ↓
Determine time of legal act vs. time law took effect
    ↓
Compare and judge
    ├── Act before law took effect → generally apply old law (non-retroactivity)
    │                               ├── Criminal law: retrieve “old law with lighter penalty if favorable”
    │                               ├── Civil law: favorable retroactivity generally not allowed
    │                               └── Procedural law: apply new law (procedure from the new)
    └── Act after law took effect → apply new law
            ↓
Judge whether the law has been repealed (express / implied)
            ↓
Judge whether it is a time-spanning act → generally apply new law (from-the-new principle)
```

#### 3.4.4 Level of Effect and Conflict Resolution

| Knowledge Point | Application Scenario | Operational Steps | Judgment Standard | Common Errors | Case Example |
| ---------------- | -------- | --------------------------------------- | --------------- | ---------- | ---------------------- |
| **Higher-level law prevails over lower-level law** | Conflict across ranks | 5 steps: determine enacting body → judge effect level → compare provisions → judge conflict → preferentially apply higher-level law | Legislation Law Arts. 87–89 | Wrongly applying lower-level law | Municipal rule 20 m conflicts with administrative regulation 30 m; apply 30 m |
| **Special law prevails over general law** | Conflict at the same rank | 5 steps: confirm same body → compare scope → judge special vs. general → same matter → special prevails | Legislation Law Art. 92 | Wrongly identifying “same body” | Regulations on Highway Safety Protection prevail over Highway Law |
| **New law prevails over old law** | Conflict at the same rank | 4 steps: confirm same body → compare implementation dates → judge new vs. old → new prevails (only for acts after new law takes effect) | Legislation Law Art. 92 | Applying to prior acts | 2021 revised Guangdong Province Highway Regulations prevail |
| **New general law vs. old special law** | Cross conflict at the same rank | 4 steps: confirm same body → judge new general vs. old special → if uncertain → request enacting body to decide | Legislation Law Art. 94 | Unilaterally choosing which to apply | Statutes decided by NPC Standing Committee |
| **Local regulations vs. departmental rules** | Cross conflict across ranks | 4 steps: confirm conflicting parties → State Council gives opinion → apply local regulations or request NPC Standing Committee decision | Legislation Law Art. 95(1)(2) | Directly applying departmental rules | Not involved in this case |
| **Departmental rules vs. local government rules** | Conflict at the same rank | 3 steps: confirm conflicting parties → equal effect → State Council decides | Legislation Law Art. 95(1)(3) | Unilaterally choosing which to apply | Not involved in this case |
| **Autonomy / separate regulation adaptations** | Cases in ethnic autonomous areas | 6 steps: confirm autonomous locality → retrieve regulations → confirm adaptations → confirm authority → confirm approval → preferential application | Legislation Law Art. 90 | Failing to verify approval documents | Autonomous prefecture adaptation of highway construction compensation standards |
| **SEZ regulation adaptations** | SEZ cases | 5 steps: confirm within SEZ → retrieve SEZ regulations → confirm authorization → confirm adaptations → preferential application within the SEZ | Legislation Law Art. 95(2) | Failing to verify authorizing decision | Shenzhen SEZ highway management rules |

**Conflict-resolution decision flowchart**:
```
Discover conflict between provisions
    ↓
Judge whether enacted by the same body
    ├── Yes (same rank) → Judge conflict type
    │                       ├── Special vs. general → apply special law
    │                       ├── New vs. old → apply new law (only for acts after new law takes effect)
    │                       └── New general vs. old special → request enacting body to decide
    └── No (different ranks) → Judge level of effect
                            ├── Lower conflicts with higher → apply higher-level law
                            ├── Local regulations vs. departmental rules → State Council opinion → decision
                            ├── Departmental rules vs. local government rules → State Council decides
                            ├── Autonomy / separate regulation adaptations → preferential within authority
                            └── SEZ regulation adaptations → preferential within the SEZ
```


General principles for resolving legal conflicts

| Rank Relationship | Principle | Content |
| -------- | -------- | ------------------- |
| **Different ranks** | Higher-level law prevails over lower-level law | Constitution > statutes > administrative regulations > local regulations > rules |
| **Same rank** | Special law prevails over general law | On the same matter, special provisions prevail |
| **Same rank** | New law prevails over old law | On the same matter, new provisions prevail |

Special situations in resolving legal conflicts

| Conflict Situation | Resolution Rule | Decision Body |
| ---------------- | ------------------------------ | ------------------- |
| New general law vs. old special law | Decided by the enacting body | Statutes: NPC Standing Committee; administrative regulations: State Council |
| Local regulations vs. departmental rules | Three steps (State Council opinion → apply local regulations / request NPC Standing Committee decision) | State Council, NPC Standing Committee |
| Departmental rules vs. local government rules | Decided by the State Council | State Council |
| Autonomy / separate regulations vs. higher-level law | Adapted provisions prevail (within adaptation authority) | — |
| SEZ regulations vs. higher-level law | Authorized legislation; decided by NPC Standing Committee | NPC Standing Committee |

**When conflict cannot be resolved**: Refer to the purpose of the norms and existing precedents; use dialectical reasoning (substantive reasoning) to resolve hard problems caused by the complexity of legal provisions.

**Situations for dialectical reasoning**:
- Certain legal provisions clearly lag behind social development
- Provisions at the same rank conflict with each other
- Hard problems arise from the complexity of legal provisions
- Two legal propositions serving as premises of legal reasoning contradict each other
**Special conflict-resolution situations**:

>**Highway case: hierarchy-of-effect conflict check**:
>


| Conflict Situation | Analysis | Conclusion |
| -------------------------------- | ---------------------------------------------- | --------------------------- |
| Regulations on Highway Safety Protection (30 m) vs. Guangdong Province Highway Regulations (200 m) | Not a true conflict: 30 m is a prohibitory floor (building control zone); 200 m is a planning ceiling (planning spacing); different application scenarios | **Apply in parallel**: 30 m as minimum standard; 200 m as aspirational/planning standard |
| Civil Code Art. 295 vs. General Principles of the Civil Law Art. 83 | New law prevails over old law: Civil Code has repealed the General Principles of the Civil Law | Cases after 2021 apply the Civil Code |




>Validity-check table (highway case)

| Provision | Authenticity | Validity | Subject-Matter Effect | Temporal Effect | Level of Effect | Overall Judgment |
| -------------- | --- | ------ | ------------ | ----------- | ----------- | ------------- |
| Civil Code Art. 295 | ✓ | ✓ Currently in force | ✓ Applies to neighboring relations of immovable property | ✓ Applies after 2021 | Statute (second tier) | **Citable** |
| General Principles of the Civil Law Art. 83 | ✓ | ✗ Repealed | — | Applies before 2021 | Statute (repealed) | **Citable for pre-2021 cases** |
| Regulations on Highway Safety Protection Art. 11 | ✓ | ✓ Currently in force | ✓ Applies to highway building control zones | ✓ Applies after 2011 | Administrative regulation (third tier) | **Citable** |
| Guangdong Province Highway Regulations Art. 5 | ✓ | ✓ Currently in force | ✓ Applies within Guangdong Province | ✓ Applies after 2021 | Local regulation (fourth tier) | **Citable within Guangdong** |
| Shanghai Municipality Highway Regulations | ✓ | ✓ Currently in force | ✗ Geographic mismatch (Shanghai) | — | Local regulation | **Not citable** |
| Meeting minutes of a municipal transport bureau | ✗ | ✗ Internal document | ✗ Cannot serve as adjudicative authority | — | Non-legal document | **Not citable** |



---

## Stage 4: Retrieval Execution Methods and Techniques

### 4.0 Data-Source and Tool-Call Convention (Mandatory)

> **Core principle: Every statutory provision cited under this skill must come from real retrieval. Fabricating article numbers or content from memory is strictly forbidden.**

Before executing the retrieval methods below, first determine whether a **regulation-retrieval tool** exists in the runtime environment (e.g., a connected regulation-library MCP service, retrieval API, or local regulation library):

1. **If it exists**: The designed search queries must be submitted to that tool; its returned real results (law name, document number, effect level, effective/expiry dates, provision text, source link) are the sole data source for subsequent subsumption, citation, and reporting. Do not substitute or supplement retrieval results with “provisions” from memory.
2. **If it does not exist**: Complete search-query design and methodological steps as usual, but mark every place involving a concrete provision as `[待查]` (to be verified), and state in the report that “no regulation library is connected; the following queries must be executed manually.” **Never fabricate article numbers, content, or document numbers.**
3. **Tool-agnostic**: This convention depends only on the abstract capability “input search terms → return real statutory text,” and is not tied to any particular vendor. For concrete integration methods (e.g., PKULaw MCP), see [`README.md`](./README.md) in this skill’s directory.

### 4.1 Systematic Retrieval Method (Top-Down)

**Core idea**: Provisions at higher levels of the legal hierarchy are usually highly general, while more detailed rules often appear in related judicial interpretations. When understanding a judicial-interpretation provision, consult the “Understanding and Application” materials organized by the Supreme People’s Court for that interpretation, or the press release and press conference Q&A issued by the SPC or its relevant departments when the interpretation was released.

**Operational steps**:
1. **Start from the legal system / structure of provisions**: First review the principled rules of the basic law (e.g., before looking up Marriage Law judicial interpretations, first look at the Marriage Law itself)
2. **Use automatic indexing**: Professional databases automatically index under each provision other laws, judicial interpretations, judgments, etc., that cite it
3. **From general law to special law**: e.g., for real-estate research, first Property Law, then departmental laws such as Land Administration Law

**Sources that may serve as adjudicative authority**:
- NPC legislation, administrative regulations, judicial interpretations, local regulations
- Guiding Cases of the SPC and SPP (quasi-sources of law)

**Tips for identifying judicial interpretations**:
- Post-1997 judicial interpretations must carry a “Fa Shi” document number
- Pre-1997 judicial interpretations are determined by convention
- **Critical distinction**: “Ta” (他) series replies are only case-specific replies, not judicial interpretations; “Fa Shi” approvals are judicial interpretations
- **Verification sources**: Gazette of the Supreme People’s Court and Collection of Judicial Interpretations of the Supreme People’s Court (1949–2013)

**References for understanding provisions**:
- NPC legislation: consult NPC Legislative Affairs Commission statutory commentaries and corresponding SPC “understanding and application” books
- SPC judicial interpretations: consult corresponding SPC “understanding and application” books for those interpretations

**Principle–specific-part approach**: Use a general-to-special retrieval path

> **[Case Study] Highway and Residential Area Distance Case**
> **Systematic retrieval process**:
> 1. **General-law retrieval**: From General Principles of the Civil Law Art. 83 (general neighboring-relations rule) → Property Law Art. 91 (safety of immovable property)
> 2. **Special-law retrieval**: Highway Law → Regulations on Highway Safety Protection (specialized administrative regulation)
> 3. **Local-rule retrieval**: Guangdong Province Highway Regulations (local special rule: 200-meter spacing)
> 4. **Technical-norm retrieval**: Technical Standard of Highway Engineering (industry standard)
> 5. **Discovery of related provisions**: Art. 11 of the Regulations on Highway Safety Protection and Art. 5 of the Guangdong Province Highway Regulations differ (30 m vs. 200 m); conflict analysis is required

### 4.2 Keyword Retrieval Method (Precise Targeting)

**Three-step method**:
1. **Reverse from purpose**: Derive keywords from the retrieval purpose
2. **Add/remove keywords** (delete noise): Process core keywords
3. **Keyword association**: After establishing core keywords, radiate related dimensions

**Methods for discovering keywords**:
1. **Start from Chinese text**: Synonyms, near-synonyms, antonyms (e.g., “spouse” instead of “wife/husband/hubby/wifey”)
2. **Derive from legal doctrine**: Unauthorized disposition → bona fide acquisition; unauthorized agency → apparent agency
3. **Discover from wording of related provisions**
4. **Discover from the prose of judgments**
5. **Start from industry customary terms**
6. **Extract overlapping characters/words**: e.g., “contract invalid,” “contract valid,” “contract loses effect” → extract “contract effect”
7. **Search logic symbols**: space (AND), - (exclude), or (OR)

**Expansion techniques**:
- Base keywords (core elements)
- Expanded keywords (synonyms / higher-order terms)
- Exclusion keywords (reduce noise)

**Adjusting retrieval aperture**:
- **Narrow aperture**: Lengthen keywords (agency → unauthorized agency); add more keywords (disposition → disposition*invalid); add more retrieval fields (limit issuing body to SPC)
- **Widen aperture**: Use fewer words; use wildcards; add synonyms joined by OR

**Principles for setting keywords**:
1. Fuzzy first, then precise
2. Procedure first, then substance
3. Time first, then focus

**Building search queries**:
- Search query = retrieval path + search term + operators + search term
- Classification search, subject search, author search, title search, number search

**Logical operators (Boolean operators)**:
- Logical AND (AND/*): Narrow scope; raise precision
- Logical OR (OR/+): Widen scope; raise recall
- Logical NOT (NOT/-): Exclude specific terms

**Wildcards (truncation symbols)**:
- * (asterisk): Stands for one or more characters
- ? (question mark): Stands for one character

> **[Case Study] Highway and Residential Area Distance Case**
> **Keyword retrieval process**:
> - **Round 1**: “highway, meters” (too broad)
> - **Round 2**: “highway, construction” (still broad)
> - **Round 3**: “highway, land acquisition / expropriation / requisition / demolition” (expand synonyms)
> - **Optimization strategy**: Discover related terms such as “building control zone,” “safety distance,” “spacing”
> - **Geographic association**: Add “Guangdong Province,” “Highway Regulations” to limit local rules

### 4.3 Case Reverse-Lookup Method (Backward Derivation)

**Applicable scenarios**: Unfamiliar fields, or when statutory provisions cannot be precisely located

**Theoretical basis**: The major premise of a case usually cycles repeatedly between facts and law, between the individual case and similar cases, and between general and special situations. Individual cases do not arise according to the design scenarios of legal provisions; for constitutive elements, one must not only understand, interpret, and inwardly confirm them, but also “trim” the elements needed as premises of inference.

**Operational process**:
1. Retrieve cases with “case fact” keywords (subject, conduct, result)
2. Locate the structure of the judgment:
   - “Having ascertained through trial” (facts)
   - “This Court holds” (reasoning)
   - “In sum, pursuant to” (statutory provisions)
3. Reverse-derive applicable provisions; extract issues and rules

**Retrieval-loop mechanism**:
Where no more applicable norm exists, and for objective reasons relevant materials are truly lacking so the matter cannot be resolved from the fact side, further retrieve other materials (e.g., targeted cases, legal theory) to interpret norms or fill gaps, while managing risk.

> **[Case Study] Highway and Residential Area Distance Case**
> **Discoveries from case reverse-lookup**:
> - Retrieve similar neighboring-relations disputes via China Judgments Online
> - Claim bases found in similar-case judgments:
>   - Cases ⑧ and ⑩ cite General Principles of the Civil Law Art. 106 (fault-based tort liability)
>   - Case ⑨ cites General Principles of the Civil Law Art. 117 (property damage compensation) + Tort Liability Law Art. 85
> - Damages calculation rule: Use house value as the base; discretionary reduction for plaintiff’s fault or natural depreciation

---


# Stage 5: Retrieval Review and Quality Evaluation System

## 5.1 Retrieval Quality Evaluation Indicators


### 5.1.1 Core Indicator Definitions

| Indicator | Formula | Meaning in Legal Retrieval | Quality-Control Target |
| ------------------- | --------------------------- | -------------- | ---------------- |
| **Recall** | Relevant documents retrieved / total relevant documents in the collection × 100% | Were important statutes or cases missed? | ≥85% (no critical norms omitted) |
| **Precision** | Relevant documents retrieved / total documents retrieved × 100% | How accurate are the results? How much noise? | ≥70% (most results usable directly) |

## 5.2 Retrieval Review Mechanisms

### Layer 1: Recall Assurance—Cross-Validation (Prevent Omissions)

**Necessity**: A single retrieval may produce biased conclusions; multi-dimensional verification is needed to ensure recall

Validation 1: Comparison across databases (core recall assurance)

**Operational process**:

| Step | Operation | Recall Assessment | If Below Target |
|------|------|-----------|-----------|
| 1 | Run the same query in PKULaw and China Judgments Online separately | Compare differences in result counts | If difference >20%, analyze causes |
| 2 | Identify exclusive documents | Check whether critical cases were missed | Supplement retrieval in the missing database |
| 3 | Cross-compare results | Calculate overlap rate | If overlap <50%, expand retrieval |

> **[Case Study] Highway and Residential Area Distance Case**
> 
> **Initial search (PKULaw)**:
> - Keywords: “highway neighboring relations”
> - Results: 15 cases
> - **Recall assessment**: Found Regulations on Highway Safety Protection Art. 11 ✓
> 
> **Cross-validation (China Judgments Online)**:
> - Same keywords
> - Results: 22 cases (7 more)
> - **Difference analysis**: Among the extra cases, 2 are critical similar cases (on compensation standards for building control zones)
> - **Recall problem**: Initial search missed important similar cases; recall insufficient
> - **Remedial measures**: Supplement exclusive China Judgments Online cases; expand keywords with “building control zone”

Validation 2: Validation by different methods

**Method combinations**:

| Method Combination | Role for Recall | Validation Standard |
|----------|-----------|----------|
| Systematic retrieval + keyword retrieval | Systematic retrieval completes the legal system; keyword retrieval targets precisely | Overlap of results from the two methods should be >60% |
| Statutory retrieval + case reverse-lookup | Statutory retrieval ensures normative coverage; case reverse-lookup discovers practice rules | Provisions found by reverse-lookup should already be covered in systematic retrieval |
| Higher-level-law retrieval + lower-level-law retrieval | Higher-level law sets the framework; lower-level law supplies detail | Quantity of lower-level law should match ordinary proportions (e.g., local regulations ≥3) |

> **[Case Study] Highway and Residential Area Distance Case**
> 
> **Systematic retrieval results**:
> - Found General Principles of the Civil Law Art. 83 (neighboring relations), Property Law Art. 91 (safety of immovable property)
> - **Recall assessment**: Civil-law norms fully covered ✓
> 
> **Keyword retrieval validation**:
> - Keywords: “highway distance compensation”
> - Found Regulations on Highway Safety Protection Art. 13 (compensation rules)
> - **Recall assessment**: Administrative regulations fully covered ✓
> 
> **Case reverse-lookup validation**:
> - Through similar cases, found Guangdong Province Highway Regulations Art. 5 (200-meter spacing)
> - **Recall assessment**: Local rules previously omitted; recall insufficient ✗
> - **Remedial measures**: Add geographic limiters; retrieve similar rules in other provinces

Validation 3: Timeliness review

**Review content**:

| Check Item | Significance for Recall | Operational Standard |
|--------|-----------|----------|
| Were the latest amendments retrieved? | Avoid missing new law | Check new rules within 3 months before the retrieval date |
| Were repealed old laws retrieved? | Understand historical evolution | Old law may contain critical interpretations or transitional clauses |
| Were soon-to-be-effective rules retrieved? | Anticipate legal change | Watch regulations “published but not yet implemented” |

---

### Layer 2: Precision Optimization—Subsumption Test (Prevent Misuse)

**Core task**: After the retrieval report is formed, “subsume” it into the practice case to test the precision of results (whether they accurately apply to this case).

#### Six Elements of the Subsumption Test (Item-by-Item Precision Assessment)

| Difference Factor | Precision Assessment Question | Effect on Precision | Optimization Measures |
| ----------------- | ------------------------ | ---------- | ------------ |
| **1. Differences in legal facts** | Are retrieved case facts substantially similar to this case? | Large factual difference → precision ↓ | Adjust keywords; add fact limiters |
| **2. Differences in legal application** | Do retrieved provisions apply to this case’s legal relationship? | Wrong application → precision ↓ | Re-characterize the legal relationship |
| **3. High/low effect hierarchy** | Do results contain conflicts between higher- and lower-level law? | Unresolved conflict → precision ↓ | Choose applicable norms per conflict rules |
| **4. Evolution of norms and adjudication** | Do retrieved cases reflect the latest judicial tendency? | Outdated cases → precision ↓ | Limit retrieval time to the last 3–5 years |
| **5. Geographic differences** | Do retrieved rules apply to this case’s locality? | Geographic mismatch → precision ↓ | Add or exclude geographic limiters |
| **6. Quantity** | Is the quantity of results appropriate? (Too many or too few both hurt precision) | Quantity imbalance → precision ↓ | Adjust retrieval aperture |

> **[Case Study] Highway and Residential Area Distance Case**
> 
> **Subsumption test process**:
> 
> | Test Element | Initial Result | Precision Assessment | Problem Found | After Optimization |
> |----------|----------|-----------|----------|--------|
> | Legal facts | Retrieved “highway construction” cases | △ | Mostly “land-acquisition compensation,” not “neighboring relations” | Add “neighboring relations” limiter; precision ↑ |
> | Legal application | Regulations on Highway Safety Protection Art. 11 | ✓ | Correct application | Keep |
> | Effect hierarchy | Found 30 m vs. 200 m conflict | ✗ | Conflict unresolved; precision ↓ | Analyze different application scenarios; precision ↑ |
> | Evolutionary status | Retrieved 2010 cases | △ | Some cases outdated | Limit to last 5 years; precision ↑ |
> | Geographic difference | Guangdong Province Highway Regulations | ✓ | Geography matches | Keep |
> | Quantity | Initial search 200 items | ✗ | Too many; hard to screen | Optimized to 15; precision ↑ |

#### Example Precision Calculation After Subsumption Testing

```
[Precision Comparison Before and After Subsumption Testing]

Initial results (200 items):
- Actually relevant (directly usable in the report): 60
- Actually irrelevant (to be excluded): 140
- Initial precision = 60/200 = 30% (too low; needs optimization)

After subsumption-test optimization (15 items):
- Actually relevant (directly usable in the report): 12
- Actually irrelevant (to be excluded): 3
- Optimized precision = 12/15 = 80% (meets target)

Precision-improvement strategies:
- Exclude repealed provisions (General Principles of the Civil Law-related clauses)
- Exclude irrelevant causes of action (ordinary traffic accidents)
- Exclude geographically mismatched rules (other provinces differing too much from Guangdong)
- Exclude outdated cases (compensation standards from 5+ years ago have changed)
```

---

### Layer 3: Quality Balance—Second-Retrieval Decision

**Trigger condition**: When recall and precision cannot both meet targets, start a second retrieval

Second-retrieval decision matrix

| Recall Status | Precision Status | Decision | Focus of Second Retrieval |
| -------- | -------- | ---- | ----------------- |
| Insufficient (<85%) | Good (≥70%) | Expand retrieval | Guided by “subsumption” purpose; supplement omitted norms |
| Good (≥85%) | Insufficient (<70%) | Narrow retrieval | Optimize keywords; exclude noise; raise precision |
| Insufficient (<85%) | Insufficient (<70%) | Re-retrieve | Fully adjust strategy; check database selection |
| Good (≥85%) | Good (≥70%) | Proceed to report | Retrieval complete; form final report |

 Three principles of second retrieval

1. **Make up for deficiencies of the first retrieval**
   - Insufficient recall: Add databases, expand keywords, widen time range
   - Insufficient precision: Add limiters, use logical NOT, screen by authority

2. **Oriented to the purpose of “subsumption”**
   - All second-retrieval improvements must center on “whether it applies to this case”
   - Avoid seeking recall for its own sake and introducing many norms that cannot be subsumed

3. **Follow the general retrieval process**
   - Second retrieval is not simple repetition, but a complete “retrieve → cross-compare → report” process
   - Record differences between the two retrievals; explain the optimization process in the report

> **[Case Study] Highway and Residential Area Distance Case—Complete Second-Retrieval Process**
> 
> **First-retrieval assessment**:
> - Recall: 75% (missed Guangdong Province Highway Regulations Art. 5’s 200-meter rule)
> - Precision: 40% (many traffic-accident cases mixed in)
> - **Decision**: Both recall and precision insufficient; second retrieval needed
> 
> **Second-retrieval optimization**:
> 
> | Optimization Dimension | First Retrieval | Second Retrieval | Improvement Effect |
> |----------|------------|------------|----------|
> | Databases | PKULaw only | Add China Judgments Online, local government websites | Found local regulations; recall ↑ |
> | Keywords | “highway neighboring relations” | “highway building control zone Guangdong Province” | Precise targeting; precision ↑ |
> | Time range | All time | Last 10 years | Fewer outdated cases; precision ↑ |
> | Geographic limits | None | Add “Guangdong Province” | Match this case’s locality; precision ↑ |
> | Cause-of-action screening | None | Limit to “neighboring-relations disputes” | Exclude traffic accidents; precision ↑ |
> 
> **Second-retrieval assessment**:
> - Recall: 95% (covers core norms and local rules)
> - Precision: 80% (most results usable directly)
> - **Decision**: Targets met; proceed to report drafting

---


## 5.4 Common Quality Problems and Countermeasures

| Quality Problem | Appearance | Root-Cause Analysis | Countermeasures |
|----------|------|----------|----------|
| **Insufficient recall** | Critical statutes/cases missing | Single database, keywords too narrow, time range too small | Multi-database cross-check, synonym expansion, widen time range |
| **Insufficient precision** | Hard to screen; too much noise | Keywords too broad, no cause/geography limits, old law not excluded | Add limiters, logical NOT exclusion, authority screening |
| **Recall–precision imbalance** | Full but imprecise, or precise but incomplete | Retrieval strategy lacks iteration; no layered optimization | Use a “funnel model”: full first, then precise; gradually narrow |
| **Subsumption failure** | Results cannot apply to this case | No difference-factor analysis; mechanical copying | Strictly compare the 6 elements item by item; second retrieval if needed |

---

## Stage 6: Presenting Retrieval Results and Drafting the Report

### 6.1 Legal Analysis Structural Framework

**Analysis order** (do not skip steps; do not merge):
1. Characterize the legal relationship
2. Break down constitutive elements
3. Compare elements item by item
4. Allocate the burden of proof
5. Analyze possible defenses
6. Assess conclusion probability

#### 6.1.1 Characterization of the Legal Relationship

**Must clearly state**:

| Element | Description |
| :--------- | :--------------- |
| **Type of legal relationship** | Labor / contract / tort / neighboring relations, etc. |
| **Subject qualification** | Whether both parties have statutory subject qualification |
| **Content of rights and obligations** | Rights each party enjoys and obligations each bears |
| **Applicable law** | Which statutes, administrative regulations, and judicial interpretations apply |

#### 6.1.2 Explanation of Technical Terms

**[Mandatory] The report must include a “Technical Terms Explained” section:**

| Term | Legal Definition / Explanation | Legal Basis |
| :--- | :--- | :--- |
| De facto employment relationship | Employer and worker have not concluded a written employment contract, but the worker provides labor to and is managed by the employer | Labor Contract Law Art. 7; Notice on Matters Concerning Establishing Employment Relationships, Lao She Bu Fa 〔2005〕 No. 12, Art. 1 |
| Economic compensation (N) | One-time compensation paid by the employer after lawfully terminating the employment contract, based on the worker’s years of service | Labor Contract Law Art. 47 |
| Damages (2N) | Double economic compensation paid when the employer unlawfully dissolves or terminates the employment contract | Labor Contract Law Art. 87 |
| Triple wages | Statutory-holiday overtime pay = normal working-day wage × 3 | Labor Law Art. 44 |
| Payment in lieu of notice | Employer dissolves the contract after 30 days’ prior written notice at one month’s wages, or pays an extra month’s wages | Labor Contract Law Art. 40 |
| Building control zone | Area within a certain range on both sides of a highway where construction of buildings and surface structures is prohibited to ensure highway operational safety | Regulations on Highway Safety Protection Art. 11 |

### 6.2 Norms for Citing Statutory Provisions

**[Mandatory] Every legal authority must include the following elements:**

| Element | Description | Example |
| :------- | :--------------------- | :--------------------------------------------------------------------------------------------------- |
| **Document name** | Full name of the law or regulation | Labor Contract Law of the People’s Republic of China |
| **Document number** | Enacting body and document number | Presidential Order No. 65 |
| **Effective time** | When it took effect / was amended | Implemented from 1 January 2008 |
| **Article number** | Specific article(s) | Articles 44 and 45 |
| **Verbatim citation** | [Article topic] + statutory text | [Calculation of economic compensation] Economic compensation shall be paid to the worker at the rate of one month’s wages for each full year of service with the employer… |
| **Validity status** | In force / repealed / amended | In force |

**Annotation of citation relationships among provisions**:

```
→ Citation relationship: Labor Contract Law Art. 87 → Labor Contract Law Art. 47 (economic compensation calculation standard)
→ Citation relationship: Lao She Bu Fa 〔2005〕 No. 12 Art. 1 → Labor Law Art. 16
→ Citation relationship: Regulations on Highway Safety Protection Art. 11 → Highway Law (higher-level authorizing law)
```

### 6.3 Labeling Hierarchy of Legal Norms

| Level | Effect | Examples |
| :---- | :---------------------- | :---------------- |
| Statutes (laws) | Enacted by the NPC and its Standing Committee; highest effect among ordinary norms | Labor Law; Labor Contract Law; Civil Code |
| Administrative regulations | Enacted by the State Council; effect below statutes | Regulations on the Implementation of the Labor Contract Law; Regulations on Highway Safety Protection |
| Judicial interpretations | Enacted by the SPC and SPP; have legal effect | Fa Shi 〔2020〕 No. 17 |
| Departmental rules | Enacted by State Council ministries and commissions | Interim Provisions on Wage Payment |
| Local regulations | Enacted by provincial people’s congresses | Shanghai Municipality Labor Contract Regulations; Guangdong Province Highway Regulations |
| Guiding Cases | Issued by the SPC; have referential effect | Guiding Case No. 72 |
| Typical cases | Issued by the SPC; for reference only | SPC typical cases |

**[Important Distinctions]**
- Judicial interpretations: Have legal effect; courts at all levels must apply them
- Guiding Cases: Have referential effect (to be referred to and followed), but are not adjudicative authority
- Typical cases: For research reference only; no legal binding force

### 6.4 Organizing Limitation Periods and Deadlines

If limitation issues are involved, organize them separately:

| Matter | Period | Basis | Notes |
| :----- | :-------- | :-------------- | :--------------------------- |
| Civil litigation limitation | 3 years (general) | Civil Code Art. 188 | Runs from when the right-holder knew or should have known that rights were harmed and who the obligor is |
| Special litigation limitations | 1 / 2 / 4 years, etc. | Civil Code Arts. 189–194 | Carriage of goods by sea contracts, international sale of goods contracts, etc. |
| Preclusive period (除斥期间) | Per specific rules | Various special laws | Nature: formative right; right extinguished upon expiry |
| Administrative reconsideration period | 60 days | Administrative Reconsideration Law Art. 20 | Runs from knowledge of the specific administrative act |
| Administrative litigation period | 6 months / 15 days | Administrative Litigation Law Art. 46 | 15 days if dissatisfied with reconsideration decision; 6 months if suing directly |
| Labor arbitration limitation | 1 year | Labor Dispute Mediation and Arbitration Law Art. 27 | Not limited while the employment relationship continues |

### 6.5 Controlling the Strength of Conclusion Language

Conclusions must mark judgment strength:
- **High probability of being established**
- **Substantial controversy exists**
- **Insufficient evidence to judge**

**Do not use absolute expressions** (e.g., “certain to win,” “definitely unlawful”).

### 6.6 Standard Structure of the Retrieval Report

**Normative legal-document retrieval results should be ordered as follows**:
1. List document name, effective date, and clauses related to the case’s issues
2. List valid, relevant legal rules
3. Note the databases used and keywords entered
4. When submitting electronically, hyperlink the names of laws and regulations

**Required report sections**:

#### 1. Statement of the Problem
- Clearly state the problem this retrieval addresses
- Facilitates judging whether the overall direction is wrong or biased

#### 2. Course of Retrieval
- Note databases used
- Record keywords entered
- Describe the retrieval path

#### 3. Listing of Norms (by Effect Hierarchy)
- Statutes (laws)
- Administrative regulations
- Local regulations
- Departmental rules
- Judicial interpretations
- Other normative documents

#### 4. Retrieval Analysis
- Remain neutral and objective
- Group by relevance and strength
- Highlight conflicting authorities and explain reasons
- Elaborate separately at three levels: legislation (whether rules exist / reasons for gaps), enforcement (administrative application), and adjudication (judicial tendency / geographic differences / temporal evolution)
- Charts may be used to show adjudicative tendencies

#### 5. Retrieval Conclusion
- Directly answer the retrieval purpose
- Clarify the current state of the law
- Summarize judicial practice tendencies
- Point out legal-application risk points (positive consequences + negative consequences)
- Seek opposing views or arguments; avoid accepting a single view
- Be wary of practice articles with brand-promotion aims; absorb critically

---

## Complete Sample Retrieval Report

### Legal Retrieval Report (Sample)

#### Main Text
**Retrieval purpose:**
Ascertain restrictive rules on how far a highway under construction must be kept from residential areas

**Retrieval tools:**
PKULaw (北大法宝), China Judgments Online

**Retrieval keywords:**
highway, meters; highway, construction; highway, land acquisition / expropriation / requisition / demolition

**Retrieved regulations and other documents:**

**4-1 Invalid retrieval (record the path):**
- Road Traffic Safety Law of the People’s Republic of China (no specific distance rules)
- Regulations on the Implementation of the Road Traffic Safety Law of the People’s Republic of China (no specific distance rules)
- Detailed Rules for the Implementation of the Measures for Completion (Handover) Acceptance of Highway Engineering Projects (no specific distance rules)

**4-2 Valid retrieval:**

**4-2-1 Statutes (laws)**

| Document Name | Document Number | Effective Time | Article Number | Verbatim Citation | Validity Status |
| :------- | :----- | :--------- | :--------- | :--------- | :--------- |
| General Principles of the Civil Law of the PRC | Presidential Order No. 37 | 1 Jan 1987 | Article 83 | [Neighboring relations] Adjacent parties to immovable property shall correctly handle neighboring relations concerning water diversion and drainage, passage, ventilation, lighting, and the like in the spirit of benefiting production, facilitating life, solidarity and mutual assistance, and fairness and reasonableness. Where obstruction or loss is caused to the adjacent party, infringement shall cease, obstruction shall be eliminated, and loss shall be compensated. | Repealed (superseded by the Civil Code) |
| General Principles of the Civil Law of the PRC | Presidential Order No. 37 | 1 Jan 1987 | Article 106, paragraph 2 | [Fault liability] Citizens and legal persons who, through fault, infringe state or collective property, or another’s property or person, shall bear civil liability. | Repealed |
| General Principles of the Civil Law of the PRC | Presidential Order No. 37 | 1 Jan 1987 | Article 117, paragraph 2 | [Property damage compensation] One who damages another’s property shall restore it to its original condition or compensate at a discounted price. | Repealed |
| Property Law of the PRC | Presidential Order No. 62 | 1 Oct 2007 | Article 91 | [Safety of immovable property] A holder of rights in immovable property who excavates land, constructs buildings, lays pipelines, or installs equipment, etc., must not endanger the safety of adjacent immovable property. | Repealed (superseded by Civil Code Art. 296) |
| Tort Liability Law of the PRC | Presidential Order No. 21 | 1 Jul 2010 | Article 85 | [Liability for falling objects from buildings] Where buildings, structures, or other facilities, or objects placed or hung thereon, fall or drop and cause harm to another, and the owner, manager, or user cannot prove absence of fault, they shall bear tort liability. | Repealed (superseded by Civil Code Art. 1253) |

→ Citation relationship: Civil Code Art. 296 → former Property Law Art. 91 (succession relationship)
→ Citation relationship: Civil Code Art. 1253 → former Tort Liability Law Art. 85 (succession relationship)

**4-2-2 Administrative regulations**

| Document Name | Document Number | Effective Time | Article Number | Verbatim Citation | Validity Status |
| :------- | :--------- | :-------- | :---- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------ |
| Regulations on Highway Safety Protection | State Council Order No. 593 | 1 Jul 2011 | Article 11 | [Scope of building control zones] Local people’s governments at or above the county level shall, according to principles of ensuring highway operational safety and economizing land use and the needs of highway development, organize transport, land and resources, and other departments to demarcate the scope of highway building control zones. Distances outward from the outer edge of highway land use are: (1) national highways not less than 20 meters; (2) provincial highways not less than 15 meters; (3) county highways not less than 10 meters; (4) township highways not less than 5 meters. For expressways, the building control zone shall extend not less than 30 meters outward from the outer edge of highway land use. | In force |
| Regulations on Highway Safety Protection | State Council Order No. 593 | 1 Jul 2011 | Article 13 | [Construction restrictions within control zones] Within highway building control zones, except as needed for highway protection, construction of buildings and surface structures is prohibited; those lawfully built before demarcation may not be expanded; if demolition is required for highway construction or to ensure operational safety, compensation shall be given according to law. | In force |
| Regulations on Highway Safety Protection | State Council Order No. 593 | 1 Jul 2011 | Article 28 | [Permit for road-related construction] The construction entity applying for road-related construction shall submit to the highway management authority: (1) design and construction plans meeting relevant technical standards and norms; (2) a technical assessment report ensuring the quality and safety of the highway and ancillary facilities; (3) an emergency plan for construction hazards and accidents. | In force |
| Guangdong Province Highway Regulations | Announcement of the Guangdong Province People’s Congress Standing Committee | 2003 | Article 5 | [Planning coordination] Compilation and approval of highway plans shall follow the Highway Law. Where a highway passes through an urban planning area, route selection and positioning of the crossing section shall coordinate with local urban planning and solicit opinions of the local planning authority. | In force (amended) |
| Guangdong Province Highway Regulations | Announcement of the Guangdong Province People’s Congress Standing Committee | 2003 | Article 9 | [Land-acquisition compensation] Land use for highway construction shall be handled under relevant laws and administrative regulations. Standards for land compensation fees, resettlement subsidies, and compensation for attachments and young crops on highway construction land shall follow relevant provincial government rules… | In force |

→ Conflict note: Art. 11 of the Regulations on Highway Safety Protection (expressway 30 m) differs from Art. 5 of the Guangdong Province Highway Regulations (expressway 200 m); the former is a “building control zone” (new construction prohibited), the latter is “planning spacing” (planning control)

**4-2-3 Other normative documents**

| Document Name | Issuing Body | Article Number | Verbatim Citation | Validity Status |
| :------- | :---- | :------ | :-------------------------------------------------- | :--- |
| Technical Standard of Highway Engineering | Ministry of Transport | Art. 3.0.1 | [Route design requirements] Trunk highways should avoid passing through towns. Route design should occupy less farmland, demolish fewer houses, convenience the public, and not damage important historical relics. | Industry standard |

**Retrieval analysis:**

**6-1 Legal analysis of retrieval**

On the legal analysis, perhaps due to legislative lag or legislative orientation, **there is no specific statutory restriction on how much distance must be kept when a highway under construction passes near residential areas**. Yet safety is mutual: rules on 30-meter highway control zones, safety technical assessment reports, environmental impact assessments, and the like all regulate the safety of highway construction. Still, these rules **are hard for judges to use as a basis for finding that building a highway too close is unlawful**.

Counsel’s conjecture as to why courts support plaintiffs’ claims is mainly that judges inwardly regard demolition and resettlement compensation as a necessary cost of highway construction, and secondarily that judges emphasize safety. The claim basis in such judgments is General Principles of the Civil Law Art. 106 in cases ⑧ and ⑩; case ⑨ cites General Principles of the Civil Law Art. 117 and Tort Liability Law Art. 85. On damages calculation, courts use house value as the base and discretionary reduce for plaintiff’s fault or natural depreciation of house value.

**6-2 Norm conflict analysis**

| Norm A | Norm B | Conflict Point | Resolution |
| :----- | :----- | :------- | :--------- |
| Regulations on Highway Safety Protection Art. 11 (30 m) | Guangdong Province Highway Regulations Art. 5 (200 m) | Differing distance standards | Different application scenarios: 30 m is the building control zone (new construction prohibited); 200 m is planning spacing (planning control) |

**Retrieval conclusion:**

**Chinese law has no concrete, clear restrictive rule on the distance between a highway under construction and adjacent residential areas.** (Conclusion strength: high probability of being established)

**Legal-application risk warnings**:
- **Positive consequences**: Damages may be claimed on neighboring-relations grounds; courts may support compensation requests
- **Negative consequences**: Hard to find the construction entity directly “unlawful”; difficult to seek stoppage of construction or demolition

**8. Retrieval time spent:** xx hours

**9. Completion date:** 4 January 2016



#### Appendix—Retrieval Quality

I. Recall assurance measures
1. **Cross-database validation**: Dual-database retrieval with PKULaw and China Judgments Online; overlap rate 65%;
   supplemented 3 exclusive cases
2. **Cross-method validation**: Systematic retrieval covered 3 levels—statutes, administrative regulations, local regulations;
   keyword retrieval underwent 3 rounds of expansion (“highway” → “building control zone” → “neighboring relations”)
3. **Timeliness review**: Retrieval cutoff April 2026, including latest Civil Code-related amendments

**Self-assessed recall**: 95% (no critical norms omitted, including core authorities such as Regulations on Highway Safety Protection Art. 11 and
Guangdong Province Highway Regulations Art. 5)

## Precision optimization measures
1. **Authority-ranked screening**:
   - Kept: 1 Guiding Case, 2 SPC Gazette cases, 5 high-court typical cases
   - Excluded: 12 intermediate/basic-court cases (reference only), 8 cases related to repealed provisions
2. **Subsumption test**: Compared the 6 difference factors item by item; excluded 23 inapplicable norms
3. **Geographic matching**: Limited to Guangdong Province and nationwide rules; excluded 15 local rules of other provinces

**Self-assessed precision**: 80% (of the final 15 norms, 12 are directly usable for legal analysis)

Retrieval process iteration log

| Round | Keywords | Result Count | Recall | Precision | Main Problems | Optimization Measures |
|------|--------|----------|--------|--------|----------|----------|
| Round 1 | highway neighboring relations | 200 | 75% | 30% | Missed local regulations; too much noise | Add databases; optimize keywords |
| Round 2 | highway building control zone Guangdong Province | 42 | 90% | 65% | Still some outdated cases | Limit time range |
| Round 3 | highway building control zone Guangdong Province last 10 years | 15 | 95% | 80% | Targets met | Proceed to report stage |

Quality conclusion
Through three rounds of iteration, this retrieval reached good levels on both recall and precision; the results can support a legal analysis report.
