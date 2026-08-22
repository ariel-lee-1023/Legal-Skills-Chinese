---
name: multi-document-summarization
description: |
  Trigger this skill when multiple related documents need comprehensive analysis, extraction of shared views, identification of conflicts, and generation of a unified overview.
  Typical trigger scenarios include, but are not limited to:
  - The user uploads multiple judgments or rulings and asks for a summary of key holdings in similar cases
  - The user provides multiple contract texts and asks for a comparison of clause similarities/differences and key variances
  - The user provides multiple statutes, regulations, or judicial interpretations and asks for a review of normative evolution and application points
  - The user provides multiple pieces of evidence or investigation transcripts and asks for an integrated factual narrative
  - The user provides multiple academic papers or research reports and asks for research consensus and disagreements
  - The user asks to compare viewpoint differences across multiple legal opinions
  Core value of this skill: not merely compressing a single document, but building cross-document relational analysis, identifying commonalities and differences, and generating new integrative insights.
---

> **Chinese source (authoritative):** [`../../skills/multi-document-summarization/SKILL.md`](../../skills/multi-document-summarization/SKILL.md)

# Multi-Source Document Synthesis

## Overview Table

| Item | Content |
|------|------|
| **Capability ID** | 19 |
| **Capability Name** | Multi-Source Document Synthesis |
| **Capability Type** | Comprehensive synthesis |
| **Core Functions** | Cross-analyze multiple related documents; extract commonalities; identify conflicts; generate integrated conclusions |
| **Input** | Multiple thematically related texts, PDFs, Word documents, or web links |
| **Output** | Integrated summary (paragraph or bullet format), comparative analysis table, conflict list, cross-document insights |
| **Related Capabilities** | Legal document summarization (single-document summary), legal document formatting (unified output format), similar-case retrieval and analysis (judgment comparison) |
| **Key Principles** | Cross-document linkage, consistency integration, conflict annotation, insight generation |

## Legal Disclaimer

> **Important notices:**
> 1. Multi-document synthesis depends on the accuracy and reliability of each source document; uneven source quality may bias synthesis conclusions.
> 2. Synthesis conclusions reflect the overall picture of the input documents and do not constitute an independent judgment of objective facts.
> 3. In legal disputes, different documents may represent opposing positions; synthesis must remain neutral and present each side’s views objectively.
> 4. When documents conflict on facts, synthesis only identifies conflict points and does not adjudicate truth or falsity.

## I. Core Concepts

### 1.1 Single-Document Summary vs. Multi-Document Synthesis

| Dimension | Single-Document Summary | Multi-Document Synthesis |
|------|-----------|-----------|
| **Object of processing** | One document | Multiple related documents |
| **Core task** | Compress information; extract key points | Cross-compare; integrate linkages |
| **Nature of output** | Faithful condensation of the original | A new cross-document knowledge structure |
| **Key capabilities** | Information filtering | Consistency recognition, conflict discovery, pattern extraction |
| **Typical value** | Quickly grasp one instrument | Grasp the full picture, trends, and controversies across a set of documents |

### 1.2 Four Levels of Multi-Document Analysis

```
Level 1: Single-document understanding
    Understand the core content of each document separately
    
Level 2: Commonality extraction
    Identify themes, views, and facts shared across documents
    
Level 3: Difference comparison
    Identify viewpoint conflicts, factual contradictions, and wording differences across documents
    
Level 4: Insight generation
    Based on cross-document comparative analysis, generate new integrative conclusions
```

### 1.3 Document Relationship Types

| Relationship Type | Features | Analysis Focus | Example |
|----------|------|----------|------|
| **Parallel** | Multiple documents address different aspects of the same topic | Integrate information across aspects into a panoramic view | Multiple academic papers on the same legal issue |
| **Chronological** | Documents ordered by time | Trace the evolution path; identify trend changes | Different versions of the same regulation; a series of judgments in the same case |
| **Adversarial** | Documents represent opposing positions | Present each side objectively; annotate conflict points | Plaintiff and defendant opinions; competing scholarly views |
| **Hierarchical** | Documents stand in inclusion or citation relationships | Map the hierarchy; identify core vs. derivative materials | Hierarchy of statutes, judicial interpretations, and guiding cases |
| **Complementary** | Documents supplement each other and cover different facets | Integrate complementary information; fill single-document blind spots | Master contract and supplemental agreement; complaint and evidence list |

## II. Complete Workflow

### Phase One: Preparation and Input

#### Step 1: Receive and Organize Documents

1. **Confirm document count and sources**: List all documents; annotate source and type
2. **Unify format**: Convert PDFs, Word files, web pages, etc. into processable text
3. **Build a document archive**: Number each document for later citation

```markdown
### Document Inventory

| ID | Document Name | Type | Source | Date | Word Count / Pages |
|------|----------|------|------|------|----------|
| D1 | [...] | [Judgment / Contract / Statute / Paper] | [...] | [...] | [...] |
| D2 | [...] | [...] | [...] | [...] | [...] |
```

#### Step 2: Identify Inter-Document Relationships

Analyze relationship types among the documents (parallel / chronological / adversarial / hierarchical / complementary) and select the synthesis framework:

- **Parallel** → use a “theme aggregation” framework
- **Chronological** → use an “evolution path” framework
- **Adversarial** → use a “viewpoint comparison” framework
- **Hierarchical** → use a “hierarchy mapping” framework
- **Complementary** → use a “panoramic integration” framework

### Phase Two: Single-Document Understanding and Annotation

#### Step 3: Extract Core Information Document by Document

For each document, extract the following elements:

| Extraction Element | Content | Annotation Method |
|----------|------|----------|
| **Core theme** | What central question the document addresses | One-sentence summary |
| **Main views** | Core claims or conclusions | 3–5 bullet points |
| **Key facts** | Important facts supporting the views | Objective statements |
| **Grounds / evidence** | Supporting materials for the views | Legal provisions, data, cases, etc. |
| **Stance / angle** | Document stance (neutral / supporting / opposing / representing a party) | Explicitly annotate |

#### Step 4: Build Document Information Cards

Create a standardized information card for each document:

```markdown
### D1 Information Card

- **Document name:** [...]
- **Core theme:** [...]
- **Main views:**
  1. [...]
  2. [...]
- **Key facts:**
  - [...]
- **Grounds / evidence:** [...]
- **Stance:** [Neutral / Plaintiff / Defendant / Scholar A / Administrative agency]
- **Credibility / authority:** [High / Medium / Low, with brief reasons]
```

### Phase Three: Cross-Analysis and Synthesis

#### Step 5: Extract Cross-Document Commonalities

Identify themes, views, and facts shared across multiple documents:

- Which views are jointly mentioned across documents?
- Which facts are cross-corroborated by multiple documents?
- Which legal authorities are commonly cited?
- Are there widely accepted conclusions or a consensus?

**Output format:**
```markdown
### Cross-Document Consensus

| Consensus Theme | Documents Involved | Consensus Content | Consensus Strength |
|----------|----------|----------|----------|
| [...] | D1, D2, D3 | [...] | Strong (3/3 agree) |
```

#### Step 6: Identify Inter-Document Conflicts

Identify differences, contradictions, or oppositions among documents:

- **Viewpoint conflict**: Opposing positions on the same issue
- **Factual contradiction**: Inconsistent statements about the same fact
- **Divergence in legal application**: Different understandings or applications of the same provision
- **Conclusion difference**: Different conclusions based on the same or similar facts

**Conflict annotation requirements:**
- State both sides’ views objectively; do not adjudicate truth or falsity
- Analyze possible causes (information asymmetry, different stances, different applicable standards, etc.)
- Annotate importance (core conflict / secondary disagreement)

**Output format:**
```markdown
### Inter-Document Conflict Points

| Conflict ID | Conflict Theme | Document A View | Document B View | Conflict Type | Importance |
|----------|----------|-----------|-----------|----------|----------|
| C-01 | [...] | D1: [...] | D2: [...] | [Viewpoint / Fact / Legal application] | [Core / Secondary] |
```

#### Step 7: Generate Cross-Document Insights

On the basis of commonality and difference analysis, generate new integrative conclusions:

- **Trend judgment**: What overall trend or direction do the documents present?
- **Pattern recognition**: Are there recurring patterns or structures?
- **Blind-spot identification**: What important information do the documents jointly omit?
- **Linkage discovery**: Does combining information across documents yield new understanding?

### Phase Four: Output

#### Step 8: Format the Integrated Synthesis Output

Choose an output form based on user needs:

**Form A: Paragraph-style integrated summary** (suitable for detailed explanation)
- Present the core content of all documents coherently
- Organize by theme or logical order
- Naturally incorporate cross-document comparison and insights

**Form B: Bullet-point summary** (suitable for quick browsing)
- List key information item by item with bullets
- Annotate source documents for each point
- List conflict points separately

**Form C: Comparative analysis table** (suitable for fine-grained comparison)
- Present corresponding elements of each document side by side in a table
- Facilitate item-by-item comparison of similarities and differences

## III. Output Format Templates

### Template A: Paragraph-Style Integrated Summary

```markdown
# Multi-Document Integrated Synthesis

## I. Document Overview
[State document count, types, sources, and overall relationships]

## II. Core Consensus
[Shared themes, views, and facts across documents]

## III. Major Disagreements
[Key conflicts and differences among documents]

## IV. Integrated Conclusions
[Insights generated from cross-document analysis]

## V. Information Gaps
[Content jointly omitted or unclear across documents; recommended supplementation]
```

### Template B: Bullet-Point Summary

```markdown
# Multi-Document Key-Point Synthesis

## Document Inventory
- D1: [...]
- D2: [...]

## Core Points
- [Point 1] (D1, D2, D3)
- [Point 2] (D1, D2)
- [Point 3] (D2, D3)

## Conflicts and Disagreements
- [Conflict 1]: D1 holds that...; D2 holds that... ([conflict type])
- [Conflict 2]: ...

## Cross-Document Insights
- [Insight 1]
- [Insight 2]

## Information Pending Verification / Supplementation
- [...]
```

### Template C: Comparative Analysis Table

```markdown
| Comparison Dimension | D1 | D2 | D3 | Consistency Assessment |
|----------|-----|-----|-----|-----------|
| Core theme | [...] | [...] | [...] | [Consistent / Similar / Different] |
| Main views | [...] | [...] | [...] | [...] |
| Key facts | [...] | [...] | [...] | [...] |
| Legal grounds | [...] | [...] | [...] | [...] |
| Conclusion / disposition | [...] | [...] | [...] | [...] |
```

## IV. Examples

### Example 1: Synthesis of Similar-Case Judgments

**Input:** 3 unfair competition dispute judgments (all plaintiffs are data platforms; all defendants are data scrapers)

**Output:**

```markdown
# Multi-Document Integrated Synthesis

## I. Document Overview
This set contains 3 civil judgments, all unfair competition disputes brought by data platforms against data scrapers, rendered respectively by the Beijing Intellectual Property Court, the Hangzhou Internet Court, and the Shanghai Intellectual Property Court (D1–D3).

## II. Core Consensus

1. **Consensus on data rights protection**: All three judgments hold that platforms enjoy competitive interests in data lawfully collected and organized at cost (D1, D2, D3).
2. **Consensus on unfair competition standards**: All apply Article 2 of the Anti-Unfair Competition Law (general clause), using “whether the conduct violates the principle of good faith and recognized business ethics” as the standard (D1, D2, D3).
3. **Consensus on harm requirements**: All require the plaintiff to prove that the defendant’s conduct caused actual harm or a threat of harm (D1, D2, D3).

## III. Major Disagreements

| Conflict ID | Conflict Theme | Document A View | Document B View | Conflict Type | Importance |
|----------|----------|-----------|-----------|----------|----------|
| C-01 | Whether scraping public data is automatically lawful | D1 (Beijing): Scraping public data must still comply with the Robots Protocol and business ethics | D2 (Hangzhou): Public data may be freely scraped under certain conditions | Divergence in legal application | Core |
| C-02 | Method of calculating damages | D1: Calculated by plaintiff’s actual loss | D3 (Shanghai): Calculated by defendant’s illegal gains | Divergence in legal application | Core |
| C-03 | Technology-neutrality defense | D2: Technology neutrality may serve as a ground for exemption | D1, D3: Technology neutrality does not exempt unfair competition liability | Viewpoint conflict | Secondary |

## IV. Integrated Conclusions

1. **Adjudicative trend**: That data platforms enjoy competitive interests in lawfully collected data has become a judicial consensus, but the legality boundary for scraping public data remains contested.
2. **Regional differences**: Beijing courts take a stricter stance on data protection; Hangzhou courts are relatively more open to circulation of public data; Shanghai courts sit in between.
3. **Legal application**: All three judgments primarily rely on Article 2 of the Anti-Unfair Competition Law, but subtle differences in application standards reflect normative uncertainty in this field.

## V. Information Gaps
- None of the three judgments addresses cross-application of scraping conduct with the Personal Information Protection Law
- Lack of concrete analysis balancing “data portability” and “platform data interests”
- No unified adjudicative rules yet on standards and methodology for calculating damages
```

### Example 2: Comparison of Multiple Contract Clauses

**Input:** 2 technology service contracts (a master contract between Company A and Company B, and a similar contract between Company C and Company D)

**Output:**

```markdown
# Multi-Document Comparative Analysis

## I. Document Overview
- D1: Company A vs. Company B, Technology Development Contract (2024)
- D2: Company C vs. Company D, Technology Service Contract (2023)

## II. Comparative Analysis Table

| Comparison Dimension | D1 (A–B) | D2 (C–D) | Difference Assessment |
|----------|-----------|-----------|----------|
| Contract subject matter | App software development | System maintenance services | Different: development vs. maintenance |
| Total price | RMB 500,000 | RMB 300,000 / year | Different: lump sum vs. annual |
| Performance period | 6 months | 12 months | Different |
| IP ownership | Owned by Company A | Owned by Company C | Consistent |
| Confidentiality obligations | Detailed clause; liquidated damages RMB 100,000 | Brief clause; no liquidated damages | Different: D1 stricter |
| Dispute resolution | Arbitration by Beijing Arbitration Commission | Litigation in court at defendant’s domicile | Different: arbitration vs. litigation |
| Force majeure | Enumerated + catch-all | Enumeration only | Different: D1 more comprehensive |

## III. Key Difference Analysis

1. **Dispute resolution**: D1 provides for arbitration (final and binding); D2 provides for litigation (appealable). Arbitration offers stronger confidentiality but no appeal; litigation is public but has more levels of review.
2. **Strength of confidentiality**: D1 sets specific liquidated damages; D2 makes only a principled stipulation. D1 better protects the non-breaching party.
3. **Risk allocation**: As a development contract, D1 has staged acceptance and payment milestones; as a maintenance contract, D2 uses annual payment with more balanced risk.

## IV. Integrated Recommendations

If negotiating a similar contract, consider:
- Referencing D1’s confidentiality clauses and staged acceptance mechanism
- Referencing D2’s annual payment model to reduce lump-sum payment risk
- Choosing dispute resolution based on confidentiality needs and efficiency preferences
```

### Example 3: Synthesis of Statutory / Regulatory Evolution

**Input:** Personal Information Protection Law (2021), Network Data Security Management Regulations (2024), an industry data compliance guide (2025)

**Output:**

```markdown
# Multi-Document Integrated Synthesis

## I. Document Overview
This set contains 3 normative instruments, presenting hierarchical evolution in personal information / data protection from statute to administrative regulation to industry guide (D1–D3).

## II. Normative Hierarchy and Effect

| Document | Level | Effect | Scope of Application |
|------|------|------|----------|
| D1 Personal Information Protection Law | Statute (law) | Highest | Personal information processing nationwide |
| D2 Network Data Security Management Regulations | Administrative regulation | High | Network data processing activities |
| D3 XX Industry Data Compliance Guide | Industry norm | Medium | Enterprises within Industry XX |

## III. Evolution of Core Content

| Theme | D1 (Statute) | D2 (Administrative Regulation) | D3 (Industry Guide) |
|------|-----------|---------------|---------------|
| Informed consent | Principled rules (Arts. 13–17) | Refined consent mechanisms and withdrawal procedures | Provides consent UI design templates and examples |
| Cross-border transfer | Three pathways: security assessment, standard contract, certification | Refined security assessment filing procedures | Provides industry-specific risk assessment points |
| Data classification and grading | Principled requirements | Classification/grading standards; identification of important data | Industry data classification sample lists |
| Legal liability | Arts. 66–71 (fines, orders to correct, etc.) | Supplements administrative penalty discretion benchmarks | Operational guidance for compliance remediation |

## IV. Progressive Relationship of Compliance Requirements

```
Statute (D1): Establish the basic institutional framework
    ↓ refine
Administrative regulation (D2): Clarify operational procedures and penalty standards
    ↓ implement
Industry guide (D3): Provide concrete implementation templates and checklists
```

## V. Integrated Insights

1. **Regulatory trend**: Evolution from principled legislation toward fine-grained enforcement; enterprise compliance obligations become increasingly concrete.
2. **Compliance path**: Enterprises should first meet mandatory requirements of the statute (D1), then follow procedural requirements of the administrative regulation (D2), and finally refer to the industry guide (D3) to optimize compliance operations.
3. **Conflict note**: If D3 is inconsistent with D1/D2, higher-effect D1/D2 prevail; D3 is for reference only.
```

## V. Common Errors and Prevention

| Error Type | Description | Consequences | Prevention |
|----------|----------|------|----------|
| **Simple stacking** | Mechanically concatenate each document’s summary without cross-analysis | Loses the value of multi-document synthesis; readers must still compare themselves | Must perform cross-document commonality and difference analysis |
| **Ignoring conflicts** | Extract only commonalities; avoid or downplay disagreements | Misleads readers into thinking all views align | Treat conflict points as a focus of analysis |
| **Stance skew** | Over-weight a longer document or one from an “authoritative” source | Synthesis loses neutrality | Weight by informational value, not source prestige |
| **Over-inference** | Over-infer beyond what documents expressly state | Conclusions lack documentary support | Distinguish “expressly stated” from “reasonable inference based on documents”; annotate the latter |
| **Omitting important documents** | Fail to verify completeness; omit key attachments | Synthesis based on incomplete information | Confirm inventory completeness upon receipt |
| **Confusing facts and views** | Treat subjective views in documents as objective facts | Unreliable conclusions | Explicitly annotate each segment’s nature (fact / view / inference) |

## VI. Special Scenario Handling

### 6.1 Too Many Documents (10+)

- First group by theme or type; synthesize within groups, then synthesize across groups
- Use a “layered synthesis” strategy: small groups → large groups → overall conclusions
- Focus on high-frequency themes and conflict points; simplify secondary documents as appropriate

### 6.2 Uneven Document Quality

- Assess document credibility; flag risk for documents of unclear provenance or with obvious errors
- Assign higher weight to high-quality documents (e.g., effective judgments, formal statutes/regulations)
- Separately annotate low-quality documents (e.g., anonymous web posts, unverified rumors) and use them cautiously

### 6.3 Inconsistent Document Languages

- For multilingual documents, unify annotation of core concepts with original text and translation
- Note subtle differences in the same legal term across language versions
- For legal texts, the official version prevails

### 6.4 Confidential or Sensitive Information

- Desensitize sensitive information in synthesis outputs
- Annotate which content comes from classified documents; remind users of use restrictions
- Anonymize personal privacy information

### 6.5 Continuously Updating Document Collections

- If documents are continually updated (e.g., regulatory databases, case databases), annotate synthesis with a timestamp
- State the temporal validity of synthesis conclusions
- Recommend periodic updates of the synthesis

## VII. Quality Checklist

```markdown
□ 1. Have all documents been received and organized (including ID, type, source)?
□ 2. Have inter-document relationship types been identified (parallel / chronological / adversarial / hierarchical / complementary)?
□ 3. Has core information been extracted from each document (theme, views, facts, grounds, stance)?
□ 4. Have cross-document commonalities been identified and organized?
□ 5. Have inter-document conflicts been identified and annotated objectively (without adjudicating truth)?
□ 6. Have possible causes of conflict points been analyzed?
□ 7. Have cross-document insights been generated (trends, patterns, blind spots, linkages)?
□ 8. Are synthesis conclusions supported by documents (distinguishing “expressly stated” from “reasonable inference”)?
□ 9. Have information gaps been annotated?
□ 10. Does the output format match user needs?
□ 11. Has sensitive information been desensitized?
□ 12. Are document quality differences reflected in the synthesis?
```

## VIII. Related Skills

| Related Skill | Relationship | Notes |
|----------|------|------|
| Legal document summarization | Upstream | First summarize each document individually, then perform multi-document synthesis |
| Legal document formatting | Complementary | Ensure multi-document synthesis output format is standardized and consistent |
| Similar-case retrieval and analysis | Extension | When all documents are judgments, combine with similar-case analysis for deeper comparison |
| Legal norm validity check | Upstream | When synthesizing statutes/regulations, first confirm each document’s current validity |
| Multi-document summarization | Self-extension | When batch-synthesizing larger volumes (10+ documents) |

## IX. Limitations and Risk Notices

- **Source dependence:** Synthesis conclusions depend entirely on the content and quality of input documents. If source documents contain errors, bias, or incomplete information, the synthesis will inherit those problems.
- **Weight judgment:** Documents may differ in importance, but this skill cannot automatically determine “which document is more important”; users must assign weights for the specific scenario.
- **Depth limits:** This skill focuses on horizontal comparison and integration of information; content requiring deep legal analysis still needs skills such as legal rule application and claim-basis analysis.
- **Temporal validity:** For time-sensitive documents such as statutes and cases, synthesis conclusions reflect only the snapshot state of the input documents.
- **Language understanding limits:** For highly specialized or obscure texts, understanding may deviate; for key legal concepts, combine with legal concept comprehension skills.
- **Conflict resolution:** This skill only identifies conflict points; it does not adjudicate factual truth or draw legal conclusions. Resolving conflicts requires further legal analysis or evidence review.
