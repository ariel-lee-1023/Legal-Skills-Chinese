---
name: conflict-resolution
description: "Trigger this skill when an AI agent encounters any of the following during legal reasoning: (1) multiple legal provisions may apply to the same facts (concurrence of legal norms / 法条竞合); (2) contradictions or inconsistencies among different pieces of evidence (evidentiary conflict / 证据矛盾); (3) multiple disputed issues requiring a determination of hearing or analysis order (issue priority ranking / 争点优先级排序); (4) different sources of law (statutes, regulations, judicial interpretations, local regulations, etc.) providing divergent rules on the same question (conflict of legal sources / 法源冲突); (5) tension between a party's claims and legal application that requires coordination. This skill is a core hub capability for legal reasoning; nearly all complex legal analyses involve some form of conflict resolution."
---

> **Chinese source (authoritative):** [`../../skills/conflict-resolution/SKILL.md`](../../skills/conflict-resolution/SKILL.md)

# Conflict Resolution and Priority Determination

## Overview Table

| Item | Content |
|------|------|
| **Capability No.** | 20 |
| **Capability Name** | Conflict Resolution and Priority Determination |
| **Core Functions** | Handle concurrence of legal norms, evidentiary conflicts, and issue priority ranking |
| **Applicable Stages** | Full legal analysis workflow (especially legal application, fact-finding, and issue framing) |
| **Input Elements** | Set of concurrent provisions, set of conflicting evidence, list of disputed issues, case facts |
| **Output Elements** | Determination of the rule to apply preferentially, conclusions on evidence admission, issue ranking scheme and reasons |
| **Related Capabilities** | Statutory retrieval and matching, evidence analysis and fact-finding, legal relationship identification, claim-basis analysis |
| **Difficulty Level** | ★★★★★ (one of the highest-difficulty comprehensive judgment skills in legal reasoning) |
| **Risk Level** | Extremely high — erroneous judgment directly causes wrong legal application or skewed fact-finding |

---

## Legal Disclaimer

> **Important notice:** This skill file provides only structured guidance for AI agents engaged in legal reasoning and does not constitute legal advice. Conflict resolution and priority determination involve highly specialized legal judgment; final conclusions should be reviewed and confirmed by a licensed legal professional. AI agents should always annotate confidence levels in their outputs and, where major rights and interests are involved or substantial uncertainty exists, expressly advise the user to consult a qualified attorney.

---

## I. Core Conceptual Framework

### 1.1 Three Major Conflict Types

```
Conflict Resolution and Priority Determination
├── A. Concurrence of Legal Norms (Norm Conflict / 法条竞合)
│   ├── A1. Concurrence of provisions within the same statute
│   ├── A2. Norm conflicts between different statutes
│   ├── A3. Conflicts between sources of law of different hierarchical ranks
│   └── A4. Concurrence of claims (请求权竞合)
├── B. Evidentiary Conflict (Fact Conflict / 证据矛盾)
│   ├── B1. Conflicts among evidence of the same type
│   ├── B2. Conflicts among evidence of different types
│   ├── B3. Conflicts between direct and circumstantial evidence
│   └── B4. Conflicts between evidence and rules of experience (经验法则)
└── C. Issue Priority (Procedural / Logical Conflict / 争点优先级)
    ├── C1. Ordering of procedural vs. substantive issues
    ├── C2. Ordering of prerequisite vs. derivative issues
    ├── C3. Ordering of primary vs. secondary issues
    └── C4. Ordering of independent vs. related issues
```

### 1.2 Key Term Definitions

| Term | Definition | Example |
|------|------|------|
| **Concurrence of legal norms (法条竞合)** | The same facts simultaneously satisfy the constituent elements of two or more legal norms, producing different legal effects | A fraudulent act constitutes both grounds for rescission under contract law and fraud as a tort under tort law |
| **Imaginative concurrence (想象竞合)** | One act violates multiple criminal offenses (peculiar to criminal law) | Shooting and killing a hostage simultaneously constitutes intentional homicide and intentional destruction of property |
| **Statutory concurrence / narrow concurrence of norms (法规竞合 / 法条竞合·狭义)** | One act simultaneously satisfies multiple sets of constituent elements, but due to logical relationship only one applies | Fraud vs. contract fraud (general law vs. special law) |
| **Concurrence of claims (请求权竞合)** | The same facts give rise to multiple claim bases; the right-holder may choose which to exercise | Product-caused personal injury may be claimed as contractual breach or tort liability |
| **Norm conflict (规范冲突)** | Different legal norms provide different or even contradictory rules on the same matter | Inconsistency between higher-ranking and lower-ranking law |
| **Evidentiary conflict (证据矛盾)** | Two or more pieces of evidence prove mutually exclusive or inconsistent facts | Two witnesses give diametrically opposite accounts of the same event |
| **Disputed issue / 争点** | A fact issue or legal issue in dispute between the parties | Whether a contract was formed; how damages should be calculated |
| **Prerequisite issue (前提性争点)** | An issue whose conclusion determines whether other issues need to be heard | Whether the limitation period has expired (if expired, substantive issues need not be heard) |

### 1.3 Basic Principles of Conflict Resolution

```
Basic Principles of Conflict Resolution
├── Principle of hierarchical ranking of legal sources (法源位阶原则)
│   ├── Higher-ranking law prevails over lower-ranking law (Constitution > Laws > Administrative regulations > Local regulations > Rules)
│   └── Apply directly when hierarchical rank is clear
├── Special law prevails over general law (特别法优于一般法)
│   ├── At the same hierarchical rank, special provisions prevail over general provisions
│   └── Must confirm that a true “special” relationship exists (special subject, special subject matter, special time)
├── New law prevails over old law (新法优于旧法)
│   ├── Laws enacted by the same organ: new provisions prevail over old provisions
│   └── Note: When a new general provision conflicts with an old special provision, the matter must be referred for ruling
├── Non-retroactivity of law (法律不溯及既往)
│   ├── New law generally does not apply to conduct before its effective date
│   └── Exception: beneficial retroactivity (criminal law: old law with lighter punishment where more favorable / 从旧兼从轻)
├── Evidentiary preponderance principles
│   ├── Civil: high degree of probability (高度盖然性)
│   ├── Criminal: beyond reasonable doubt (排除合理怀疑)
│   └── Administrative: clear preponderance (明显优势)
└── Logical priority of issues (争点逻辑优先原则)
    ├── Procedure before substance
    ├── Prerequisite before derivative
    └── Primary before secondary
```

---

## II. Complete Workflow

### Stage Zero: Conflict Identification (Preliminary Judgment)

```
Step 0.1: Scan input materials and identify whether conflicts exist
  ├── Check whether multiple applicable provisions exist → possible concurrence of norms
  ├── Check whether evidence is inconsistent → possible evidentiary conflict
  ├── Check whether multiple disputed issues exist → issue ranking needed
  └── If no conflict → exit this skill and proceed to ordinary analysis

Step 0.2: Classify the conflict
  ├── Determine whether the conflict is Type A (norm concurrence), B (evidentiary conflict), or C (issue priority)
  ├── A single case may involve multiple conflict types simultaneously
  └── Record all identified conflicts and address them one by one
  
Step 0.3: Assess conflict severity
  ├── High: the conflict’s resolution will fundamentally change the case trajectory
  ├── Medium: the conflict affects handling of some issues
  └── Low: the conflict affects only details or supporting arguments
```

### Stage One: Resolving Concurrence of Legal Norms (Type A Conflicts)

```
Step A1: List all potentially applicable legal norms
  ├── Quote the full text of each provision
  ├── Annotate the hierarchical rank of each provision’s legal source
  ├── Annotate the enactment/amendment date of each provision
  └── Annotate the scope of application of each provision (general / special)

Step A2: Determine the type of concurrence
  ├── Is it a conflict between sources of different hierarchical ranks?
  │   └── Yes → apply “higher-ranking law prevails over lower-ranking law” → go to A3a
  ├── Is it a conflict between general and special law at the same rank?
  │   └── Yes → apply “special law prevails over general law” → go to A3b
  ├── Is it a conflict between new and old law of the same organ?
  │   └── Yes → apply “new law prevails over old law” → go to A3c
  ├── Is it a conflict between a new general provision and an old special provision?
  │   └── Yes → refer to the competent authority for ruling → go to A3d
  ├── Is it concurrence of claims?
  │   └── Yes → analyze pros and cons of each claim → go to A3e
  └── Is it concurrence under criminal law?
      └── Yes → distinguish imaginative concurrence from statutory concurrence → go to A3f

Step A3a: Higher-ranking law prevails over lower-ranking law
  ├── Confirm hierarchical relationships among legal sources
  │   Constitution > Laws > Administrative regulations > Local regulations > Rules
  │   (Note: Conflicts between local regulations and departmental rules must be referred for ruling)
  ├── Apply the higher-ranking provision
  └── Record: lower-ranking related provisions are not applied, and the reasons

Step A3b: Special law prevails over general law
  ├── Verify whether a true “special” relationship exists
  │   ├── Special subject: e.g., Consumer Rights and Interests Protection Law relative to the Civil Code
  │   ├── Special subject matter: e.g., Maritime Law relative to the Contracts Book of the Civil Code
  │   ├── Special region: e.g., regulations of special economic zones
  │   └── Special time: e.g., wartime special provisions
  ├── Confirm both are at the same hierarchical rank
  ├── Apply the special-law provision
  └── Record: possibility that general-law provisions may apply supplementarily

Step A3c: New law prevails over old law
  ├── Confirm both laws were enacted by the same organ
  ├── Confirm the new law has taken effect and applies to the temporal node of this case
  ├── Check whether the new law contains retroactivity clauses
  ├── Apply the new-law provision
  └── Record: old-law provisions no longer apply, and any transitional arrangements

Step A3d: Conflict between new general law and old special law
  ├── Confirm a true conflict exists (and that the new law does not already contain special provisions)
  ├── Principle: neither side may simply be applied
  ├── Handling:
  │   ├── Laws enacted by the Standing Committee of the NPC → refer to the NPC Standing Committee for ruling
  │   ├── Administrative regulations of the State Council → refer to the State Council for ruling
  │   └── Other situations → handle per the Legislation Law (立法法)
  ├── The AI agent should annotate: legal-application uncertainty exists here
  └── Advise the user to watch for the latest rulings or judicial interpretations

Step A3e: Handling concurrence of claims
  ├── List all possible claim bases
  ├── Compare and analyze each claim regarding:
  │   ├── Constituent elements (difficulty of proof)
  │   ├── Legal effects (scope and amount of damages)
  │   ├── Limitation periods
  │   ├── Competent court / jurisdiction
  │   ├── Allocation of burden of proof
  │   └── Other procedural differences
  ├── Recommend a choice based on maximizing the party’s interests
  ├── Note: Civil Code Art. 186 allows the party to choose
  └── Record: a pros-and-cons comparison table for each claim

Step A3f: Handling criminal-law concurrence
  ├── Distinguish imaginative concurrence from statutory concurrence
  │   ├── Imaginative concurrence: one act violates multiple offenses → punish under the heavier offense (从一重罪处断)
  │   └── Statutory concurrence: special law over general law (primary); heavier law over lighter law (supplementary)
  ├── Determine the statutory penalties for each offense
  ├── Apply the rules to determine the ultimately applicable offense
  └── Record: excluded offenses and reasons

Step A4: Form the conclusion on norm concurrence
  ├── Clearly state the ultimately applicable provision(s)
  ├── Explain reasons for excluding other provisions
  ├── Annotate confidence level
  └── Annotate whether referral to a competent authority for ruling is required
```

### Stage Two: Resolving Evidentiary Conflicts (Type B Conflicts)

```
Step B1: Identify and describe the contradiction
  ├── List mutually contradictory evidence
  ├── Clarify the specific content of the contradiction (which factual assertions are mutually exclusive)
  ├── Determine whether the contradiction is fundamental or merely detailed
  └── Determine whether the contradiction can be eliminated by a reasonable explanation

Step B2: Review of evidentiary competence / admissibility (前置过滤 / preliminary filter)
  ├── Review whether all conflicting evidence has evidentiary competence (legality)
  │   ├── Should it be excluded as illegally obtained evidence?
  │   ├── Does it meet statutory formal requirements?
  │   └── Was it submitted within the time limit for producing evidence?
  ├── If one side’s evidence lacks competence → exclude that evidence; contradiction resolved
  └── If both have competence → proceed to comparison of probative force

Step B3: Comparison of probative force (core step)
  ├── Apply general rules on relative probative force:
  │   ├── Official documentary evidence of state organs > other documentary evidence
  │   ├── Notarial instruments > ordinary documentary evidence
  │   ├── Original evidence > hearsay / transmitted evidence (传来证据)
  │   ├── Direct evidence > circumstantial evidence
  │   ├── Physical evidence, archives, expert opinions, inspection records, etc. > ordinary witness testimony
  │   ├── Testimony of witnesses without interest in the case > testimony of interested witnesses
  │   └── An evidentiary chain formed by multiple items > solitary evidence (孤证)
  ├── Factors to consider:
  │   ├── Reliability of the evidence’s source
  │   ├── Proximity in time between formation of the evidence and the case facts
  │   ├── Motives and interest relationships of the evidence provider
  │   ├── Internal consistency of the evidence
  │   ├── Degree of consistency with other established facts
  │   └── Whether the evidence has been cross-examined (质证)
  └── Form a preliminary judgment on relative strength of probative force

Step B4: Comprehensive fact-finding
  ├── Take the evidence with stronger probative force as the basis for fact-finding
  ├── Test whether that finding is consistent with other evidence and rules of experience
  ├── Apply the appropriate standard of proof:
  │   ├── Civil cases: high degree of probability (preponderance; commonly understood as >50% likelihood)
  │   ├── Criminal cases: beyond reasonable doubt (near certainty)
  │   ├── Administrative cases: clear preponderance of evidence
  │   └── Special situations: e.g., fraud, duress, etc. may require a higher standard of proof
  ├── If the contradiction cannot be resolved:
  │   ├── Apply burden-of-proof allocation rules
  │   ├── Basic principle: “who asserts, proves” (谁主张，谁举证)
  │   ├── Consider statutory situations of reversed burden of proof
  │   └── The party bearing the burden suffers the adverse consequence
  └── Form the fact-finding conclusion

Step B5: Form the conclusion on evidentiary conflict
  ├── Clearly state admitted evidence and reasons
  ├── Clearly state evidence not admitted and reasons
  ├── State the facts found
  ├── Annotate confidence level
  └── Annotate whether major uncertainty in fact-finding remains
```

### Stage Three: Issue Priority Ranking (Type C Conflicts)

```
Step C1: Identify and list issues
  ├── Extract issues from the parties’ claims for relief
  ├── Extract issues from defensive pleadings
  ├── Identify implied issues arising from legal application
  └── Form a complete issue list

Step C2: Classify issues
  ├── By nature:
  │   ├── Procedural issues (jurisdiction, standing, limitation periods, etc.)
  │   ├── Fact issues (whether and how facts occurred)
  │   └── Legal issues (how law applies and how it is interpreted)
  ├── By logical relationship:
  │   ├── Prerequisite issues (their conclusion determines whether subsequent issues need hearing)
  │   ├── Independent issues (no logical dependence on other issues)
  │   └── Derivative issues (depend on conclusions of prerequisite issues)
  └── By importance:
      ├── Core issues (directly determine the case outcome)
      ├── Important issues (significantly affect the case outcome)
      └── Auxiliary issues (affect only details or supporting arguments)

Step C3: Build an issue-dependency graph
  ├── Identify logical precedence among issues
  ├── Draw issue dependencies (directed acyclic graph)
  │   Example: whether contract formed → whether contract valid → how breach liability is borne
  ├── Identify independent issues that can be handled in parallel
  └── Identify “threshold issues” (if the conclusion is negative, many subsequent issues need not be heard)

Step C4: Apply ranking rules
  ├── First priority: procedural issues
  │   ├── Jurisdictional objections
  │   ├── Party standing / capacity
  │   ├── Limitation periods / exclusion periods (除斥期间)
  │   └── Other procedural defenses
  ├── Second priority: prerequisite fact issues
  │   ├── Whether a legal relationship was formed
  │   ├── Whether a juristic act is valid
  │   └── Whether a right exists
  ├── Third priority: core legal issues
  │   ├── Choice of applicable law
  │   ├── Interpretation of statutory provisions
  │   └── Determination of liability principles
  ├── Fourth priority: derivative issues
  │   ├── Scope of liability
  │   ├── Calculation of damages
  │   └── Proportional allocation of liability
  └── Fifth priority: auxiliary issues
      ├── Allocation of litigation costs
      ├── Modes of enforcement
      └── Other incidental matters

Step C5: Efficiency optimization
  ├── Identify “short-circuit” opportunities:
  │   ├── If the limitation period has expired → substantive issues may not need hearing
  │   ├── If the contract was not formed → breach-liability issues need not be heard
  │   └── If no tort is constituted → damages issues need not be heard
  ├── Assess analytical difficulty and certainty of each issue
  ├── Prioritize high-certainty “threshold issues” that can be resolved quickly
  └── Form the final ranking scheme

Step C6: Form the issue-priority conclusion
  ├── Output the ranked issue list (with numbers and priority labels)
  ├── Explain ranking reasons
  ├── Annotate dependencies among issues
  ├── Annotate possible “short-circuit” paths
  └── Annotate confidence level
```

### Stage Four: Comprehensive Conflict Resolution (When Multiple Conflict Types Coexist)

```
Step D1: Cross-analysis of conflicts
  ├── Check whether resolution of norm concurrence affects issue ranking
  ├── Check whether resolution of evidentiary conflict affects choice of norms
  ├── Check whether issue ranking affects priority of evidence review
  └── Identify mutual dependencies among conflicts

Step D2: Iterative resolution
  ├── First resolve the most foundational conflict (usually issue ranking)
  ├── Then resolve the conflict with the broadest impact
  ├── Finally resolve derivative conflicts
  ├── Check for circular dependencies (if any, consider them jointly)
  └── Iterate through multiple rounds if necessary until all conflicts are resolved

Step D3: Consistency check
  ├── Check whether all conflict-resolution conclusions are consistent with one another
  ├── Check whether the final conclusion accords with the internal logic of the legal system
  ├── Check for omitted conflicts
  └── Form the final comprehensive conclusion
```

---

## III. Common Domains and Sources of Law

### 3.1 Common Domains of Norm Concurrence

| Domain | Common Concurrence Situations | Primary Sources | Resolution Rule |
|------|-------------|---------|---------|
| **Contract disputes** | Concurrence between General Provisions and Specific Provisions of the Civil Code Contracts Book | Civil Code Arts. 463–988 | Specific Provisions prevail over General Provisions (special over general) |
| **Tort disputes** | Concurrence of breach liability and tort liability | Civil Code Art. 186 | Party has a right of choice |
| **Consumer protection** | Concurrence of Civil Code and Consumer Rights and Interests Protection Law | Consumer Protection Law, Civil Code | Consumer Protection Law prevails (special law) |
| **Labor disputes** | Concurrence of Labor Law and Labor Contract Law | Labor Law, Labor Contract Law | Labor Contract Law prevails (newer + special law) |
| **Company disputes** | Concurrence of Civil Code and Company Law | Civil Code, Company Law | Company Law prevails (special law) |
| **Intellectual property** | Concurrence among copyright, trademark, patent, and Anti-Unfair Competition Law | Individual IP statutes, Anti-Unfair Competition Law | Case-specific analysis; specialized laws usually prevail |
| **Criminal–civil crossover (刑民交叉)** | Same conduct involves both criminal offense and civil tort | Criminal Law, Civil Code | Criminal-first principle (先刑后民), with exceptions |
| **Administrative–civil crossover** | Validity of administrative acts affects civil legal relationships | Administrative regulations, Civil Code | Distinguish the validity status of the administrative act |

### 3.2 Primary Sources for Resolving Evidentiary Conflicts

| Source | Main Content | Applicable Scenario |
|------|---------|---------|
| Civil Procedure Law Arts. 66–81 | Types of evidence; burden of proof | Civil evidence review |
| SPC Interpretation on Application of the Civil Procedure Law | Detailed evidence rules | Civil evidence review |
| SPC Provisions on Evidence in Civil Litigation (2019 Amendment) | Rules for examination and determination of evidence | Resolving evidentiary conflicts in civil cases |
| Criminal Procedure Law Arts. 50–63 | Criminal evidence rules | Criminal evidence review |
| SPC Interpretation on Application of the Criminal Procedure Law | Examination and evaluation of criminal evidence | Resolving evidentiary conflicts in criminal cases |
| Administrative Litigation Law Arts. 33–43 | Administrative litigation evidence rules | Administrative evidence review |

### 3.3 Primary Sources for Issue Ranking

| Source | Relevant Provisions | Guiding Significance |
|------|---------|---------|
| Civil Procedure Law | Jurisdiction, acceptance, trial procedure | Legal basis for prioritizing procedural issues |
| SPC Provisions on Evidence in Civil Litigation Art. 51 | Summarizing disputed issues | Procedural basis for issue framing |
| Nine Minutes (九民纪要) — Minutes of the National Court Civil and Commercial Trial Work Conference | Handling of various difficult issues | Practical guidance for issue handling |
| Trial guidance of courts at all levels | Key points for similar-case adjudication | Reference for issue ranking in specific case types |

---

## IV. Verification and Screening Rules

### 4.1 Verification Rules for Norm Concurrence

```
Verification Rule A-1: Confirm hierarchical rank
  ├── Confirm the enacting organ of each legal norm
  ├── Confirm its position in the hierarchy of legal sources
  ├── Verify that the hierarchical judgment is correct
  └── Special attention: special status of SEZ regulations and autonomous regulations/separate regulations

Verification Rule A-2: Confirm special-law relationship
  ├── Confirm that the two laws truly stand in a general–special relationship
  ├── Verification standard: whether the special law’s scope of application is a proper subset of the general law’s scope
  ├── Caution: the two laws may stand in a crossing relationship rather than an inclusion relationship
  └── Where the relationship is crossing, “special law prevails over general law” cannot simply be applied

Verification Rule A-3: Confirm temporal effect
  ├── Confirm when the case facts occurred
  ├── Confirm effective and expiry dates of each legal norm
  ├── Confirm whether retroactivity clauses exist
  └── Confirm transitional provisions

Verification Rule A-4: Confirm concurrence of claims
  ├── Confirm that each claim basis is actually established (all constituent elements satisfied)
  ├── Confirm there is no statutory provision expressly excluding concurrence
  ├── Confirm whether the party has already made a choice
  └── Confirm whether the choice may be changed afterward
```

### 4.2 Verification Rules for Evidentiary Conflicts

```
Verification Rule B-1: Confirm genuineness of the contradiction
  ├── Confirm the contradiction is real rather than merely apparent
  ├── Check whether it can be eliminated by a reasonable explanation
  │   Example: two witnesses describe different times, which may be memory deviation rather than factual contradiction
  └── Distinguish fundamental contradictions from detailed differences

Verification Rule B-2: Confirm evidentiary competence
  ├── Confirm all conflicting evidence has evidentiary competence
  ├── Exclude illegally obtained evidence
  └── Exclude evidence that fails to meet statutory form

Verification Rule B-3: Confirm reasonableness of probative-force assessment
  ├── Confirm comparison of probative force followed statutory rules
  ├── Confirm all relevant factors were adequately considered
  └── Confirm the conclusion accords with rules of experience and logic

Verification Rule B-4: Confirm application of the standard of proof
  ├── Confirm the correct standard of proof was applied
  ├── Confirm the application of that standard was appropriate
  └── Special note: different facts in the same case may be subject to different standards of proof
```

### 4.3 Verification Rules for Issue Ranking

```
Verification Rule C-1: Confirm completeness of issues
  ├── Confirm no important issues were omitted
  ├── Confirm inclusion of issues not expressly raised by the parties but that must be examined as a matter of law
  └── Confirm inclusion of matters subject to ex officio examination by the court

Verification Rule C-2: Confirm dependency relationships
  ├── Confirm logical dependencies among issues are correct
  ├── Confirm no dependency relationships were omitted
  └── Confirm whether circular dependencies exist (if so, special handling is required)

Verification Rule C-3: Confirm reasonableness of ranking
  ├── Confirm procedural issues are ranked before substantive issues
  ├── Confirm prerequisite issues are ranked before derivative issues
  ├── Confirm “short-circuit” paths were correctly identified
  └── Confirm the ranking facilitates analytical efficiency
```

---

## V. Output Format Templates

### 5.1 Output Template for Norm-Concurrence Resolution

```markdown
## Norm Concurrence Analysis Report

### I. Identification of Concurrence
- **Type of concurrence:** [Hierarchical conflict / Special vs. general law / New vs. old law / Concurrence of claims / Criminal concurrence]
- **Provisions involved:**
  - Provision A: [Name of law] Art. X — [Summary] ([Rank / Enactment date / Scope])
  - Provision B: [Name of law] Art. Y — [Summary] ([Rank / Enactment date / Scope])
  - (Continue listing if more provisions)

### II. Analysis of Concurrence
- **Applicable resolution rule:** [Higher over lower / Special over general / New over old / Party’s right of choice / Punish under heavier offense / Other]
- **Analytical process:**
  [Explain in detail why that rule applies, including hierarchical comparison, special-relationship argumentation, temporal comparison, etc.]

### III. Conclusion
- **Provision preferentially applied:** [Name of law] Art. X
- **Provision(s) excluded:** [Name of law] Art. Y
- **Reasons for exclusion:** [Brief explanation]
- **Supplementary notes:** [Any provisions for supplementary application or other caveats]

### IV. Confidence: [High / Medium / Low] — [Specific sources of uncertainty]
```

### 5.2 Output Template for Evidentiary-Conflict Resolution

```markdown
## Evidentiary Conflict Analysis Report

### I. Identification of Contradiction
- **Description of contradiction:** [Specifically describe which evidence conflicts and how]
- **Nature of contradiction:** [Fundamental contradiction / Detailed difference / Explainable inconsistency]
- **Evidence involved:**
  - Evidence A: [Type] — [Summary of what it proves] ([Source / Formation time])
  - Evidence B: [Type] — [Summary of what it proves] ([Source / Formation time])

### II. Review of Evidentiary Competence
- Evidence A: [Has / Lacks] competence — [Reasons]
- Evidence B: [Has / Lacks] competence — [Reasons]

### III. Comparison of Probative Force
| Comparison Dimension | Evidence A | Evidence B | Advantage |
|---------|--------|--------|--------|
| Evidence type | | | |
| Source reliability | | | |
| Proximity to case facts | | | |
| Internal consistency | | | |
| Consistency with other evidence | | | |
| Provider’s interest relationship | | | |
| **Overall assessment** | | | |

### IV. Fact-Finding
- **Admitted evidence:** [Evidence A / Evidence B]
- **Reasons for admission:** [Detailed explanation]
- **Facts found:** [Facts found based on admitted evidence]
- **Standard of proof applied:** [High degree of probability / Beyond reasonable doubt / Clear preponderance]

### V. Confidence: [High / Medium / Low] — [Specific sources of uncertainty]
```

### 5.3 Output Template for Issue Priority Ranking

```markdown
## Issue Priority Ranking Report

### I. Issue List
| No. | Issue Content | Nature | Type | Importance |
|------|---------|------|------|--------|
| 1 | | Procedural / Fact / Legal | Prerequisite / Independent / Derivative | Core / Important / Auxiliary |
| 2 | | | | |
| ... | | | | |

### II. Dependencies
```
Issue 1 → Issue 3 → Issue 5
Issue 2 (independent)
Issue 4 → Issue 6
```

### III. Ranking Results
| Priority | Issue No. | Issue Content | Ranking Reason |
|--------|---------|---------|---------|
| 1 (highest) | | | |
| 2 | | | |
| ... | | | |

### IV. Short-Circuit Path Identification
- **Path 1:** If Issue [X] concludes [No], then Issues [Y, Z] need not be heard
- **Path 2:** [Other short-circuit paths, if any]

### V. Confidence: [High / Medium / Low] — [Specific sources of uncertainty]
```

---

## VI. Confidence Annotation System

### 6.1 Confidence Level Definitions

| Level | Marker | Meaning | Typical Scenarios |
|------|------|------|---------|
| **High** | 🟢 | Conflict-resolution rules are clear; application is undisputed; conclusion is highly determinate | Clear higher-vs.-lower law conflict; statutory rules expressly governing concurrence |
| **Medium** | 🟡 | Conflict-resolution rules are basically clear, but some interpretive room or factual uncertainty remains | Disputed identification of special-law relationship; comparison of probative force involves subjective judgment |
| **Low** | 🔴 | Conflict-resolution rules are unclear; major controversy or legal gap exists | New general vs. old special law conflict; evenly matched evidence; fundamental disagreement on legal interpretation |

### 6.2 Confidence Downgrade Factors

The presence of the following factors should lead to a lower confidence level:

```
Downgrade factor checklist:
├── Regarding norm concurrence:
│   ├── Involved norms were recently amended or are about to be amended
│   ├── Divergent adjudicative views among different courts
│   ├── New types of cases lacking precedents
│   ├── Contested identification of special-law relationship
│   └── Situations requiring referral to a competent authority for ruling
├── Regarding evidentiary conflicts:
│   ├── Probative force of conflicting evidence is close (evenly matched)
│   ├── Key evidence is missing
│   ├── Authenticity of the evidence itself is in doubt
│   ├── Technical issues requiring expert appraisal
│   └── Contested application of rules of experience
└── Regarding issue ranking:
    ├── Unclear dependencies among issues
    ├── Circular dependencies exist
    ├── Major disagreement among parties on issue definition
    └── Matters for ex officio court examination with uncertain scope
```

### 6.3 Confidence Annotation Norms

```
Annotation format:
[Confidence level] [Level marker] — [Brief reason]

Examples:
- Confidence: High 🟢 — Legislation Law Art. 92 expressly provides that special law prevails over general law; the special-law relationship in this case is clear
- Confidence: Medium 🟡 — Two expert opinions reach different conclusions; must comprehensively assess appraisal methods and appraiser qualifications
- Confidence: Low 🔴 — Divergent views among different adjudicative divisions of the Supreme People’s Court in this field; no unified opinion yet
```

---

## VII. Common Errors and Prevention

### 7.1 Fatal Error Table

| No. | Error Type | Error Description | Consequence | Preventive Measures |
|------|---------|---------|------|---------|
| F-01 | **Hierarchical ranking error** | Applying a lower-ranking provision as if it were higher-ranking, or misjudging hierarchical rank | Fundamental error in legal application | Strictly confirm hierarchical rank under the Legislation Law; annotate low confidence for uncertain ranking relationships |
| F-02 | **Misjudging special-law relationship** | Mistaking a crossing relationship for special–general and wrongly applying “special over general” | Excluding norms that should have applied | Strictly verify special-law relationship: the special law’s scope must be a proper subset of the general law’s scope |
| F-03 | **Ignoring temporal effect** | Failing to consider temporal effect and relying on law not yet in force or already repealed | Applying the wrong version of the law | Always confirm correspondence between when facts occurred and when the law took effect |
| F-04 | **Failure to exclude illegal evidence** | Including evidence lacking competence in the comparison of probative force | Fact-finding founded on an unlawful basis | Complete competence review before any comparison of probative force |
| F-05 | **Mixing standards of proof** | Applying the criminal standard in a civil case, or vice versa | Wrong standard for fact-finding | Clarify case nature and apply the corresponding standard of proof |
| F-06 | **Omitted issues** | Omitting key prerequisite issues so subsequent analysis rests on unverified assumptions | The entire analytical framework may collapse | Systematically extract issues from claims, defenses, and legal application |
| F-07 | **Circular reasoning** | Using resolution of Conflict A as a premise for Conflict B, and resolution of Conflict B as a premise for Conflict A | Invalid reasoning | Build a conflict-dependency graph and check for cycles; if cycles exist, consider jointly |
| F-08 | **Ignoring the party’s right of choice in claim concurrence** | Choosing for the party in claim concurrence instead of analyzing pros and cons of each option | May harm the party’s interests | Expressly inform the party of the right of choice and provide comparative analysis of options |

### 7.2 Common Traps

| No. | Trap Name | Description | Response Strategy |
|------|---------|------|---------|
| T-01 | **Apparent-concurrence trap** | Two provisions appear applicable, but careful analysis shows only one set of constituent elements is satisfied | Before finding concurrence, strictly check whether every provision’s constituent elements are fully met |
| T-02 | **Over-simplification trap** | Reducing complex multi-layer conflicts to a single conflict | Systematically identify all conflicts, build a conflict-relationship graph, and address them one by one |
| T-03 | **Authority-bias trap** | Admitting evidence solely because its source is authoritative, ignoring comprehensive analysis of other evidence | Authority is only one factor in probative force; comprehensive assessment is required |
| T-04 | **Hindsight trap** | Letting known conclusions influence issue ranking and advancing issues that should be heard later | Rank strictly by logical dependency, unaffected by prejudgment |
| T-05 | **General-clause escape trap** | Invoking a general clause (e.g., good faith) when a specific provision is available | General clauses apply only when specific provisions are lacking (principle of supplementary application) |
| T-06 | **Misranking judicial interpretations** | Equating SPC judicial interpretations with the hierarchical rank of statutes | Judicial interpretations rank below statutes but are binding in adjudication practice; locate them accurately |
| T-07 | **Oversimplifying local regulation vs. departmental rule conflicts** | Simply treating one side as prevailing | Under Legislation Law Art. 95, refer to the State Council for an opinion; cannot simply decide |
| T-08 | **Ignoring party autonomy** | In contract disputes, ignoring party agreements and directly applying default discretionary legal rules | In the realm of discretionary norms, party agreements prevail over statutory defaults |

---

## VIII. Special Scenario Handling

### 8.1 Criminal–Civil Crossover Cases (刑民交叉)

```
Processing workflow:
1. Identify whether the same facts simultaneously involve criminal and civil legal relationships
2. Determine whether the “criminal first, civil later” (先刑后民) principle applies
   ├── Applicable: fact-finding in the criminal case directly affects handling of the civil case
   ├── Not applicable:
   │   ├── Criminal and civil cases are based on different facts
   │   ├── The civil case does not presuppose the criminal conclusion
   │   └── The criminal case is long delayed, seriously impairing protection of civil rights
   └── Note: not all criminal–civil crossover cases must follow criminal-first
3. Analyze criminal and civil legal relationships separately
4. Note the preclusive effect of facts found in a criminal judgment on the civil case
5. Note the relationship between civil damages and incidental civil action in criminal proceedings
```

### 8.2 Administrative–Civil Crossover Cases

```
Processing workflow:
1. Identify how administrative acts affect civil legal relationships
2. Determine the validity status of the administrative act
   ├── Valid administrative act: generally respected in civil adjudication
   ├── Revoked administrative act: void ab initio; does not constrain civil judgment
   ├── Administrative act of uncertain validity:
   │   ├── Whether civil litigation must be stayed pending the administrative result
   │   └── Whether the civil court may incidentally review legality of the administrative act
   └── Invalid administrative act: the civil court may directly find it invalid
3. Note the public notice and good-faith effect of administrative registration (e.g., real-estate registration)
4. Note the effect of administrative licensing on the validity of civil contracts
```

### 8.3 Foreign-Related Conflicts of Law

```
Processing workflow:
1. Identify whether the case has foreign-related elements
2. Determine the applicable law (准据法)
   ├── Apply the Law on Application of Law to Foreign-Related Civil Relations
   ├── Apply relevant international treaties
   └── Apply the law chosen by the parties (party autonomy)
3. After determining the applicable law, resolve conflicts under the rules of that legal system
4. Note application of public-order reservation clauses
5. Note problems of ascertaining foreign law
```

### 8.4 Cases in the Transition Period Between Old and New Law

```
Processing workflow:
1. Determine when the case facts occurred
2. Determine when the new law took effect
3. Check transitional clauses of the new law
   ├── Clear transitional provisions → follow them
   ├── No transitional provisions → apply non-retroactivity
   └── Continuing legal relationships → may require segmented application
4. Check SPC judicial interpretations or notices on application of the new law
5. Note exceptions for “beneficial retroactivity”
```

### 8.5 Extreme Cases of Evenly Matched Evidence

```
Processing workflow:
1. Confirm that comparison of probative force truly cannot distinguish superior from inferior
2. Return to burden-of-proof allocation rules
   ├── Determine burden allocation in this case
   │   ├── General rule: “who asserts, proves”
   │   ├── Statutory reversed-burden situations
   │   └── Special burden allocations under judicial interpretations
   ├── The party bearing the burden suffers the adverse consequence
   └── Clearly annotate: fact-finding rests on burden allocation, not evidentiary preponderance
3. Annotate low confidence
4. Advise the party to supplement evidence or apply for appraisal / investigation and evidence collection
```

### 8.6 Complex Cases with Multiple Layers of Concurrence

```
Processing workflow:
1. List all concurrence relationships
2. Resolve layer by layer in the following order:
   ├── Layer 1: Resolve hierarchical conflicts among legal sources (most foundational)
   ├── Layer 2: Resolve special-vs.-general conflicts at the same rank
   ├── Layer 3: Resolve new-vs.-old law conflicts
   ├── Layer 4: Resolve concurrence of claims (involving party choice)
   └── Layer 5: Resolve remaining interpretive conflicts
3. After resolving each layer, check whether it affects analysis of other layers
4. Form the final legal-application scheme
5. Annotate overall confidence (usually no higher than the lowest confidence among layers)
```

---

## IX. Quality Checklists

### 9.1 Checklist for Norm-Concurrence Resolution

- [ ] Have all potentially applicable provisions been listed?
- [ ] Has the hierarchical rank of each provision’s legal source been accurately annotated?
- [ ] Has the enactment/amendment date of each provision been accurately annotated?
- [ ] Has the type of concurrence been correctly identified?
- [ ] Has the correct conflict-resolution rule been applied?
- [ ] Has identification of the special-law relationship been strictly verified?
- [ ] Have temporal-effect issues been considered?
- [ ] Has room for party autonomy been considered?
- [ ] Are there situations requiring referral to a competent authority for ruling?
- [ ] Is the conclusion consistent with the overall logic of the legal system?
- [ ] Has confidence been annotated?

### 9.2 Checklist for Evidentiary-Conflict Resolution

- [ ] Have all contradictions been accurately identified?
- [ ] Have fundamental contradictions been distinguished from detailed differences?
- [ ] Has competence review (preliminary filter) been completed?
- [ ] Has comparison of probative force followed statutory rules?
- [ ] Have all relevant factors been comprehensively considered?
- [ ] Has the correct standard of proof been applied?
- [ ] When evidence is evenly matched, has burden-of-proof allocation been correctly applied?
- [ ] Is fact-finding consistent with other established facts and rules of experience?
- [ ] Has confidence been annotated?

### 9.3 Checklist for Issue Ranking

- [ ] Is the issue list complete (no important issues omitted)?
- [ ] Is issue classification accurate?
- [ ] Have dependencies been correctly identified?
- [ ] Do circular dependencies exist?
- [ ] Are procedural issues ranked before substantive issues?
- [ ] Are prerequisite issues ranked before derivative issues?
- [ ] Have all “short-circuit” paths been identified?
- [ ] Does the ranking facilitate analytical efficiency?
- [ ] Has confidence been annotated?

### 9.4 Comprehensive Checklist

- [ ] Have all conflicts been identified and addressed?
- [ ] Are the resolution conclusions of each conflict consistent with one another?
- [ ] Have any cross-effects among conflicts been omitted?
- [ ] Does the final conclusion accord with the internal logic of the legal system?
- [ ] Have all uncertainties been annotated?
- [ ] Has the user been advised to consult a professional attorney where necessary?

---

## X. Complete Examples

### Example One: Simple Scenario — Concurrence of Claims in Product Liability

#### Facts

Zhang purchased an electric water heater at a shopping mall. Three months after use, a product quality defect caused electric leakage; Zhang was injured by electric shock, incurred RMB 50,000 in medical expenses and RMB 20,000 in lost wages, and suffered substantial mental distress. Zhang wishes to sue to protect his rights.

#### Conflict Identification

```
Conflict type: Type A — Concurrence of claims
Specific situation: Zhang may claim breach liability based on the sales contract,
         or claim product liability based on tort
Laws involved:
  - Civil Code Art. 577 (breach liability)
  - Civil Code Art. 1202 (product liability — producer)
  - Civil Code Art. 1203 (product liability — seller)
  - Civil Code Art. 186 (concurrence of breach and tort liability)
  - Consumer Rights and Interests Protection Law Arts. 40, 49, 51
Conflict severity: High — choosing different claims directly affects the scope and amount of damages
```

#### Norm-Concurrence Analysis

**Step A1: List possible claim bases**

| Claim Basis | Legal Basis | Constituent Elements | Legal Effect |
|-----------|---------|---------|---------|
| Breach liability | Civil Code Art. 577 | Valid formed contract + breach + damage | Damages (within contractual interest) |
| Product tort (sue producer) | Civil Code Art. 1202 | Product defect + damage + causation | Damages (including personal-injury damages) |
| Product tort (sue seller) | Civil Code Art. 1203 | Product defect + damage + causation + seller fault | Damages (including personal-injury damages) |
| Consumer protection | Consumer Protection Law Arts. 40, 49, 51 | Consumer status + product defect + damage | Damages + possible punitive damages |

**Step A2: Determine type of concurrence**

This case is concurrence of claims. Civil Code Art. 186 expressly provides: “Where a party’s breach of contract harms the other party’s personal rights and interests or property rights and interests, the injured party is entitled to choose to request that the party bear breach liability or tort liability.”

**Step A3e: Comparative analysis of claims**

| Comparison Dimension | Breach Path | Tort Path | Consumer Protection Path |
|---------|------------|------------|-----------|
| **Defendant** | Mall (contractual counterpart) | Producer and/or mall | Mall and/or producer |
| **Burden of proof** | Zhang proves breach | Zhang proves defect + damage + causation (producer bears no-fault liability) | Similar to tort; consumer’s burden may be lighter |
| **Scope of damages** | Losses within contractual interest | Personal-injury damages (medical, lost wages, nursing, etc.) + mental distress damages | Personal-injury damages + mental distress damages + possible punitive damages |
| **Mental distress damages** | ❌ Generally not supported | ✅ May be claimed | ✅ May be claimed |
| **Punitive damages** | ❌ Not applicable | ✅ Civil Code Art. 1207 (knowingly producing/selling defective products) | ✅ Consumer Protection Law Art. 55 (triple damages for fraud) |
| **Limitation period** | 3 years | 3 years (from knowledge or constructive knowledge) | 3 years |
| **Jurisdiction** | Place of performance or defendant’s domicile | Place of tort or defendant’s domicile | Same as tort |

**Conclusion**

```markdown
## Norm Concurrence Analysis Report

### I. Identification of Concurrence
- **Type of concurrence:** Concurrence of claims (breach liability vs. tort liability)
- **Provisions involved:**
  - Civil Code Art. 577 (breach liability)
  - Civil Code Arts. 1202, 1203 (product liability)
  - Consumer Rights and Interests Protection Law Arts. 40, 49, 51
  - Civil Code Art. 186 (concurrence handling rule)

### II. Analysis of Concurrence
Under Civil Code Art. 186, Zhang is entitled to choose to request breach liability or tort liability.
Meanwhile, as a consumer, Zhang may also invoke the special protections of the Consumer Rights and Interests Protection Law.

### III. Conclusion
- **Recommended preferred path:** Tort liability path + Consumer Rights and Interests Protection Law
- **Reasons:**
  1. The tort path allows mental distress damages (generally unavailable on the breach path)
  2. Product liability is no-fault liability, with a relatively lighter burden of proof
  3. The Consumer Protection Law offers possible additional punitive damages
  4. Both producer and seller may be sued, expanding the range of liable parties
- **Excluded path:** Pure breach-liability path (narrower damages, excluding mental distress)
- **Supplementary notes:** Final choice should be determined in light of specific evidence and litigation strategy

### IV. Confidence: High 🟢 — Claim-concurrence rules are clear; pros and cons of each path are distinct
```

---

### Example Two: Complex Scenario — Multiple Conflicts in a Construction Project Dispute

#### Facts

Company A (employer) and Company B (contractor) entered into a construction project contract with a total contract price of RMB 30 million. After completion, the parties disputed the following:

1. Company B lacked the corresponding construction qualifications; Company C (which had qualifications) actually performed the work under an affiliation / 挂靠 arrangement
2. Company A asserts quality defects and submitted a testing report it commissioned unilaterally (Report A)
3. Company B submitted another testing report (Report B) concluding the quality was compliant
4. Company A has paid RMB 20 million; Company B claims Company A still owes the remaining RMB 10 million plus interest for late payment
5. Company A counterclaims for RMB 5 million in damages for quality defects
6. Company A also asserts the contract is void and demands return of amounts already paid

#### Conflict Identification

```
Conflict 1 (Type A): Concurrence of legal application after contract invalidity
  - Civil Code Art. 157 (legal consequences of invalid contracts)
  - Construction Project Judicial Interpretation (I) Art. 1 (contracts without qualifications are void)
  - Construction Project Judicial Interpretation (I) Art. 24 (invalid contract but project accepted as qualified)

Conflict 2 (Type B): Evidentiary conflict between two testing reports
  - Report A (commissioned by Company A): quality noncompliant
  - Report B (commissioned by Company B): quality compliant

Conflict 3 (Type C): Priority ranking among multiple issues
  - Contract validity, project quality, payment of contract price, damages, and other issues

Conflict severity: All High — resolution of each conflict will fundamentally affect the case trajectory
```

#### Stage Three: Issue Priority Ranking (Handle Type C First)

**Steps C1–C2: Issue identification and classification**

| No. | Issue Content | Nature | Type | Importance |
|------|---------|------|------|--------|
| ① | Does Company B have construction qualifications? Is Company C’s affiliation established? | Fact | Prerequisite | Core |
| ② | Is the construction project contract valid? | Legal | Prerequisite | Core |
| ③ | Is the project quality compliant? | Fact | Prerequisite | Core |
| ④ | Must Company A pay the remaining RMB 10 million? | Legal | Derivative (depends on ②③) | Core |
| ⑤ | Must Company B compensate RMB 5 million for quality defects? | Legal | Derivative (depends on ③) | Important |
| ⑥ | May Company A demand return of the RMB 20 million already paid? | Legal | Derivative (depends on ②③) | Core |
| ⑦ | How is interest for late payment calculated? | Legal | Derivative (depends on ④) | Auxiliary |

**Step C3: Dependency graph**

```
① Qualifications / affiliation facts → ② Contract validity
                                          ↓
③ Project quality ──────→ ④ Payment of contract price → ⑦ Interest calculation
    ↓                          ↓
    ⑤ Quality-defect damages    ⑥ Return of amounts paid
```

**Steps C4–C5: Ranking results**

| Priority | Issue | Ranking Reason |
|--------|------|---------|
| 1 | ① Qualifications / affiliation facts | Prerequisite fact issue determining contract-validity analysis |
| 2 | ② Contract validity | Prerequisite legal issue determining the framework for all subsequent issues |
| 3 | ③ Project quality | Prerequisite fact issue determining payment and damages |
| 4 | ④ Payment of contract price | Core derivative issue |
| 4 | ⑤ Quality-defect damages | Core derivative issue (parallel with ④) |
| 4 | ⑥ Return of amounts paid | Core derivative issue (parallel with ④⑤) |
| 5 | ⑦ Interest calculation | Auxiliary derivative issue |

**Short-circuit path identification:**
- Path 1: If Issue ② concludes the contract is valid → Issue ⑥ (return of amounts paid) need not be heard
- Path 2: If Issue ③ concludes quality is compliant → Issue ⑤ (quality-defect damages) need not be heard
- Note: Even if the contract is void, under Construction Project Judicial Interpretation (I) Art. 24, if the project is accepted as qualified, payment may still refer to the contractual price terms; thus Issue ②’s conclusion does not fully “short-circuit” Issue ④

#### Stage One: Norm-Concurrence Resolution (Type A Conflict)

**Legal-application analysis for Issue ②:**

```
Provisions involved:
1. Civil Code Art. 153: Civil juristic acts violating mandatory provisions of laws and administrative regulations are void
2. Civil Code Art. 157: Return of property and compensation for losses after a civil juristic act is void
3. Construction Law Art. 26: Prohibits undertaking projects without qualifications or beyond qualification grade
4. Construction Project Judicial Interpretation (I) Art. 1: Contracts signed by an unqualified actual constructor borrowing the name of a qualified construction enterprise are void
5. Construction Project Judicial Interpretation (I) Art. 24: Where a construction project contract is void but the project has been accepted as qualified, compensation to the contractor may refer to the contractual terms on project price

Concurrence analysis:
- Construction Law Art. 26 is a mandatory provision of validity effect (效力性强制性规定) → violation renders the contract void
- Construction Project Judicial Interpretation (I) Art. 1 concretizes the above for judicial application
- Construction Project Judicial Interpretation (I) Art. 24 is a special rule on consequences of contract invalidity
  → Relative to the general rule in Civil Code Art. 157, it is a special provision
  → Apply “special law prevails over general law”

Conclusion:
- The contract is void due to affiliated construction (borrowing qualifications)
- Post-invalidity handling: do not apply the general restitution rule of Civil Code Art. 157;
  apply the special rule of Construction Project Judicial Interpretation (I) Art. 24
- That is: if the project is accepted as qualified, pay the contract price by reference to the contract
```

#### Stage Two: Evidentiary-Conflict Resolution (Type B Conflict)

**Evidence analysis for Issue ③:**

```
Contradiction identification:
- Report A (issued by a testing institution unilaterally commissioned by Company A): project quality noncompliant, multiple defects
- Report B (issued by another testing institution unilaterally commissioned by Company B): project quality compliant

Nature of contradiction: Fundamental — the two reports reach diametrically opposite conclusions on the same project’s quality

Competence review:
- Report A: unilaterally commissioned appraisal; the opposing party did not participate in the cross-examination process,
  but as documentary evidence it has competence
- Report B: same — unilaterally commissioned appraisal
- Conclusion: both reports have competence, but both are unilaterally commissioned, so probative force is limited

Comparison of probative force:
| Comparison Dimension | Report A | Report B | Advantage |
|---------|-------|-------|--------|
| Evidence type | Unilaterally commissioned testing report | Unilaterally commissioned testing report | Even |
| Testing institution qualifications | To be verified | To be verified | Pending |
| Testing methods | To be verified | To be verified | Pending |
| Testing time | To be verified | To be verified | Pending |
| Commissioning party’s interest | Company A (benefits from finding noncompliance) | Company B (benefits from finding compliance) | Even (both interested) |
| Cross-examined with opposing participation | No | No | Even |

Overall assessment: The two reports are close in probative force; both are unilaterally commissioned and involve commissioning-party interests;
quality compliance cannot be determined from existing evidence alone.

Handling plan:
1. Recommend applying for judicial appraisal — the court commissions a qualified appraisal institution to appraise project quality
2. Before a judicial appraisal conclusion is issued, neither report alone can serve as the basis for finding project quality
3. If the parties do not apply for appraisal:
   ├── Company A asserts noncompliance (counterclaim for damages) and bears the burden of proof
   ├── Existing evidence is insufficient to meet the high-degree-of-probability standard
   └── Company A may bear the adverse consequence of failure of proof
```

#### Comprehensive Conclusion

```markdown
## Comprehensive Conflict Resolution Report

### I. Issue Ranking
Hear in the order ①→②→③→④⑤⑥→⑦.

### II. Norm-Concurrence Resolution
The contract is void due to borrowing qualifications (affiliation), but post-invalidity handling
applies the special rule of Construction Project Judicial Interpretation (I) Art. 24,
not the general restitution rule of Civil Code Art. 157.

### III. Evidentiary-Conflict Resolution
The two unilaterally commissioned testing reports are close in probative force; recommend judicial appraisal.
Until an appraisal conclusion is issued, the project-quality issue remains unresolved.

### IV. Case Trajectory Analysis

**Scenario One: Appraisal finds quality compliant**
- Although the contract is void, by reference to the contract Company A should pay the remaining RMB 10 million
- Company A’s claim for return of the RMB 20 million already paid is not supported
- Company A’s counterclaim for RMB 5 million in quality-defect damages is not supported
- Interest for late payment is calculated under applicable rules

**Scenario Two: Appraisal finds quality noncompliant**
- Further distinguish whether the noncompliant portion can be repaired
  ├── Repairable: pay the contract price after deducting repair costs
  └── Not repairable and unusable: Company A may claim return of amounts paid and damages

### V. Confidence
- Issue ranking: High 🟢 — Logical dependencies are clear
- Norm concurrence: High 🟢 — Judicial interpretation is clear; practice is uniform
- Evidentiary conflict: Low 🔴 — Existing evidence insufficient to find facts; judicial appraisal needed
- Overall confidence: Medium 🟡 — Ultimate trajectory depends on the project-quality appraisal conclusion

### VI. Recommendations
1. Promptly apply for judicial appraisal to resolve the project-quality issue
2. Collect evidence of the affiliation relationship (contracts, fund flows, actual constructor, etc.)
3. Attend to Company C’s (actual constructor’s) procedural status and rights claims
4. Advise consulting an attorney specializing in construction projects
```

---

## Appendix: Quick Decision Tree

```
Quick judgment path when a conflict is encountered:

Q1: What type is the conflict?
├── Multiple provisions all applicable → Type A (norm concurrence) → go to Q2
├── Evidence mutually contradictory → Type B (evidentiary conflict) → go to Q5
├── Multiple issues need ranking → Type C (issue priority) → go to Q7
└── Multiple types coexist → first handle Type C ranking, then handle Types A and B in order

Q2: Do the concurrent provisions belong to different hierarchical ranks?
├── Yes → Higher-ranking law prevails over lower-ranking law → End
└── No → go to Q3

Q3: Do the concurrent provisions stand in a special–general relationship?
├── Yes → Special law prevails over general law → End
└── No → go to Q4

Q4: Do the concurrent provisions stand in a new–old law relationship?
├── Yes (and enacted by the same organ) → New law prevails over old law → End
├── New general law vs. old special law conflict → Refer to competent authority for ruling; annotate low confidence → End
└── Concurrence of claims → Analyze pros and cons of each claim; inform the party of the right of choice → End

Q5: Does all conflicting evidence have evidentiary competence?
├── Some lacks competence → Exclude that evidence; contradiction resolved → End
└── All have competence → go to Q6

Q6: Can comparison of probative force distinguish superior from inferior?
├── Yes → Admit the evidence with stronger probative force → End
└── No (evenly matched) → Apply burden-of-proof allocation rules → End

Q7: Do procedural issues exist?
├── Yes → Procedural issues have highest priority → go to Q8
└── No → go to Q8

Q8: Do prerequisite issues exist?
├── Yes → Prerequisite issues prevail over derivative issues → go to Q9
└── No → Rank by importance → End

Q9: Are there “short-circuit” opportunities?
├── Yes → Prioritize issues that may produce a “short-circuit” effect → End
└── No → Rank by logical dependency → End
```

---

> **Version information:** v1.0  
> **Last updated:** 2024  
> **Applicable-law cutoff:** Always verify that cited laws and regulations remain currently in force  
> **Usage reminder:** This skill involves some of the most complex judgments in legal reasoning. AI agents should remain modest in their outputs, clearly annotate uncertainty, and in complex cases advise the user to seek professional legal advice.
