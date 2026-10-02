---
name: teleological-interpretation
description: |
  Teleological interpretation skill (目的解释). When textual interpretation of a legal provision still cannot yield a determinate conclusion, systematically discover and argue the purpose of the provision, choose the most justified meaning within the range the text can bear, and form an adjudicable interpretive conclusion. Trigger conditions (any one suffices): textual interpretation yields two or more meanings and none can be chosen; the textual conclusion is clearly unreasonable; the provision contains open evaluative concepts (e.g., “reasonable,” “正当,” “necessary,” “重大”); the provision is relatively old and textual coverage is inadequate for novel facts.
---

> **Chinese source (authoritative):** [`../../skills/teleological-interpretation/SKILL.md`](../../skills/teleological-interpretation/SKILL.md)

# 41 Teleological Interpretation Skill

## 1. Description 

This skill applies when textual interpretation of a legal provision still cannot yield a determinate conclusion: systematically discover and argue the purpose of the provision, choose the most justified meaning within the range the text can bear, and ultimately form an adjudicable interpretive conclusion.

Trigger conditions (invoke if any one is met):
- Textual interpretation is complete, but the provision has two or more possible meanings and none can be chosen
- The textual conclusion leads to a clearly unreasonable result
- The provision contains open evaluative concepts (e.g., “reasonable,” “正当” (正当), “necessary,” “重大” (重大)), and the text cannot adequately define them
- The provision is relatively old, and textual coverage is inadequate when facing novel facts

---

## 2. Capabilities

- Identify the provision / concept / sentence to be interpreted and compress the dispute into a single concrete legal question
- Reconstruct the legislator’s original intent from three levels: statutory text, legislative materials, and legislative background
- Construct the reasonable purpose the provision should now carry from four dimensions: institutional function, legal values, real-world needs, and authoritative adjudication
- Judge consistent / complementary / conflicting relationships; when conflicting, allocate weight by three criteria: age of the regulation, concreteness of the provision, and rule vs. principle character
- Convert abstract purpose into a concrete judgment of statutory meaning
- Test the conclusion against textual limits, systematic coherence, higher-law principles, and public persuasiveness

---

## 3. How to Use

```
PHASE_1: Skill handoff
├── STEP_1: Receive textual-interpretation results
│   ├── INPUT: Output of the prior textual-interpretation skill
│   ├── ACTION: Extract the following (any one suffices)
│   │   ├── Interpretive object → specific provision / concept / sentence
│   │   ├── Possible textual meanings
│   │   ├── Textual boundary → upper and lower limits of possible linguistic range
│   │   └── Reason textual interpretation is insufficient → ambiguity / abstraction / unreasonableness / novel facts
│   └── OUTPUT: Structured interpretive starting point
│
├── STEP_2: Fix the disputed question
│   ├── ACTION: Compress the dispute into one concrete question sentence
│   ├── FORMAT: "In Article X of the X Law, should 'Y' in this case be understood as A or B?"
│   └── RULE: The narrower the question, the better; forbid broad formulations such as "should the claim be upheld"

PHASE_2: Identify purpose
├── STEP_4: Find subjective purpose
│   ├── Data sources (by priority)
│   │   ├── L1: The provision itself → wording / structure / position / purpose clauses / chapter titles / preamble
│   │   ├── L2: Legislative explanatory materials → draft explanations / deliberation reports / amendment notes / drafting notes
│   │   └── L3: Legislative background → real problem then to be solved / defects of old rules / reasons for addition, amendment, or deletion
│   ├── OUTPUT_FORMAT: One complete purpose statement
│   │   ├── Do: "The subjective purpose of this article is, by [means], to prevent/achieve [concrete effect]"
│   │   └── Don't: "protect rights" / "maintain order" (forbid slogan-style formulations)
│   └── IF legislative materials are insufficient or vague
│       └── → Mark as "subjective purpose unclear" and increase objective-purpose weight in STEP_6
│
├── STEP_5: Find objective purpose
│   ├── Analytical dimensions (check all)
│   │   ├── D1: Institutional whole
│   │   │   ├── Is the article a general rule OR an exception?
│   │   │   ├── What function does it perform in this chapter / book?
│   │   │   └── Would a given interpretation disrupt the institutional arrangement?
│   │   ├── D2: Basic principles and legal values
│   │   │   └── Which are implicated? → equality / good faith / rights protection / transactional security / self-responsibility / public safety / personality dignity / ...
│   │   ├── D3: Real social needs
│   │   │   └── Technology scenarios / new transaction structures / new tort patterns / new risk pathways
│   │   └── D4: Purpose expressions in authoritative adjudication
│   │       └── Guiding cases / Gazette cases / typical cases
│   └── OUTPUT_FORMAT: Same as STEP_4 — one complete purpose statement

PHASE_3: Integrate and conclude
├── STEP_6: Integrate subjective and objective purpose
│   ├── CASE_1: Consistent
│   │   └── → Integrate directly; dual confirmation; strongest persuasiveness
│   ├── CASE_2: Subjective unclear + objective clear
│   │   └── → Note insufficient materials; let objective purpose lead
│   └── CASE_3: Conflict
│       └── → Weigh by the following three criteria
│           ├── Criterion 1: Age of the regulation → newer → more weight to subjective; older → more weight to objective
│           ├── Criterion 2: Concrete vs. abstract provision → more concrete → more subjective; more abstract → more objective
│           └── Criterion 3: Rule vs. principle → rule provisions weigh subjective purpose more; principle provisions weigh objective purpose more
│
├── STEP_7: Form the interpretive conclusion
│   ├── ACTION: Convert final purpose into a concrete meaning judgment
│   ├── Must clearly answer at least one of
│   │   ├── Should the word / concept be given a broad OR narrow reading?
│   │   ├── Should the exception clause be strictly OR expansively construed?
│   │   ├── Should the case facts be included in OR excluded from the scope of application?
│   │   └── Does the conduct fall within the regulated object of the provision?
│   └── RULE: Purpose itself ≠ conclusion; must land on an adjudicable meaning judgment
│
└── STEP_8: Legality review (all four must pass before output)
    ├── CHECK_1: Textual limit → Is the conclusion still within possible linguistic range?
    ├── CHECK_2: Systematic coherence → Does the conclusion deprive neighboring provisions of meaning?
    ├── CHECK_3: Higher-law principles → Does the conclusion contradict basic values?
    └── CHECK_4: Public persuasiveness → Can the argument withstand public scrutiny?
    ├── IF all pass → Output the final result
    └── IF any fails → Return to STEP_6 and re-weigh
```

---

## 4. Input Format

```yaml
# Required
prior_textual_interpretation:        # Output of prior textual interpretation
  target: ""                         # Interpretive object (full text of the specific provision, with number and statute name)
  disputed_expression: ""            # Disputed concept / formulation
  reason_insufficient: ""            # Why textual interpretation is insufficient

case_summary: ""                     # Case summary

# Optional
possible_meanings: []                # Possible meanings from textual interpretation
textual_boundary: ""                 # Boundary of possible linguistic range
legislative_materials: ""            # Draft explanations / deliberation reports / amendment notes, etc.
related_provisions: []               # Systemically related provisions
existing_views: []                   # Existing interpretive positions or adjudicative views
text_type: []                        # Legal norm | contract | will | other private-law text
```

---

## 5. Output Format

```yaml
purposive_interpretation:
  section_1_dispute:
    label: "Statement of dispute"
    content: "The dispute in this case is how 'Y' in Article X of the X Law should be understood."
    
  section_2_textual_bridge:
    label: "Textual bridge"
    content: "Textual interpretation failed because [...]."

  section_3_necessity:
    label: "Necessity of teleological interpretation"
    content: "Because [abstraction / polysemy / mechanical reading leads to... / tension with novel facts], interpretation must combine the provision’s purpose."

  section_4_subjective_purpose:
    label: "Subjective-purpose argument"
    source: "[statutory text / legislative explanation / legislative background]"
    conclusion: "The subjective purpose of this article is: by [means], to [achieve/prevent] [concrete effect]."

  section_5_objective_purpose:
    label: "Objective-purpose argument"
    dimensions_checked: [institutional whole, basic principles and values, real needs, authoritative adjudication]
    conclusion: "The objective purpose of this article is: in [institutional context], to [achieve/maintain/prevent] [concrete effect]."

  section_6_integration_and_conclusion:
    label: "Integration and conclusion"
    purpose_alignment: "consistent | subjective unclear | conflict"
    conflict_resolution: "(if conflict) Under [age / concreteness / rule-principle] criterion, [subjective/objective] purpose weighs more."
    interpretation_result: "'Y' in this case should be understood as [concrete meaning], therefore [concrete adjudicative conclusion]."
    legality_check:
      textual_limit: "pass / fail"
      systematic_coherence: "pass / fail"
      superior_principles: "pass / fail"
      public_persuasiveness: "pass / fail"
```

---

## 6. Example Usage

### Input

```yaml
prior_textual_interpretation:
  target: "Civil Code Art. 1176(1): 'A person who voluntarily participates in a cultural or sports activity with certain risks and is harmed by another participant’s conduct may not request that other participant to bear tort liability; provided that this does not apply if the other participant intentionally or with gross negligence caused the harm.'"
  disputed_expression: "重大过失 (gross negligence)"
  reason_insufficient: "Evaluative concept; the degree boundary of '重大' cannot be fixed from wording alone"

case_summary: "A and B are amateur football players in a community amateur match. In contesting the ball, B performs a sliding tackle that fractures A’s right tibia. A sues for damages; B raises assumption of risk. Issue: Does B’s sliding tackle constitute '重大过失' (gross negligence)?"

possible_meanings:
    - "Meaning A (broad): Clear breach of ordinary care, relatively significant in degree"
    - "Meaning B (narrow): Extreme carelessness almost completely disregarding others’ safety, approaching indifference to harm"
textual_boundary: "'重大过失' upper bound does not exceed intent; lower bound is above ordinary negligence; the concrete threshold cannot be fixed by text"
legislative_materials: "NPCSC Legal Affairs Commission Civil Code commentary: the article aims to respond to inconsistent liability standards in cultural/sports injury disputes and encourage normal cultural and sports activities."
related_provisions:
  - "Civil Code Art. 1165 (general fault-liability clause)"
  - "Civil Code Art. 1176(2) (organizer liability)"
text_type: "legal norm"
```

### Output

```yaml
purposive_interpretation:
  section_1_dispute:
    label: "Statement of dispute"
    content: "The dispute is how '重大过失' in the proviso to Civil Code Art. 1176(1) should be understood—whether a sliding tackle causing fracture in an amateur football match constitutes '重大过失,' thereby excluding assumption-of-risk immunity."

  section_2_textual_bridge:
    label: "Textual bridge"
    content: "After textual interpretation, '重大过失' admits a broad reading (clear breach of ordinary care) and a narrow reading (extreme carelessness approaching indifference). '重大' is a degree evaluative concept; upper bound does not exceed intent and lower bound is above ordinary negligence, but the concrete threshold cannot be fixed by text."

  section_3_necessity:
    label: "Necessity of teleological interpretation"
    content: "The concept is an open evaluative concept; text cannot draw an exact boundary. The proviso’s application threshold directly draws the line between assumption of risk and fault liability: too broad empties the assumption-of-risk clause; too narrow condones extremely dangerous conduct. Purpose must set a reasonable boundary."

  section_4_subjective_purpose:
    label: "Subjective-purpose argument"
    source: "Legal Affairs Commission commentary + legislative background"
    reasoning: "Art. 1176 is the Civil Code’s first establishment of assumption of risk, responding to inconsistent standards, excessive participant liability, and suppression of normal activities. The proviso shows the legislator did not grant absolute immunity, but drew a floor under immunity."
    conclusion: "The proviso’s subjective purpose is: while encouraging normal cultural/sports activities and reasonably allocating inherent risk, to exclude from immunity conduct that clearly exceeds the activity’s inherent risk and seriously departs from basic care, preventing abuse of assumption of risk."

  section_5_objective_purpose:
    label: "Objective-purpose argument"
    dimensions_checked:
      制度整体: "Arts. 1176 and 1165 form a 'principle (fault liability)—exception (assumption-of-risk immunity)' relation. The proviso is an 'exception to the exception,' preventing over-expansion of the exception. The '重大过失' threshold should not be too low (or the exception becomes empty) nor equated with intent (or the proviso loses independent meaning)."
      基本原则与价值: "Balance freedom of action and personal safety. Voluntary participation reflects autonomy of will, but personal safety cannot be infinitely surrendered because of 'voluntariness.'"
      现实需求: "Amateur participants lack professional training and protection; risk-bearing and risk-recognition capacity is lower than for professionals; standards should moderately consider actual ability and activity risk features."
      权威裁判: "omitted"
    conclusion: "The proviso’s objective purpose is: while maintaining normal cultural/sports activities, to ensure that when a participant’s conduct clearly departs from the activity’s reasonable competitive range enough to undermine the justification of risk assumption, the victim still obtains tort remedies."

  section_6_integration_and_conclusion:
    label: "Integration and conclusion"
    purpose_alignment: "consistent"
    conflict_resolution: "Subjective and objective purposes align; dual confirmation; no weighing needed."
    interpretation_result: >
      "重大过失" should not mean every careless or technically crude act, nor be raised nearly to intent;
      it should mean: conduct that clearly departs from the basic care participants in that cultural/sports activity ought to exercise,
      and seriously exceeds the activity’s inherent risk and reasonable competitive range.
      Here, a sliding tackle in amateur football clearly exceeds reasonable competitive intensity; amateur participants lack professional sliding-tackle technique and self-protection;
      B’s conduct seriously departed from basic care and exceeded inherent risk, and should be found to be "重大过失."
      B may not invoke assumption-of-risk immunity and should bear tort liability under Art. 1165.
    legality_check:
      textual_limit: "pass — conclusion within linguistic range of '重大过失'"
      systematic_coherence: "pass — systematically coherent with Arts. 1165 and 1176(2)"
      superior_principles: "pass — consistent with basic value of personal-safety protection"
      public_persuasiveness: "pass — argument can withstand public scrutiny"
```

---

## 7. Best Practices
- First find the direct normative purpose of the individual provision → institutional purpose → branch-of-law / legal-order value purpose.
- Write as “by [means] achieve/prevent [concrete effect]”; prioritize the provision’s direct normative purpose before rising to institutional purpose and legal-order values. Do not start with vague fairness, justice, or order.
- Face subjective–objective conflict head-on: do not evade; allocate weight by three criteria (age / concreteness / rule–principle).
- Purpose ≠ conclusion; convert purpose into concrete meaning judgments such as broad/narrow, include/exclude, strict/expansive.
- All four checks must pass before output; if any fails, recurse and re-weigh.
- When legislative materials are insufficient, mark truthfully, increase objective-purpose weight, and do not invent legislative intent.

---

## 8. Limitations

- This skill must be invoked only after textual interpretation is completed; do not skip textual interpretation.
- The interpretive conclusion must not go beyond the provision’s possible semantic range.
- Value judgments such as “fairness” and “justice” must be anchored in concrete provisions, institutions, and case facts; do not talk values detached from text.
- The conclusion must not clearly contradict neighboring provisions or higher-law principles.
- There is no fixed priority between subjective and objective purpose; weigh in light of concrete factors.
- Applies only to legal interpretation, not legal development (gap-filling, analogy). When the provision does not cover the facts at all, turn to other methodological tools.
- Output is structured legal analysis and argumentation, without legal force; real cases require full evidence, procedural requirements, and judicial discretion.
