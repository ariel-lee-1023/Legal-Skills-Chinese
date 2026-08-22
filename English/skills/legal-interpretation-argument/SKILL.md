---
name: legal-interpretation-argument
description: |
  Trigger this skill when legal reasoning encounters any of the following:
  (1) the statutory text is ambiguous or admits multiple readings;
  (2) applying the provision to concrete case facts is contested;
  (3) an argument is needed that a provision should / should not apply to a particular situation;
  (4) the parties disagree on the meaning of the same provision;
  (5) provisions appear to conflict on the surface and must be reconciled through interpretation;
  (6) novel facts cannot be mapped directly onto existing statutory text;
  (7) legal application in a judgment document must be analyzed or challenged.
  The core of this skill is to apply textual (grammatical), systematic, teleological, and other methods of legal interpretation to rigorously interpret and argue key provisions, reach a reasonable and defensible legal meaning, and present the interpretive process and conclusion in a standardized form.
---

> **Chinese source (authoritative):** [`../../skills/legal-interpretation-argument/SKILL.md`](../../skills/legal-interpretation-argument/SKILL.md)

# Legal Interpretation Argumentation

## Overview Table

| Item | Content |
|------|---------|
| **Capability name** | Legal Interpretation Argumentation |
| **Capability type** | Core legal-reasoning capability |
| **Applicable stages** | Legal analysis, legal application, judicial reasoning, drafting of legal opinions |
| **Core operation** | Multi-dimensional interpretive argumentation of key provisions (textual, systematic, teleological, etc.) |
| **Input** | Provision(s) to interpret + concrete case facts / legal question + interpretive goal |
| **Output** | Structured legal-interpretation opinion (methods, reasoning process, conclusion) |
| **Prerequisite skills** | Statutory retrieval and location; legal-relationship identification; claim-basis analysis |
| **Follow-on skills** | Legal-argument construction; judgment drafting; issuance of legal opinions |
| **Difficulty** | ★★★★☆ (advanced legal reasoning) |
| **Risk level** | High — interpretive error can cause fundamental deviation in legal application |

---

## Legal Disclaimer

> **Important notice:** The methodological guidance on legal interpretation in this skill file is for AI-agent-assisted legal reasoning only and does not constitute formal legal advice. Legal interpretation involves value judgments and professional discretion; final conclusions must be reviewed and confirmed by qualified legal professionals. Different jurisdictions and courts at different levels may take different interpretive positions on the same provision. The AI agent must honestly disclose interpretive uncertainty and must not conceal controversy.

---

## I. Core Concepts

### 1.1 Definition and Functions of Legal Interpretation

Legal interpretation means clarifying the meaning of legal norms. Its core functions include:

- **Clarification:** Connecting abstract legal text with concrete case facts
- **Gap-filling:** Bridging the openness of legal text and the concreteness of case facts
- **Coordination:** Eliminating surface conflicts among provisions and preserving systemic coherence
- **Development:** Adapting legal norms to new social needs

### 1.2 System of Interpretive Methods

```
System of Legal Interpretive Methods
├── Tier 1: Textual / Grammatical Interpretation
│   ├── Ordinary-meaning interpretation
│   ├── Legal-technical-term interpretation
│   └── Context-limited interpretation
├── Tier 2: Systematic Interpretation
│   ├── Intra-statute systematic interpretation
│   ├── Cross-statute systematic interpretation
│   └── Higher-law / constitution-conforming interpretation
├── Tier 3: Teleological Interpretation
│   ├── Subjective teleology (legislator's intent)
│   ├── Objective teleology (normative purpose of the provision)
│   └── Institutional-purpose interpretation
├── Tier 4: Historical Interpretation
│   ├── Analysis of legislative materials
│   ├── Analysis of legislative history / evolution
│   └── Analysis of legislative background
├── Supplementary methods
│   ├── Comparative-law interpretation
│   ├── Constitution-conforming interpretation
│   └── Sociological interpretation
└── Boundaries of interpretation
    ├── Range of possible meanings (outer limit of interpretation)
    ├── Analogical application (law-making beyond interpretation)
    └── Teleological reduction / extension
```

### 1.3 Priority Sequence of Interpretive Methods

| Priority | Method | Application notes | Binding force |
|----------|--------|-------------------|---------------|
| 1 | Textual interpretation | Starting point and endpoint — no interpretation may go beyond the provision's possible meanings | Strongest constraint |
| 2 | Systematic interpretation | Among meanings allowed by the text, choose the one coherent with the legal system | Strong constraint |
| 3 | Historical interpretation | Consult legislative materials to confirm original legislative intent | Medium constraint |
| 4 | Teleological interpretation | When prior methods cannot yield a unique meaning, choose by normative purpose | Directional constraint |
| 5 | Comparative / sociological interpretation | Auxiliary reference only; cannot alone serve as interpretive basis | Weak constraint |

> **Key rule:** There is no absolutely fixed priority among methods, but textual interpretation forms the outer boundary of interpretation (the "possible meaning" principle). When multiple methods point to the same conclusion, reliability is highest; when they diverge, methodological balancing argumentation is required.

### 1.4 Core Term Definitions

| Term | Definition |
|------|------------|
| **Possible meaning** | The full range of meanings a statutory term can bear in ordinary or legal-professional language |
| **Core meaning** | The meaning region the term covers without controversy |
| **Peripheral meaning** | The gray zone the term may or may not cover |
| **Reach / scope of application** | The range of fact-types the norm can regulate |
| **Normative purpose (*ratio legis*)** | The normative goal the legal rule pursues |
| **Legislative reasons** | Reasons the legislator expressly stated for enacting the provision |
| **Systemic connection** | Logical and functional relations between the provision under interpretation and other provisions |
| **Interpretive argumentation** | The process of reasoning about a provision's meaning with interpretive methods and giving reasons |

---

## II. Complete Workflow

### Stage 1: Identify Interpretive Need and Define the Question

```
Step 1.1: Identify interpretive triggers
├── Does the statutory text contain ambiguous wording?
├── Is applying the provision to the case facts contested?
├── Do the parties disagree on the provision's meaning?
├── Is there a surface conflict among provisions?
└── Is this a novel situation not expressly provided for?

Step 1.2: Precisely define the interpretive question
├── Specify the exact provision (down to article, paragraph, item)
├── Specify the exact term or normative element to interpret
├── Formulate the question concretely (e.g.: "Does 'fault' in Art. 1165, Para. 1 of the Civil Code include indirect intent?")
└── Specify the directional goal (expand or limit application? fill a gap or eliminate conflict?)

Step 1.3: Collect interpretive materials
├── Full text of the provision (all paragraphs/items)
├── Surrounding provisions in the same chapter
├── Related provisions in associated laws, administrative regulations, and judicial interpretations
├── Legislative explanations, draft deliberation reports, and other legislative materials
├── Relevant interpretations in SPC Guiding Cases and Gazette cases
├── Authoritative scholarly interpretations (official commentaries, textbook mainstream views)
└── Related "understanding and application" of judicial interpretations
```

### Stage 2: Textual Interpretation

```
Step 2.1: Determine ordinary meaning
├── Consult authoritative dictionaries (legal dictionaries first; general dictionaries auxiliary)
├── Confirm the term's ordinary meaning in everyday language
├── Confirm whether the term is a legal technical term
│   ├── Yes → legal-professional meaning controls
│   └── No → everyday-language meaning as baseline
└── Record the statement of ordinary meaning

Step 2.2: Delimit the textual range
├── Determine the core-meaning region (uncontroversial)
├── Determine the peripheral-meaning region (possibly covered)
├── Determine the exclusion region (clearly not covered by the text)
└── Judge which region the case controversy falls into
    ├── Core → textual interpretation alone may decide
    ├── Peripheral → further methods required
    └── Exclusion → interpretation cannot solve; consider analogy or judicial law-making

Step 2.3: Syntactic / grammatical analysis
├── Analyze the provision's sentence structure
├── Identify subject, predicate, object, and modifiers
├── Note logical meaning of connectors such as "and", "or", "but", "except"
├── Note intensity differences among "shall", "may", "must not"
└── Note how punctuation affects meaning

Step 2.4: Form a preliminary textual conclusion
├── What meaning does textual interpretation support?
├── Can textual interpretation yield a unique determinate conclusion?
├── If multiple textually possible meanings exist, what are they?
└── Record the textual conclusion and its reasons
```

### Stage 3: Systematic Interpretation

```
Step 3.1: Intra-statute systematic analysis
├── Analyze the provision's position in the statute (part, chapter, section)
├── Analyze relations with other provisions in the same chapter
│   ├── General vs. special clauses
│   ├── Principle vs. rule clauses
│   └── Constitutive-element vs. legal-effect clauses
├── Check for definition clauses of the same term in the same statute
├── Check consistency of the same term across different articles
│   ├── Consistent → presumption of same meaning for same term
│   └── Inconsistent → analyze reasons for the difference
└── Analyze relation to general provisions / basic-principle clauses

Step 3.2: Cross-statute systematic analysis
├── Identify other laws associated with the provision under interpretation
├── Analyze meanings of identical or similar terms in associated laws
├── Analyze whether associated laws' normative purposes affect interpretation of this provision
├── Check for higher-law definitions of the term
└── Check for special-law special provisions on the term

Step 3.3: Avoid systemic conflict
├── Check whether the proposed interpretation would contradict other provisions
├── Check whether it would deprive some provision of application space
├── Check whether it fits the legal system's internal logic
└── If conflict exists, coordinate with these rules:
    ├── Higher law prevails over lower law
    ├── Special law prevails over general law
    ├── Later law prevails over earlier law
    └── Constitution-conforming interpretation preferred

Step 3.4: Form a systematic-interpretation conclusion
├── What meaning does systematic interpretation support?
├── Is it consistent with the textual conclusion?
│   ├── Consistent → strengthens reliability
│   └── Inconsistent → record divergence; proceed to next analysis
└── Record the systematic conclusion and its reasons
```

### Stage 4: Teleological Interpretation

```
Step 4.1: Determine normative purpose
├── Subjective purpose (legislator's intent)
│   ├── Consult legislative / draft explanations
│   ├── Consult NPC Standing Committee deliberation reports
│   ├── Consult commentaries by legislative staff
│   └── Consult discussion records from the legislative process
├── Objective purpose (purpose of the norm itself)
│   ├── Infer from constitutive elements and legal effects
│   ├── Infer from chapter title and systemic position
│   ├── Infer from the statute's purpose clause (usually Art. 1)
│   └── Infer from the legal interest protected
└── Institutional purpose
    ├── Overall function of the legal institution to which the provision belongs
    └── Role of that institution in social governance

Step 4.2: Interpret by purpose
├── Among textually allowed meanings, which best realizes the normative purpose?
├── Would the proposed interpretation frustrate the normative purpose?
├── Would it produce effects contrary to the normative purpose?
└── Is teleological reduction or extension needed?
    ├── Teleological reduction: exclude application where text covers but purpose does not
    └── Teleological extension: include application where text does not cover but purpose does

Step 4.3: Form a teleological conclusion
├── What meaning does teleological interpretation support?
├── Is it consistent with textual and systematic conclusions?
└── Record the teleological conclusion and its reasons
```

### Stage 5: Historical Interpretation (as needed)

```
Step 5.1: Legislative-history analysis
├── Did this provision have a predecessor?
├── How does the predecessor's wording differ from the current text?
├── What were the reasons and purposes of amendment?
└── Does amendment imply a change of meaning?

Step 5.2: Legislative-background analysis
├── Social background when the provision was enacted
├── Concrete problem the provision was meant to solve
├── Contested issues during the legislative process
└── How the final text was formed

Step 5.3: Form a historical-interpretation conclusion
├── What meaning does historical interpretation support?
├── Is it consistent with other methods' conclusions?
└── Record the historical conclusion and its reasons
```

### Stage 6: Comprehensive Balancing of Methods

```
Step 6.1: Aggregate conclusions from each method
├── Textual: [Conclusion A]
├── Systematic: [Conclusion B]
├── Teleological: [Conclusion C]
├── Historical: [Conclusion D] (if applicable)
└── Other methods: [Conclusion E] (if applicable)

Step 6.2: Judge consistency
├── All consistent → high-confidence conclusion
├── Majority consistent → medium-high confidence; explain why minority methods diverge
├── Divergence → methodological balancing required
└── Severe divergence → low confidence; honestly disclose uncertainty

Step 6.3: Methodological balancing (when conclusions diverge)
├── Textual interpretation is the outer boundary — no conclusion beyond possible meaning
├── Systematic interpretation preserves coherence — prefer meanings that avoid systemic conflict
├── Teleological interpretation supplies substantive reasons — decisive when formal methods cannot decide
├── Historical interpretation is reference — original legislative intent cannot negate textual development
└── Holistic considerations:
    ├── Which interpretation better fits the normative purpose?
    ├── Which better fits social fairness and justice?
    ├── Which is more predictable and promotes legal stability?
    └── Which better balances the parties' interests?

Step 6.4: Form the final interpretive conclusion
├── State the meaning finally adopted
├── State the core reasons for adopting it
├── State reasons for excluding other possible meanings
└── Mark the confidence level
```

### Stage 7: Expressing and Outputting the Interpretive Argument

```
Step 7.1: Organize argument structure
├── Pose the interpretive question
├── Unfold analysis under each method
├── Comprehensive balancing
├── Reach the conclusion
└── Respond to possible rebuttals

Step 7.2: Check argument quality
├── Complete (were important methods omitted)?
├── Rigorous (any logical jumps)?
├── Honest (were unfavorable materials fairly presented)?
├── Clear (can the reader follow the reasoning)?
└── Is the conclusion within the range of possible meanings?

Step 7.3: Output the final product
├── Organize per the output template
├── Mark confidence
├── Mark points needing human review
└── Suggest further research (if applicable)
```

---

## III. Common Domains and Sources of Law

### 3.1 Civil Law

| Common interpretive issue | Provisions involved | Typical methods | Reference sources |
|---------------------------|---------------------|-----------------|-------------------|
| Meaning and types of "fault" | *Civil Code* Art. 1165 | Textual + systematic + teleological | Commentary on Tort Liability Book |
| Standard for "good faith" | *Civil Code* Art. 311 | Textual + teleological + comparative | Judicial interpretation on Property Rights Book |
| Determining a "reasonable period" | *Civil Code* (multiple) | Teleological + systematic | Related judicial interpretations |
| Boundaries of "public order and good morals" | *Civil Code* Arts. 8, 153 | Teleological + sociological | Guiding Cases |
| Finding "gross misunderstanding" | *Civil Code* Art. 147 | Textual + historical + teleological | Commentary on General Provisions Book |
| Scope of "force majeure" | *Civil Code* Art. 180 | Textual + teleological + systematic | Pandemic-related judicial documents |
| Scope of powers of a "right of habitation" | *Civil Code* Arts. 366–371 | Textual + systematic + historical | Property Rights Book commentary |

### 3.2 Criminal Law

| Common interpretive issue | Provisions involved | Typical methods | Special constraints |
|---------------------------|---------------------|-----------------|---------------------|
| Meaning of constitutive elements | Criminal Law special-part articles | Primarily textual + systematic | **Principle of legality: no analogy adverse to the defendant** |
| Standards for "relatively large / huge amount" | Criminal Law (multiple) | Textual + judicial interpretation | Refer to latest judicial-interpretation amount thresholds |
| Degree of "violence" required | Criminal Law (multiple) | Textual + systematic + teleological | "Violence" may differ across offenses |
| Scope of "public safety" | Criminal Law Ch. 2 | Textual + teleological | Judge in light of the specific offense |
| Finding "purpose of illegal possession" | Criminal Law (multiple) | Teleological + systematic | Objectivized interpretation of subjective elements |

> **Special rules for criminal interpretation:**
> - The principle of legality (*nullum crimen sine lege*) is the highest constraint
> - Analogy adverse to the defendant is prohibited
> - Distinguishing expansive interpretation from analogy is the core difficulty
> - When in doubt, interpretations favorable to the defendant are preferred

### 3.3 Administrative Law

| Common interpretive issue | Provisions involved | Typical methods | Special constraints |
|---------------------------|---------------------|-----------------|---------------------|
| Delimiting types of administrative penalties | *Administrative Penalty Law* Art. 9 | Textual + systematic | Principle of legality of penalties |
| Finding "abuse of power" | *Administrative Litigation Law* Art. 70 | Teleological + systematic | Combine with administrative-discretion theory |
| Scope of "interest / stake" | *Administrative Litigation Law* Art. 25 | Teleological + systematic + historical | Trend toward expanding standing |
| Interpreting licensing conditions | Individual statutes | Textual + teleological | Principle of legal reservation |

### 3.4 Commercial Law

| Common interpretive issue | Provisions involved | Typical methods |
|---------------------------|---------------------|-----------------|
| Finding "actual controller" | *Company Law* Art. 265 | Textual + teleological + systematic |
| Scope of "related-party transactions" | *Company Law* Art. 182 et seq. | Textual + teleological |
| Boundaries of "shareholder information rights" | *Company Law* Art. 57 | Teleological + systematic |
| Constitution of "trade secrets" | *Anti-Unfair Competition Law* Art. 9 | Textual + teleological |

---

## IV. Validation and Screening Rules

### 4.1 Validity Checks for Interpretive Conclusions

```
Validation checklist:

□ Rule V1 [Textual-boundary rule]
  Is the conclusion within the "possible meaning" of the statutory wording?
  → Beyond possible meaning = no longer "interpretation" but "judicial law-making"; needs stronger justification

□ Rule V2 [Systemic-coherence rule]
  Does the conclusion contradict other norms in the legal system?
  → Contradiction = revisit the conclusion or provide a conflict solution

□ Rule V3 [Purpose-realization rule]
  Does the conclusion realize the provision's normative purpose?
  → Frustration of purpose = conclusion likely erroneous

□ Rule V4 [Practical-feasibility rule]
  Is the conclusion operable in practice?
  → Inoperable = needs further concretization

□ Rule V5 [Value-reasonableness rule]
  Does the conclusion comport with basic notions of fairness and justice?
  → Clearly unreasonable = revisit the interpretive process

□ Rule V6 [Precedent-consistency rule]
  Is the conclusion consistent with the SPC's existing interpretive position?
  → Inconsistent = explain reasons for departure or mark risk

□ Rule V7 [Criminal special rule] (criminal interpretation only)
  Does the conclusion violate the principle of legality?
  Does it constitute analogy adverse to the defendant?
  → Violation = conclusion invalid
```

### 4.2 Screening Rules for Choosing Methods

```
Screening rules:

S1: Every interpretation must begin with textual interpretation
S2: When textual interpretation yields a unique determinate conclusion, further interpretation is ordinarily unnecessary
    (Exception: when the textual conclusion clearly frustrates purpose or yields absurd results, teleological correction may be used)
S3: When textual interpretation admits multiple meanings, systematic and teleological interpretation must further determine
S4: Historical interpretation is especially important when:
    ├── The provision was amended and amendment intent must be confirmed
    ├── The provision is newly enacted and legislative background must be confirmed
    └── Textual, systematic, and teleological methods all fail to determine meaning
S5: Comparative-law interpretation is auxiliary only and cannot alone serve as basis
S6: In criminal law, interpretations favorable to the defendant must be prioritized
S7: In administrative law, norms restricting citizens' rights should be interpreted strictly
S8: In civil and commercial law, protect transactional security and reliance interests
```

---

## V. Output Format Templates

### Template A: Standard Legal Interpretation Opinion

```markdown
## Legal Interpretation Argumentation Opinion

### I. Interpretive Question
- **Provision under interpretation:** [Law title] Art. [X], Para. [X]
- **Statutory text:** "[Full quotation]"
- **Interpretive question:** [Concrete formulation]
- **Background:** [Briefly why interpretation is needed]

### II. Textual Interpretation
- **Key term(s):** "[Term(s) to interpret]"
- **Ordinary meaning:** [Everyday / legal-professional ordinary meaning]
- **Textual range:**
  - Core meaning: [Uncontroversially covered]
  - Peripheral meaning: [Possibly covered]
  - Exclusion: [Clearly not covered]
- **Textual conclusion:** [Conclusion]
- **Is textual interpretation determinate?** [Determinate / multiple possibilities]

### III. Systematic Interpretation
- **Systemic position:** [Position in the legal system]
- **Related-provision analysis:**
  - [Related provision 1]: [Analysis]
  - [Related provision 2]: [Analysis]
- **Systemic relation:** [General/special / principle/rule / other]
- **Systematic conclusion:** [Conclusion]

### IV. Teleological Interpretation
- **Normative purpose:** [Purpose of the provision]
- **Basis for purpose:** [Legislative explanation / commentary / structure, etc.]
- **Teleological analysis:** [Which meaning best realizes the purpose]
- **Teleological conclusion:** [Conclusion]

### V. Historical Interpretation (if applicable)
- **Legislative history:** [Evolution of the provision]
- **Legislative materials:** [Content of relevant materials]
- **Historical conclusion:** [Conclusion]

### VI. Comprehensive Balancing and Final Conclusion
- **Summary of method conclusions:**
  | Method | Conclusion | Weight |
  |--------|------------|--------|
  | Textual | [Conclusion] | [High/Medium/Low] |
  | Systematic | [Conclusion] | [High/Medium/Low] |
  | Teleological | [Conclusion] | [High/Medium/Low] |
  | Historical | [Conclusion] | [High/Medium/Low] |

- **Final conclusion:** [Clear interpretive conclusion]
- **Core reasons:** [2–3 sentences]
- **Exclusion reasons:** [Why other meanings are rejected]

### VII. Confidence and Risk Notes
- **Confidence:** [A/B/C/D/E]
- **Main risks:** [Possible divergent interpretive positions]
- **Recommendation:** [Further research / human review needed?]
```

### Template B: Brief Legal Interpretation Opinion (for rapid analysis)

```markdown
## Brief Legal Interpretation Opinion

**Provision:** [Law title] Art. [X]
**Question:** [One-sentence summary]

**Interpretive conclusion:** [Clear conclusion]

**Brief reasons:**
1. Textually, "[key term]" means …
2. Systematically, in light of [related provisions] …
3. Teleologically, the provision aims to …

**Confidence:** [A/B/C/D/E]
**Caveats:** [Risk points to watch]
```

---

## VI. Confidence Marking System

| Level | Mark | Meaning | Criteria | Suggested action |
|-------|------|---------|----------|------------------|
| A | 🟢 High confidence | Conclusion almost uncontroversial | All methods point same way; clear judicial interpretation or Guiding Case support | May adopt directly |
| B | 🔵 Relatively high | Strongly supported | Majority of methods agree; authoritative scholarship; no clear opposition | May adopt; briefly state reasons |
| C | 🟡 Medium | Some support but contested | Partial methods support; scholarly disagreement | Need detailed argumentation; recommend human review |
| D | 🟠 Relatively low | Substantial uncertainty | Clear divergence among methods; divergent practice | Must have human review; offer multiple interpretive options |
| E | 🔴 Highly uncertain | No reliable conclusion | Legal gap or major controversy; no precedent | Must leave to human decision; AI provides analysis framework only |

### Auxiliary Rules for Confidence Judgment

```
Confidence-raising factors (+1 level each, max A):
+ Clear SPC judicial interpretation
+ Guiding Case with clear holding
+ Clear statement in NPC Legislative Affairs Commission commentary
+ Scholarly mainstream consensus
+ Multiple methods converge

Confidence-lowering factors (−1 level each, min E):
- Highly abstract statutory wording (e.g., "public order and good morals", "reasonable")
- Divergent court positions
- Major scholarly controversy
- Involves value judgment and interest balancing
- Novel legal issue with no precedent
- Recent amendment; unclear old/new transition
```

---

## VII. Common Errors and Prevention

### 7.1 Fatal Error Table

| No. | Error type | Description | Consequences | Prevention |
|-----|------------|-------------|--------------|------------|
| F1 | **Beyond textual boundary** | Conclusion exceeds possible meaning; effectively analogy while still calling it "interpretation" | Fundamental application error; in criminal law may violate legality | Always check "possible meaning"; clearly distinguish interpretation from analogy |
| F2 | **Ignoring criminal special rules** | Expansive or analogical interpretation adverse to the defendant | Violates legality; fundamental unlawfulness | Separately check legality in criminal interpretation; when in doubt, favor the defendant |
| F3 | **Conclusion-first** | Pick the desired conclusion then selectively use supporting methods; ignore unfavorable materials | Dishonest argumentation; loss of credibility | Fully unfold all methods; present unfavorable materials honestly |
| F4 | **Wrong citation** | Wrong, repealed, or nonexistent provision | Entire argument's foundation collapses | Strictly verify current validity and article numbers |
| F5 | **Confusing interpretive levels** | Mixing legal interpretation with fact-finding, or with legal application | Confused logic | Distinguish clearly: what the provision means (interpretation) → whether facts fit (subsumption) → what legal effect follows (application) |

### 7.2 Common Traps

| No. | Trap | Description | How to spot | Response |
|-----|------|-------------|-------------|----------|
| T1 | **Circular reasoning** | Using conclusion to prove premise and vice versa (e.g., "the purpose is to protect X, so interpret as protecting X") | Check for circularity in the chain | Ensure each step has independent grounding |
| T2 | **Cherry-picking** | Citing only one method that supports one's position | Check whether methods were applied comprehensively | Require at least textual, systematic, and teleological methods |
| T3 | **Authority worship** | Accepting a view solely because it comes from an authority | Check for independent analysis of the authority's reasons | Still analyze whether the reasons hold |
| T4 | **Anachronism** | Interpreting historical text with contemporary ideas, or vice versa | Check whether the time dimension was considered | Distinguish meaning at enactment from meaning today |
| T5 | **Over-interpretation** | Unnecessary over-reading of a clear provision, creating nonexistent ambiguity | Check whether the provision was already clear | Follow *in claris non fit interpretatio* |
| T6 | **Isolated interpretation** | Interpreting a term detached from systemic position and normative context | Check for contextual consideration | Always situate the provision in its normative system |
| T7 | **Purpose-as-panacea** | Over-relying on teleology to break textual boundaries in the name of "purpose" | Check whether teleology remains within the text | Teleology cannot replace textual boundary function |
| T8 | **Ignoring counter-arguments** | Failing to consider the other side's possible rebuttal interpretation | Check whether opposing views were anticipated | Actively construct and respond to the other side's interpretive argument |

---

## VIII. Special Scenario Handling

### 8.1 Interpretation When Provisions Concurrently Apply

**Scenario:** The same facts may satisfy constitutive elements of multiple provisions; interpretation must determine which applies.

**Rules:**
1. First use systematic interpretation to determine relations among provisions (general/special; basic/supplementary)
2. Special law prevails over general law
3. If special-law relation cannot be determined, use teleological interpretation to see which normative purpose best fits the facts
4. Clearly state reasons for excluding other provisions

### 8.2 Identifying and Handling Legal Gaps

**Scenario:** Interpretation reveals a gap (unplanned incompleteness).

**Rules:**
1. First confirm a true gap exists (not intentional legislative silence)
2. Distinguish "open gaps" (missing a needed rule) from "hidden gaps" (missing a needed exception)
3. If a gap is confirmed, state its type and scope
4. Note possible gap-filling methods (analogy; teleological reduction/extension), but clearly mark that this goes beyond "interpretation"
5. In criminal law, gaps may not be filled in a direction adverse to the defendant

### 8.3 Interpreting Indeterminate Legal Concepts

**Scenario:** The provision uses indeterminate concepts such as "reasonable", "appropriate", "major", "necessary".

**Rules:**
1. Acknowledge openness; do not attempt a closed definition
2. Use typification: list typical affirmative and negative cases
3. Extract judgment criteria (consideration factors), not a precise definition
4. Refer to standards already formed in judicial practice
5. Clearly mark the necessity of case-by-case judgment

### 8.4 Interpretation in Old/New Law Transition

**Scenario:** After amendment, old and new provisions differ; transitional application must be determined.

**Rules:**
1. First consult transitional clauses and effective-date rules
2. Confirm amendment intent through historical interpretation
3. Apply non-retroactivity, except where favorable to the party
4. In criminal law, apply "old law unless new law is lighter"
5. Clearly mark uncertainty in old/new transition

### 8.5 When Judicial Interpretation and Statutory Text Diverge

**Scenario:** A judicial interpretation appears to go beyond the statutory text's meaning range.

**Rules:**
1. First confirm the judicial interpretation is currently in force
2. Analyze whether it remains within the provision's "possible meaning"
3. If within textual range, it binds legal application
4. If beyond textual range, assess:
   - Whether it is "quasi-legislative" in nature
   - Whether courts generally follow it in practice
5. Honestly disclose tension between statutory text and judicial interpretation

### 8.6 Constitution-Related Interpretation

**Scenario:** A proposed interpretation may conflict with constitutional principles or fundamental rights.

**Rules:**
1. Among possible interpretations, prefer the one consistent with the Constitution (constitution-conforming interpretation)
2. Constitution-conforming interpretation may not exceed possible meaning
3. If all possible interpretations conflict with the Constitution, flag a possible constitutionality problem
4. Note: the AI agent must not itself adjudicate unconstitutionality; it should flag need for professional review

---

## IX. Quality Checklist

### After completing interpretive argumentation, check item by item:

**I. Basics**
- [ ] Provision cited accurately (title, article numbers, text)
- [ ] Provision is the currently effective version
- [ ] Interpretive question is clear and concrete
- [ ] Background adequately explained

**II. Textual interpretation**
- [ ] Ordinary meaning of key terms determined
- [ ] Core vs. peripheral meaning distinguished
- [ ] Grammar / syntax analyzed
- [ ] Textual conclusion clear

**III. Systematic interpretation**
- [ ] Position in the legal system analyzed
- [ ] Relations with associated provisions analyzed
- [ ] Consistency of the same term across articles checked
- [ ] Conclusion does not contradict other provisions

**IV. Teleological interpretation**
- [ ] Normative purpose determined (with supporting basis)
- [ ] Analyzed whether conclusion realizes purpose
- [ ] Teleology did not exceed textual boundary

**V. Comprehensive**
- [ ] At least textual, systematic, and teleological methods used
- [ ] Method conclusions aggregated and compared
- [ ] Balancing argumentation done when conclusions diverged
- [ ] Final conclusion clear
- [ ] Reasons for excluding other meanings stated

**VI. Compliance**
- [ ] Conclusion within "possible meaning"
- [ ] Criminal interpretation does not violate legality (if applicable)
- [ ] Unfavorable interpretive materials disclosed honestly
- [ ] Confidence level marked
- [ ] Points needing human review marked

**VII. Expression**
- [ ] Argument structure clear
- [ ] No logical jumps in reasoning
- [ ] Professional terms used accurately
- [ ] Conclusion unambiguous

---

## X. Complete Examples

### Example 1: Simple Scenario — Interpreting "Written Form" in the Civil Code

#### Background

In a contract dispute, parties A and B reached an agreement via WeChat chat records. The law requires that such contracts "shall adopt written form." Dispute focus: do WeChat chat records constitute "written form"?

#### Legal Interpretation Argumentation Opinion

**I. Interpretive Question**
- **Provision under interpretation:** *Civil Code of the PRC* Art. 469, Paras. 2 and 3
- **Statutory text:**
  - Para. 2: "Written form means a form that tangibly expresses the content carried, such as a contract instrument, letter, telegram, telex, or fax."
  - Para. 3: "A data message that can tangibly express the content carried and can be retrieved and used at any time by means such as electronic data interchange or email is deemed written form."
- **Interpretive question:** Do WeChat chat records constitute "written form" under Art. 469?
- **Background:** Parties reached consensus via WeChat; the other side argues the contract was not formed or is invalid for lack of "written form".

**II. Textual Interpretation**
- **Key terms:** "written form"; "data message"; "by means such as electronic data interchange or email"
- **Ordinary meaning:**
  - "Written form": form recording content in writing or similar symbols, as opposed to oral form
  - "Data message": information generated, sent, received, or stored by electronic, optical, magnetic, or similar means
  - "等" in "等方式": open-ended enumeration, not exhaustive
- **Textual range:**
  - Core: contract instruments, letters, telegrams, telexes, faxes, email — uncontroversially written form
  - Peripheral: WeChat chat records — possibly covered by "such means"
  - Exclusion: pure oral conversation with no record — clearly not written form
- **Textual conclusion:** Art. 469, Para. 3 uses open-ended enumeration ("electronic data interchange, email, **and other such means**"); WeChat chat records, as an electronic communication method, can textually be covered by "such means". Further check whether the functional requirements ("tangibly express content" and "retrievable and usable at any time") are met.
- **Is textual interpretation determinate?** Basically yes, but functional requirements need further analysis.

**III. Systematic Interpretation**
- **Systemic position:** Art. 469 is in Contract Book, General Provisions, Ch. 2 "Formation of Contracts", governing contract form.
- **Related-provision analysis:**
  - Art. 469, Para. 1: parties may conclude contracts in written, oral, or other forms — establishes freedom of form.
  - *Electronic Signature Law* Art. 2, Para. 2: definition of data message — WeChat chat records fully fit.
  - *Civil Procedure Law* Art. 66 lists "electronic data" as a statutory evidence type.
  - SPC *Provisions on Evidence in Civil Litigation* Art. 14 expressly lists information in "instant messaging" as electronic data.
- **Systematic conclusion:** Within the legal system, WeChat chat records fall within "data message" and are recognized as a valid information carrier. Including them in "written form" creates no systemic conflict.

**IV. Teleological Interpretation**
- **Normative purpose:** Deeming data messages "written form" under Art. 469, Para. 3 aims to: (1) adapt to e-commerce and the information society; (2) protect transactional convenience; (3) ensure recordability and retrievability of contract content (core functions of written form).
- **Basis:** NPC Legislative Affairs Commission *Civil Code Commentary* states the clause aims to "adapt to modern information technology and recognize the written-form effect of data messages".
- **Teleological analysis:** WeChat chat records can record contract content in writing, can be retrieved at any time, and possess written form's core functions (fixation and retrievability). Treating them as written form fully fits the purpose of adapting to informatization.
- **Teleological conclusion:** Treating WeChat chat records as written form fits Art. 469, Para. 3's normative purpose.

**V. Comprehensive Balancing and Final Conclusion**

| Method | Conclusion | Weight |
|--------|------------|--------|
| Textual | WeChat chat records can be covered by "such means" | High |
| Systematic | WeChat chat records are system-recognized "data messages" | High |
| Teleological | Treating as written form fits normative purpose | High |

- **Final conclusion:** WeChat chat records are "data messages" under *Civil Code* Art. 469, Para. 3 and, if they "tangibly express the content carried and can be retrieved and used at any time", are deemed written form.
- **Core reasons:** They are generated, sent, received, and stored electronically, fitting the data-message definition; content is fixed in writing and retrievable; inclusion fits the purpose of adapting law to informatization.
- **Exclusion reasons:** Excluding them would empty the open-ended enumeration of Para. 3 and create systemic conflict with the *Electronic Signature Law* and *Civil Procedure Law*.
- **Additional conditions:** To be deemed written form, WeChat chat records must: (1) have complete content that tangibly expresses contract terms; (2) be retrievable and usable at any time (not deleted, or recoverable).

**VI. Confidence and Risk Notes**
- **Confidence:** 🟢 A (high)
- **Reasons:** Three methods converge; statutory support (*Electronic Signature Law*) and judicial-interpretation support; widely recognized in practice.
- **Risk notes:** Authenticity and integrity of WeChat records are evidence issues, not interpretation issues.

---

### Example 2: Complex Scenario — Criminal Interpretation of "By Other Methods Rendering the Victim Unable to Resist"

#### Background

Defendant A put sleeping pills in victim B's drink; after B fell asleep, A took B's valuable watch (worth RMB 50,000). The procuratorate charged robbery; defense argued theft. Dispute focus: does putting sleeping pills in a drink so the victim falls asleep, then taking property, fall within "robbery by other methods" under *Criminal Law* Art. 263?

#### Legal Interpretation Argumentation Opinion

**I. Interpretive Question**
- **Provision under interpretation:** *Criminal Law of the PRC* Art. 263
- **Statutory text:** "Whoever robs public or private property by violence, coercion, or **other methods** shall be sentenced to fixed-term imprisonment of not less than three years but not more than ten years and shall also be fined …"
- **Interpretive question:** Does secretly administering sleeping pills so the victim falls asleep, then taking property, fall within "other methods" in Art. 263?
- **Background:** Characterization directly affects the offense (robbery vs. theft), with significant differences in statutory penalties.

**II. Textual Interpretation**

- **Key term:** "other methods"
- **Ordinary meaning:** A catch-all referring to means other than violence or coercion; meaning must be fixed by reference to the preceding enumerated items (violence, coercion).
- **Textual-range analysis:**
  - Literally, "other methods" could cover any method, which would infinitely expand the offense — clearly unreasonable.
  - Apply the **ejusdem generis** rule: the catch-all "other methods" should be of the same type as "violence" and "coercion", sharing the same functional features.
  - Shared functional feature of violence and coercion: **suppressing the victim's ability or will to resist**.
  - Thus "other methods" should mean methods other than violence or coercion that **render the victim unable, afraid, or unaware to resist**.
- **Preliminary textual conclusion:** Administering sleeping pills so the victim loses consciousness and is "unaware to resist" can textually fall within "other methods".
- **Is textual interpretation determinate?** Basically yes, but further verification needed.

**III. Systematic Interpretation**

- **Systemic position:** Art. 263 is in Criminal Law special part, Ch. 5 "Crimes against Property".
- **Related-provision analysis:**
  - **Vs. theft (Art. 264):** Theft is "secret taking"; core is taking property in a manner the actor believes the victim does not notice. Robbery's core is obtaining property by suppressing resistance.
  - **Vs. snatching (Art. 267):** Snatching is open taking by surprise, not by suppressing resistance.
  - **Key distinction:** Whether the actor applied force to the victim's person (physical or psychological), causing loss of control over the property.
  - **SPC Guiding Opinions on Robbery Cases** expressly state: obtaining property by methods such as drug anesthesia so the victim is unaware to resist shall be punished as robbery.
  - **Art. 267, Para. 2:** Carrying a lethal weapon while snatching is punished under Art. 263 — showing that the degree of threat to personal safety is key to distinguishing robbery from other property crimes.

- **Systematic conclusion:** In the property-crime system, robbery's essence is applying force to the person to suppress resistance. Administering sleeping pills is neither "violence" nor "coercion", but its functional effect equals violence — complete loss of resistance. Including it in "other methods" fits robbery's place in the system.

**IV. Teleological Interpretation**

- **Normative purpose:**
  - **Direct purpose:** Art. 263 punishes obtaining property by suppressing the victim's resistance.
  - **Protected interest:** Robbery is a dual-interest crime protecting both property and personal rights — the root reason its statutory penalty is much heavier than theft.
  - **Legislative reason:** Heavier penalties because the actor not only invades property rights but also creates real danger to personal safety.

- **Teleological analysis:**
  - Administering sleeping pills so the victim falls asleep:
    - ✅ Invades property rights (taking the watch)
    - ✅ Invades personal safety (drugs may endanger health or even life)
    - ✅ Completely deprives the victim of control over the property
    - ✅ Applies force to the person (pharmacological force)
  - Treating this only as theft would fail to fully evaluate the invasion of personal safety, yielding disproportionate punishment.

- **Teleological conclusion:** Treating post-drugging taking as "other methods" of robbery fits dual-interest protection and the principle of proportionality between crime and punishment.

**V. Historical Interpretation**

- **Legislative history:** 1979 Criminal Law Art. 150 already used "violence, coercion, or other methods"; the 1997 revision retained this wording.
- **Legislative materials:** NPC Legislative Affairs Commission *Criminal Law Commentary*, explaining "other methods", expressly states: methods other than violence or coercion that render the victim unable or unaware to resist, such as drug anesthesia or intoxicating with alcohol.
- **Historical conclusion:** The legislature expressly lists "drug anesthesia" as a typical "other method"; administering sleeping pills is a form of drug anesthesia — historical interpretation clearly supports inclusion.

**VI. Criminal Special-Rule Check**

```
□ Principle of legality check:
  - Does interpreting administration of sleeping pills as "other methods" exceed the possible meaning of "other methods"?
  → No. "Other methods" is itself a catch-all; rendering the victim unaware to resist is of the same functional type as violence (unable to resist) and coercion (afraid to resist); it is interpretation within the text, not analogy.

□ Is it analogy adverse to the defendant?
  → No. It is expansive interpretation within the possible meaning of "other methods", not applying the provision to situations the text cannot cover (analogy).
    Distinguishing criterion: Could an ordinary citizen foresee that "other methods" might include drug anesthesia?
    Answer: yes.

□ Expansive interpretation vs. analogy:
  - Expansive interpretation: choosing a broader meaning within possible meanings ✅
  - Analogy: going beyond possible meanings to similar but different situations ✗
  - This case is expansive interpretation; it does not violate legality.
```

**VII. Comprehensive Balancing and Final Conclusion**

| Method | Conclusion | Weight | Notes |
|--------|------------|--------|-------|
| Textual | Sleeping pills can be covered by "other methods" | High | Supported by ejusdem generis |
| Systematic | Consistent with robbery's systemic place | High | Key vs. theft is personal compulsion |
| Teleological | Fits dual-interest protection | High | Proportionality of crime and punishment |
| Historical | Legislative commentary expressly lists "drug anesthesia" | High | Direct support |

- **Final conclusion:** Putting sleeping pills in the victim's drink so the victim falls asleep, then taking property, constitutes "robbery by other methods" under Art. 263 and shall be punished as robbery.
- **Core reasons:**
  1. "Other methods" should mean methods functionally equivalent to violence/coercion that render the victim unable / afraid / unaware to resist;
  2. Administering sleeping pills completely deprives resistance (unaware to resist), functionally equivalent to violence;
  3. The conduct invades both property and personal safety, fitting robbery's dual-interest purpose;
  4. Legislative commentary expressly lists "drug anesthesia" as a typical "other method".
- **Exclusion reasons:** Should not be theft, because theft is "secret taking" without personal compulsion. Here the actor applied pharmacological force to the person — a feature theft's elements cannot evaluate.
- **Response to defense:** Defense may argue the administration was "secret" and thus fits theft's "secret taking". That confuses "secrecy of the means" with "secrecy of the taking modality". Robbery's "other methods" may also be carried out secretly (e.g., secret poisoning); the key distinction is not secrecy but whether force was applied to the person.

**VIII. Confidence and Risk Notes**
- **Confidence:** 🟢 A (high)
- **Reasons:** Four methods fully converge; clear SPC guiding opinion; clear legislative listing; practice consensus on characterization.
- **Risk notes:**
  1. Watch whether the dose of sleeping pills was sufficient to cause sleep — a tiny dose causing only mild drowsiness may affect finding "unaware to resist".
  2. If the victim voluntarily took sleeping pills and fell asleep, and the actor then took property, it is not "robbery by other methods" (the actor did not render the victim unaware to resist) and should be theft.
  3. Watch whether the sleeping pills actually harmed the victim's health — may affect sentencing.

---

## Appendix: Quick Reference Card

### Interpretive Methods Quick Table

| Method | Core question | Typical materials | When to use |
|--------|---------------|-------------------|-------------|
| Textual | What does the statutory wording mean? | Dictionaries, grammar rules | All scenarios (starting point) |
| Systematic | How is the provision positioned in the system? | Related provisions, context | When text admits multiple meanings |
| Teleological | What goal does the provision pursue? | Purpose clauses, commentaries | When formal methods cannot decide |
| Historical | What was the legislator's original intent? | Legislative explanations, deliberation reports | When amended or newly enacted |
| Constitution-conforming | Which reading accords with the Constitution? | Constitutional text and principles | When interpretation may implicate fundamental rights |

### Three-Step Rapid Check for Interpretive Argumentation

```
Step 1: Is the conclusion within the range of possible meanings?
  → No = fatal error; correct immediately
  → Yes = go to Step 2

Step 2: Is the conclusion coherent with the legal system?
  → No = revisit or provide a conflict solution
  → Yes = go to Step 3

Step 3: Does the conclusion realize the normative purpose?
  → No = revisit
  → Yes = conclusion is basically reliable
```
