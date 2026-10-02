---
name: deductive-reasoning
description: |
  Perform rigorous legal deductive reasoning based on formal logic. Use this skill when the user asks to "analyze case logic", "verify legal reasoning", "extract a syllogism", "map the relationship between case facts and legal provisions", or "assess the validity of a legal argument".
  Provides a formal-logic framework for legal reasoning that turns unstructured legal norms and case facts into valid, testable, and reproducible deductive argument chains (P-F-C).
---

> **Chinese source (authoritative):** [`../../skills/deductive-reasoning/SKILL.md`](../../skills/deductive-reasoning/SKILL.md)

# Deductive Reasoning

## Description
Perform rigorous legal deductive reasoning based on formal logic. Use this skill when the user asks to “analyze case logic”, “verify legal reasoning”, “extract a syllogism”, “map the relationship between case facts and legal provisions”, or “assess the validity of a legal argument”.
Provides a formal-logic framework for legal reasoning that turns unstructured legal norms and case facts into valid, testable, and reproducible deductive argument chains (P-F-C).

## Instruction Steps

### Step 1: Input

Read the case materials provided by the user and classify them into the following three initial states (if missing, temporarily record as empty):
1. **Major premise (Provision, P):** Legal rules, including written law (statutes, regulations, rules) as well as case law, social norms, etc.
2. **Minor premise (Fact, f/F):**
   - **Natural minor premise (f):** Natural events, acts, states, etc. (parties’ oral statements or factual narratives, e.g., “A asked B to transport goods”).
   - **Legal minor premise (F):** Events, acts, or states with legal significance (a lawyer’s or judge’s characterization of natural facts, e.g., “A and B formed a carriage contract relationship”).
3. **Conclusion (hypothesis) (Conclusion, C):** Partial or final conclusions drawn in judgment documents (e.g., guilty/not guilty, breach/no breach). Partial conclusions include intermediate conclusions or hypothesis conclusions awaiting verification, such as issues summarized by the judge, or preliminary inferences by parties or counsel.

Example:
【Major premise】: empty
【Minor premise – legal facts】: empty
【Minor premise – natural facts】: Company Jia entrusted transport of a shipment of goods to consignee Company Yi. Company Jia’s legal representative contacted by phone and entrusted a certain motor transport company with the carriage. The motor transport company did not conclude a written carriage contract with Company Jia. During transport, a traffic accident caused by the driver’s negligence damaged the goods. Company Yi therefore could not receive the goods on time and suffered loss.
【Conclusion (hypothesis)】 Against whom should Company Yi claim compensation? Company Yi believes it can claim against the transport company.

### Step 2: Reasoning
Strictly perform the following Parts A and B, and **cycle alternately** until all logic is closed and no further supplementation is needed:

#### A. Complete the logical structure of each part
1. **Major premise (P):** Organize the logical structure; if there is no express provision, supply an implied major premise. Identify the type:
   - **Categorical syllogism:** Applicable to constitutive elements and conditions of establishment. Form: All acts satisfying feature $X$ have legal consequence $Y$.
   - **Hypothetical syllogism:** Applicable to “if … then …” rules.
     - Affirming the antecedent (modus ponens): $X \rightarrow Y$; the facts satisfy $X$, $\therefore Y$. (Most common)
     - Denying the consequent (modus tollens): $X \rightarrow Y$; $\neg Y$, $\therefore \neg X$. (Used for defenses and excluding legality)
2. **Minor premise (f/F):**
	1. Clarify the nature, sequence, causation, and subordination of events.
	2. Clarify the legal relationships among subjects; check whether a legal relationship exists between each pair of subjects.
	3. Exhaust each relationship; mark missing or ambiguous legal relationships.
3. **Conclusion (C):** Rank and filter multiple conclusions; identify and mark “intermediate conclusions”.

#### B. Link relationships and identify the middle term
> **Note:** The middle term appears in both premises but not in the conclusion. It is the bridge connecting the syllogism, typically the “condition part” of a legal rule.

1. **Fact subsumption (f-F):** Link from the natural minor premise to the legal minor premise; extract and state the middle term (e.g., the mediating concept from “failure to pay the balance” to “fundamental breach”).
2. **Finding the norm (F-P):** Link from the legal minor premise to the relevant legal major premise; extract and state the middle term that triggers the provision.
3. **Deriving the conclusion (P-F-C):** From the legal major premise and legal minor premise, reason to the conclusion; write it in a complete standard syllogism format; verify that the middle term has been correctly derived.

### Step 3: Output
Each time this skill is invoked, output two parts strictly in the following format:
#### 1. Explainable reasoning chain
Use a clear P-F-C structure diagram or hierarchical list to show how the conclusion traces step by step, through intermediate conclusions, legal minor premises, and natural minor premises, back and links to the corresponding major premises. Clearly mark the middle term used at each step.

Example:

1. Fact subsumption

| Natural facts (f: Raw Facts)                           | Legal minor premise (F: Legal Facts)    | Characterization               |
| ------------------------------------------- | ----------------------- | ------------------ |
| f1: There is an arrangement for delivery of goods between Jia and Yi                            | **F1: There is a contractual relationship between Jia and Yi**      | An arrangement for delivery of goods usually implies a sales or supply contract |
| f2: Jia entrusted Bing by phone to transport the goods                             | **F2: There is a carriage contract relationship between Jia and Bing**    | Entrustment by phone may constitute a valid oral carriage contract    |
| f3: During transport, Bing’s driver carelessly opened the truck door, causing loss of goods; Yi failed to receive the goods on time and suffered loss | F21: As carrier, Bing’s driver’s negligence caused damage to the goods | The carrier is responsible for its staff’s negligence       |
| f3 (same as above)                                      | Consequence of F11: Jia’s non-performance toward Yi        | Breach caused by a third party          |
| f5 (missing)❗ No statement whether a contract or agreement exists between Yi and Bing                   | F3 (missing): Whether a contractual relationship exists between Yi and Bing    | No contractual relationship stated; default is that none exists.   |
2. Finding the norm

| Legal minor premise F                    | Corresponding legal norm P                                   | Triggering middle term (Middle Term) |
| -------------------------- | ------------------------------------------ | ------------------ |
| **F1: Contractual relationship between Jia and Yi**         | **P1: Civil Code Art. 465(2)**: A lawfully established contract is legally binding only on the parties.   | Parties to the contract              |
| **F21: As carrier, Bing’s driver’s negligence caused damage to the goods** | **P3 (first sentence) Civil Code Art. 593**: Breach due to a third party → liability to the counterparty.   | Party in breach due to a third party       |
| **F2: Carriage contract relationship between Jia and Bing**       | **P3 (second sentence) Civil Code Art. 593**: Disputes between a party and a third party → handled according to law or agreement. | Disputes between a party and a third party       |
| **F21 (same as above)**                | **P2: Civil Code Art. 832**: Carrier causes cargo damage → carrier bears liability for compensation.       | Carrier causes cargo damage            |
| **F3 (missing)❗: Whether Yi and Bing are parties to a contract**    | **P1: Civil Code Art. 465(2)**: same as above                      | Parties to the contract              |

3. Reasoning chain
**C1: Yi recovers from Jia**

C1‑1: Jia owes contractual duties to Yi
P1: All parties to a contract → bound by the contract
F1: Jia and Yi are parties to the contract
C1‑1: Jia owes contractual duties to Yi

C1: Yi may recover from Jia
P3‑1: Breach due to a third party → liability to the counterparty
F21: Bing’s negligence caused Jia’s breach toward Yi
C1: Yi may recover from Jia

**C2′: Yi recovers from Bing**

P1: All parties to a contract → bound by the contract
F3 (missing): Yi and Bing are parties to the contract
C2′: Yi may recover from Bing

**C3: Jia recovers from Bing**

 C3‑1: Bing bears liability to Jia for compensation
P2: Carrier causes cargo damage → carrier bears liability for compensation
F21: Bing caused cargo damage
C3‑1: Bing bears liability to Jia for compensation

C3: Jia may recover from Bing
P3‑2: Disputes between a party and a third party → handled according to law or agreement
F2: There is a carriage contract relationship between Jia and Bing
C3: Jia may recover from Bing

#### 2. Validity explanation report
Verify the form of the reasoning against the following standards and output a report:
- **Validity conclusion:** Clearly state which parts of the reasoning chain are “valid” and which are “invalid”.
- **Fallacy explanation:** If invalid, specifically identify which logical fallacy it is.
When verifying validity, strictly check the following three common logical fallacies:
1. **Affirming the Consequent:** - Erroneous form: $P \rightarrow Q$, $Q$, $\therefore P$.
   - Explanation: Treating “the result occurred” as “this must have been the cause”.
2. **Denying the Antecedent:**
   - Erroneous form: $P \rightarrow Q$, $\neg P$, $\therefore \neg Q$.
   - Explanation: Treating “this cause is absent” as “the result will not occur”.
3. **Fallacy of Four Terms:**
   - Erroneous form: All $A$ are $B$. All $C$ are $D$. $\therefore$ All $A$ are $D$.
   - Explanation: The middle term does not truly connect, or the concept was switched (the middle term must be distributed at least once).

Example:

| Conclusion            | Formal validity  | Middle-term status     | Fallacy type   | Explanation           |
| ------------- | ------ | -------- | ------ | ------------ |
| C1: Yi recovers from Jia      | Valid     | Middle term present     | None      | Reasoning chain complete        |
| **C2′: Yi recovers from Bing** | **Invalid** | **Middle term missing** | Affirming the consequent | Premise forced in; reasoning structure broken |
| C3: Jia recovers from Bing      | Valid     | Middle term present     | None      | Reasoning chain complete        |

### Skill Boundaries & Troubleshooting Guide (Troubleshooting & Constraints)
Validity judgment **depends only on form, not on content**. Even if the major or minor premise is factually false, so long as the logical form is correct, the reasoning must still be judged “valid”.
