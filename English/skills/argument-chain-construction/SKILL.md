---
name: argument-chain-construction
description: |
  Trigger this skill when an AI agent needs to organize legal reasoning results into a complete, internally consistent, and persuasive argumentative structure.
  Typical trigger scenarios include, but are not limited to:
  - Drafting the argumentative sections of legal documents such as legal opinions, written submissions (代理词), defense briefs (辩护词), and answers/pleadings (答辩状)
  - Answering complex legal questions from the user that require multi-step reasoning and a presented conclusion
  - Systematically analyzing disputed issues and constructing a complete reasoning path from facts to law to conclusion
  - Rebutting an opposing view by constructing an alternative argument chain
  - Conducting comprehensive analysis of multiple legal issues while ensuring logical consistency and non-contradiction among arguments
  - Presenting analytical conclusions in a legal research memorandum
  Trigger-signal keywords: argument, analysis, reasoning, why, prove, grounds/reasons, discourse, articulate a position, legal analysis
---

> **Chinese source (authoritative):** [`../../skills/argument-chain-construction/SKILL.md`](../../skills/argument-chain-construction/SKILL.md)

# Constructing Rigorous Argument Chains

## Overview Table

| Item | Content |
|------|------|
| **Capability name** | Constructing rigorous argument chains |
| **Capability type** | Organization and expression of legal reasoning |
| **Core objective** | Organize dispersed elements of legal reasoning (facts, norms, judgments) into a complete, internally consistent, and persuasive argumentative structure |
| **Input** | Case facts, relevant legal norms, preliminary reasoning conclusions, disputed issues |
| **Output** | A structured argument chain containing a complete reasoning path of major premise → minor premise → conclusion |
| **Quality standards** | Logical validity, truth of premises, completeness of argumentation, internal consistency, persuasiveness |
| **Difficulty level** | ★★★★★ (core integrative capability of legal reasoning) |
| **Prerequisite capabilities** | Legal research, statutory interpretation, fact-finding, analysis of legal relationships, claim-basis analysis (请求权基础分析) |

## Legal Disclaimer

> **Important notice:** This skill guides AI agents in constructing legal argument chains. Its output is for reference only and does not constitute formal legal advice. Whether a legal argument is ultimately adopted depends on the specific case facts, the adjudicative tendencies of the competent court, and the parties’ litigation strategy. Users should adjust the output in light of a practicing lawyer’s professional judgment. AI-generated argument chains should always state a confidence level and flag possible alternative argumentative paths.

---

## I. Core Concepts

### 1.1 What Is an Argument Chain

An argument chain (Chain of Legal Argumentation) is a structured expression that organizes the process of legal reasoning in a logically rigorous way. A complete argument chain should enable the reader to start from known premises and, along a clear logical path, arrive at the conclusion necessarily or with a high degree of probability.

### 1.2 Basic Unit of an Argument Chain: the Argument Node

Each argument node (Argument Node) contains three elements:

```
┌─────────────────────────────────┐
│      Argument Node Structure    │
├─────────────────────────────────┤
│  Major Premise                  │
│  → Legal norm / legal principle │
│    / adjudicative rule          │
│                                 │
│  Minor Premise                  │
│  → Case facts / evidential      │
│    findings                     │
│                                 │
│  Conclusion                     │
│  → Legal effect / legal         │
│    evaluation                   │
└─────────────────────────────────┘
```

### 1.3 Relationship Between Argument Chains and Argument Nodes

```
Conclusion of Node A ──→ Minor premise of Node B (or part of its major premise)
                              │
                              ▼
                         Conclusion of Node B ──→ Minor premise of Node C
                                                       │
                                                       ▼
                                                  Final conclusion
```

An argument chain is a complete reasoning structure formed by linking multiple argument nodes in series or in parallel according to their logical dependencies.

### 1.4 Five Quality Dimensions of an Argument Chain

| Dimension | Meaning | Verification method |
|------|------|----------|
| **Logical validity** | The conclusion can be logically derived from the premises | Check for logical fallacies |
| **Truth of premises** | The major premise (legal norm) and minor premise (facts) are true or adequately supported | Verify that statutes are currently in force; facts are supported by evidence |
| **Completeness of argumentation** | No critical reasoning steps are omitted | Check for “leap” reasoning |
| **Internal consistency** | No contradictions among argument nodes | Cross-compare premises and conclusions across nodes |
| **Persuasiveness** | The argument can effectively persuade the target audience | Assess rhetorical effect and authority of the argument |

---

## II. Complete Workflow

### Phase One: Argument Preparation

#### Step 1: Clarify the Argumentative Goal

```
Ask yourself:
□ What am I trying to prove? (What is the ultimate conclusion?)
□ For whom am I arguing? (Plaintiff / defendant / third party / the court?)
□ Who is the target audience? (Judge / arbitrator / opposing party / client?)
□ What is the argumentative context? (Litigation / non-contentious / advisory / academic?)
□ What rebuttals might the other side raise?
```

#### Step 2: Inventory Argument Materials

Classify and organize all available reasoning materials:

| Material type | Specific content | Source |
|----------|----------|------|
| Legal norms | Specific statutory provisions; judicial interpretation provisions | Legal research results |
| Legal principles | Good faith (诚实信用), fairness, etc. | Legal theory |
| Adjudicative rules | Holdings / rationes from guiding cases and gazette cases | Case research results |
| Case facts | Established facts; facts supported by evidence | Evidentiary materials |
| Scholarly views | Theoretical views of authoritative scholars | Academic literature |

#### Step 3: Identify Disputed Issues

```
Framework for identifying disputed issues:
1. Factual disputes: On which facts do the parties disagree?
2. Disputes over applicable law: Which statute / which provision should apply?
3. Disputes over legal interpretation: Are there different readings of the same provision?
4. Disputes over legal characterization: How should the same facts be characterized in law?
5. Disputes over legal effects: What legal consequences should follow?
```

### Phase Two: Argument Architecture Design

#### Step 4: Choose the Argument Structure Type

Select the structure best suited to the argumentative goal:

**Structure A: Sequential Chain**

```
Applicable scenarios: Single claim basis; clear causal chain
Structure: A → B → C → D → final conclusion
Features: Each step depends on the conclusion of the previous step
```

**Structure B: Parallel Support**

```
Applicable scenarios: Multiple independent grounds supporting the same conclusion
Structure:
  Ground 1 ─┐
  Ground 2 ─┼→ final conclusion
  Ground 3 ─┘
Features: Any one ground may suffice to support the conclusion; strengthens argumentative resilience
```

**Structure C: Hierarchical Progression**

```
Applicable scenarios: Complex legal relationships; multi-level analysis
Structure:
  Level 1: Characterization of the legal relationship
    └→ Level 2: Element-by-element analysis of constitutive requirements
         └→ Level 3: Derivation of legal effects
              └→ Final conclusion
Features: From macro to micro, progressing layer by layer
```

**Structure D: Defensive Architecture**

```
Applicable scenarios: Need to address opposing rebuttals
Structure:
  Main argument chain ──→ conclusion
       │
       ├── Anticipated rebuttal 1 → Response 1
       ├── Anticipated rebuttal 2 → Response 2
       └── Anticipated rebuttal 3 → Response 3
Features: Proactively anticipate and neutralize opposing attacks
```

**Structure E: Alternative Chain**

```
Applicable scenarios: Uncertainty in the claim; need for fallback options
Structure:
  Main argument chain (preferred path) ──→ Conclusion A
  Alternative chain 1 (if a premise of the main chain fails) ──→ Conclusion B
  Alternative chain 2 (if alternative 1 also fails) ──→ Conclusion C
Features: Embodies a “fallback” litigation strategy
```

**Structure F: Composite**

```
Applicable scenarios: Complex cases
Structure: Combination of the structures above
```

#### Step 5: Draft the Argument Blueprint

Before formal construction, draft an overall blueprint of the argument:

```
Argument blueprint template:
═══════════════════════════════════════
Argumentative goal: [Ultimate conclusion to be proved]
═══════════════════════════════════════
Argument structure type: [Selected structure type]
───────────────────────────────────────
List of argument nodes:
  Node 1: [Brief description] → Output: [Conclusion of this node]
  Node 2: [Brief description] → Output: [Conclusion of this node]  
  Node 3: [Brief description] → Output: [Conclusion of this node]
  ...
───────────────────────────────────────
Node dependencies:
  Node 2 depends on the conclusion of Node 1
  Node 3 depends on the conclusion of Node 2
───────────────────────────────────────
Predicted weak links:
  [Mark the node(s) in the chain most likely to be attacked]
═══════════════════════════════════════
```

### Phase Three: Argument Node Construction

#### Step 6: Construct Each Argument Node One by One

For each argument node, perform the following:

**6a. Establish the Major Premise**

```
Major-premise construction checklist:
□ Is the statutory provision currently in force? (Check whether amended or repealed)
□ Does the provision apply to the temporal scope of this case? (Temporal effect of law)
□ Does the provision apply to the territorial scope of this case? (Spatial effect of law)
□ Does the provision apply to the subjects in this case? (Personal effect of law)
□ Does the meaning of the provision require interpretation? (If so, which interpretive method?)
□ Is there a situation in which special law prevails over general law (特别法优于一般法)?
□ Is there a conflict between superior and inferior law (上位法与下位法)?
```

**6b. Establish the Minor Premise**

```
Minor-premise construction checklist:
□ Are the facts supported by evidence?
□ Does the evidence have legality, authenticity, and relevance?
□ Is fact-finding disputed?
□ Is factual presumption required? (If so, on what basis?)
□ Do the case facts fully cover the constitutive elements of the legal norm in the major premise?
```

**6c. Perform Subsumption**

Subsumption is the process of bringing the minor premise (facts) under the major premise (legal norm):

```
Subsumption operation template:
Major premise: Legal norm R provides that when elements a, b, and c are satisfied, legal effect E arises.
Minor premise:
  - Case fact F1 satisfies element a because [specific reasons]
  - Case fact F2 satisfies element b because [specific reasons]
  - Case fact F3 satisfies element c because [specific reasons]
Conclusion: This case satisfies all constitutive elements of legal norm R; legal effect E should arise.
```

**6d. Draw the Node Conclusion**

```
Requirements for stating a node conclusion:
□ The conclusion is clear and unambiguous
□ The logical relationship between conclusion and premises is clear
□ The degree of certainty of the conclusion is marked (necessary / highly probable / possible / doubtful)
□ The conclusion can serve as input to the next node
```

#### Step 7: Connect Argument Nodes

Connect the nodes according to the dependencies in the blueprint:

```
Connection checklist:
□ Does the conclusion of the prior node fully become a premise of the next node?
□ Is there a logical leap at the connection?
□ Is transitional argumentation needed at the connection?
□ Are there contradictions among nodes?
```

### Phase Four: Argument Reinforcement

#### Step 8: Strengthen Weak Links

Reinforce the weak links predicted in the argument blueprint:

| Weakness type | Strengthening method |
|----------|----------|
| Uncertain major premise | Supplement interpretive argumentation; cite authoritative doctrine; invoke analogous cases |
| Disputed minor premise | Supplement evidence analysis; apply rules of experience; invoke burden-of-proof rules |
| Disputed subsumption | Supplement analogical, teleological, and systematic argumentation |
| Alternative conclusions possible | Proactively raise and rebut alternative conclusions |

#### Step 9: Build a Defensive Layer

```
Steps for building a defensive layer:
1. List possible opposing rebuttal points (at least 3)
2. Prepare a response to each rebuttal point
3. Embed the responses at appropriate places in the argument chain
4. Ensure responses do not contradict the main argument
```

#### Step 10: Add Auxiliary Arguments

```
Types of auxiliary argumentation:
- Analogical argumentation: Invoke adjudicative outcomes in similar cases
- Argumentum a contrario (反面论证): Argue the unreasonableness of the opposite conclusion
- Teleological argumentation: Support the argument from legislative purpose
- Systematic argumentation: Support from the internal consistency of the legal system
- Historical argumentation: Support from legislative history
- Comparative-law argumentation: Refer to approaches in other jurisdictions (auxiliary)
- Interest-balancing argumentation: Support from balancing of interests
- Social-effect argumentation: Support from the social effects of adjudication
```

### Phase Five: Argument Verification

#### Step 11: Logical Validity Check

Screen one by one for the following logical fallacies:

| Fallacy type | Manifestation | Example |
|----------|------|------|
| **Affirming the consequent** | Inferring that the premise holds because the conclusion holds | “The contract is void, so there must have been fraud” |
| **Denying the antecedent** | Inferring that the conclusion fails because the premise fails | “There is no written contract, so no contract was formed” |
| **Circular reasoning** | Using the conclusion to prove the premise | “The act is unlawful because it is illegal” |
| **Slippery slope** | Improperly deriving extreme consequences | “Allowing this exception will collapse the legal system” |
| **Straw man** | Distorting the opposing view and then rebutting it | Mischaracterizing the opponent’s claim and then criticizing it |
| **Appeal to authority** | Improperly relying on authority instead of reasoning | Treating something as correct merely because a scholar said so |
| **Hasty generalization** | Deriving a general rule from a single case | Deriving a universal rule from one precedent |
| **False dichotomy** | Ignoring intermediate possibilities | “Either fully support the plaintiff or dismiss all claims” |
| **Equivocation / concept-switching** | The same term means different things in different places | “Damage” denotes different contents at different nodes |
| **Causal fallacy** | Incorrectly establishing causation | Treating temporal sequence as causation |

#### Step 12: Completeness Check

```
Completeness checklist:
□ Does every constitutive element have corresponding factual argumentation?
□ Are there unargued implicit premises?
□ Have defenses been considered and responded to?
□ Has allocation of the burden of proof been clarified?
□ Have limitation / prescription issues been addressed?
□ Have procedural issues been addressed?
□ Has necessary analysis of legal relationships been omitted?
```

#### Step 13: Consistency Check

```
Consistency check method:
1. Extract the conclusions of all argument nodes into a list
2. Compare pairwise for contradictions
3. Check whether the same concept is used consistently across nodes
4. Check whether the legal evaluation of the same fact is consistent
5. Check whether the argumentative stance is consistent throughout
```

### Phase Six: Argument Presentation

#### Step 14: Organize the Order of Presentation

```
Principles for order of presentation:
1. Strongest points first (primacy effect)
2. Next-strongest points last (recency effect)
3. Weaker points in the middle
4. Argumentation on disputed issues at the core position
5. Background argumentation at the beginning
6. Summarizing argumentation at the end
```

#### Step 15: Draft the Argument Text

Follow these expression norms:

```
Argument expression norms:
□ Present each argument node in an independent paragraph or numbered section
□ Clearly cite the legal basis of the major premise (precise to article, paragraph, and item)
□ Clearly cite the factual basis of the minor premise (precise to evidence number)
□ Use logical connectives to mark reasoning relations (therefore, thus, accordingly, in sum)
□ Give clear definitions of key terms
□ Give adequate reasons for contested judgments
□ Distinguish certain conclusions from probabilistic conclusions
□ Use a numbering system to make argumentative levels clear
```

---

## III. Common Domains and Sources of Law

| Legal domain | Typical argument structure | Core sources of law | Argumentative focus |
|----------|-------------|----------|----------|
| **Contract disputes** | Claim-basis analysis (hierarchical progression) | Contract Book of the Civil Code (《民法典》合同编) | Formation → effectiveness → performance → breach → liability |
| **Tort disputes** | Element-by-element analysis (sequential chain) | Tort Liability Book of the Civil Code (《民法典》侵权责任编) | Act → damage → causation → fault |
| **Criminal defense** | Defensive architecture + alternative argumentation | Specific offenses in the Special Part of the Criminal Law (《刑法》分则) | Elements not satisfied / justification (违法阻却) / excuse (责任阻却) |
| **Criminal prosecution** | Sequential chain + parallel support | Special Part of the Criminal Law + judicial interpretations | Argue the four elements of crime / three-tier structure one by one |
| **Administrative litigation** | Legality review framework (hierarchical progression) | Administrative Litigation Law (《行政诉讼法》) | Authority → procedure → facts → application of law → discretion |
| **Company disputes** | Composite structure | Company Law (《公司法》) + judicial interpretations | Subject qualification → validity of resolutions → attribution of liability |
| **Labor disputes** | Parallel support + alternative argumentation | Labor Contract Law (《劳动合同法》) + judicial interpretations | Employment relationship → rights and duties → damages calculation |
| **Intellectual property** | Hierarchical progression + analogical argumentation | Patent Law / Trademark Law / Copyright Law | Right basis → infringement comparison → defenses → damages |
| **Marriage and family** | Composite structure | Marriage and Family Book of the Civil Code (《民法典》婚姻家庭编) | Status relationships → property division → child custody |

---

## IV. Verification and Screening Rules

### 4.1 Admission Rules for Argument Nodes

Each argument node must pass the following admission tests before it may be included in the argument chain:

```
Admission tests (all must pass for inclusion):
[Required] The major premise has a clear legal basis or a generally recognized legal principle
[Required] The minor premise is supported by evidence or is an undisputed fact
[Required] The conclusion can be logically derived from the premises
[Required] The node does not contradict other nodes in the argument chain
[Recommended] The node’s conclusion makes a substantial contribution to the ultimate argumentative goal
[Recommended] The node can withstand reasonable challenge from the opposing side
```

### 4.2 Overall Verification Rules for the Argument Chain

```
Overall verification (all must pass before output):
[Required] The argument chain can reach the preset argumentative goal
[Required] No logical breaks (every step has a basis)
[Required] No internal contradictions
[Required] All key disputed issues have been addressed
[Required] All legal bases are currently in force
[Recommended] Main rebuttals have been considered and responded to
[Recommended] Weak links and confidence levels have been marked
[Recommended] Alternative argumentative paths have been provided (where applicable)
```

### 4.3 Priority for Screening Argument Materials

```
Priority from high to low:
1. Express statutory provisions (mandatory norms)
2. Express provisions of judicial interpretations
3. Guiding cases of the Supreme People’s Court
4. Gazette cases of the Supreme People’s Court
5. Trial guidance opinions of provincial high courts (limited to the relevant jurisdiction)
6. Prevailing views of authoritative scholars
7. Comparative-law references (auxiliary only)
```

---

## V. Output Format Templates

### Template A: Standard Argument-Chain Output

```markdown
## Argument Chain: [Brief statement of the argumentative goal]

### Argument Summary
- **Argumentative goal:** [Ultimate conclusion to be proved]
- **Argument structure:** [Structure type adopted]
- **Overall confidence:** [High / Medium / Low] + [percentage range]
- **Key disputed issues:** [List 1–3]

### Argument Development

#### Step 1: [Title of Argument Node 1]

**Major premise (legal basis):**
Pursuant to Article X, Paragraph X of the [Name of Law]: “[Original text of the provision].”

**Minor premise (case facts):**
In this case, [specific fact description]. This fact is proved by [evidence name/number].

**Subsumption and reasoning:**
[Concrete argumentation bringing the facts under the legal norm]

**Node conclusion:**
Therefore, [conclusion of this node].

**Confidence:** [High / Medium / Low]
**Potential rebuttal:** [Possible opposing rebuttal and brief response]

---

#### Step 2: [Title of Argument Node 2]
[Same format as above]

---

#### Step N: [Title of the final argument node]
[Same format as above]

### Argument Summary Wrap-Up

**Final conclusion:**
In sum, through the above [N] steps of argumentation, it follows that: [complete statement of the final conclusion].

**Assessment of argumentative strength:**
- Strongest link: [Identify]
- Weakest link: [Identify]
- Overall evaluation: [Evaluation]

**Alternative argumentative paths:**
If [a certain link] of the above argument is not accepted, consider the following alternatives:
- Alternative path 1: [Brief description]
- Alternative path 2: [Brief description]

**Risk warnings:**
[List the main risk points in the argument]
```

### Template B: Adversarial Argument Output (Litigation Scenario)

```markdown
## Argument Chain: [Our litigation claim]

### I. Our Main Argument

#### (I) [First disputed issue]
1. **Legal basis:** [Provision]
2. **Factual foundation:** [Facts + evidence]
3. **Argumentative process:** [Subsumptive reasoning]
4. **Sub-conclusion:** [Node conclusion]

#### (II) [Second disputed issue]
[Same as above]

### II. Possible Opposing Rebuttals and Our Responses

#### (I) The other side may contend: [Rebuttal point 1]
**Our response:** [Responsive argumentation]

#### (II) The other side may contend: [Rebuttal point 2]
**Our response:** [Responsive argumentation]

### III. Alternative Arguments (Fallback Plans)

#### Alternative Plan One: [Brief description]
[Argument development]

#### Alternative Plan Two: [Brief description]
[Argument development]

### IV. Conclusion
[Final conclusion and litigation recommendations]
```

---

## VI. Confidence Annotation System

### 6.1 Single-Node Confidence

| Level | Marker | Meaning | Judgment criteria |
|------|------|------|----------|
| **High** | 🟢 | The node’s argumentation is reliable; low likelihood of being overturned | Clear legal basis + undisputed facts + unambiguous subsumption |
| **Medium** | 🟡 | The node’s argumentation is basically reliable, but some room for dispute remains | Clear legal basis but contested interpretation, or some factual dispute |
| **Low** | 🔴 | The node’s argumentation involves substantial uncertainty | Unclear legal basis, major factual dispute, or major disagreement on subsumption |

### 6.2 Overall Argument-Chain Confidence

```
Calculation rules:
- Overall confidence ≤ confidence of the weakest node in the chain (barrel principle)
- In a parallel-support structure, overall confidence may exceed that of any single supporting ground
- The existence of alternative arguments can raise the resilience score of the overall argument

Annotation format:
Overall confidence: 🟡 Medium (approx. 60%–75%)
Weak link: Step 3 (causation argumentation), confidence 🔴 Low
Recommendation: Focus on strengthening evidence and argumentation on causation
```

### 6.3 Factors Affecting Confidence

```
Factors that raise confidence:
+ Express statutory provision with no interpretive dispute
+ Support from SPC guiding cases
+ Facts proved by direct evidence
+ Multiple independent grounds supporting the same conclusion
+ The other side can hardly raise an effective rebuttal

Factors that lower confidence:
- Vague statutory language requiring interpretation
- Only circumstantial evidence
- Strong opposing views exist
- Subsumption involves value judgments
- Reliance on analogical application
- No precedent available
```

---

## VII. Common Errors and Prevention

### 7.1 Fatal Error Table

| No. | Error name | Error description | Consequence | Preventive measure |
|------|----------|----------|------|----------|
| F01 | **Invalid statute** | Citing a repealed or amended provision as the major premise | Entire argument node is invalid | Verify current validity before every statutory citation |
| F02 | **Logical break** | Unargued leaps in the argument chain | Argument fails | Stepwise check whether each reasoning step has a basis |
| F03 | **Internal contradiction** | Conclusions of different nodes contradict each other | Argument collapses on itself | Perform consistency cross-checks after completion |
| F04 | **Omitted constitutive elements** | Failure to argue all constitutive elements of the legal norm | Argument incomplete; conclusion fails | List and verify every constitutive element one by one |
| F05 | **Unsupported facts** | Facts in the minor premise lack evidential support | Weak argumentative foundation | Annotate corresponding evidence for every factual assertion |
| F06 | **Changing the issue** | Departing from the original argumentative goal during argumentation | Argument invalid | Periodically revisit the argumentative goal to avoid drift |
| F07 | **Circular reasoning** | Using the conclusion to be proved as a premise of the argument | Argument invalid | Check whether any premise depends on the conclusion |

### 7.2 Common Traps

| No. | Trap name | Description | Response |
|------|----------|------|----------|
| T01 | **Over-argumentation** | Lengthy argumentation of obvious points that need no argument | Distinguish propositions that need argument from those that do not |
| T02 | **Argument stacking** | Listing many grounds without logical organization | Design the structure first, then fill in content |
| T03 | **Strength indifference** | Mixing strong and weak points, lowering overall persuasiveness | Distinguish strength; consider deleting weak points |
| T04 | **Ignoring rebuttal** | Building only affirmative arguments without considering opposing rebuttals | Mandatorily perform the “how would the other side rebut?” thinking step |
| T05 | **Concept drift** | The meaning of the same legal concept changes across argument nodes | Clearly define key concepts at the start of the argument |
| T06 | **Authority dependence** | Over-relying on authoritative views without independent reasoning | Treat authoritative views as auxiliary; rely on reasoning at the core |
| T07 | **Selective citation** | Citing only favorable statutes/cases and ignoring unfavorable ones | Proactively research and respond to unfavorable sources of law |
| T08 | **Conclusion first** | Reaching a conclusion first and then finding reasons, producing strained argumentation | Keep an open mind; let argumentation lead to the conclusion |
| T09 | **Confused levels** | Mixing argumentation of different levels | Strictly organize according to the levels in the argument blueprint |
| T10 | **Overconfidence** | Stating uncertain conclusions too absolutely | Use confidence annotations; distinguish certain from uncertain |

---

## VIII. Special Scenario Handling

### 8.1 Legal Gap Scenarios

```
When the law has no express provision:
1. First confirm whether a true legal gap exists (exclude incomplete research)
2. Attempt analogical application of the closest legal norm
3. Invoke legal principles (e.g., good faith, public order and good morals (公序良俗))
4. Refer to legislative purpose for teleological extension or restriction
5. Refer to authoritative doctrine and comparative law
6. Clearly mark: argumentation here is based on analogy / principle application; lower confidence accordingly
```

### 8.2 Legal Conflict Scenarios

```
When different legal norms conflict:
1. Apply conflict-resolution rules:
   - Superior law prevails over inferior law (上位法优于下位法)
   - Special law prevails over general law (特别法优于一般法)
   - Later law prevails over earlier law (新法优于旧法)
2. If conflict-resolution rules cannot be applied directly, conduct interest balancing
3. In the argument, clearly state the conflict and the path to resolution
4. Annotate confidence and provide alternative argumentation
```

### 8.3 Factual Uncertainty Scenarios

```
When key facts are disputed or evidence is insufficient:
1. Clarify allocation of the burden of proof
2. Distinguish “proved facts” from “facts to be proved”
3. For facts to be proved, construct arguments under both “established” and “not established” hypotheses
4. Apply rules of experience and factual presumptions (where applicable)
5. In the argument, clearly mark how factual uncertainty affects the conclusion
```

### 8.4 Multi-Party Scenarios

```
When complex legal relationships involve multiple parties:
1. First clarify the legal relationships among the parties
2. Construct separate argument chains targeting different parties
3. Check consistency among the argument chains
4. Note argumentation requirements for special liability forms such as joint and several liability and supplementary liability
5. Ensure the argument covers all necessary parties
```

### 8.5 Novel Case Scenarios

```
When encountering novel cases without precedent:
1. Construct argumentation from basic legal principles
2. Seek the closest analogous cases for analogical argumentation
3. Apply methods of legal interpretation (especially teleological and systematic interpretation)
4. Refer to cutting-edge academic views
5. Conduct interest-balancing and value-judgment argumentation
6. Clearly mark the innovativeness and uncertainty of the argumentation
7. Provide multiple alternative argumentative paths
```

### 8.6 Argumentative-Goal Adjustment Scenarios

```
When the original goal becomes difficult to achieve during argumentation:
1. Do not force construction of an unsustainable argument
2. Honestly assess the reasons for the difficulty
3. Consider adjusting the argumentative goal (e.g., reducing the claim)
4. Construct alternative argument chains pointing to the adjusted goal
5. Clearly explain to the user the difficulty of arguing the original goal and the recommendation
```

---

## IX. Quality Checklist

### Final Check After Completing the Argument

```
═══════════════════════════════════════════════
Argument Chain Quality Checklist
═══════════════════════════════════════════════

【Logical dimension】
□ Each node’s conclusion can be logically derived from its premises
□ No known logical fallacies exist
□ No logical leaps or breaks in the argument chain
□ No contradictions among argument nodes
□ The same concept has a consistent meaning throughout

【Legal dimension】
□ All cited statutory provisions are currently in force
□ Statutory citations are precise to article, paragraph, and item
□ Methods of legal interpretation are properly applied
□ The relationship between special and general law has been considered
□ Temporal effect of law has been considered

【Factual dimension】
□ Every factual assertion has corresponding evidential support
□ Undisputed facts and disputed facts have been distinguished
□ Burden of proof is correctly allocated
□ Fact-finding accords with rules of experience

【Completeness dimension】
□ All constitutive elements have been argued one by one
□ Main defenses have been considered and responded to
□ Limitation / prescription issues have been considered
□ Procedural issues have been considered
□ The argument covers all disputed issues

【Expression dimension】
□ Argument structure is clear; levels are distinct
□ Logical connectives are used accurately
□ Key terms have clear definitions
□ Depth of argumentation is appropriate
□ Conclusions are stated clearly and unambiguously

【Risk dimension】
□ Weak links of the argument have been marked
□ Confidence of each node and of the whole has been annotated
□ Alternative argumentative paths have been provided (where applicable)
□ Main risk points have been flagged
□ Opposing rebuttal strategies have been considered

═══════════════════════════════════════════════
Check result: □ All passed  □ Issues present (list issue numbers)
═══════════════════════════════════════════════
```

---

## X. Complete Examples

### Example One: Simple Scenario — Damages for Breach of a Sales Contract

**Case brief:**
Company A and Company B entered into a goods sales contract providing that Company B would deliver 100 devices by 1 March 2024 at a unit price of RMB 100,000, for a total price of RMB 10,000,000. The contract stipulated liquidated damages for late delivery at 0.05‰ of the total contract price per day. Company B actually delivered on 1 April 2024, 31 days late. Company A demanded that Company B pay liquidated damages of RMB 155,000. Company B defended that the liquidated damages were excessively high and requested a reduction.

---

```markdown
## Argument Chain: Company A Is Entitled to Require Company B to Pay Liquidated Damages of RMB 155,000

### Argument Summary
- **Argumentative goal:** Prove that Company A is entitled, pursuant to the contract, to require Company B to pay late-delivery liquidated damages of RMB 155,000, and that such liquidated damages should not be reduced
- **Argument structure:** Hierarchical progression + defensive argumentation
- **Overall confidence:** 🟡 Medium (approx. 65%–80%; principal uncertainty is whether liquidated damages will be reduced)
- **Key disputed issue:** Whether the agreed liquidated damages are excessively high

### Argument Development

#### Step 1: A Valid Sales Contract Relationship Exists Between A and B 🟢

**Major premise (legal basis):**
Pursuant to Article 469 of the Civil Code of the People’s Republic of China, parties may conclude a contract in written form, oral form, or other forms. Article 595 provides that a sales contract is a contract under which the seller transfers ownership of the subject matter to the buyer and the buyer pays the price. Article 502, Paragraph 1 provides that a contract formed in accordance with law becomes effective upon formation.

**Minor premise (case facts):**
Company A and Company B executed a written goods sales contract stipulating the principal terms including the subject matter (100 devices), the price (total RMB 10,000,000), and the delivery time (by 1 March 2024). Both parties had the corresponding capacity for civil conduct, their expressions of intent were genuine, and the contract content neither violated mandatory provisions of laws or administrative regulations nor contravened public order and good morals.

**Subsumption and reasoning:**
The contract in this case has the basic elements of a sales contract (transfer of subject matter + payment of price); the parties’ expressions of intent concurred; the contract content is lawful and meets the statutory conditions for formation and effectiveness of a contract.

**Node conclusion:**
A lawful and valid sales contract relationship exists between A and B.

**Confidence:** 🟢 High — formation and effectiveness of the contract are undisputed

---

#### Step 2: Company B’s Late Delivery Constitutes Breach 🟢

**Major premise (legal basis):**
Pursuant to Article 509, Paragraph 1 of the Civil Code, the parties shall fully perform their obligations in accordance with the agreement. Article 577 provides that where a party fails to perform a contractual obligation or performs in a manner inconsistent with the agreement, it shall bear liability for breach including continued performance, remedial measures, or compensation for losses.

**Minor premise (case facts):**
The contract provided for delivery by 1 March 2024. Company B’s actual delivery date was 1 April 2024, 31 days late.

**Subsumption and reasoning:**
Company B failed to deliver within the contractually agreed period, which constitutes “performance inconsistent with the agreement” and thus breach. The number of days late is 31 (from 2 March 2024 through 1 April 2024).

**Node conclusion:**
Company B delivered 31 days late and thereby breached the contract.

**Confidence:** 🟢 High — the fact of breach is clear and undisputed

---

#### Step 3: Company A Is Entitled Under the Contract to Claim Liquidated Damages of RMB 155,000 🟢

**Major premise (legal basis):**
Pursuant to Article 585, Paragraph 1 of the Civil Code, the parties may agree that upon breach one party shall pay the other a certain amount of liquidated damages according to the circumstances of the breach, or may agree on a method for calculating the amount of compensation for losses arising from the breach.

**Minor premise (case facts):**
The contract stipulated late-delivery liquidated damages at 0.05‰ of the total contract price per day. Total contract price RMB 10,000,000; 31 days late. Calculation: RMB 10,000,000 × 0.05% × 31 days = RMB 155,000.

**Subsumption and reasoning:**
The parties clearly agreed on the method for calculating liquidated damages; that agreement was their genuine expression of intent and does not violate mandatory legal provisions. Calculated as agreed, liquidated damages are RMB 155,000. Company A is entitled to claim such liquidated damages pursuant to the contract.

**Node conclusion:**
Company A is entitled under the contract to claim liquidated damages of RMB 155,000 from Company B.

**Confidence:** 🟢 High — the agreement is clear and the calculation is correct

---

#### Step 4: The Agreed Liquidated Damages Are Not “Excessively Higher Than the Losses Caused” and Should Not Be Reduced 🟡

**Major premise (legal basis):**
Pursuant to Article 585, Paragraph 2 of the Civil Code, where the agreed liquidated damages are excessively higher than the losses caused, the people’s court or arbitration institution may, upon a party’s request, appropriately reduce them. Pursuant to Article 65 of the Interpretation of the Supreme People’s Court on Several Issues Concerning the Application of the General Provisions of the Contract Book of the Civil Code of the People’s Republic of China, where a party asserts that the agreed liquidated damages are excessively high and requests an appropriate reduction, the people’s court shall take actual losses as the basis, comprehensively consider factors including the status of contract performance, the degree of the parties’ fault, and expected interests, measure the matter in accordance with the principles of fairness and good faith, and render a ruling. Where the parties’ agreed liquidated damages exceed 30% of the losses caused, they may generally be found to be “excessively higher than the losses caused.”

**Minor premise (case facts and loss analysis):**
- Amount of liquidated damages: RMB 155,000
- Total contract price: RMB 10,000,000
- Liquidated damages as a percentage of total contract price: 1.55%
- A daily rate of 0.05‰ converts to an annualized rate of approximately 18.25%, which, though higher than the LPR, is a common stipulation in commercial contracts
- Losses Company A may have suffered from late delivery include: production delay losses from idle equipment, possible downstream breach risk, etc.

**Subsumption and reasoning:**
First, the absolute amount of liquidated damages (RMB 155,000) is a low proportion (1.55%) of the total contract price (RMB 10,000,000) and is not extraordinarily high. Second, a daily rate of 0.05‰ is a common stipulation in commercial contracts and reflects the parties’ reasonable expectation of the cost of breach. Third, Company A’s actual losses from late delivery (production delay, downstream breach risk, etc.) may be no less than RMB 155,000. Even taking actual losses as the basis, RMB 155,000 can hardly be found to “exceed 30% of the losses caused.”

Further, Company B, as the breaching party asserting a reduction of liquidated damages, bears the burden of proving that the liquidated damages are “excessively higher than” Company A’s actual losses. If Company B cannot prove that Company A’s actual losses were far below RMB 155,000, its reduction request should not be upheld.

**Node conclusion:**
Agreed liquidated damages of RMB 155,000 are not “excessively higher than the losses caused”; Company B’s reduction request should not be upheld.

**Confidence:** 🟡 Medium — whether liquidated damages are excessively high falls within judicial discretion and involves some uncertainty. Judging from the amount ratio and industry practice, however, the likelihood of reduction is relatively low.

**Potential rebuttal and response:**
- **Rebuttal:** Company B may contend that Company A suffered no actual loss.
- **Response:** Liquidated damages serve both compensatory and punitive functions; even if Company A cannot precisely prove the amount of actual loss, that does not mean there was no loss. Late delivery necessarily causes capital occupation costs and lost commercial opportunities. One purpose of a liquidated damages clause is precisely to relieve the non-breaching party of the burden of proving loss.

---

### Argument Summary Wrap-Up

**Final conclusion:**
In sum, (1) a valid sales contract relationship exists between A and B; (2) Company B’s 31-day late delivery constitutes breach; (3) Company A is entitled under the contract to claim liquidated damages of RMB 155,000; and (4) such liquidated damages are not excessively higher than actual losses and should not be reduced. Therefore, Company A’s claim that Company B pay liquidated damages of RMB 155,000 should be upheld.

**Assessment of argumentative strength:**
- Strongest links: Steps 1–3 (contract relationship, fact of breach, liquidated damages calculation), all 🟢 High confidence
- Weakest link: Step 4 (whether liquidated damages are excessively high), 🟡 Medium confidence
- Overall evaluation: The argument chain is complete and logically clear; the principal risk is the court’s discretion to reduce liquidated damages

**Alternative argumentative paths:**
If the court finds the liquidated damages excessively high and reduces them, consider:
- Alternative path 1: Argue for calculating liquidated damages by reference to four times the LPR as a benchmark
- Alternative path 2: Supplement evidence of Company A’s actual losses (production delay losses, downstream breach compensation, etc.) and argue for determining liquidated damages on the basis of actual losses

**Risk warnings:**
1. Courts have discretion to reduce liquidated damages; adjudicative standards may differ across courts
2. Company A is advised to prepare evidence of actual losses to respond to Company B’s reduction request
3. If Company A’s actual losses are indeed far below RMB 155,000, there is a risk of reduction
```

---

### Example Two: Complex Scenario — Corporate Executive’s Breach of Non-Compete Obligations

**Case brief:**
Zhang was the Chief Technology Officer (CTO) of Tech Company A (registered capital RMB 50,000,000), held 5% of the company’s equity, and was a senior management officer of the company. Zhang entered into an employment contract and a non-compete agreement with Company A, stipulating that for two years after departure Zhang would not work for competing enterprises in the same industry; non-compete compensation would be paid monthly at 30% of average wages for the 12 months before departure; and liquidated damages for breach would be RMB 1,000,000. In January 2024, Zhang left Company A. In March 2024, Zhang caused Tech Company B to be registered in the name of Zhang’s spouse Li; Company B’s business scope highly overlapped with Company A’s. Although Zhang was neither the legal representative nor a registered shareholder of Company B, Zhang actually participated in Company B’s technology R&D and business management. After discovering this, Company A demanded that Zhang pay non-compete liquidated damages of RMB 1,000,000 and continue to perform the non-compete obligations. Zhang defended that: (1) Zhang was not a shareholder or executive of Company B and thus did not compete; (2) Company A failed to pay non-compete compensation as agreed (paid only for January and February 2024 and not thereafter); and (3) the liquidated damages were excessively high.

---

```markdown
## Argument Chain: Company A Is Entitled to Require Zhang to Pay Non-Compete Liquidated Damages and Continue Performing Non-Compete Obligations

### Argument Summary
- **Argumentative goal:** Prove that Zhang breached non-compete obligations and that Company A is entitled to require payment of liquidated damages of RMB 1,000,000 and continued performance of non-compete obligations
- **Argument structure:** Hierarchical progression + defensive argumentation + alternative argumentation
- **Overall confidence:** 🟡 Medium (approx. 55%–70%)
- **Key disputed issues:** 
  1. Whether Zhang’s conduct constitutes breach of non-compete obligations
  2. Whether Company A’s failure to continuously pay compensation affects the effectiveness of the non-compete agreement
  3. Whether liquidated damages of RMB 1,000,000 are reasonable

### Argument Development

#### Step 1: Zhang Is a Proper Subject of Non-Compete Obligations 🟢

**Major premise (legal basis):**
Pursuant to Article 23, Paragraph 2 of the Labor Contract Law of the People’s Republic of China, for a worker who bears confidentiality obligations, the employer may agree with the worker on non-compete clauses in the employment contract or a confidentiality agreement. Article 24, Paragraph 1 provides that persons subject to non-compete restrictions are limited to the employer’s senior management personnel, senior technical personnel, and other personnel who bear confidentiality obligations.

**Minor premise (case facts):**
Zhang served as CTO of Tech Company A, was a senior management officer, and as the person responsible for core technology was also senior technical personnel, possessing the company’s core technical secrets and trade secrets. Zhang entered into a non-compete agreement with Company A.

**Subsumption and reasoning:**
Zhang falls within both the “senior management personnel” and “senior technical personnel” categories and is thus a proper subject of non-compete obligations under the law. The non-compete agreement executed by the parties has a legal basis.

**Node conclusion:**
Zhang is a proper subject of non-compete obligations; the non-compete agreement executed by the parties is lawful and valid.

**Confidence:** 🟢 High

---

#### Step 2: The Agreed Content of the Non-Compete Agreement Is Lawful and Valid 🟢

**Major premise (legal basis):**
Pursuant to Article 24, Paragraph 2 of the Labor Contract Law, the non-compete term shall not exceed two years. Article 23, Paragraph 2 provides that during the non-compete term the employer shall pay the worker economic compensation on a monthly basis.

**Minor premise (case facts):**
The non-compete agreement stipulated: (1) a non-compete term of two years after departure, not exceeding the statutory maximum; (2) a non-compete scope limited to competing enterprises in the same industry, which is reasonable; (3) non-compete compensation (monthly payment of 30% of average wages for the 12 months before departure), meeting legal requirements; and (4) liquidated damages of RMB 1,000,000.

**Subsumption and reasoning:**
The agreed term (two years) does not exceed the statutory maximum; the scope limited to competing enterprises in the same industry is reasonable; and economic compensation was agreed, satisfying the statutory requirements for a non-compete agreement. The compensation standard (30% of monthly average wages) is not below the minimum standards ordinarily recognized in judicial practice across localities.

**Node conclusion:**
The agreed content of the non-compete agreement is lawful and valid.

**Confidence:** 🟢 High

---

#### Step 3: Zhang’s Conduct Substantively Constitutes Breach of Non-Compete Obligations 🟡

**Major premise (legal basis):**
Pursuant to Article 24, Paragraph 1 of the Labor Contract Law, the content of a non-compete agreement includes that the worker shall not take employment with another employer that produces or operates similar products or engages in similar business in competition with the worker’s unit, and shall not personally open a business producing or operating similar products or engaging in similar business.

Under the “substance-over-form review” principle in judicial practice, whether non-compete obligations have been breached should be determined by piercing formal appearances to examine the substantive relationship. Where a worker does not establish a competing enterprise in the worker’s own name but actually controls or participates in operating a competing enterprise, that still constitutes breach of non-compete obligations. (Reference: adjudicative views of courts in multiple localities, such as the positions of courts in Beijing, Shanghai, Shenzhen, and elsewhere in similar cases.)

**Minor premise (case facts):**
(1) After Zhang’s departure, Zhang’s spouse Li registered and established Tech Company B, closely following Zhang’s departure in time (only a two-month interval);
(2) Company B’s business scope highly overlaps with Company A’s, constituting same-industry competition;
(3) Although Zhang is not a registered shareholder or legal representative of Company B, Zhang actually participated in Company B’s technology R&D and business management;
(4) Establishing a company in a spouse’s name is a typical means of circumventing non-compete obligations.

**Subsumption and reasoning:**
Although Zhang formally neither worked for nor held shares in Company B, substantively:

First, the high correlation among three factors—the timing of Company B’s establishment (two months after Zhang’s departure), the founder (Zhang’s spouse), and the business scope (highly overlapping with Company A)—suffices to form a reasonable inference that Zhang actually controlled Company B.

Second, the fact that Zhang actually participated in Company B’s technology R&D and business management shows that Zhang was substantively engaged in competitive activities of the same kind of business as Company A.

Third, “personally open a business producing or operating similar products or engaging in similar business” under Article 24 of the Labor Contract Law should be given a substantive interpretation and should not be limited to registration in one’s own name. Engaging in competitive business through spouse nominee holdings, actual control, or similar means likewise falls within the scope of “personally opening a business.”

Fourth, if workers were allowed to circumvent non-compete obligations through spouse nominee holdings and similar means, the non-compete system would be rendered empty, contrary to legislative purpose.

**Node conclusion:**
Zhang’s conduct in causing Company B to be established through spouse Li and actually participating in its management and operations substantively constitutes breach of non-compete obligations.

**Confidence:** 🟡 Medium — adequate evidence is needed to prove Zhang’s “actual participation” in Company B’s management and operations. If Company A can provide sufficient evidence (e.g., records of Zhang entering and leaving Company B, communications showing participation in Company B’s business, testimony of Company B’s customers or employees, etc.), confidence may rise to High.

**Potential rebuttals and responses:**

**Rebuttal 1:** Zhang contends that Zhang is neither a shareholder nor an executive of Company B and thus does not compete.
**Response:** Whether non-compete obligations have been breached should be judged by substantive rather than formal standards. Although Zhang is not a registered shareholder or executive, actual participation in management and operations constitutes substantive breach. Establishing a company in a spouse’s name is a typical circumvention act and should not receive legal protection.

**Rebuttal 2:** Zhang may contend that Company B is independently operated by Li and unrelated to Zhang.
**Response:** Judgment should be based on a comprehensive assessment of circumstantial evidence including: correlation between Company B’s establishment time and Zhang’s departure time; degree of overlap between Company B’s business scope and Company A’s; match between Zhang’s technical expertise and Company B’s business; and evidence of Zhang’s actual participation in Company B’s activities. As to burden of proof, Company A has made a preliminary showing of Zhang’s connection to Company B; Zhang should bear the burden of producing contrary evidence that Zhang “did not actually participate.”

---

#### Step 4: Company A’s Failure to Continuously Pay Compensation Does Not Affect Zhang’s Liability for Breach 🟡

**Major premise (legal basis):**
Pursuant to Article 36 of the Interpretation (I) of the Supreme People’s Court on Issues Concerning the Application of Law in the Trial of Labor Dispute Cases (Fa Shi [2020] No. 26), where the parties agreed on non-compete restrictions in an employment contract or confidentiality agreement but did not agree on economic compensation after dissolution or termination of the employment contract, and the worker performed the non-compete obligations and requests that the employer pay economic compensation monthly at 30% of the worker’s average wages for the twelve months before dissolution or termination of the employment contract, the people’s court shall uphold the request.

Article 37 provides that where the parties agreed on non-compete restrictions and economic compensation in an employment contract or confidentiality agreement, and after the worker performed the non-compete obligations the worker requests that the employer pay economic compensation as agreed, the people’s court shall uphold the request.

Article 38 provides that where the parties agreed on non-compete restrictions and economic compensation in an employment contract or confidentiality agreement, **the condition for a party to dissolve the non-compete agreement is that the employer has failed to pay economic compensation for an additional three months**. That is, where due to reasons attributable to the employer economic compensation has not been paid for three months, and the worker requests dissolution of the non-compete agreement, the people’s court shall uphold the request.

**Minor premise (case facts):**
Company A paid non-compete compensation for January and February 2024 and not thereafter. Zhang began breaching non-compete obligations in March 2024 (causing Company B to be established in Zhang’s spouse’s name).

**Subsumption and reasoning:**

Key timeline analysis:
```
January 2024: Zhang left; Company A paid January compensation ✓
February 2024: Company A paid February compensation ✓
March 2024: Zhang’s spouse registered Company B (Zhang began to breach)
           Company A did not pay March compensation
```

First, Zhang’s breach (establishing Company B in March 2024) occurred at or before the time Company A stopped paying compensation. Even if Company A thereafter failed to pay compensation, Zhang’s breach had already occurred first.

Second, under Article 37 of the judicial interpretation, the condition for a worker to dissolve the non-compete agreement is that the employer has “failed to pay economic compensation for three months.” Even if Company A stopped paying compensation from March 2024, Zhang would at the earliest be entitled to request dissolution of the non-compete agreement in June 2024. Zhang had already breached in March 2024, at which time the non-compete obligations remained in effect.

Third, Zhang cannot rely on Company A’s failure to pay compensation to defend against breach that had already occurred. Breach came first; cessation of payment came later (or simultaneously); one cannot reverse cause and effect.

Fourth, even if Company A’s cessation of compensation payment constitutes breach, where both parties are in breach, each should independently bear its own liability for breach; Zhang cannot use Company A’s breach to escape Zhang’s own liability for breach.

**Node conclusion:**
Company A’s failure to continuously pay non-compete compensation does not affect Zhang’s liability for breach arising from Zhang’s prior breach.

**Confidence:** 🟡 Medium — precise determination of the timeline is critical. If it can be shown that Zhang’s breach indeed occurred before or simultaneously with Company A’s cessation of compensation payments, the argument is relatively strong. But if the court finds that Company A’s cessation of compensation payments itself constitutes fundamental breach, that may affect the determination of Zhang’s liability for breach.

**Potential rebuttal and response:**

**Rebuttal:** Zhang may contend that Company A’s failure to pay compensation constitutes prior breach and that the non-compete agreement should be dissolved.
**Response:** (1) On the timeline, Zhang’s breach (establishing Company B in March) and Company A’s cessation of compensation payments (from March) occurred almost simultaneously; there is no “prior” breach by Company A; (2) even if Company A stopped paying compensation, under the judicial interpretation three months of non-payment are required before the worker is entitled to request dissolution of the non-compete agreement, and Zhang had already breached before then; (3) Zhang should assert rights through lawful channels (e.g., demand, arbitration) rather than unilaterally violating non-compete obligations.

---

#### Step 5: Argumentation on the Reasonableness of Liquidated Damages of RMB 1,000,000 🟡

**Major premise (legal basis):**
The Labor Contract Law does not expressly provide for adjustment of non-compete liquidated damages. In judicial practice, courts ordinarily make a comprehensive judgment by reference to factors including: (1) the worker’s wage income level; (2) the amount of non-compete compensation; (3) the nature and degree of the worker’s breach; (4) the employer’s actual losses from the worker’s breach; (5) the worker’s ability to pay; and (6) the principle of fairness.

Some courts refer to and apply Article 585, Paragraph 2 of the Civil Code on adjustment of liquidated damages.

**Minor premise (case facts and analysis):**
- Liquidated damages: RMB 1,000,000
- Zhang holds 5% equity in Company A (registered capital RMB 50,000,000; equity value approximately RMB 2,500,000)
- As CTO, Zhang’s compensation level is relatively high (assume annual salary around RMB 1,000,000)
- Zhang possesses Company A’s core technical secrets
- Zhang’s breach is serious in nature: not only breach of non-compete obligations, but deliberate circumvention through spouse nominee holding
- Company A may suffer major losses such as customer attrition and technology leakage from Zhang’s competitive conduct

**Subsumption and reasoning:**

First, as to the ratio of liquidated damages to the worker’s income, RMB 1,000,000 is approximately one times Zhang’s annual salary; given Zhang’s executive status and high income level, that ratio is not extraordinarily high.

Second, as to the nature of the breach, Zhang not only breached non-compete obligations but deliberately circumvented them through spouse nominee holding, showing clear subjective bad faith and serious circumstances of breach.

Third, as to the employer’s losses, Zhang as CTO possesses core technology; establishing a competing enterprise may cause Company A major losses such as leakage of technical secrets and loss of core customers—losses that are often difficult to quantify precisely but have enormous actual impact.

Fourth, as to Zhang’s ability to pay, Zhang holds 5% equity in Company A (value approximately RMB 2,500,000) and has the economic capacity to pay RMB 1,000,000 in liquidated damages.

Fifth, as to the principle of fairness, a substantial reduction of liquidated damages would greatly diminish the deterrent force of the non-compete system and would not favor protecting the employer’s lawful rights and interests.

**Node conclusion:**
Liquidated damages of RMB 1,000,000, comprehensively considering Zhang’s income level, circumstances of breach, Company A’s potential losses, and Zhang’s ability to pay, fall within a reasonable range and should not be substantially reduced.

**Confidence:** 🟡 Medium — whether liquidated damages are reasonable falls within judicial discretion. RMB 1,000,000 is at a relatively high level in non-compete cases and may be appropriately reduced. But given Zhang’s executive status, deliberate circumvention in bad faith, and the seriousness of potential losses, maintenance of the original amount or only a slight reduction is comparatively likely.

---

#### Step 6: Company A Is Entitled to Require Zhang to Continue Performing Non-Compete Obligations 🟡

**Major premise (legal basis):**
Pursuant to Articles 23 and 24 of the Labor Contract Law, non-compete obligations are the worker’s obligations (within the agreed scope). Where a worker breaches a non-compete agreement, the worker shall pay liquidated damages to the employer as agreed. Payment of liquidated damages does not relieve the obligation of continued performance.

Pursuant to Article 577 of the Civil Code, modes of bearing liability for breach include continued performance.

**Minor premise (case facts):**
Zhang’s non-compete term is two years after departure (expiring in January 2026) and is still within the non-compete term. Zhang’s breach of non-compete obligations by establishing and operating Company B is ongoing.

**Subsumption and reasoning:**
Non-compete obligations are continuing in nature; payment of liquidated damages does not mean “buying out” the non-compete obligations. Before the non-compete term expires, Zhang must continue to perform the non-compete obligations. Company A is entitled to require Zhang to cease the breach (cease participating in Company B’s operations) and continue performing non-compete obligations for the remaining term.

**Node conclusion:**
Company A is entitled to require Zhang to continue performing non-compete obligations until the non-compete term expires.

**Confidence:** 🟡 Medium — a request for continued performance may face enforcement difficulties in practice, but as a matter of law Company A’s claim basis is established.

---

### Argument Summary Wrap-Up

**Final conclusion:**
In sum:
1. Zhang is a proper subject of non-compete obligations, and the non-compete agreement is lawful and valid (🟢 High);
2. Zhang’s establishment of a competing enterprise through spouse nominee holding and actual participation in operations substantively constitutes breach of non-compete obligations (🟡 Medium);
3. Company A’s failure to continuously pay compensation does not affect Zhang’s liability for breach arising from prior breach (🟡 Medium);
4. Liquidated damages of RMB 1,000,000 fall within a reasonable range (🟡 Medium);
5. Company A is entitled to require Zhang to continue performing non-compete obligations (🟡 Medium).

Therefore, Company A’s claim that Zhang pay non-compete liquidated damages of RMB 1,000,000 and continue performing non-compete obligations has factual and legal bases and should be upheld.

**Assessment of argumentative strength:**
- Strongest links: Steps 1 and 2 (proper subject status and agreement validity), 🟢 High confidence
- Weakest link: Step 3 (finding of substantive breach), highly dependent on sufficiency of evidence
- Overall evaluation: The argument chain is complete and logically self-consistent, but overall confidence is constrained by the state of the evidence and judicial discretion

**Alternative argumentative paths:**

**Alternative path 1 (if the court finds liquidated damages excessively high):**
As a fallback, argue for determining liquidated damages by reference to 3–5 times the total compensation Zhang should receive during the non-compete term as a benchmark, while also asserting Company A’s actual losses (customer attrition, technology leakage, etc.) as supplementary bases.

**Alternative path 2 (if the court finds Company A’s cessation of compensation payments affects the liquidated damages claim):**
Argue for offsetting Company A’s unpaid compensation against Zhang’s payable liquidated damages, with Company A still entitled to claim the difference in liquidated damages.

**Alternative path 3 (if the non-compete liquidated damages claim is obstructed):**
Switch the claim basis and, on the ground of trade secret infringement, claim damages pursuant to Article 9 of the Anti-Unfair Competition Law.

**Risk warnings:**
1. **Evidentiary risk:** Proving Zhang’s “actual participation” in Company B’s management and operations is critical to this case; Company A is advised to fix evidence through notarized evidence collection, investigation, and similar means
2. **Compensation risk:** Company A should promptly make up unpaid non-compete compensation to avoid Zhang’s counterclaim for dissolution of the non-compete agreement due to continued non-payment
3. **Liquidated damages reduction risk:** Liquidated damages of RMB 1,000,000 may be appropriately reduced by the court; evidence of actual losses should also be prepared
4. **Enforcement risk:** Even if a judgment for continued performance is obtained, actual enforcement may face difficulties
5. **Limitation risk:** Note the labor dispute arbitration limitation period (one year) and timely file for arbitration
```

---

## Appendix: Quick Reference for Argument-Chain Construction

```
┌─────────────────────────────────────────────┐
│   Six-Phase Quick Reference for Building    │
│            Argument Chains                  │
├─────────────────────────────────────────────┤
│                                             │
│  Phase One: Preparation                     │
│  □ Clarify the argumentative goal           │
│  □ Inventory argument materials             │
│  □ Identify disputed issues                 │
│                                             │
│  Phase Two: Architecture design             │
│  □ Choose the argument structure type       │
│  □ Draft the argument blueprint             │
│                                             │
│  Phase Three: Node construction             │
│  □ Build each node (major → minor →         │
│    conclusion)                              │
│  □ Connect argument nodes                   │
│                                             │
│  Phase Four: Argument reinforcement         │
│  □ Strengthen weak links                    │
│  □ Build a defensive layer                  │
│  □ Add auxiliary arguments                  │
│                                             │
│  Phase Five: Argument verification          │
│  □ Logical validity check (screen 10        │
│    fallacy types)                           │
│  □ Completeness check                       │
│  □ Consistency check                        │
│                                             │
│  Phase Six: Argument presentation           │
│  □ Organize order of presentation           │
│  □ Draft argument text                      │
│  □ Annotate confidence                      │
│                                             │
└─────────────────────────────────────────────┘
```
