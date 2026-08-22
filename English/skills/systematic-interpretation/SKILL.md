---
name: systematic-interpretation
description: |
  Systematic interpretation (体系解释) addresses disputes over meaning or scope of application that remain after textual interpretation, by reference to the provision’s position in the legal system (which statute, book, chapter, or section), the meaning of related norms, or what the law as a system properly requires, so as to adopt the interpretation most consistent with systemic coherence and thereby clarify the provision’s meaning and scope from a systemic perspective.
  Trigger conditions (invoke if any one is met):
---

> **Chinese source (authoritative):** [`../../skills/systematic-interpretation/SKILL.md`](../../skills/systematic-interpretation/SKILL.md)

# Systematic Interpretation (体系解释)

## Trigger Conditions

1. Under textual interpretation, the legal norm yields two or more possible meanings and none can be chosen.

2. Textual interpretation has fixed the core scope of application, but the borderline remains fuzzy and needs clarification.

3. Under textual interpretation, a legal fact is covered by the wording of two or more norms or clusters of norms, and it is unclear which should apply.

__Capabilities__

This skill can:

1. Capability 1: When textual interpretation cannot fix the meaning of a legal norm, elucidate that meaning by reference to the legal system.

2. Capability 2: From a systemic perspective, judge whether a legal norm applies to particular facts.

3. Capability 3: From a systemic perspective, judge which legal norm or cluster of norms should apply to particular facts.

__How to Use__

__Step-by-step instructions__

step 1 From the result of textual interpretation, identify the unresolved dispute type and compress it into one concrete question sentence.

1. Dispute types are limited to the following three:

(1) Under textual interpretation, the legal norm yields two or more possible meanings and none can be chosen.

(2) Textual interpretation has fixed the core scope of application, but the borderline remains fuzzy and needs clarification.

(3) Under textual interpretation, a legal fact is covered by the wording of two or more norms or clusters of norms, and it is unclear which should apply.

2. The question sentence should preferably be a single-sentence Q&A form, for example:

(1) In Article 1169 of the Civil Code (民法典), should “共同” (joint / common) be understood as “subjective jointness” or “objective jointness”?

(2) Does Article X apply to fact Y?

(3) Should fact A be governed by Article X or Article Y?

step 2 For the disputed issue, use systemic interpretive resources from near to far, under the following rules:

1. Interpret the statutory text itself in light of what the legal system properly requires:

1. If a legal norm lists specific persons or things and then assigns them to a “category of the same type,” interpretation of the open-ended clause should treat them as of the same type as the listed persons or things.
2. If a legal norm makes no special provision on its scope of application, it should be understood as general law, generally applicable to all subjects, matters, and territories.
3. Under a closed enumeration, if the text expressly mentions one or more matters of a given kind, other matters of that kind not mentioned may be treated as impliedly excluded.

(4) If a norm is an exception to a general norm, its scope of application must be strictly limited; it must not be casually expanded or analogically applied.

2. Interpret according to the systemic position of the relevant legal norms. Specific rules:

(1) Determine meaning or scope by the name of the book, chapter, or section in which the norm sits.

1. If a norm is labeled general provisions (总则) in a statute, or basic / general provisions in a book or chapter, or sits near the front of a chapter or section (often as the first article), and subsequent norms in the same statute, book, chapter, or section regulate matters that its wording can cover, it may also apply to matters regulated by those subsequent norms.
2. When a fact is covered by two or more norms, apply higher law over lower law, special law over general law, and later law over earlier law. Criteria:

a. Hierarchy: Constitution > statutes (法律) > administrative regulations (行政法规) > local regulations (地方性法规) and administrative rules (行政规章, including departmental rules and local government rules). Local regulations prevail over administrative rules of the same or lower-level government.

b. Norms that sit earlier in the system, cover a broader range, and are more abstract are usually general norms.

c. The later-enacted norm is the new law.

3. Find related legal norms and, from their meanings, determine the meaning or scope of the contested norm. Specific rules:

(1) Apart from the division between general and special norms, if an interpretation would deprive neighboring norms of independent application, prefer to exclude that interpretation.

(2) Use the rule that “the same term in the same statute should, in principle, keep a uniform meaning” to determine concept meaning or scope of application.

(3) Use the rule that “if the law uses two terms, they should in principle be distinguished” for interpretation.

  
step 3 In the following situations, do not output a final conclusion; truthfully report that the situation exists:

1. The textual core itself is not yet fixed, so systematic interpretation cannot proceed.

2. The above rules yield no conclusion, or yield conflicting conclusions, so no systematic-interpretation conclusion can be drawn.

3. The facts to be decided already fall outside the possible textual meaning of the provision, and gap-filling is required.

4. Resolution of the dispute mainly depends on teleological interpretation, interest balancing, or policy judgment, and cannot be made through systematic interpretation.

5. A new general provision and an old special provision of the same organ conflict; local regulations and departmental rules conflict on the same matter; departmental rules conflict with each other or with local government rules; or regulations made under authorization conflict with statute.

step 4 If none of the step-3 situations applies, output a conclusion containing:

1. The disputed issue

2. Systemic grounds and reasons for the judgment

3. The systematic-interpretation conclusion

__Input Format__

Describe expected input:

Format : Description Input should include:

(1) Content of the legal norm (required)

(2) Disputed word / disputed scope (required)

(3) Candidate meanings from textual interpretation (optional)

(4) Facts to be judged (optional)

Example: In Article 1168 of the Civil Code, “二人以上共同实施侵权行为” (“two or more persons jointly commit a tort”), “共同” may mean subjective jointness or objective jointness, and cannot be fixed.

__Output Format__

Describe what will be produced:1

1. Output 1: Description Where a conclusion can be reached through systematic interpretation, output:

(1) The disputed issue

(2) Systemic grounds and reasons

(3) The systematic-interpretation conclusion

Example: In Article 1168 of the Civil Code, “共同” may mean “subjective jointness” or “objective jointness.” Combining Articles 1171 and 1172 on multi-party torts without subjective liaison but with objectively combined conduct causing harm shows that “共同” in Article 1168 already excludes multi-party torts without liaison of intent; therefore it means joint fault, i.e. “subjective jointness.”

2. Output 2: Description Where systematic interpretation cannot yield a conclusion, output:

1. The part that cannot be judged
2. The reason it cannot be judged

Example: Regarding “显失公平” (obvious unfairness) in Article 105 of the Civil Code, interpretation mainly depends on value judgment and legislative purpose, and cannot be decided through systematic interpretation alone.

__Example Usage__

● Under step 2 1.(1): Article 999 of the Civil Code provides “为公共利益实施新闻报道、舆论监督等行为” (news reporting, public-opinion supervision, and similar acts for the public interest). In interpreting “等行为” (and similar acts), it should mean acts of the same type as news reporting and public-opinion supervision that serve the public interest, not other public-interest acts of a different kind.

● Under step 2 1.(2): Article 1165(1) of the Civil Code makes no special provision on scope; it is a generally applicable rule of tort damages.

● Under step 2 1.(3): Article 1125 of the Succession Book of the Civil Code provides that an heir who alters or conceals a will under serious circumstances loses the right to inherit. Under expressio unius, other situations such as mere concealment without the statutory conditions do not cause loss of succession rights (as stated in the source illustration for closed enumeration).

● Under step 2 1.(4): Article 1190(1) of the Civil Code provides that a person with full capacity who temporarily lacks consciousness or control and causes harm bears tort liability if at fault; if not at fault, shall make appropriate compensation according to economic condition. The no-fault appropriate-compensation rule is an exception and must be strictly construed: only where the fully capable person temporarily lacked consciousness or control and caused harm without fault does the actor bear compensation rather than tort liability.

● Under step 2 2.(1): Representation by subrogation under Article 1128 of the Civil Code could, on the text alone, cover intestate or testamentary succession; but its systemic position is the chapter on intestate succession in the Succession Book, so systematically it covers only intestate succession.

● Under step 2 2.(1): “占有” (possession) in the Property Rights Book of the Civil Code, when used in the Ownership subdivision, means the possession incident of ownership; when used in the Possession subdivision, it means the fact of possession.

● Under step 2 2.(2): Article 1245 provides that keepers or managers of animals that cause harm bear tort liability, subject to defenses of intentional or grossly negligent conduct by the victim. It sits before Article 1249 on abandoned or escaped animals. Textually, matters regulated by Article 1249 also fall within Article 1245’s wording; therefore Article 1245’s defenses and mitigation may also apply to Article 1249.

● Under step 2 3.(1): Whether “共同” in Article 1168 on joint tort adopts joint-fault or objective-connection theory is disputed. Combining Articles 1171 and 1172 on multi-party torts without subjective liaison but with objectively combined harm shows that “共同” in Article 1168 excludes multi-party torts without liaison of intent; therefore it means joint fault.

● Under step 2 3.(2) (scope): Article 367(2) on contents of a habitation-right contract lists “当事人的姓名或者名称和住所” (name or designation and domicile of the parties). Systematically, Article 1012 gives natural persons the right to a personal name (姓名), while Article 1013 gives legal persons and unincorporated organizations the right to a designation (名称). The Civil Code distinguishes 姓名 and 名称; “名称” is used for legal persons and unincorporated organizations. Therefore, systematically, the subject of a habitation right is not limited to natural persons and includes legal persons and unincorporated organizations.

● Under step 2 3.(2) (meaning): Article 1222 refers to “隐匿或者拒绝提供与纠纷有关的病历资料” (concealing or refusing to provide medical records related to the dispute); Article 1225 specifies types of medical records (admission notes, orders, test reports, etc.). Interpretation of Article 1222 should therefore refer to Article 1225.

● Under step 2 3.(3): In the Contracts Book, some norms say “债权债务” (creditor’s rights and debts) and others “合同权利义务” (contractual rights and obligations). Systematically, norms using “债权债务” (e.g., assignment of claims and assumption of debts in Chapter 6 on modification and assignment) apply not only to contracts but also to other obligatory relationships; norms using “合同的权利义务” (e.g., Article 556 on comprehensive transfer of contractual rights and obligations) apply only to contractual relationships.

__Best Practices__

● This skill must be invoked only after textual interpretation is completed; do not skip textual interpretation.

● Systematic interpretation must not go beyond the possible textual meaning of the legal norm.

● For the disputed issue, use systemic resources from near to far: first the same article, same book/chapter/section, and neighboring articles in the same statute, then other norms in the same branch of law; avoid over-generalizing at the outset.

● Where systematic interpretation cannot yield a conclusion, do not force a judgment; output the part that cannot be judged and the reason.

__Limitations__

● Systematic interpretation presupposes that textual interpretation has fixed the core meaning; if the core meaning is unclear, systematic interpretation cannot apply.

● Systematic interpretation easily depends on the external form of law. Positive law is presumed to be systemic, but that presumption is not absolutely reliable and should be checked against teleological interpretation.

● It applies only to legal interpretation, not to legal development (gap-filling, analogy). When the provision does not cover the facts at all, turn to other methodological tools.

● Output is structured legal analysis, not a substitute for an adjudicative conclusion; real cases still require full facts, evidence, procedural posture, and adjudicative authority.
