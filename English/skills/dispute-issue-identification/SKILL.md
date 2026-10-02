---
name: dispute-issue-identification
description: |
  Dispute-issue identification means, after legal-element extraction, extracting the issues in dispute from the legal facts and further converting case relationships into questions of legal relationship.
  It can exclude undisputed matters and effectively focus subsequent analysis on the parties' disputed facts, evidence, and application of law.
  By further refining disputed issues through fact investigation and evidence review, one can approach the essence of the dispute more deeply and analyze the case more thoroughly.
---

> **Chinese source (authoritative):** [`../../skills/dispute-issue-identification/SKILL.md`](../../skills/dispute-issue-identification/SKILL.md)

# Dispute Issue Identification

## Capabilities

This skill can:

- Identify disputed issues from case materials.
- Determine which disputes are factual disputes and which are legal disputes.
- Convert scattered content into legal questions that provide a foundation for subsequent analysis.

## How to Use

Step-by-step instructions:

1. Identify the parties to the case (two or more).

   Identify the parties' identities and clarify how many parties are involved and who each party is.

2. Identify each party's claims.

3. Determine whether the parties' disputes center on facts or on legal evaluation. Clarify the content of the dispute—i.e., where the parties' claims differ. Distinguish between: differences of fact and differences of legal evaluation.

   Factual disputed issues, often also called general disputed issues, are mainly facts about which the parties dispute the formation, modification, or extinction of a legal relationship. For example, in a private lending case, whether the borrower actually received the funds; in a creditor's subrogation dispute, whether the debtor neglected to exercise its own rights in a way that impaired the creditor's claim, and so on.

   The most common legal disputed issues concern the correct interpretation and application of law. Their formulation is more specialized and often intertwined with facts, making boundary-drawing and characterization objectively difficult. When factual disputed issues encounter problems of legal application or evidence rules, they can easily convert into legal disputed issues, including allocation of the burden of proof, evidentiary validity and probative force, interpretation of legal provisions, and correct application of law.

   Accurately grasping the core elements of what the parties are contesting, and appropriately summarizing the disputed issues, not only directly affects the outcome of the case but also has a directional effect on protecting the parties' substantive rights. For example, whether the parties constitute repetitive litigation involves both factual disputes over whether the parties, claims, and subject matter are the same, and legal disputes over how the parties understand each element differently, and directly determines the adjudicative direction of the parties' substantive rights.

4. Convert disagreements into standardized disputed issues. Convert scattered dispute content into problem statements that have legal-analytical significance. Formulations of disputed issues should be as objective, concise, and adjudicable as possible, avoiding purely emotional or colloquial language.

5. Assess the hierarchy of different disputed issues. Not all disagreements are equally important; further distinguish core issues, secondary issues, and background disagreements. Specifically:

- Core issues: questions that directly affect whether a claim is established, whether a defense is established, whether liability is borne, and how legal effects are determined;
- Secondary issues: usually affect the scope of liability, amount of damages, arrangement of the burden of proof, auxiliary fact-finding, or specific forms of relief;
- Background disagreements: although contested, they have weaker impact on the adjudicative conclusion and mainly serve narrative supplementation or factual background.

6. Separately organize the supporting grounds for each party's claims—i.e., which facts, evidence, and legal bases each party relies on to support its position.

   This step usually includes: what key facts the plaintiff's claims rest on; what key facts the defendant's defenses rest on; which evidence each side cites; and which legal norms or legal effects each side's claims attempt to map onto.

7. Dynamic adjustment check. Disputed issues are not fixed. As litigation progresses, new facts or evidence may appear; disputed issues must be dynamically adjusted based on trial developments, and the parties' views should be sought before the close of trial to ensure the disputed issues accurately reflect the case's core disputes.

## Input Format

Expected input forms:

- Format 1: Case fact materials that have already been preliminarily organized.

  Input may be case materials after legal-fact extraction, including subject facts, conduct facts, temporal facts, result facts, causation, etc. This type of input is suitable for directly conducting disputed-issue identification.

- Format 2: Case fact narratives that have not undergone legal-fact extraction.

  Input may also be judgment case summaries, trial dispute statements, summaries of advocacy opinions, consultation records, or case materials containing the plaintiff's claims, the defendant's defenses, evidence status, and preliminary legal disagreements. This type of input is suitable for further extracting disputed issues from the factual structure.

## Output Format

Will generate:

- Disputed-issue descriptions:

  Descriptions of disputed issues are generally expressed as interrogative sentences, e.g., "Whether Zhang San constitutes unauthorized possession," "Whether Li Si's acquisition of property has a legal basis." Output may follow a "conclusion → reasons → basis" format.

  Output as a structured list of disputed issues, usually including core disputed issues, secondary disputed issues, and brief explanations, and indicating the main factual disagreements and legal questions corresponding to each issue.

- Disputed-issue format:

  May output a disputed-issue checklist or table. For complex cases, may also output a chronologically expanded issue structure, suitable for organizing complex cases and visual presentation.

## Example Usage

Examples:

- Example 1:

  Based on the following case materials, identify the disputed issues in this case and distinguish which are factual disputes and which are legal disputes:

  Party A claims that in May 2024 it transferred RMB 100,000 to Party B, with an agreement to repay within one month; Party B contends that the RMB 100,000 was not a loan but cooperative investment funds. Party A demands that Party B return the loan principal and interest; Party B disagrees.

- Example 2:

  Based on the following sale-of-goods dispute materials, extract core disputed issues suitable for civil claim analysis, and explain which key facts, evidence, and legal questions each disputed issue corresponds to:

  The plaintiff claims that when purchasing a computer on a second-hand platform, the seller clearly stated it was 'brand new and unopened'; the defendant contends it never promised the computer was brand new and only said 'good appearance.' After receiving the goods, the plaintiff discovered repair marks on the motherboard and requests return and refund.

- Example 3:

  Based on this case summary, organize the disputed issues by the hierarchy 'core issues—secondary issues—background disagreements':

  The plaintiff claims a platform disclosed its mobile number to a third party without consent, causing continuous harassment; the defendant platform contends the information at issue is not sensitive personal information and that the plaintiff failed to prove causation between the harassment and the platform's conduct.

- Example 4:

  Based on the following trial dispute statement, organize each side's supporting grounds and map them under the respective disputed issues:

  The plaintiff claims the contract was formed and the payment obligation has been performed; the defendant claims the contract has not yet taken effect, and even if it has, non-performance was caused by the plaintiff's prior breach.

## Scripts (if applicable)

## Best Practices

1. Identify issues centered on claims and defenses

   Disputed issues should revolve around whether claims are supported and defenses are established. Only disagreements that affect judgments of rights and obligations, allocation of liability, or legal effects should be identified as true disputed issues.

2. Disputed issues should be formulated as adjudicable questions

   Issue formulations should be as objective, concise, and standardized as possible, avoiding emotional, partisan, or conclusion-presuming language, and should focus on what facts and normative questions need to be decided.

## Limitations

- **Limitation 1**  

  Disputed-issue identification depends on the quality of case-fact organization. If underlying fact extraction is incomplete, the parties' claims are unclear, or evidence materials are severely insufficient, the issue-identification results may be relatively vague.

- **Limitation 2**  

  This skill cannot replace resolution of the dispute; it can only serve as a preliminary step in legal analysis.
