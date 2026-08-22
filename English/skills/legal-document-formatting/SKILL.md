---
name: legal-document-formatting
description: |
  Draft complete civil or criminal judgments based on the document-production standards of Chinese people's courts. Use this skill when the user asks to "draft a judgment", "generate a judicial document", "write a civil judgment", "write a criminal judgment", "prepare a document from the case file", or provides case-file materials and requests a judgment document. While drafting each section, autonomously invoke atomic skills (e.g., dispute-issue identification, statutory retrieval, deductive reasoning, evidence-efficacy evaluation).
---

> **Chinese source (authoritative):** [`../../skills/legal-document-formatting/SKILL.md`](../../skills/legal-document-formatting/SKILL.md)

# Legal Document Formatting

## Description

Convert case-file materials into format-compliant civil or criminal judicial documents. This skill does not itself perform statutory retrieval or evidence evaluation; rather, while drafting each section of the document, it identifies what legal judgment is currently required, explicitly invokes the corresponding atomic skill, and integrates that skill's result into the document text. Before drafting each paragraph, first determine which capability must be invoked, invoke it, and only then proceed with drafting.

## Instruction Steps

### Step 1: Input

Read all case-file materials provided by the user and complete the following two steps:

1. **Determine civil vs. criminal**, based on these signals:
   - Plaintiff is a natural person / legal person → civil; prosecuting authority is a people's procuratorate → criminal; if the plaintiff is a natural person but the cause of action or claims seek criminal liability (e.g., intentional injury, defamation), classify as a criminal (private prosecution) case → criminal
   - Core dispute concerns civil rights and obligations → civil; core dispute concerns whether a crime is constituted → criminal
   - If materials are insufficient to decide → **pause** and ask the user to supplement

2. **Invoke `Legal Core Element Extraction` (Skill #4)** to extract and register from the case file: party information, legal relationship (preliminary), claims or charges, key factual timeline, evidence list, and procedural information. Mark each item as "complete" or "missing".

> **Note:** If party identity information is severely incomplete (unable to identify plaintiff/defendant or the accused), pause drafting and list the missing items for the user.

Outcome routing: civil → Step 2-A; criminal → Step 2-B; if pause is triggered → immediately terminate this skill run, output the missing-items list, and wait for the user's reply.

---

### Step 2-A: Drafting a Civil Judgment

Draft in the following seven-section order. **Before drafting each section, confirm whether an atomic skill must be invoked; if so, invoke it and record the result.**

#### A-1. Caption / Title
- Court name (prefix provincial name for basic-level / intermediate courts; for foreign-related cases, prefix "People's Republic of China")
- Document name (Civil Judgment)
- Case number: (year) court abbreviation + type abbreviation + serial number + "号". Year in Arabic numerals; full-width parentheses.

#### A-2. Opening — Parties and Procedural History
- Natural person: name, sex, date of birth, ethnicity, occupation / unit and position, domicile (per ID card / household registration)
- Legal person: full name, domicile, legal representative's name and position
- Litigation-status order: first instance — plaintiff → defendant → third party; second instance — appellant (note first-instance status in parentheses) → appellee → others
- Appointed litigation agents on a separate line; for lawyers write "Name, lawyer of XX Law Firm"
- Punctuation: **colon** after litigation status; **comma** after the name
- Case origin: state case name and source; procedural history: filing date, applicable procedure, hearing modality, persons appearing in court

**Invoke:** `Dispute Issues and Legal Relationship Identification` (Skill #6) → confirm the cause of action is accurate.

#### A-3. Facts Section

Draft three parts in order:

**(1) Pleadings / arguments:** Plaintiff's claims + factual grounds → defendant's defense → third-party statements. Synthesize the complaint and trial submissions; do not copy verbatim. After "the defendant argued" use a **comma**; after "××× submitted the following claims to this Court" use a **colon**.

**(2) Evidence exchange / cross-examination overview:** Start a new paragraph: "The parties in this case submitted evidence in accordance with law around the claims, and this Court organized evidence exchange and cross-examination."

**(3) Evidence findings and fact findings:**
- Undisputed evidence: "Evidence to which the parties raised no objection is confirmed by this Court and is on file for corroboration."
- Disputed evidence: **Invoke `Evidence Efficacy` (Skill #12)** → evaluate authenticity, legality, and relevance (the "three attributes") and probative force item by item → state the evidence name, the court's finding, and the reasons.
- Narrate fact findings chronologically; may use the lead-in "It is further found that" for supplements.

> **Note (three situations that require a mandatory pause):**
> 1. Plaintiff and defendant give completely contradictory accounts of the same fact and both have evidence → invoke `Evidence Efficacy` (Skill #12) + `Conflict Resolution and Priority Determination` (Skill #20); reach a conclusion before continuing
> 2. Key evidence's three attributes are in doubt (unclear source; photocopy without original for comparison) → invoke `Evidence Efficacy` (Skill #12) and first conclude whether the evidence is admitted
> 3. Characterization of the legal relationship is disputed (e.g., dispute over contract nature) → invoke `Dispute Issues and Legal Relationship Identification` (Skill #6) + `Legal Concept Comprehension` (Skill #5); the characterization conclusion determines how facts are narrated

#### A-4. Reasoning Section ("This Court holds")

Begin with "This Court holds," (**note: followed by a comma**). This is the core paragraph of the document; apply the following skill-invocation rules:

| Step | Atomic skill invoked | Purpose |
|------|----------------------|---------|
| 1 | `Dispute Issues and Legal Relationship Identification` (Skill #6) | Determine dispute nature; list dispute issues |
| 2 | `Statutory Retrieval` (Skill #8) | Retrieve laws, regulations, and judicial interpretations corresponding to the dispute issues; if legal conflict exists, determine priority |
| 3 | `Conflict Resolution and Priority Determination` (Skill #20) | If rights conflict exists, determine priority |
| 4 | `Deductive Reasoning` (Skill #16) | Syllogism: major premise (legal norm) + minor premise (found facts) → conclusion; argue each dispute issue one by one |
| 5 | `Case Retrieval` (Skill #9) | When Guiding Cases must be cited |
| 6 | `Judicial Value Judgment` (Skill #22) | Weighing of civil interests in adjudication |

Reasoning structure requirements:
- Unfold issue by issue around the dispute foci, with clear hierarchy
- When citing law, always state: full official title of the normative document + article/paragraph/item numbers
- When citing an "item" (项), always use Chinese characters without parentheses (e.g., "第一项", not "第（一）项")
- The closing paragraph may use "In summary" to introduce an overall assessment of whether the claims are supported

> **Note:**
> - Conflict among statutes → invoke `Statutory Retrieval` (Skill #8); determine hierarchy under the *Legislation Law* before continuing
> - Subsumption between facts and statutory elements is ambiguous → invoke `Legal Concept Comprehension` (Skill #5) to define the concept's extension first, then judge whether the facts fall within it
> - Interest balancing or proportionality review is needed → invoke `Judicial Value Judgment` (Skill #22); make the balancing process explicit; do not avoid it

#### A-5. Legal Basis for Adjudication

After "Pursuant to", list the statutory provisions relied on for judgment, in this citation order:
1. Laws and legislative interpretations → administrative regulations → local regulations → judicial interpretations
2. Same tier: basic laws first, other laws later
3. Substantive law before procedural law

Prohibited citations: the Constitution; trial guidance documents of courts at any level; meeting minutes; reply opinions (their principles may be elaborated in reasoning but may not serve as adjudicative basis).

Format: "Pursuant to Article ×, Paragraph ×, Item × of the *×××* …, the judgment is as follows:" (use a **colon** after "the judgment is as follows")

#### A-6. Operative Provisions (Judgment Main Text)

- Serial numbers in Chinese numerals (一、二、三……), followed by a **顿号** (enumeration comma)
- Use parties' full names
- Money judgments must state: principal for interest calculation, interest rate, start and end dates
- For multiple monetary awards, first list each item name and amount, then the aggregate amount
- Performance deadlines must be definite

#### A-7. Closing and Signature Block

- Litigation costs: separate paragraph (not part of the operative provisions); state case acceptance fee and who bears it
- Delayed-performance notice (mandatory when there is a monetary payment obligation): "If the monetary payment obligation is not performed within the period designated by this judgment, debt interest for the period of delayed performance shall be paid in double pursuant to Article 264 of the *Civil Procedure Law of the People's Republic of China*."
- Appeal rights notice: "If dissatisfied with this judgment, an appeal petition may be submitted to this Court within fifteen days from the date of service of the judgment, with copies according to the number of opposing parties or their representatives, appealing to the ×××× People's Court."
- Signature block: signatures of the presiding judge / judges / people's assessors → date in Chinese numerals (e.g., 二〇二四年八月二十九日) → "This copy has been verified against the original" → clerk's signature

---

### Step 2-B: Drafting a Criminal Judgment

Strictly follow the criminal judgment form (ordinary procedure for first-instance public prosecution cases), drafting in the following order.

#### B-1. Caption / Title

Same format as civil; change the document name to "Criminal Judgment" and the case-number type abbreviation to the criminal abbreviation.

#### B-2. Opening

- Prosecuting authority: "Prosecuting authority ××× People's Procuratorate." (no punctuation or space between the name and "Prosecuting authority")
- Defendant's basic information: name (note aliases / assumed names in parentheses), sex, date of birth (mandatory for minors), ethnicity, place of birth, education level, occupation / unit and position, domicile, prior convictions, compulsory measures (detention / arrest dates, for sentence offset), current place of custody
- Multiple defendants ordered by principal–accessory relationship
- Defense counsel on a separate line: name, work unit, and position; for assigned counsel write "Assigned defense counsel"
- Procedural history: procuratorate indictment number and filing date → collegial panel composition → hearing modality → persons appearing → close with "The trial of this case is now concluded."

#### B-3. Facts Section

Write in four natural paragraphs:

1. Crimes charged by the procuratorate, evidence, and legal opinions → **invoke `Legal Core Element Extraction` (Skill #4)**
2. Defendant's confession, explanations, and self-defense opinions
3. Defense counsel's opinions and evidence
4. "It is found upon trial that ……" → facts found by the court + evidence relied on for conviction and its sources + analysis and authentication of disputed evidence
   → **invoke `Evidence Efficacy` (Skill #12)** + **`Dispute Issues and Legal Relationship Identification` (Skill #6)**

Fact-narration rules: chronological order; for one person with multiple crimes, narrate by primacy of offenses; for joint crimes, narrate along the principal offender as the main thread; for organized-group crimes, summarize first then detail separately.

> **Note:** When prosecution and defense have major disputes over the criminal facts, you must first invoke `Evidence Efficacy` (Skill #12) to analyze and authenticate item by item. It is strictly forbidden to replace concrete authentication with vague formulations such as "the evidence is ample, the defendant also confessed without reservation, and the facts are sufficiently established."

#### B-4. Reasoning Section ("This Court holds")

Mandatory invocation chain:

| Step | Atomic skill invoked | Purpose |
|------|----------------------|---------|
| 1 | `Dispute Issues and Legal Relationship Identification` (Skill #6) | Decide whether the defendant's conduct constitutes a crime and which crime |
| 2 | `Statutory Retrieval` (Skill #8) | Retrieve Criminal Law articles and related judicial interpretations |
| 3 | `Deductive Reasoning` (Skill #16) | Build a syllogism with constitutive elements as major premise and found facts as minor premise |
| 4 | `Case Retrieval` (Skill #9) | When Guiding Cases must be cited |
| 5 | `Judicial Value Judgment` (Skill #22) | Find circumstances for lighter, mitigated, exempted, or heavier punishment |

Reasoning must cover: whether the charges are established → whether the conduct constitutes a crime → determination of the offense → sentencing circumstances → analytical acceptance or rejection of both sides' legal opinions, with reasons stated.

Citation order for adjudicative basis: conviction and sentencing-range articles → lighter / mitigated / aggravated articles → principal penalty articles → supplementary penalty articles; statutes before judicial interpretations.

#### B-5. Judgment Outcome

- Conviction and sentence: "Defendant ××× is guilty of the crime of ×× and is sentenced to …… (principal penalty, supplementary penalty). (Explanation of sentence offset.)"
- Conviction with exemption from punishment: "Defendant ××× is guilty of the crime of ×× and is exempted from criminal punishment."
- Acquittal: "Defendant ××× is not guilty."



Notes:
- Write full names of penalty types; no abbreviations (do not write "死缓"; write "sentenced to death with a two-year suspension of execution")
- Fixed-term imprisonment must state penalty type, term, offset method, and start/end dates
- Recovery / restitution / confiscation must state name, type, and amount
- Concurrent punishment for multiple crimes: convict and sentence for each crime separately, then decide the sentence to be executed; do not "lump estimate" sentencing
- Multiple defendants: adjudicate person by person by primacy of culpability or severity of penalty

#### B-6. Closing and Signature Block

- Appeal rights notice: "If dissatisfied with this judgment, an appeal may be filed through this Court or directly with the ××× People's Court within ten days from the day after receipt of the judgment. For a written appeal, one original and × copies of the appeal petition shall be submitted."
- Where Article 63, Paragraph 2 of the Criminal Law applies, add: "This judgment takes effect upon approval by the Supreme People's Court in accordance with law."
- Signature-block format same as civil (presiding judge / judges' signatures → Chinese-numeral date → "This copy has been verified against the original" → clerk's signature)

---

### Step 3: Full-Text Format Compliance Check

After the full document is drafted, verify each item on the checklist below. **If any item fails, return to the corresponding section, correct it, and re-verify.**

| Check item | Correct practice | Common error |
|------------|------------------|--------------|
| Operative-provision serial numbers | Chinese numerals + 顿号 (一、二、三、) | Arabic numerals "1. 2. 3." |
| Signature-block date | Chinese numerals (二〇二四年八月二十九日) | Arabic numerals "2024年8月29日" |
| Case-number year | Arabic numerals + full-width parentheses （2024） | Chinese characters or half-width/Chinese parentheses |
| After "This Court holds" | Comma | Colon |
| After "the judgment is as follows" | Colon | Comma or period |
| After "the defendant argued" | Comma | Colon |
| Legal citation | Full title + book-title marks + article/paragraph/item numbers + text of the provision | Citing numbers only without the text |
| Citing an "item" | Chinese characters without parentheses ("第一项") | "第（一）项" or "第1项" |
| Location of litigation costs | Separate paragraph after the operative provisions; not part of them | Written into the operative provisions |
| Delayed-performance notice | Mandatory when there is a monetary payment obligation | Omitted |
| Party names | Consistent across opening, facts, and operative provisions | Inconsistent or abbreviated |

---

### Step 4: Output

Present the verified complete judgment to the user as plain text, preserving the formal layout of a judicial document.

Example output structure (civil):
```
××× People's Court
Civil Judgment
（2024）×民初×号

  Plaintiff: ……
  Defendant: ……
  …… case origin and procedural history ……
  Plaintiff ××× submitted the following claims to this Court: ……
  Defendant ××× argued, ……
  The parties in this case submitted evidence in accordance with law around the claims……
  Based on the parties' statements and evidence confirmed upon review, this Court finds the facts as follows: ……
  This Court holds, ……
  Pursuant to Article × of the *……*, the judgment is as follows:
  一、……
  二、……
  If the monetary payment obligation is not performed within the period designated by this judgment……
  Case acceptance fee …… yuan, to be borne by …….
  If dissatisfied with this judgment……

                          Presiding Judge  ×××
                          Judge  ×××
                          Judge  ×××
                      二〇××年×月××日
                  This copy has been verified against the original
                          Clerk  ×××
```

## Example 1: Civil Judgment

### Input

**【Case-file summary】**
Plaintiff Supply-Chain Co. and Defendant Trading Co. signed a *Product Sales Contract* providing for monthly settlement. Trading Co. owed RMB 1,355,570.49, issued a *Payment Plan* confirming the debt and installment schedule, and Zheng signed a *Letter of Guarantee* undertaking joint and several guarantee. After the plan was issued, Trading Co. paid RMB 231,884.63; the balance of RMB 1,123,685.86 remained unpaid. Plaintiff sued for payment of the balance and liquidated damages, with Zheng to bear joint and several liability. Zheng failed to appear after being summoned.

**【Results already returned by atomic skills】**

**Legal Core Element Extraction:**
- Parties: Plaintiff Supply-Chain Co.; Defendant 1 Trading Co. (legal person); Defendant 2 Zheng (natural person, guarantor)
- Legal relationships: sales contract + guarantee
- Claims: ① pay balance RMB 1,123,685.86 and liquidated damages; ② Zheng to bear joint and several liability
- Procedure: first-instance ordinary procedure; Zheng in default
- Court: Beijing Daxing District People's Court
- Case number: （2025）京0115民初34164号

**Dispute Issues and Legal Relationship Identification:**
- Cause of action: sales contract dispute
- Dispute issues: ① whether the outstanding amount is established; ② liquidated-damages calculation standard and start date; ③ whether Zheng bears joint and several liability

**Evidence Efficacy Evaluation:**
- Original *Product Sales Contract*: no objection by either side; admitted
- *Payment Plan* and *Letter of Guarantee*: no objection by either side; admitted
- Payment records: both sides confirm RMB 231,884.63 paid; admitted

**Statutory Retrieval:**
- No statutory conflict; application priority: Civil Code ＞ Civil Procedure Law ＞ judicial interpretations
- *Civil Code* Art. 509: "The parties shall fully perform their own obligations as agreed."
- *Civil Code* Art. 577: "Where a party fails to perform its contractual obligations or its performance does not conform to the agreement, it shall bear default liability such as continuing performance, taking remedial measures, or compensating for losses."
- *Civil Code* Art. 585: "The parties may agree that if one party breaches the contract it shall pay the other a certain amount of liquidated damages according to the breach, and may also agree on a method for calculating the amount of compensation for losses arising from the breach. Where the agreed liquidated damages are lower than the losses caused, the people's court or arbitration institution may, upon a party's request, increase them; where the agreed liquidated damages are excessively higher than the losses caused, the people's court or arbitration institution may, upon a party's request, appropriately reduce them. Where the parties agree on liquidated damages for delayed performance, after paying the liquidated damages the breaching party shall still perform the debt."

- *Civil Code* Art. 626: "The buyer shall pay the price according to the agreed amount and method of payment. Where there is no agreement or the agreement is unclear as to the amount and method of payment, Articles 510 and 511, Items 2 and 5 of this Code apply."
- *Civil Code* Art. 628: "The buyer shall pay the price at the agreed time. Where there is no agreement or the agreement is unclear as to the time of payment, and it still cannot be determined under Article 510 of this Code, the buyer shall pay at the same time as receiving the subject matter or the documents for taking delivery of the subject matter."
- *Civil Code* Art. 688: "Where the parties to a guarantee contract agree that the guarantor and the debtor shall bear joint and several liability for the debt, it is a joint and several liability guarantee. Where the debtor under a joint and several liability guarantee fails to perform a due debt or a circumstance agreed by the parties occurs, the creditor may request the debtor to perform the debt, or may request the guarantor to assume guarantee liability within the scope of its guarantee."
- *Civil Procedure Law* Art. 40: "When trying a first-instance civil case, a people's court shall form a collegial panel of judges and people's assessors or of judges. The number of members of a collegial panel must be odd."
- *Civil Procedure Law* Art. 147: "Where a defendant, having been summoned by summons, refuses to appear in court without justified reason, or withdraws midway without the court's permission, a judgment by default may be rendered."

**Conflict Resolution and Priority Determination:**
- No rights conflict in this case; only disagreement over the liquidated-damages claim. Norms apply by superior law over inferior law and primary law over judicial interpretation; no rights-priority determination is needed.

**Deductive Reasoning:**
- **Principal of goods:** Major premise *Civil Code* Arts. 509 and 626 (perform payment obligation as agreed); minor premise contract valid, plaintiff performed, Trading Co. acknowledged unpaid RMB 1,123,685.86; conclusion **support plaintiff's principal claim**.
- **Liquidated-damages standard:** Major premise *Civil Code* Art. 585 (excessive liquidated damages may be adjusted) and Art. 18 of the sales-contract judicial interpretation; minor premise plaintiff already reduced daily 1‰ liquidated damages to four times LPR, Trading Co. did not prove losses below that standard; conclusion **support four-times-LPR standard**.
- **Liquidated-damages start date:** Major premise *Civil Code* Art. 577 (liquidated damages run from the date of breach); minor premise Trading Co. failed to pay the first installment under the payment plan on 2024-11-25; court adjusted the start point in light of the facts; conclusion **start from 2024-12-26**.
- **Joint and several liability:** Major premise *Civil Code* Art. 688 (joint and several guarantee liability as agreed); minor premise Zheng signed the letter of guarantee undertaking joint and several guarantee, no exemption circumstance, and failed to appear to defend; conclusion **Zheng bears joint and several liability**.

**Case Retrieval:**
- No need to cite Guiding Cases; the court adjudicates directly under statutes and judicial interpretations.

**Judicial Value Judgment:**
- Uphold **pacta sunt servanda**, recognize the validity of the contract / instruments, and respect party autonomy;
- Balance the **principle of fairness**, fine-tune the liquidated-damages start date, both condemning the breach and weighing both sides' interests;
- Protect the creditor's rights, support a reasonable liquidated-damages standard, find joint and several guarantee liability, and strengthen debt recovery;
- Give equal weight to procedure and substance: enter default judgment against Zheng, clarify the adverse consequences of waiving litigation rights, and balance procedural and substantive justice.

---
### Generated Document

**Routing:** Prosecuting party is a legal person → civil. All elements complete → enter Step 2-A.

```
北京市大兴区人民法院
民事判决书
（2025）京0115民初34164号

  原告：某某供应链管理有限责任公司。
  被告：某某贸易有限公司。
  被告：郑某。
  原告某某供应链管理有限责任公司（以下简称供应链公司）与被告某某贸易有限公司（以下简称贸易公司）、被告郑某买卖合同纠纷一案，本院立案受理后，依法适用普通程序，公开开庭进行了审理。原告供应链公司的委托诉讼代理人宋某、贸易公司的委托诉讼代理人葛某到庭参加诉讼。被告郑某经本院依法送达开庭传票，未到庭参加诉讼，本院依法缺席审理。本案现已审理终结。
  供应链公司向本院提出以下诉讼请求：1.请求二被告立即支付原告账款1123685.86元并支付违约金（以1123685.86元为基数，自2024年11月26日起至实际付清之日止，按照同期一年期LPR四倍的标准计算）；2.请求判令被告郑某对贸易公司的债务承担连带还款责任；3.判令诉讼费、公告费、保全费由二被告承担。事实和理由：2024年4月1日，原告与被告签订《产品销售合同》，约定月结付款。贸易公司未按约支付货款，后出具《付款计划书》确认欠款1355570.49元及分期还款安排，郑某签署《保证函》承诺连带保证。计划书签订后二被告未按约定付款。原告主动将违约金标准降低为LPR四倍。
  贸易公司辩称，对于原告主张的欠付货款本金金额没有异议。不认可原告主张的违约金，案涉合同约定的违约金过高，应按照一年期LPR至多加计30%-50%计算逾期付款违约金，且应当自最后一次付款时间的次日即2025年7月25日起算。郑某经本院依法传唤未到庭参加诉讼，亦未提交书面答辩意见。
  本院经审理查明，认定事实如下：
  2024年4月1日，供应链公司与贸易公司签订《产品销售合同》，约定贸易公司向供应链公司下达订单采购货品，付款方式为月结，每月25日前支付上月款项。合同约定甲方逾期付款的，每违约一日，按应付款金额的1‰支付违约金。
  2024年11月11日，贸易公司向供应链公司出具《付款计划书》，确认截至该日欠款总金额为1355570.49元，并约定分期还款安排，首期于2024年11月25日支付。《付款计划书》下方《保证函》载明郑某同意对上述欠款承担连带保证责任，郑某在保证人处签字。
  庭审中，双方确认《付款计划书》出具后，贸易公司向供应链公司支付了231884.63元。
  本院认为，根据我国民事诉讼法的规定，当事人有答辩并对对方当事人提交的证据进行质证的权利。本案中，被告郑某经本院依法传唤，无正当理由未到庭参加诉讼，视为其放弃在庭审中答辩和举证质证等诉讼权利，不利后果应由其自行承担。
  案涉《产品销售合同》及《付款计划书》系各方真实意思表示，内容合法有效，各方均应按照合同约定履行各自义务。对于供应链公司所主张的欠付账款1123685.86元，证据充分且贸易公司认可，本院予以支持。贸易公司未及时支付欠款构成违约，应当承担相应的违约责任，供应链公司有权主张违约金，具体标准本院依法确认自2024年12月26日起，按照同期一年期LPR四倍的标准计算。郑某出具《保证函》，承诺其作为案涉欠款的连带保证人，故供应链公司有权要求郑某与贸易公司共同承担还款责任。
  据此，依照《中华人民共和国民法典》第五百七十七条、第六百二十六条、第六百二十八条，《中华人民共和国民事诉讼法》第四十条、第一百四十七条之规定，缺席判决如下：
  一、某某贸易有限公司于本判决生效后十日内支付某某供应链管理有限责任公司1123685.86元，并支付违约金（以1123685.86元为基数，自2024年12月26日起至欠款实际付清之日止，按照全国银行间同业拆借中心公布的同期一年期贷款市场报价利率的四倍计算），郑某承担连带责任；
  二、驳回某某供应链管理有限责任公司的其他诉讼请求。
  如果未按本判决指定的期间履行给付金钱义务，应当依照《中华人民共和国民事诉讼法》第二百六十四条之规定，加倍支付迟延履行期间的债务利息。
  案件受理费14913元、保全费5000元，均由某某贸易有限公司、郑某共同负担（于本判决生效后七日内交纳）；公告费200元及判决书公告费（具体金额以票据为准），由郑某负担（于本判决生效后七日内交纳）。
  如不服本判决，可在判决书送达之日起十五日内，向本院递交上诉状，并按对方当事人的人数提出副本，交纳上诉案件受理费，上诉于北京市第二中级人民法院。如在上诉期满后七日内未交纳上诉案件受理费的，按自动撤回上诉处理。

                                                                                              审 判 员 XXX
                                                                                      二〇二六年三月二十五日
                                                                                          本件与原本核对无异
                                                                                              法官助理 XXX
                                                                                              书 记 员 XXX
             
```

**Format check:**
- Operative serial numbers in Chinese ✓
- Signature-block Chinese-numeral date ✓
- Case-number Arabic year + full-width parentheses ✓
- Comma after "This Court holds" ✓
- Colon after "the judgment is as follows" ✓
- Delayed-performance notice ✓
- Litigation costs not in operative provisions ✓
- Party full names consistent ✓
- → Pass; output.

---

## Example 2: Criminal Judgment

### Input

**【Case-file summary】**
Defendant Yang 1, from 2017 to 2023, headed a department under a certain group, publicly promoted investment projects by word of mouth, promised high returns, and illegally absorbed funds totaling over RMB 100 million. Appeared after telephone summons; family remitted RMB 2.45 million on his behalf; over RMB 800,000 more remitted during litigation. Pleaded guilty and accepted punishment. Defense counsel argued accessory, voluntary surrender, restitution, and suspended sentence.

**【Results already returned by atomic skills】**

**Legal Core Element Extraction:**
- Prosecuting authority: Beijing Changping District People's Procuratorate
- Defendant: Yang 1, male, no prior convictions
- Charged offense: illegally absorbing public deposits
- Compulsory measures: (case file does not state specific detention/arrest dates)
- Procedure: summary converted to ordinary procedure; collegial panel
- Court: Beijing Changping District People's Court
- Case number: （2025）京0114刑初679号

**Dispute Issues and Legal Relationship Identification:**
- Dispute issues: ① whether overlapping amounts in the case should be deducted; ② whether voluntary surrender is constituted; ③ whether a suspended sentence may apply

**Evidence Efficacy Evaluation:**
- Defendant's confession, witness testimony, company electronic data, and two judicial appraisal opinions confirmed after courtroom presentation and cross-examination
- On overlapping statistics: based on witness testimony, electronic data, and two appraisal opinions on file, this is a joint crime; distribution of proceeds does not affect the amount of illegal absorption; basis for cross-deduction is insufficient

**Statutory Retrieval:**
- *Criminal Law* Art. 176, Para. 1: "Whoever illegally absorbs public deposits or does so in a disguised form, thereby disrupting the financial order, shall be sentenced to fixed-term imprisonment of not more than three years or criminal detention, and shall also, or shall only, be fined; where the amount is huge or there are other serious circumstances, fixed-term imprisonment of not less than three years but not more than ten years, and a fine; where the amount is especially huge or there are other especially serious circumstances, fixed-term imprisonment of not less than ten years, and a fine." Para. 3: "Where a person who commits an act under the preceding two paragraphs actively returns stolen goods or makes restitution before public prosecution is initiated, thereby reducing the harmful consequences, a lighter or mitigated punishment may be given."
- *Criminal Law* Art. 25, Para. 1: "A joint crime means an intentional crime committed by two or more persons jointly."
- *Criminal Law* Art. 27: "An accessory is a person who plays a secondary or auxiliary role in a joint crime. An accessory shall be given a lighter or mitigated punishment or be exempted from punishment."
- *Criminal Law* Art. 67, Para. 3: [voluntary surrender / truthful confession provisions as in the statute]
- *Criminal Law* Art. 52: "The amount of a fine shall be determined according to the circumstances of the crime."
- *Criminal Law* Art. 53: [rules on payment of fines]
- *Criminal Law* Art. 61: "When deciding the punishment of a criminal, the court shall, in accordance with the relevant provisions of this Law, base the decision on the facts, nature, and circumstances of the crime and the degree of harm to society."
- *Criminal Law* Art. 64: [recovery, restitution, confiscation]
- *Criminal Procedure Law* Art. 15: "Where a criminal suspect or defendant voluntarily and truthfully confesses his crimes, admits the charged criminal facts, and is willing to accept punishment, he may be dealt with leniently in accordance with law."

**Deductive Reasoning:**
- No rights or norm conflict; only disagreement between prosecution and defense on sentencing circumstances. Apply Criminal Law special provisions ＞ general provisions and Criminal Procedure Law sentencing rules; no priority determination needed.

**Deductive Reasoning:**
- **Amount of illegal absorption:** Major premise *Criminal Law* Arts. 176 and 25 (joint offenders responsible for the full amount); minor premise joint crime, evidence proves absorption of over RMB 100 million, no statutory basis to deduct relatives' investments; conclusion **no deduction; find over RMB 100 million (especially huge amount)**.
- **Voluntary surrender:** Major premise *Criminal Law* Art. 67, Para. 1 (voluntary appearance + truthful confession); minor premise Yang 1, after telephone summons, did not immediately disclose the criminal facts; conclusion **not voluntary surrender; subsequent truthful confession treated as confession**.
- **Accessory:** Major premise *Criminal Law* Art. 27 (secondary/auxiliary role); minor premise Yang 1 was a subordinate department head with a secondary role; conclusion **find accessory; mitigate punishment according to law**.
- **Suspended sentence:** Major premise suspension applies to relatively light circumstances, no risk of reoffending, etc.; minor premise especially huge amount and substantial social harm; conclusion **does not meet suspension conditions; not applicable**.
- **Lenient treatment:** Major premise *Criminal Procedure Law* Art. 15 and *Criminal Law* Art. 67, Para. 3 (plea and acceptance of punishment, confession, restitution may warrant leniency); minor premise Yang 1 pleaded guilty and accepted punishment, confessed, and remitted all illegal proceeds; conclusion **mitigate punishment according to law**.

**Case Retrieval:**
- No need to cite Guiding Cases; adjudicate under the Criminal Law and Criminal Procedure Law in light of the facts.

**Judicial Value Judgment:**
- Accessory (statutory mitigation): secondary/auxiliary role in the joint crime
- Truthful confession (statutory lighter punishment): confessed after appearance but not immediately; not voluntary surrender
- Plea and acceptance of punishment (statutory leniency)
- Restitution (discretionary lighter punishment): remitted all illegal proceeds
- Suspended sentence: insufficient basis given the facts; not applicable
- Overall assessment: mitigate according to law; fixed-term imprisonment of three years and two months, and a fine of RMB 120,000

---

### Generated Document

**Routing:** Prosecuting authority is a people's procuratorate → criminal. All elements complete → enter Step 2-B.

```
北京市昌平区人民法院
刑事判决书
（2025）京0114刑初679号

  公诉机关北京市昌平区人民检察院。
  被告人杨某1。
  辩护人田某。
  辩护人胡某某。
  北京市昌平区人民检察院以京昌检刑诉〔2025〕609号起诉书指控被告人杨某1犯非法吸收公众存款罪，于2025年7月22日向本院提起公诉。公诉机关于2025年11月11日建议、本院决定延期审理，于2025年12月11日建议、本院决定恢复审理。本院依法组成合议庭，将本案由简易程序转为普通程序，公开开庭审理了本案。北京市昌平区人民检察院指派检察员王志萌出庭支持公诉。被告人杨某1及其辩护人田某、胡某某到庭参加诉讼。本案现已审理终结。
  北京市昌平区人民检察院指控：2017年至2023年间，被告人杨某1担任某集团下属部门负责人，在北京市昌平区等地以口口相传等方式向社会公开宣传某集团投资项目，承诺高额收益，直接或间接向左某某、林某某等人非法吸收资金共计人民币1亿余元。2024年12月15日，被告人杨某1经电话传唤到案。被告人杨某1的家属代为退缴违法所得人民币245万元。公诉机关认为被告人杨某1的行为触犯了《中华人民共和国刑法》第一百七十六条第一款之规定，应当以非法吸收公众存款罪追究其刑事责任，提请本院依法惩处。
  被告人杨某1对指控事实、罪名没有异议，认罪认罚并签字具结，在开庭审理过程中亦无异议，但辩解其本人及其母亲欧洋某某、哥哥杨某2均有投资。
  二辩护人对本案指控基本事实、罪名均不持异议，主要意见为：1.本案缺乏集资参与人的证言，投资人和涉案金额可能与吴某某存在交叉统计的情况，非杨某1名下的投资人及金额应予扣除；2.杨某1本人及母亲、哥哥均参与投资，相应金额应予扣除；3.杨某1认罪认罚，系从犯，接电话传唤后到案，在侦查阶段如实供述所犯罪行，构成自首；4.提起公诉前退赔大部分违法所得；5.初犯，偶犯，悔罪态度好，家庭困难；6.大部分吸纳资金行为发生在旧法实施期间。综上，建议对其从宽处罚并适用缓刑。
  经审理查明：2017年至2023年间，被告人杨某1担任某集团下属部门负责人，在北京市昌平区等地以口口相传等方式向社会公开宣传某集团投资项目，承诺高额收益，直接或间接向左某某、林某某等人非法吸收资金共计人民币1亿余元。
  2024年12月15日，被告人杨某1经电话传唤到案。被告人杨某1的家属代为退缴违法所得人民币245万元。
  诉讼中，被告人杨某1退缴人民币80余万元，冻结于其名下招商银行卡中。
  上述事实，有经庭审举证、质证，本院确认的证据证明。
  本院认为，被告人杨某1非法吸收公众存款，扰乱金融秩序，数额特别巨大，其行为已构成非法吸收公众存款罪，依法应予惩处。北京市昌平区人民检察院指控被告人杨某1犯非法吸收公众存款罪的事实清
楚，证据确实、充分，罪名成立。辩护人关于投资人和涉案金额可能与吴某某存在交叉统计，非杨某1名下的投资人及金额应予扣除的相关意见，经查，根据在案证人证言、某公司电子数据、北京国创鼎诚司法鉴定所司法鉴定意见书、华利信（北京）会计师事务所有限责任公司司法会计鉴定意见书等证据，本案系共同犯罪，被告人应对共同犯罪的全部行为承担责任，犯罪所得分配情况不影响对非吸金额的认定，前述意见依据不足，不予采纳；关于杨某1构成自首的意见，杨某1主动到案后未能第一时间交代犯罪事实，不构成自首，但在后续侦查阶段能如实供述，本院在量刑时依法予以从轻处罚；关于杨某1哥哥投资的相应金额应予扣除及对杨某1适用缓刑的意见，结合本案案情，依据不足，均不予采纳；其余辩护意见，酌予考虑。鉴于被告人杨某1在共同犯罪中起次要、辅助作用，系从犯；自愿认罪认罚；到案后如实供述所犯罪行；提起公诉前及诉讼中积极退赃，退缴全部违法所得，对其依法予以减轻处罚。综上，根据被告人杨某1犯罪的事实、性质、情节、社会危害程度及认罪、悔罪表现，依照《中华人民共和国刑法》第一百七十六条第一款、第三款，第二十五条第一款，第二十七条，第六十七条第三款，第五十二条，第五十三条，第六十一条，第六十四条及《中华人民共和国刑事诉讼法》第十五条之规定，判决如下：
  一、被告人杨某1犯非法吸收公众存款罪，判处有期徒刑三年二个月，并处罚金人民币十二万元。
  二、在案冻结及随案移送款物，依法处理。
  如不服本判决，可在接到判决书的第二日起十日内，通过本院或者直接向北京市第一中级人民法院提出上诉。书面上诉的，应当提交上诉状正本一份，副本二份。

                                                                                           审  判  长  XXX
                                                                                           人民陪审员  XXX
                                                                                           人民陪审员  XXX                                                                      
                                                                                       二〇二六年三月十一日
                                                                                         本件与原本核对无异
                                                                                           书  记  员  XXX

```

**Format check:**
- Operative serial numbers in Chinese ✓
- Signature-block Chinese-numeral date ✓
- Case-number format ✓
- Comma after "This Court holds" ✓
- Colon after "the judgment is as follows" ✓
- Prosecuting-authority format ✓
- Full penalty-type names ✓
- Parties consistent ✓
- Evidence authentication not vague ✓
- → Pass; output.


## Atomic Skill Invocation Index

When drafting each section, select and invoke as needed from the following atomic skills:

| Invocation scenario | Atomic skill | No. | Typical timing |
|---------------------|--------------|-----|----------------|
| Initial case-file parsing | Legal Core Element Extraction | #4 | Step 1: after receiving the case file |
| Terminology delimitation | Legal Concept Comprehension | #5 | When subsumption is ambiguous, define concept extension |
| Determining dispute issues | Dispute Issues and Legal Relationship Identification | #6 | Before starting facts and reasoning sections |
| Finding the law | Statutory Retrieval | #8 | Before drafting the reasoning section |
| Finding similar cases | Case Retrieval | #9 | When Guiding Cases must be cited |
| Evidence examination | Evidence Efficacy Evaluation | #12 | Evidence findings in the facts section |
| Characterizing legal relationships | Dispute Issues and Legal Relationship Identification | #6 | Confirming cause of action; characterization in reasoning |
| Facts and reasoning | Deductive Reasoning | #16 | Issue-by-issue argumentation in reasoning |
| Statutory or rights conflict | Conflict Resolution and Priority Determination | #20 | When statutes or rights conflict |
| Sentencing / discretion | Judicial Value Judgment | #22 | Criminal sentencing; civil interest balancing |

## Skill Boundaries and Troubleshooting Guide

**What this skill does not do:**
- Does not replace a legal research system; primarily invokes `Statutory Retrieval` for provisions and does not maintain a built-in statute library
- Does not invent facts; relies on case-file materials and `Evidence Efficacy` analysis results
- Does not generate non-judgment legal documents (contracts, lawyer's letters, etc. are out of scope)
- Does not handle documents outside Mainland China jurisdictions
- Currently supports only civil and criminal judgments

**Note:**

In any of the following situations, never guess a ruling; must pause drafting, invoke the corresponding atomic skill, and obtain an objective conclusion before continuing:
1. Plaintiff and defendant assert contradictory claims and both have supporting evidence
2. Key evidence's three attributes are in doubt
3. Characterization of the legal relationship is disputed
4. Conflict of application among statutes
5. Insufficient case-file materials → return an "information-gap list" to the user

If `Statutory Retrieval` returns no result → at the corresponding place in the document mark "【To be supplemented: need to retrieve legal basis related to ×××】"
If `Evidence Efficacy` cannot decide → state "the authenticity / legality / relevance of this evidence is in doubt" and give reasons
No judgment document title may be bolded; "This Court holds" and "the judgment is as follows" are flush left; dispute issues are phrased as "一、××× 问题" and also not bolded.
Before "the judgment is as follows" there should be a string of cited legal provisions, in the form: Accordingly, pursuant to xxx (fill in the relevant articles), the judgment is as follows:

**Common errors and corrections:**

| Error phenomenon | Cause | Correction |
|------------------|-------|------------|
| Colon after "This Court holds" | Confused punctuation rules | Change to comma |
| Arabic numerals for operative serial numbers | Confused numeral usage | Change to Chinese (一、二、三、) |
| Chinese characters for case-number year | Confused numeral usage | Change to Arabic numerals |
| Citing article numbers without text | Omitted citation requirement | Supply full text of the provision |
| Missing delayed-performance notice paragraph | Omitted mandatory notice | Check whether there is a monetary award; if so, add the notice |
| Vague authentication of evidence in criminal documents | Authentication not concrete | Analyze and authenticate evidence one by one or by category |
