---
name: inductive-reasoning
description: "Trigger this skill when one or more concrete cases, judgments, or fact patterns must be distilled into general legal rules, adjudicative rules, or legal principles. Typical triggers include: summarizing adjudicative holdings from a series of cases; extracting generalizable legal propositions from individual cases; identifying common legal rules across multiple fact patterns; building adjudicative-rule digests for similar-case retrieval; and summarizing judicial application standards from practice precedents."
---

> **Chinese source (authoritative):** [`../../skills/inductive-reasoning/SKILL.md`](../../skills/inductive-reasoning/SKILL.md)

# Inductive Reasoning: Distilling General Rules from Cases

## Overview Table

| Item | Content |
|------|---------|
| **Capability ID** | 17 |
| **Capability Name** | Inductive Reasoning |
| **Core Function** | Distill and abstract general legal rules or adjudicative rules from concrete cases |
| **Direction of Reasoning** | From particular to general (bottom-up) |
| **Complementary Capabilities** | Deductive reasoning (general to particular); analogical reasoning (particular to particular) |
| **Input** | One or more concrete cases (facts, issues in dispute, reasons for judgment, outcomes) |
| **Output** | General legal rules / adjudicative rules / legal propositions, with confidence level and scope of application |
| **Typical Users** | Judges, lawyers, legal researchers, legal AI systems |
| **Risk Level** | High (over-generalization of inductive conclusions may lead to erroneous application) |

## Legal Disclaimer

> **Important notice:** The “general rules” produced by inductive reasoning are scholarly summaries of the adjudicative logic of existing cases; they are not equivalent to legislation or judicial interpretations. The force of an inductive conclusion depends on the authority, representativeness, and sufficient number of sample cases. In non–common-law systems (such as mainland China), inductively derived rules have only reference value and are not legally binding; however, under the Guiding Cases system, the adjudicative points of Guiding Cases issued by the Supreme People’s Court “shall be referred to.” Users must always verify that inductive conclusions are consistent with current written law and must heed the boundaries of their application.

---

## Description

A probabilistic reasoning skill that moves from the particular to the general, suited to case-law systems. When no ready-made legal rule can be applied by matching, it inductively extracts general legal rules or principles from concrete precedents—activity that is legislative in nature. It follows the inductive principle that “more cases are better, broader coverage is better, and greater individual variation is better.” By systematically analyzing similarities and differences across multiple precedents, it builds legal arguments that are highly probable but not absolutely certain.

## Capabilities
- **Precedent retrieval and screening**: Identify from a large body of precedents those with substantial similarity to the case at hand; distinguish supporting precedents from contrary precedents
- **Similarity mapping analysis**: Systematically compare precedents and the pending case on material facts, legal issues, and points in dispute—similarities and differences
- **Rule induction and extraction**: Abstract general legal rules from the reasons for judgment in concrete precedents
- **Analogical argument construction**: Apply standards that strengthen or weaken analogy to build persuasive precedent-citation arguments
- **Difference-based rebuttal**: Anticipate contrary precedents the other side may cite and defeat their analogical force through difference analysis
- **Rule applicability assessment**: Judge the scope of application, boundary conditions, and limiting factors of inductively derived rules

## How to Use
### Phase One: Precedent Identification and Initial Screening
1. **Identify the core legal dispute**: Convert the pending case facts into a precise legal proposition and clarify the rule gap that induction must fill
   - Example: The core of the case is not “whether theft is constituted,” but “whether fishers have established possession/control in the legal sense over a school of fish when the net is about to close”
2. **Bidirectional precedent retrieval**:
   - **Supporting-precedent search**: Find cases with similar facts whose outcomes support one’s claim (e.g., *Keeble*—interfering with an economic activity over which control has been established constitutes a tort)
   - **Contrary-precedent search**: Find cases with similar facts but opposite outcomes (e.g., *Pierson*—mere pursuit does not create property rights)
3. **Build a comparison baseline table**: Extract features of the pending case and candidate precedents along these dimensions:
   - Nature of the resource (owned / unowned / wild animals)
   - Nature of the plaintiff’s conduct (investment-based commercial activity / mere recreational pursuit)
   - Degree of control established (physical control / imminent control / mere intent to pursue)
   - Timing of the defendant’s act (before control is established / during establishment of control / after control is established)

### Phase Two: Similarity Analysis and Rule Distillation (Supporting Precedents)
1. **Identify relevant similarities**:
   - Focus on factual features causally linked to the legal conclusion; exclude superficial similarities
   - Example: The “relevant similarity” between *Keeble* and the present case is that “the plaintiff, through substantial investment, established a state of exclusive control over the resource,” not that “both involve water” or “both involve animals”
2. **Induce the legal rule** (use a “condition–effect” structure): Major premise (rule): When a right-holder, by lawful means (Condition 1), is about to obtain control over a resource (Condition 2), and that control is reasonably foreseeable (Condition 3), and a third party intentionally interferes with that acquisition process (Condition 4), causing the right-holder to lose expected benefits (effect), the conduct constitutes a tort / theft.
3. **Justify the rule**:
   - Economic efficiency: Protect nearly completed lawful investment; encourage resource development and use
   - Fairness: Prevent free-riding; protect legitimate expectations
   - Consistency with precedent: The rule can apply across multiple similar cases (*Keeble*, *Ghen v. Rich*, and other whaling cases)

### Phase Three: Difference Analysis and Rule Narrowing (Contrary Precedents)
1. **Identify material differences**:
   - The difference between *Pierson* and the present case is not “land vs. sea,” but:
     - **Degree of control established**: Pursuing a fox (mere chase) vs. net about to close (exclusive control imminent)
     - **Nature of conduct**: Recreational hunting vs. commercial fishing
     - **Identifiability of the resource**: Fox free to escape vs. school of fish already confined by gear
2. **Defeat analogy to the contrary precedent**:
   - Argue that *Pierson*’s rule applies only where there is “mere pursuit, with no exclusive control yet established”
   - Place the present facts outside *Pierson*: net about to close already constitutes “quasi-possession,” beyond mere pursuit
3. **Refine key concepts**:
   - Propose a “tiered theory of possession”:
     - Tier 1: Complete physical control (in hand)
     - Tier 2: Exclusive control about to be completed (net about to close; trap already set)
     - Tier 3: Mere intent to pursue (*Pierson*)
   - Argue that theft/tort requires only Tier 2 or above, not Tier 1

### Phase Four: Argument Construction and Output
**Standard output format**:
> Major premise: Inductively derived legal rule
> 1. [Condition 1: conduct element, e.g., “intentional and without lawful right”]
> 2. [Condition 2: object element, e.g., “property over which another has established control”]
> 3. [Condition 3: result element, e.g., “depriving another of expected benefits”]
>
> Rule-Based Explanation:
> [Develop in a three-layer structure: similarity – difference – rule application]
> 4. **Establishing similarity**: Precedent [*Case Name*] and the present case have relevant similarity on [material dimension]—[specific explanation]
> 5. **Excluding differences**: The [*contrary precedent*] the other side may cite differs materially from this case—[specific explanation, emphasizing that the difference makes the contrary precedent inapplicable]
> 6. **Applying the rule**: The present facts satisfy Condition [X] of the above rule—[specific argument]; therefore [legal effect] should follow

### Phase Five: Critical Testing and Calibration
1. **Reverse test**: Construct an analogy identical in form but absurd in conclusion to test the soundness of the reasoning form
2. **Re-examine differences**: Revisit identified differences and confirm whether they suffice to defeat the analogy
3. **Rule-conflict check**: Verify whether the inductive rule conflicts with superior law, mandatory provisions, or public policy
4. **Acceptability of the conclusion**: Assess whether the conclusion accords with legal justice, fairness, and social effects
5. **Calibrate strength of expression**: Adjust how definitively the conclusion is stated according to argument strength (“shall apply” vs. “may apply”); avoid necessity language; prefer “this case has a high probability of constituting…”

## Input

- **Facts of the pending case**: Structured statement of case facts, including time, place, parties’ conduct, subject matter in dispute, etc.
- **Core legal issue**: The legal dispute to be resolved, usually framed as “whether … constitutes …” or “whether … should …”
- **Candidate precedent set**: List of relevant precedents available for retrieval, including docket/case names, material facts, holdings, and reasons
- **Opposing views**: Legal positions the opposing party may assert

## Output

- **Similarity analysis report**: Systematic comparison of similarities and differences between precedents and the pending case, with relevance ratings
- **Inductively derived legal rule**: General legal rule distilled from precedents, including conditions of application and legal effects
- **Argument analysis**: Detailed argument on similarity, difference exclusion, and rule application
- **Rebuttal plan**: Response strategies to possible distinguishing arguments
- **Argument-strength assessment**: High / medium / low probability (based on quality and quantity of similarities)

## Best Practices
1. **Prefer “relevant similarity” over “pile of numbers”**: One highly relevant similarity (e.g., consistent causal chain) is more persuasive than many superficial similarities (e.g., proximity in time or place)
2. **Disclose and respond to differences proactively**: Honestly identifying differences and arguing they are non-material strengthens credibility more than avoiding them
3. **Distinguish *ratio* from *dicta***: Ensure citation rests on binding core reasons in the judgment, not incidental judicial comments
4. **Corroborate with multiple precedents**: Induction from a single case is weak; cite multiple consistently pointing precedents to form a “precedent chain” where possible
5. **Keep conclusions probabilistic**: Induction is inherently probabilistic; avoid “necessarily,” “absolutely,” and similar certainty language; prefer “should,” “has a high probability,” etc.
6. **Test the rule counterfactually**: If applying the inductive rule to the opposite situation yields absurd results, revisit the induction
7. **Refine rather than generalize loosely**: Avoid “both cases involve fishing, so they are similar”; prefer “both were interfered with when control was about to be completed, so they are similar.” Use devices such as “tier theory” to resolve precedent conflict—e.g., divide “possession” into tiers so different precedents apply at different tiers, rather than simply rejecting a precedent.

## Limitations
- **Probabilistic nature**: Induction cannot reach the certainty of deduction; conclusions remain open to being overturned
- **Dependence on case law**: This skill mainly suits common-law traditions or systems with guiding-precedent significance; applicability is limited in pure statute-based systems
- **Availability of precedents**: Quality of reasoning depends on completeness and retrievability of precedent databases; without relevant precedents, effective induction is difficult
- **Subjectivity of “similarity”**: Judging the relevance of similarities and differences involves value judgment and discretion; different lawyers may reach different conclusions
- **Factual complexity**: Real cases are often more complex than examples; induction may face intertwined multiple similarities and differences
- **Over-/under-generalization risk**: Rules distilled from limited precedents may be too broad or too narrow and must continually be tested and revised against new cases
- **Temporal and geographic limits**: Changes in legal values and social attitudes may weaken older analogies; assess current validity. Persuasive force of early or foreign precedents diminishes with temporal/spatial distance; assess present effectiveness.

## Example

**Pending case (variant of *Young v. Hitchens*)**:
Plaintiff fishes on the high seas with a net; as the net is about to close, defendant steams into the net, captures the school of fish, and sails away.

**Candidate precedents**:
Supporting precedent: *Keeble v. Hickeringill* (decoy pond)
- Plaintiff owned a pond and operated it for profit by attracting ducks
- Defendant intentionally fired shots to scare the ducks away
- Holding: Defendant liable in tort / for conversion-like interference
- Ratio: Interfering with another’s process of acquiring a resource over which control has been established, and depriving expected benefits, constitutes a tort

Contrary precedent: *Pierson v. Post* (fox chase)
- Plaintiff pursued a fox; defendant intercepted and killed it
- Holding: Defendant not liable
- Ratio: Mere pursuit creates no property right; wild animals are acquired by first occupancy

**Reasoning process**:

*Step 1: Identify the legal issue*
Core dispute: Does the defendant, intervening when the plaintiff is about to complete the capture, infringe the plaintiff’s property rights?

*Step 2: Similarity analysis (using *Keeble* as the analogical base)*

| Comparison Dimension | *Keeble* (precedent) | *Young* (pending) | Relevance Assessment |
| ---- | --------------- | --------------- | ------------------- |
| Plaintiff’s conduct | Operating a decoy pond for profit on own land | Fishing with a net on the high seas | High relevance (both lawful commercial resource-acquisition activities) |
| Defendant’s conduct | Intentionally firing to scare ducks away | Steaming into the net and capturing the fish | High relevance (both intentional interference with another’s resource acquisition) |
| Resource state | Ducks already within plaintiff’s control (pond) | Fish about to be netted (net about to close) | Extremely high relevance (both: plaintiff about to obtain control) |
| Harm | Plaintiff loses expected profits | Plaintiff loses expected catch | High relevance (both loss of expected benefits) |
| Potential difference | Private land vs. open high seas | | Must assess: whether this is a material difference |

*Step 3: Rule induction*

From *Keeble* one may induce:
**Resource-acquisition protection rule**: When a right-holder, by lawful means, is about to obtain control over a resource, and that control is reasonably foreseeable, a third party who intentionally interferes with that acquisition process, causing the right-holder to lose expected benefits, commits a tort.

*Step 4: Difference assessment*

Distinguishing points the other side may raise:
- **Private land vs. open high seas**: High-seas resources are open; first-occupancy principles apply more strongly
- **Response strategy**: Although the high seas are open, the plaintiff has already established a state of “imminent completion of control” through the net; that state is legally protected and does not depend on land ownership

*Step 5: Argument construction*
One’s own argument:
Just as the court in *Keeble* protected the plaintiff’s reasonable expectation of capturing the ducks, here the defendant, intervening as the net was about to close, destroyed the exclusive control the plaintiff was about to establish through lawful labor. The core similarity is that both plaintiffs, through substantial investment, established a ‘quasi-control’ state over the resource, and both defendants’ intentional interference caused loss of reasonably expected gains. Openness of the high seas cannot justify disrupting another’s nearly completed lawful capture; otherwise free-riding would be encouraged and resource-use efficiency harmed.

**Opposing argument**:
“Under *Pierson v. Post*, mere pursuit creates no property right. Here the net had not fully closed; the plaintiff had not yet acquired ownership of the fish; therefore the defendant’s conduct is not a tort.”

**Rebuttal construction (absurd analogy)**:
“On the other side’s logic—‘so long as the resource is not yet under complete physical control, another may intervene and seize it’—a miner about to dig out gold could be shoved aside at the last step and the gold taken; or a farmer about to harvest could have the entire crop stolen the night before. That clearly violates legal justice. The other side’s analogy ignores the material element of ‘reasonable expectation of imminent completion of control’ and overextends the precedent.”

Full example (plaintiff and defendant arguments)

**Output (plaintiff side)**:

> **A person ordinarily commits theft when the following conditions are met:**
> 1. The person intentionally and without consent takes possession of another’s property.
> 2. The property has economic value to the owner and is treated as personal property.
>
> **Rule-based explanation:**
>
> **Establishing similarity**: *Keeble* and this case have highly relevant similarity on core legal elements. In the precedent, the plaintiff, by investing in a decoy pond, established exclusive control over the ducks (ducks within the pond; capture reasonably expected). Here, the plaintiff, through net fishing, likewise established exclusive control over the fish (net about to close; fish confined to a defined space; capture virtually certain). The core similarity: both plaintiffs, through **substantial investment**, established a state of **imminent completion of control** over the resource—a state with **economic value** and **reasonable foreseeability**.
>
> **Excluding differences (as to *Pierson*)**: The other side may cite *Pierson* for “no right until complete control.” Yet *Pierson* and this case differ **materially**: in *Pierson*, the plaintiff had only **intent to pursue**; the fox remained free to escape, with no exclusive control established. Here, the net is about to close; the fish are physically confined to a defined space; the plaintiff’s control has reached the **“quasi-possession” (imminent possession)** tier. *Pierson*’s rule applies only to “mere pursuit,” not to “imminent completion of control.”
>
> Rule application: The facts satisfy the core elements of theft—the defendant **intentionally intervened** as the plaintiff was about to complete control, **without lawful right**, seized fish of economic value, and caused the plaintiff to lose **expected benefits**. The about-to-close net made the fish the plaintiff’s “quasi-property”; the defendant’s conduct meets all conditions of the rule.
>
> **Conclusion**: The defendant committed theft.

**Output (defendant side)**:

> **A person ordinarily commits theft when the following conditions are met:**
> 1. The person unlawfully appropriates property belonging to another.
> 2. The property is treated as tangible property and has already been taken into the owner’s possession.
>
> **Rule-based explanation:**
>
> **Establishing similarity**: *Pierson* and this case have relevant similarity on “when possession arises.” In the precedent, the court held that wild animals are no one’s property **before actual capture**; mere pursuit creates no legal right. Here, before the net **fully closes**, the fish remain in open waters; the plaintiff has not established physical control; when the defendant intervened, the fish were still **unowned**.
>
> **Excluding differences (as to *Keeble*)**: The other side may invoke *Keeble*’s “interference with commercial activity” rule. Yet *Keeble* and this case differ **materially**: in *Keeble*, the ducks were **already in a pond on the plaintiff’s private land**, within the plaintiff’s **exclusive control space**. Here, though the net is about to close, the area inside the net remains **part of the open seas**; openness of the high seas negates any pre-established exclusive right. Further, *Keeble* involved a **fixed facility (pond)**; this case involves a **mobile resource (high-seas fish)**—geographic openness is a fundamental difference.
>
> **Rule application**: The facts do not satisfy the core theft element—“**property belonging to another**.” When the defendant captured them, the fish were still in open waters; the plaintiff’s “about-to-close” net shows only **expected control**, not **legal possession**. Under the first-occupancy principle in *Pierson*, property in wild animals arises upon **actual capture**, not during pursuit. The defendant’s conduct may be immoral, but it does not meet the property-law elements of theft.
>
> **Conclusion**: The defendant did not commit theft.
