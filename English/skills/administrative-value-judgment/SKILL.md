---
name: administrative-value-judgment
description: Assist legal staff of administrative organs in mainland China, based on a given administrative fact pattern, in making value judgments and interest balancing under the basic principles of administrative law, and in forming a provisional discretionary conclusion.
---

> **Chinese source (authoritative):** [`../../skills/administrative-value-judgment/SKILL.md`](../../skills/administrative-value-judgment/SKILL.md)

This Skill is for administrative organs handling value conflicts and discretionary choices in a concrete fact pattern. It does not replace a formal administrative decision; it only outputs value judgments and discretionary recommendations of an internal analytical nature.

## Capabilities

- Extract from the fact pattern the discretionary issue, affected parties, main interests, and value conflicts.
- Review item by item under legality, rationality, the principle of proportionality, the principle of equality, due process, and good faith and legitimate expectation protection.
- Distinguish public interest, individual rights and interests, institutional values, and instrumental values.
- Identify the risk that administrative convenience, performance-assessment pressure, or managerial efficiency is mislabeled as public interest.
- Compare the interest gains and rights harms of different handling options.
- Output a provisional discretionary conclusion, reasons, least-harmful measures, and matters requiring verification.

## How to Use

### Step 1: Fact-pattern preprocessing

**Goal:**  
Extract the basic information needed for subsequent review.

**Operations:**

1. Extract the core discretionary issue.
2. Identify the affected parties.
3. List the main interests and values.
4. Provisionally locate the value conflict.

**Output:**

- Core discretionary issue:
- Affected parties:
- Main interests/values:
- Provisional value conflict:


----------

### Step 2: Legality principle review

**Goal:**  
Determine whether the value judgment breaches the bottom line of administration according to law (依法行政).

**Rules:**

1.  Options that are clearly unlawful, ultra vires, or without legal basis must not enter interest balancing.
    
2.  Public interest, policy goals, or administrative efficiency must not be used to justify unlawful administration.
    
3.  Where legality information is insufficient, mark “not stated in the fact pattern”.
    

**Output:**

- Whether there is clear risk of unlawfulness, ultra vires action, or lack of basis:
- Whether subsequent interest balancing may proceed:
- Explanation:

----------

### Step 3: Rationality principle review

**Goal:**  
Determine whether the handling direction is fair, appropriate, and consistent with the circumstances of the individual case.

**Rules:**

1.  Identify mechanical enforcement and one-size-fits-all handling.
    
2.  Identify manifest unfairness.
    
3.  Identify disregard of special circumstances of the individual case.
    
4.  Identify treating administrative convenience or performance-assessment pressure as public interest.
    

**Output:**

- Whether there is clear unreasonableness:
- Value judgments that need correction:
- Explanation:
----------

### Step 4: Proportionality principle review

**Goal:**  
Determine whether the administrative objective and the harm to rights and interests are proportionate.

**Rules:**

1.  **Suitability (适当性):** Whether the measure helps achieve the administrative purpose.
    
2.  **Necessity (必要性):** Whether there is a less harmful alternative that is equally effective.
    
3.  **Balancing / proportionality stricto sensu (均衡性):** Whether the gain in public interest outweighs the harm to individual rights and interests.
    

**Output:**

- Suitability:
- Necessity:
- Balancing:
- Conclusion under the principle of proportionality:

----------

### Step 5: Equality principle review

**Goal:**  
Determine whether like cases are treated alike and unlike cases are treated with reasonable differentiation.

**Rules:**

1.  Like cases should be treated alike.
    
2.  Different circumstances may be treated with reasonable differentiation.
    
3.  Prevent selective enforcement.
    
4.  Reasonable accommodation may be made for vulnerable or special groups.
    

**Output:**

- Whether there is risk of unequal or selective treatment:
- Whether differentiated treatment is needed:
- Explanation:

----------

### Step 6: Due process principle review

**Goal:**  
Determine whether procedural values have been adequately considered.

**Rules:**

1.  Whether reasons must be given.
    
2.  Whether statements and defenses must be heard.
    
3.  Whether rectification, supplementation, hearing, argumentation, disclosure, or risk assessment is needed.
    
4.  When major rights and interests are affected, the intensity of procedural safeguards should be increased.
    

**Output:**
- Procedural values that need to be safeguarded:
- Whether additional procedures are needed:
- Explanation:

----------

### Step 7: Good faith and legitimate expectation protection review

**Goal:**  
Determine whether the administrative organ should protect the relative party’s reasonable reliance (合理信赖).

**Rules:**

1.  Whether there is an administrative license, promise, guidance, confirmation, or long-standing stable practice.
    
2.  Whether the relative party formed a reasonable expectation based on that conduct.
    
3.  Whether the relative party has already invested costs or formed stable interests.
    
4.  Whether a transition period, rectification period, compensation, statement of reasons, or buffering arrangement is needed.
    

**Output:**

- Whether reasonable reliance exists:
- Whether reliance interests may be harmed:
- Whether buffering or remedy is needed:
- Explanation:

----------

### Step 8: Interest balancing

**Goal:**  
Compare the value gains and rights harms of different handling directions.

**Rules:**

1.  Public interest must be concretized.
    
2.  Administrative efficiency, managerial convenience, and performance-assessment pressure are usually only instrumental values.
    
3.  Foundational values usually take priority over instrumental values.
    
4.  Individual rights and interests may yield according to law, but must not be sacrificed without explanation.
    
5.  Where a less harmful option can achieve the administrative purpose, a heavier option should not be chosen.
    
6.  Values that yield should still retain a minimum level of protection.
    

**Output:**

- Interests that should be prioritized for protection:
- Interests that may moderately yield:
- Bottom lines that must not be breached:
- Comparison of gains and losses across options:

----------

### Step 9: Discretionary conclusion

**Goal:**  
Form a provisional discretionary opinion.

**The conclusion must include:**

1.  Recommended handling direction.
    
2.  Core reasons.
    
3.  Least-harmful or buffering measures.
    
4.  Options that should not be taken, and why.
    
5.  Matters requiring further verification.
    

**Output:**

- Provisional conclusion:
- Reasons:
- Least-harmful or buffering measures:
- Options that should not be taken:
- Matters requiring further verification:

## Input Format

Input is primarily a passage of administrative facts.

【Fact pattern】
An administrative organ, in handling a matter, faces different handling choices. The fact pattern includes the factual background, parties involved, contemplated measures, and possibly affected public interests and individual rights and interests.

## Output Format

Final output is fixed as:

```markdown
# Administrative Value Judgment and Discretionary Analysis

## I. Fact-pattern preprocessing
- Core discretionary issue:
- Affected parties:
- Main interests/values:
- Provisional value conflict:

## II. Legality principle review
- Whether there is clear risk of unlawfulness, ultra vires action, or lack of basis:
- Whether subsequent interest balancing may proceed:
- Explanation:

## III. Rationality principle review
- Whether there is clear unreasonableness:
- Value judgments that need correction:
- Explanation:

## IV. Proportionality principle review
- Suitability:
- Necessity:
- Balancing:
- Conclusion under the principle of proportionality:

## V. Equality principle review
- Whether there is risk of unequal or selective treatment:
- Whether differentiated treatment is needed:
- Explanation:

## VI. Due process principle review
- Procedural values that need to be safeguarded:
- Whether additional procedures are needed:
- Explanation:

## VII. Good faith and legitimate expectation protection review
- Whether reasonable reliance exists:
- Whether reliance interests may be harmed:
- Whether buffering or remedy is needed:
- Explanation:

## VIII. Interest balancing
- Interests that should be prioritized for protection:
- Interests that may moderately yield:
- Bottom lines that must not be breached:
- Comparison of gains and losses across options:

## IX. Discretionary conclusion
- Provisional conclusion:
- Reasons:
- Least-harmful or buffering measures:
- Options that should not be taken:
- Matters requiring further verification:

```

## Example Usage

### Example Request

```text
Please conduct administrative value judgment and discretionary analysis based on the following fact pattern:

In a special food-safety rectification campaign, a municipal market regulation department found that a small community catering shop had substandard kitchen hygiene and nonstandard storage of some ingredients. The shop is located in an older community and mainly serves nearby elderly residents and students. The operator said recent renovation and staff turnover led to inadequate management, and is willing to rectify immediately.

Enforcement personnel have two views:
Option 1: Order suspension of business for rectification, to safeguard food safety and the effect of the special campaign.
Option 2: Order rectification within a time limit and strengthen follow-up inspection, to balance residents’ living convenience and the livelihood of the micro operator.

```

### Expected Output

```markdown
# Administrative Value Judgment and Discretionary Analysis

## I. Fact-pattern preprocessing
- Core discretionary issue: Whether to order immediate suspension for rectification, or first order time-limited rectification with strengthened follow-up inspection.
- Affected parties: Market regulation department, catering shop operator, nearby elderly and students, community residents, the public interested in food-safety regulation.
- Main interests/values:
  - Public interest: food safety, public health, market regulation order;
  - Individual rights and interests: freedom to operate, livelihood interests;
  - Social interests: living convenience of community residents;
  - Institutional values: effect of the special campaign, credibility of enforcement;
  - Instrumental values: administrative efficiency, uniform enforcement scale.
- Provisional value conflict: Food-safety regulatory effect vs. livelihood of the micro operator and convenience of community residents.

## II. Legality principle review
- Whether there is clear risk of unlawfulness, ultra vires action, or lack of basis: Not shown in the fact pattern.
- Whether subsequent interest balancing may proceed: Yes.
- Explanation: The administrative organ has a legitimate basis to intervene based on food-safety issues, but the fact pattern does not state whether the degree of violation reaches the level requiring mandatory suspension for rectification.

## III. Rationality principle review
- Whether there is clear unreasonableness: Immediate suspension for rectification may risk overly heavy treatment.
- Value judgments that need correction: The strictest measure should not be chosen merely because there is a special campaign.
- Explanation: The operator is willing to rectify, and the shop serves residents of an older community; individual-case circumstances should be considered.

## IV. Proportionality principle review
- Suitability: Both suspension for rectification and time-limited rectification help food-safety regulation.
- Necessity: If time-limited rectification plus reinspection can eliminate the hazard, suspension is not the least-harmful option.
- Balancing: Immediate suspension has a larger impact on the operator’s livelihood and community convenience.
- Conclusion under the principle of proportionality: Option 2 better satisfies necessity and balancing.

## V. Equality principle review
- Whether there is risk of unequal or selective treatment: Not stated in the fact pattern.
- Whether differentiated treatment is needed: Fine-grained treatment is needed based on severity of violation, attitude toward rectification, and community service function.
- Explanation: Like violations should be treated alike, but reasonable differentiation is allowed where special circumstances exist.

## VI. Due process principle review
- Procedural values that need to be safeguarded: Notice of problems, hearing of statements and defenses, statement of reasons, clear rectification requirements.
- Whether additional procedures are needed: If suspension for rectification is contemplated, fuller statement of reasons and procedural safeguards should be provided.
- Explanation: Due process reflects respect for the relative party’s operating rights and livelihood interests.

## VII. Good faith and legitimate expectation protection review
- Whether reasonable reliance exists: The fact pattern does not show a special administrative promise or license change.
- Whether reliance interests may be harmed: Immediate suspension may affect the operator’s stable operating expectations.
- Whether buffering or remedy is needed: A rectification period and reinspection mechanism may be set.
- Explanation: This case is better suited to balancing governance goals and reliance protection through a rectification period.

## VIII. Interest balancing
- Interests that should be prioritized for protection: Food safety, public health.
- Interests that may moderately yield: Freedom to operate, community convenience—but they must not be wholly disregarded.
- Bottom lines that must not be breached: Individual rights and interests must not be excessively sacrificed merely to demonstrate campaign intensity.
- Comparison of gains and losses across options:
  - Option 1: Strengthens regulatory effect, but causes greater harm and may be overly heavy;
  - Option 2: Balances food safety, operator livelihood, and community convenience, with less harm.

## IX. Discretionary conclusion
- Provisional conclusion: Prefer Option 2—order time-limited rectification and strengthen follow-up inspection.
- Reasons: Option 2 can achieve the food-safety regulatory purpose while reducing impact on the operator and community residents, and better accords with rationality and proportionality.
- Least-harmful or buffering measures: Specify rectification deadline, standards, and reinspection checkpoints; locally restrict for immediate risks; escalate if overdue without rectification.
- Options that should not be taken: Where the fact pattern does not show serious harm or refusal to rectify, immediate suspension for rectification is inappropriate.
- Matters requiring further verification: Severity of violation, whether a food-safety incident occurred, prior violation record, local scale of treatment in like cases, whether rectification can eliminate the hazard.

```

    

## Best Practices

1.  First extract the discretionary issue, then conduct principle review.
    
2.  First conduct principle review, then interest balancing.
    
3.  Public interest must be concretized.
    
4.  Administrative efficiency, managerial convenience, and performance-assessment pressure are usually only instrumental values.
    
5.  Proportionality review must fully cover suitability, necessity, and balancing.
    
6.  Where a milder alternative exists, prefer the less harmful option.
    
7.  Rights and interests that yield should still retain minimum protection.
    
8.  For information not stated in the fact pattern, clearly mark it; do not fabricate.
    
9.  The discretionary conclusion is only a provisional opinion, not a final administrative decision.
    

## Limitations

-   Does not replace a complete administrative legality review.
    
-   Does not replace specialized legal-application analysis of administrative penalties, licenses, compulsion, expropriation, etc.
    
-   Is not responsible for retrieving or confirming specific legal bases.
    
-   Does not make final decisions for the administrative organ.
    
-   Must not provide value justification for clearly unlawful conduct, ultra vires acts, fabricating evidence, concealing facts, or evading supervision.
