---
name: legal-norm-validity-check
description: |
  Trigger this skill when, after retrieving a concrete legal provision in the course of legal reasoning, the AI agent must verify that provision's legal force (validity). Trigger conditions include, without limitation:
  1. Before the agent cites any statutory provision as a basis for reasoning;
  2. When the user provides a provision and asks for an analysis of its applicability;
  3. When multiple norms may conflict and priority of application must be determined;
  4. When temporal force is in doubt (possible amendment or repeal);
  5. When it must be confirmed whether a normative document has legally binding force;
  6. When cross-tier or cross-region application of norms raises questions.
  This skill ensures that every legal norm the agent cites is currently in force, correctly tiered, and free of conflict with higher-tier and same-tier norms, thereby safeguarding the reliability and authority of legal-reasoning conclusions.
---

> **Chinese source (authoritative):** [`../../skills/legal-norm-validity-check/SKILL.md`](../../skills/legal-norm-validity-check/SKILL.md)

# Legal Norm Validity Check

## Overview Table

| Item | Content |
|------|---------|
| **Capability name** | Legal Norm Validity Check |
| **Core goal** | Confirm that retrieved provisions are currently in force, correctly tiered, and conflict-free |
| **Input** | One or more retrieved legal-norm provisions (with source information) |
| **Output** | Validity-status report for each norm (valid / invalid / partially amended / conflict exists), with reasons and confidence |
| **Prerequisite skill** | Legal retrieval (statutory retrieval already completed) |
| **Follow-on skills** | Legal application; legal argumentation; drafting of legal opinions |
| **Risk level** | **Extremely high** — citing repealed or conflicting provisions directly yields wrong legal conclusions |
| **Applicable jurisdiction** | Legal system of the People's Republic of China (including notes on HKSAR / Macao SAR linking rules) |

---

## Legal Disclaimer

> **Important notice:** This skill file provides methodological guidance only for AI agents performing legal-norm validity checks; it does not constitute formal legal advice. Validity status of legal norms may change at any time due to legislative activity. When executing this skill, the agent shall:
> 1. Clearly inform the user of the as-of date/time of the validity check;
> 2. Honestly mark uncertainty for any validity status that cannot be confirmed;
> 3. Advise the user to consult a practicing lawyer or official legal databases (e.g., the National Database of Laws and Regulations) on critical legal issues;
> 4. Never use a validity-doubtful provision as the sole basis for a definitive conclusion.

---

## I. Core Concepts

### 1.1 Three Dimensions of Legal-Norm Validity

Validity checks must cover all three dimensions below; none may be omitted:

```
┌─────────────────────────────────────────────────┐
│     Three Dimensions of Legal-Norm Validity Check │
│                                                   │
│   ┌──────────┐  ┌──────────┐  ┌──────────┐      │
│   │ Temporal │  │Hierarchy │  │ Conflict │      │
│   │ validity │  │ validity │  │  check   │      │
│   │(temporal)│  │(hierarchy│  │(conflict)│      │
│   │          │  │         )│  │          │      │
│   └────┬─────┘  └────┬─────┘  └────┬─────┘      │
│        │             │             │              │
│   Currently in   Does the        Conflict with   │
│   force? Amended │enacting body  higher/same-tier│
│   or repealed?   │have authority?│norms? How to  │
│   Transitional   │Is the tier    │choose which   │
│   clauses?       │correct?       │applies?       │
└─────────────────────────────────────────────────┘
```

### 1.2 Classification of Validity Status

| Validity status | Definition | Marker |
|-----------------|------------|--------|
| **Currently valid** | The norm has taken effect and has not been amended, repealed, or revoked | ✅ VALID |
| **Amended / revised** | The original text has been replaced by a new text; the latest version must be cited | 🔄 AMENDED |
| **Partially invalid** | The norm as a whole remains valid, but specific clauses have been amended or repealed | ⚠️ PARTIAL |
| **Repealed** | The norm has been expressly repealed and no longer has legal force | ❌ REPEALED |
| **Expired** | The norm has naturally lost force because its term ended or its regulatory object disappeared | ❌ EXPIRED |
| **Not yet in force** | The norm has been promulgated but has not yet reached its effective date | ⏳ PENDING |
| **Validity uncertain** | Validity status cannot be determined; further verification needed | ❓ UNCERTAIN |

### 1.3 Norm Hierarchy in the Chinese Legal System

```
Tier 1: Constitution
  │
Tier 2: Laws (enacted by the NPC and its Standing Committee)
  │  ├── Basic laws (NPC)
  │  └── Other laws (NPC Standing Committee)
  │
Tier 3: Administrative regulations (State Council)
  │
Tier 4: Local regulations ←→ departmental rules (same tier, different enacting bodies)
  │  ├── Provincial local regulations
  │  ├── Local regulations of cities divided into districts
  │  └── Autonomous regulations and separate regulations
  │
Tier 5: Local government rules
  │
Other: Judicial interpretations (SPC / SPP)
      Normative documents (governments and departments at all levels)
      Guiding Cases (issued by the SPC)
```

### 1.4 Key Legal Bases

Core legal norms the agent itself relies on when executing this skill:

| Legal norm | Key clauses | Regulatory content |
|------------|-------------|-------------------|
| *Legislation Law of the PRC* (2023 amendment) | Full text, esp. Arts. 87–101 | Enactment authority, hierarchy, conflict resolution |
| *Constitution of the PRC* | Arts. 5, 62–67 | Unity of the legal system; division of legislative competence |
| *Regulations on Filing and Review of Regulations and Rules* | Full text | Filing and review procedures |
| *SPC Provisions on Citing Laws, Regulations and Other Normative Legal Documents in Judgment Documents* | Full text | Scope of citable normative documents |

---

## II. Complete Workflow

### 2.0 Data Sources and Tool-Invocation Convention (Mandatory)

> **Core principle: Current validity status of a provision must come from real source-tracing. It is strictly forbidden to judge by memory whether a provision has been amended or repealed.**

This skill's risk level is **extremely high** — citing repealed or conflicting provisions directly yields wrong legal conclusions. Before running the verification workflow below, first determine whether the runtime environment has **statute source-tracing / validation tools** (e.g., a connected regulations-library MCP service, statute identification and tracing tools, retrieval APIs, or a local regulations library):

1. **If such tools exist:** The agent must submit the provision identifier (law title + article number, or the cited text) to the tool, and use the tool's returned real results (full text, document number, **force level**, **timeliness: currently valid / amended / repealed**, amendment history) as the basis for validity determination. If the tool can "validate / correct model-generated provisions", also use it to compare the provision cited this time and flag article-number displacement, outdated versions, or fabricated articles.
2. **If no such tools exist:** Still complete the methodological verification steps, but any validity status that cannot be confirmed online must be marked for uncertainty under "VI. Confidence Marking System", with an express statement that "no regulations library is connected; validity status awaits human verification". **Never disguise validity-doubtful provisions as definitive conclusions, and never fabricate amendment/repeal information.**
3. **Tool-agnostic:** This convention depends only on the abstract capabilities "trace a provision's current status" and "validate whether a citation is real/current"; it is not bound to any specific vendor. Concrete integration methods (e.g., PKULaw MCP statute tracing, hallucinated-provision correction services) are described in [`README.md`](./README.md) under this skill's directory.

> Tool verification results should be weighed together with "4.2 Information-Source Reliability Grading"; for critical provisions, cross-check against the official [National Database of Laws and Regulations](https://flk.npc.gov.cn) is still recommended.

### 2.1 Overall Flowchart

```
Input: Retrieved legal-norm provision(s)
         │
         ▼
┌─────────────────────┐
│ Step 1: Identify and │ ──→ Confirm full name, enacting body,
│ locate the norm      │      promulgation date, effective date, document number
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│ Step 2: Temporal     │ ──→ Currently in force? Amended/repealed?
│ validity check       │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│ Step 3: Enacting     │ ──→ Does the enacting body have authority?
│ body & hierarchy     │      Is the tier correct?
│ validity check       │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│ Step 4: Norm conflict│ ──→ Conflict with higher/same-tier norms?
│ check                │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│ Step 5: Special      │ ──→ Retroactivity, transitional clauses,
│ validity-rule check  │      special provisions, etc.
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│ Step 6: Comprehensive│ ──→ Aggregate three-dimension conclusions;
│ determination & output│      give final determination
└─────────────────────┘
         │
         ▼
Output: Validity-status report (with confidence)
```

### 2.2 Detailed Operations for Each Step

#### Step 1: Identify and Locate the Norm

**Purpose:** Precisely lock the identity information of the norm under check; avoid mistaken identity.

**Operations checklist:**

- [ ] Confirm the norm's **full official title** (distinguish same-named norms at different tiers)
- [ ] Confirm the **enacting body** (NPC / State Council / local people's congress / ministry, etc.)
- [ ] Confirm the **document number** (e.g., "Order of the President of the PRC No. XX")
- [ ] Confirm **promulgation date** and **effective date**
- [ ] Confirm the **specific clause citation** (Art. X, Para. X, Item X)
- [ ] Confirm whether **same-named different versions** exist (e.g., multiple amendments)

**Key caveats:**

```
⚠️ Common confusion scenarios:
1. General Principles of the Civil Law vs. Civil Code — the former has been repealed
2. Company Law 2018 amendment vs. 2023 revision — huge version differences
3. Administrative Penalty Law 1996 vs. 2021 revised version
4. Departmental rules and local regulations with the same name but different content
5. Difference between "amendment" (修正) and "revision" (修订):
   - Amendment: changes to individual clauses; remaining clauses unchanged
   - Revision: comprehensive rewrite of the law, producing a new text
```

#### Step 2: Temporal Validity Check

**Purpose:** Confirm whether the norm is valid at the current time point (or the case-relevant time point).

**Operations flow:**

```
2.1 Check effective date
    │
    ├── Effective date not yet reached → mark ⏳ PENDING
    │
    └── Effective date reached → continue
         │
         2.2 Check for an express validity period
         │
         ├── Has a period and it has expired → mark ❌ EXPIRED
         │
         └── No period or not yet expired → continue
              │
              2.3 Check whether amended / revised
              │
              ├── Amended → confirm amendment scope
              │   ├── Affects the cited clause → mark 🔄 AMENDED; locate the new clause
              │   └── Does not affect the cited clause → mark ✅ VALID (note that an amended version exists)
              │
              ├── Revised (comprehensive rewrite) → mark 🔄 AMENDED; must use the new version
              │
              └── Not amended/revised → continue
                   │
                   2.4 Check whether repealed
                   │
                   ├── Expressly repealed (new law lists a repeal schedule) → mark ❌ REPEALED
                   │
                   ├── Impliedly repealed (new law contradicts old law and does not expressly repeal)
                   │   → mark ⚠️ PARTIAL or ❓ UNCERTAIN; further analysis needed
                   │
                   └── Not repealed → mark ✅ VALID
```

**Temporal validity check points:**

| Check item | Concrete operation | Information source |
|------------|--------------------|--------------------|
| Effective date | Check the commencement clause at the end of the text | Statutory text |
| Amendment / revision record | Query successive amendments of the law | National Database of Laws and Regulations |
| Repeal information | Query whether a new law expressly repealed it | Repeal decisions; annexes of new laws |
| Validity period | Some regulations have an express term (e.g., temporary regulations) | Statutory text |
| Cleanup decisions | Periodic cleanup of regulations and rules by the State Council / local governments | Cleanup decision documents |

#### Step 3: Enacting Body and Hierarchy Validity Check

**Purpose:** Confirm that the enacting body has corresponding legislative competence and that the tier placement is correct.

**Operations flow:**

```
3.1 Identify the enacting body
    │
    3.2 Confirm the enacting body's legislative competence
    │
    ├── NPC → may enact basic laws
    ├── NPC Standing Committee → may enact other laws
    ├── State Council → may enact administrative regulations (within legal authorization or constitutional competence)
    ├── State Council ministries → may enact departmental rules (limited to implementing laws/administrative regulations)
    ├── Provincial people's congresses and their standing committees → may enact local regulations
    ├── People's congresses of cities divided into districts and their standing committees → may enact local regulations
    │     on urban/rural construction and management, ecological environmental protection, historical/cultural protection, etc.
    ├── Provincial governments → may enact local government rules
    ├── Governments of cities divided into districts → may enact local government rules (limited to the above matters)
    ├── SPC / SPP → may issue judicial interpretations
    └── Other bodies → may be only normative documents, without strict "law" force
    │
    3.3 Check for ultra vires legislation
    │
    ├── Does it involve matters reserved to law?
    │   (Legislation Law Art. 11: crimes and penalties; deprivation and restriction of citizens' political rights;
    │     compulsory measures and penalties restricting personal liberty; establishment of tax types, determination of
    │     tax rates, and basic tax collection/administration systems; expropriation/requisition of non-state-owned
    │     property; basic civil systems; basic economic systems; basic litigation and arbitration systems, etc. —
    │     may only be provided by law)
    │
    ├── Do departmental rules exceed the scope of implementing legislation?
    │
    └── Do local regulations conflict with higher-tier law?
    │
    3.4 Determine the norm's tier
    │
    └── Locate per the hierarchy in §1.3
```

**Legislative competence quick reference:**

| Matter type | Lowest competent tier | Legal basis |
|-------------|----------------------|-------------|
| Crimes and penalties | Law (absolute reservation) | Legislation Law Art. 11(1) |
| Compulsory measures and penalties restricting personal liberty | Law (absolute reservation) | Legislation Law Art. 11(2) |
| Establishment of tax types; determination of tax rates | Law (absolute reservation) | Legislation Law Art. 11(3) |
| Expropriation / requisition of non-state-owned property | Law (absolute reservation) | Legislation Law Art. 11(4) |
| Basic civil systems | Law | Legislation Law Art. 11(5) |
| Basic economic systems | Law | Legislation Law Art. 11(6) |
| Basic litigation and arbitration systems | Law | Legislation Law Art. 11(7) |
| Concrete administrative management matters | Administrative regulations / local regulations | Related Legislation Law provisions |
| Implementing laws / administrative regulations | Departmental rules / local government rules | Legislation Law Arts. 91, 93 |

#### Step 4: Norm Conflict Check

**Purpose:** Identify contradictions between the provision under check and other legal norms, and determine priority-of-application rules.

**Operations flow:**

```
4.1 Vertical conflict check (different tiers)
    │
    ├── Conflict with the Constitution?
    ├── Does lower-tier law contradict higher-tier law?
    │   Rule: higher law prevails over lower law (Legislation Law Art. 99)
    │
    4.2 Horizontal conflict check (same tier)
    │
    ├── Conflict among laws enacted by the same body?
    │   ├── General vs. special → special prevails over general
    │   ├── New vs. old → later prevails over earlier
    │   └── New general vs. old special → if application cannot be determined,
    │       the enacting body decides (Legislation Law Art. 103)
    │
    ├── Conflict between local regulations and departmental rules?
    │   → State Council gives an opinion:
    │     Apply local regulations → apply local regulations
    │     Apply departmental rules → submit to NPC Standing Committee for decision
    │     (Legislation Law Art. 104)
    │
    ├── Conflict among departmental rules?
    │   → State Council decides (Legislation Law Art. 105)
    │
    └── Conflict among local government rules?
        → Within the same province, the provincial government decides
        → Across provinces, the State Council decides
    │
    4.3 Special conflict rules
    │
    ├── SEZ regulations → may vary laws/administrative regulations within the SEZ
    ├── Autonomous / separate regulations → may lawfully vary laws/administrative regulations
    └── Authorized legislation → may depart from existing law within the scope of authorization
```

**Conflict-resolution quick matrix:**

| Conflict type | Applicable rule | Legal basis | Deciding body |
|---------------|-----------------|-------------|---------------|
| Constitution vs. law | Constitution prevails | Constitution Art. 5 | NPC / NPC Standing Committee |
| Law vs. administrative regulation | Law prevails | Legislation Law Art. 99 | — |
| Law vs. local regulation | Law prevails | Legislation Law Art. 99 | — |
| Administrative regulation vs. local regulation | Administrative regulation prevails | Legislation Law Art. 99 | — |
| Administrative regulation vs. departmental rule | Administrative regulation prevails | Legislation Law Art. 99 | — |
| Local regulation vs. local government rule | Local regulation prevails | Legislation Law Art. 99 | — |
| Same body: special vs. general | Special prevails | Legislation Law Art. 103 | — |
| Same body: new vs. old | Later prevails | Legislation Law Art. 103 | — |
| Same body: new general vs. old special | If indeterminate, request a decision | Legislation Law Art. 103 | Enacting body |
| Local regulation vs. departmental rule | State Council gives an opinion | Legislation Law Art. 104 | State Council / NPC Standing Committee |
| Departmental rule vs. departmental rule | State Council decides | Legislation Law Art. 105 | State Council |

#### Step 5: Special Validity-Rule Check

**Purpose:** Handle special situations in legal-norm validity.

**Checklist:**

```
5.1 Retroactivity check
    │
    ├── General principle: non-retroactivity of law
    ├── Exceptions:
    │   ├── Criminal law: old law unless new law is lighter (Criminal Law Art. 12)
    │   ├── Civil law: favorable retroactivity (some judicial interpretations)
    │   └── Administrative law: where the new law expressly provides for retroactivity
    │
    5.2 Transitional-clause check
    │
    ├── Does the new law provide a transition period?
    ├── Does the old law continue to apply during the transition?
    └── Start and end of the transition period?
    │
    5.3 Territorial validity check
    │
    ├── Nationwide laws → nationwide force (except HKSAR/Macao/Taiwan unless listed in Basic Law Annex III)
    ├── Local regulations → valid only within the administrative region
    └── SEZ regulations → valid only within the SEZ
    │
    5.4 Personal validity check
    │
    ├── Applicable only to specific subjects? (e.g., military personnel, civil servants)
    ├── Issues involving foreigners / stateless persons?
    └── Differential application to legal persons vs. natural persons?
    │
    5.5 Special validity rules for judicial interpretations
    │
    ├── Force of judicial interpretations is below laws and administrative regulations
    ├── Judicial interpretations may not create new rights/obligations beyond the statute
    ├── When old and new judicial interpretations conflict, generally apply the new one
    └── Temporal force of a judicial interpretation usually tracks the law it interprets
```

#### Step 6: Comprehensive Validity Determination and Output

**Purpose:** Aggregate results of the first five steps into a final validity determination.

**Determination logic:**

```
IF temporal validity = repealed / expired / not yet in force
   THEN final determination = corresponding status (stop further checks)

ELSE IF temporal validity = amended / revised
   THEN mark that the latest version must be used
        continue hierarchy and conflict checks on the latest version

ELSE IF hierarchy validity = enacting body lacks authority / ultra vires
   THEN final determination = validity uncertain (state reasons)
        Tip: the norm may be inapplicable for violating higher-tier law

ELSE IF norm conflict exists
   THEN determine the preferentially applicable norm under conflict-resolution rules
        mark the conflict and the solution

ELSE
   final determination = currently valid
```

---

## III. Common Domains and Sources of Law

| Legal domain | Core statutes | Common accompanying regulations / judicial interpretations | Validity-check focus |
|--------------|---------------|------------------------------------------------------------|----------------------|
| **Contract disputes** | *Civil Code* Contract Book | Contract Book Judicial Interpretations (I)(II) | Note *Contract Law* repealed; whether old judicial interpretations still apply |
| **Tort liability** | *Civil Code* Tort Liability Book | Personal-injury compensation judicial interpretation | Compensation standards may vary by local rules |
| **Labor disputes** | *Labor Law*; *Labor Contract Law* | Implementing regulations; local labor-arbitration rules | Large local variation; watch hierarchy |
| **Criminal cases** | *Criminal Law* and amendments | Offense-specific judicial interpretations | Temporal force of Criminal Law amendments (old unless new is lighter) |
| **Administrative penalties** | *Administrative Penalty Law* (2021) | Sectoral penalty measures | Major 2021 revision; watch old/new transition |
| **Corporate governance** | *Company Law* (2023 revision) | Company Law Judicial Interpretations (I)–(V) | Effective 1 July 2024; watch transitional rules |
| **IP** | *Patent Law*; *Trademark Law*; *Copyright Law* | Implementing regulations; judicial interpretations | All three recently amended; version verification critical |
| **Real estate** | *Civil Code* Property Rights Book | Interim Regulations on Immovable Property Registration | *Property Law* repealed; update citations |
| **Tax** | Tax-type laws / interim regulations | Implementing rules; STA announcements | Some tax types still exist as interim regulations |
| **Environmental protection** | *Environmental Protection Law* (2014) | Pollution-prevention laws; EIA law | Local standards may be stricter than national |

---

## IV. Validation and Screening Rules

### 4.1 Priority Rules for Validity Verification

When checking validity, execute in this priority order:

```
Priority 1 (blocking check): Temporal validity
  → If repealed/expired, stop immediately; no further checks
  
Priority 2 (foundational check): Enacting body and hierarchy
  → Confirm the norm's "identity" is correct

Priority 3 (relational check): Norm conflict
  → After confirming the norm itself is valid, check relations with other norms

Priority 4 (supplementary check): Special validity rules
  → Handle retroactivity, transitional clauses, and similar details
```

### 4.2 Information-Source Reliability Grading

| Reliability grade | Information source | Usage advice |
|-------------------|--------------------|--------------|
| **Grade A (authoritative)** | National Database of Laws and Regulations (flk.npc.gov.cn); China Government Legal Information Network; NPC official website | Prefer; may cite directly |
| **Grade B (reliable)** | PKULaw; Wolters Kluwer Ahead; China Judgments Online | Usable; recommend cross-verification |
| **Grade C (reference)** | Law Press publications; authoritative law textbooks | Auxiliary reference only |
| **Grade D (use with caution)** | Ordinary web sources; unofficial compilations | May not alone serve as basis for validity judgment |

### 4.3 Screening Rules

The following situations should trigger **mandatory re-verification**:

1. **Norm promulgated more than 10 years ago** with no amendment record found → possible overlooked amendments
2. **Departmental rules or local regulations** cited as core basis → extra check for conflict with higher-tier law
3. **Judicial interpretation** issued earlier than the latest amendment of the law it interprets → may no longer apply
4. **Normative documents** (not laws, regulations, or rules) used as basis → confirm legal binding force
5. **Transitional application involving repealed laws** → carefully check transitional clauses

---

## V. Output Format Templates

### 5.1 Single-Norm Validity Check Report

```markdown
## Legal Norm Validity Check Report

### Basic Information
- **Norm title:** [Full official title]
- **Enacting body:** [Full name]
- **Norm tier:** [Constitution / law / administrative regulation / local regulation / departmental rule / local government rule / judicial interpretation / normative document]
- **Document number:** [Promulgation number]
- **Promulgation date:** [YYYY-MM-DD]
- **Effective date:** [YYYY-MM-DD]
- **Clause under check:** Art. [X], Para. [X], Item [X]
- **Check date:** [YYYY-MM-DD]

### Validity Determination

| Dimension | Result | Details |
|-----------|--------|---------|
| Temporal validity | [✅/🔄/⚠️/❌/⏳/❓] | [Specific explanation] |
| Hierarchy validity | [✅/⚠️/❓] | [Specific explanation] |
| Conflict check | [✅ No conflict / ⚠️ Conflict exists / ❓ Pending confirmation] | [Specific explanation] |

### Final Determination
- **Validity status:** [Currently valid / Amended / Partially invalid / Repealed / Expired / Not yet in force / Validity uncertain]
- **Confidence:** [High / Medium / Low] (see Confidence Marking System)
- **Usage advice:** [May cite directly / Update to latest version / Must not cite / Further verification needed]

### Notes
- [If amended, list latest version information]
- [If conflict, list conflicting norms and solution]
- [If special validity rules apply, list relevant notes]
```

### 5.2 Multi-Norm Batch Check Summary Table

```markdown
## Legal Norm Validity Batch Check Summary

| No. | Norm title | Cited clause | Temporal | Hierarchy | Conflict | Final determination | Confidence | Advice |
|-----|------------|--------------|----------|-----------|----------|---------------------|------------|--------|
| 1 | [Title] | Art. X | [Status] | [Status] | [Status] | [Determination] | [H/M/L] | [Advice] |
| 2 | [Title] | Art. X | [Status] | [Status] | [Status] | [Determination] | [H/M/L] | [Advice] |
| ... | ... | ... | ... | ... | ... | ... | ... | ... |

### Issues Requiring Special Attention
1. [List validity issues requiring special attention]
2. [List conflicting norm combinations and solutions]
```

---

## VI. Confidence Marking System

### 6.1 Confidence Level Definitions

| Confidence | Marker | Definition | Typical scenarios |
|------------|--------|------------|-------------------|
| **High** | 🟢 HIGH | Validity status can be determined; authoritative source; no contradictory signals | Law clearly marked "currently valid" in the National Database of Laws and Regulations |
| **Medium** | 🟡 MEDIUM | Validity basically judgeable, but factors need attention | Recent amendment but cited clause unaffected; possible conflict with a clear resolution rule |
| **Low** | 🔴 LOW | Validity cannot be determined, or major uncertainties exist | Cannot confirm latest amendments; conflict unresolvable by existing rules; unclear binding force of a normative document |

### 6.2 Confidence Determination Rules

```
Confidence = HIGH if and only if:
  ✓ Information source is Grade A (authoritative)
  ✓ Temporal validity clear (express "currently valid" mark or repeal record)
  ✓ Hierarchy validity undisputed
  ✓ No norm conflict found, or conflict has a clear resolution rule

Confidence = MEDIUM if any of the following:
  △ Information source is Grade B
  △ Law recently amended; need to confirm whether cited clause is affected
  △ Norm conflict exists but has a clear resolution rule
  △ Involves application of transitional clauses

Confidence = LOW if any of the following:
  ✗ Information source is Grade C or D
  ✗ Cannot confirm latest amendment/repeal
  ✗ Norm conflict cannot be resolved by existing rules
  ✗ Enacting body's legislative competence is doubtful
  ✗ Legal binding force of a normative document is unclear
```

### 6.3 Effect of Confidence on Follow-on Operations

| Confidence | Follow-on requirements |
|------------|------------------------|
| 🟢 HIGH | May use the provision directly in legal reasoning |
| 🟡 MEDIUM | May use in legal reasoning, but note validity-check reservations in the conclusion |
| 🔴 LOW | **Must not** use the provision as the basis for a definitive conclusion; must advise further verification; should seek alternative legal bases |

---

## VII. Common Errors and Prevention

### 7.1 Fatal Error Table

| Error No. | Error type | Description | Severity | Prevention |
|-----------|------------|-------------|----------|------------|
| **E01** | Citing repealed law | Citing a repealed provision as a valid basis | ⭐⭐⭐⭐⭐ Fatal | Always run Step 2 temporal check before citation; maintain a common-repealed-laws list |
| **E02** | Version confusion | Citing an old-version text instead of the latest amendment/revision | ⭐⭐⭐⭐⭐ Fatal | Confirm latest amendment date; compare old and new texts |
| **E03** | Hierarchy error | Citing lower-tier rules as higher-tier, or ignoring higher-tier priority | ⭐⭐⭐⭐ Serious | Clearly mark each norm's tier; strictly apply higher-over-lower on conflict |
| **E04** | Ignoring conflict | Failing to detect contradiction with other valid norms | ⭐⭐⭐⭐ Serious | Run Step 4 conflict check on core basis provisions; watch multiple statutes in the same field |
| **E05** | Beyond scope of application | Applying local regulations outside their region, or special law to general situations | ⭐⭐⭐ Major | Check territorial and personal validity |
| **E06** | Misidentifying normative documents | Treating non-binding normative documents as laws/regulations | ⭐⭐⭐ Major | Strictly distinguish laws, regulations, rules from ordinary normative documents |
| **E07** | Retroactivity misjudgment | Wrongly applying new law to pre-commencement conduct, or wrongly refusing favorable retroactivity | ⭐⭐⭐ Major | Clarify relation between fact-occurrence time and law effective date |

### 7.2 Common Traps

#### Trap 1: Laws Repealed upon Commencement of the Civil Code

```
⚠️ Trap description:
The Civil Code took effect on 1 January 2021 and simultaneously repealed nine laws:
1. Marriage Law of the PRC
2. Succession Law of the PRC
3. General Principles of the Civil Law of the PRC
4. Adoption Law of the PRC
5. Guarantee Law of the PRC
6. Contract Law of the PRC
7. Property Law of the PRC
8. Tort Liability Law of the PRC
9. General Provisions of the Civil Law of the PRC

✅ Prevention:
- Replace any citation of the above nine laws with the corresponding Civil Code provisions
- Note: some judicial interpretations under old laws remain effective after amendment; verify one by one
- The SPC Provisions on the Temporal Effect of Applying the Civil Code specially address transition issues
```

#### Trap 2: Temporal-Force Trap for Judicial Interpretations

```
⚠️ Trap description:
After a law is amended, existing judicial interpretations may:
(a) Be expressly repealed
(b) Continue to apply after amendment
(c) Be left unaddressed but substantially contradict the new law

✅ Prevention:
- Consult SPC decisions on cleaning up judicial interpretations
- Compare judicial-interpretation text with the latest version of the interpreted law
- If the judicial interpretation predates the law's latest amendment, be especially alert
```

#### Trap 3: "Latent Invalidity" of Local Regulations

```
⚠️ Trap description:
After higher-tier law is amended, local regulations may not be updated in time, leading to:
- Formally still "valid" (not expressly repealed)
- Substantively contradicting higher-tier law (should not be applied)

✅ Prevention:
- Validity checks of local regulations must include consistency comparison with higher-tier law
- Watch local people's congress standing committees' cleanup announcements
- If contradiction is found, apply higher-tier law
```

#### Trap 4: Ultra Vires Legislation by Departmental Rules

```
⚠️ Trap description:
Departmental rules may only be made within the scope of implementing laws and administrative regulations,
but in practice some departmental rules exceed authority and create new rights/obligations.

✅ Prevention:
- Check whether departmental rules have a higher-tier legal basis
- Departmental rules may not set norms that diminish citizens' rights or increase citizens' obligations
  (Legislation Law Art. 91)
- Departmental rules may not add administrative licenses (Administrative Licensing Law Art. 17)
```

#### Trap 5: "Vacuum Zones" in Old/New Law Transition

```
⚠️ Trap description:
There may be a time gap between new-law commencement and old-law repeal,
or the new law may omit issues that the repealed old law covered.

✅ Prevention:
- Carefully read the new law's transitional clauses (usually in the annex)
- Consult accompanying commencement explanations or judicial interpretations
- If a true legal gap exists, honestly inform the user
```

---

## VIII. Special Scenario Handling

### 8.1 Scenario: Norms Involving Hong Kong, Macao, and Taiwan

```
Handling rules:
1. Application of nationwide laws in the HKSAR / Macao SAR:
   - Limited to nationwide laws listed in Basic Law Annex III
   - Promulgated or legislatively implemented locally by the SAR
   
2. Taiwan-related legal issues:
   - Mainland law generally does not apply directly in Taiwan
   - Taiwan-related civil/commercial cases apply the Law on the Application of Law
     to Foreign-Related Civil Relations and related rules
   
3. Validity-check points:
   - Clarify the territory implicated by the legal issue
   - Confirm whether the relevant law applies in that territory
   - If interregional conflict of laws arises, apply relevant conflict norms
```

### 8.2 Scenario: Norm Undergoing Revision

```
Handling rules:
1. Revision drafts / consultation drafts → no legal force; must not be cited as basis
2. New law passed but not yet in force → mark ⏳ PENDING
3. Transition period before new-law commencement → apply currently valid old law
4. Should tip the user:
   - Relevant law is under revision
   - Revised law may change current application conclusions
   - Recommend monitoring legislative developments
```

### 8.3 Scenario: Determining Force of Normative Documents

```
Handling rules:
1. Normative documents ("red-header documents") are not laws, regulations, or rules
2. In court adjudication:
   - May be cited as a basis for reasoning
   - May not be cited as the legal basis for the judgment
   - Courts may conduct incidental review of normative documents (in administrative litigation)
3. Validity-check points:
   - Clearly mark their "normative document" nature
   - Check for conflict with higher-tier laws/regulations
   - Check whether the enacting body had authority
   - Check legality review and filing
   - Lower the confidence grade
```

### 8.4 Scenario: Force of Guiding Cases and Similar Cases

```
Handling rules:
1. SPC Guiding Cases:
   - Not legal norms, but have "shall be referred to" force
   - Courts at all levels shall refer to them when trying similar cases
   - Validity-check focus: whether still a valid Guiding Case (replaced or revoked?)
   
2. Other cases:
   - No legal binding force
   - Reference only
   
3. Validity-check points:
   - Confirm Guiding Case number and release batch
   - Confirm it remains effective
   - Confirm its holdings are consistent with current law
```

### 8.5 Scenario: Relation Between International Treaties and Domestic Law

```
Handling rules:
1. International treaties China has concluded or acceded to:
   - Generally treated as having equal force with domestic law (mainstream view)
   - When a treaty conflicts with domestic law, the treaty generally prevails
     (except the Constitution; and except clauses to which China entered a reservation)
   
2. Validity-check points:
   - Confirm China is a party / acceding state
   - Confirm the treaty has entered into force
   - Confirm whether China reserved relevant clauses
   - Confirm whether there is domestic transforming/implementing legislation
```

---

## IX. Quality Checklist

After completing the validity check, the agent should verify each item below:

### 9.1 Completeness Check

- [ ] Was every cited legal norm validity-checked?
- [ ] Were all three dimensions (temporal, hierarchy, conflict) fully checked?
- [ ] Were special validity rules (retroactivity, transitional clauses, territorial force, etc.) checked?
- [ ] Was validity status and confidence marked for each norm?

### 9.2 Accuracy Check

- [ ] Are title, document number, and dates accurate?
- [ ] Are cited clause numbers correct (article, paragraph, item, sub-item)?
- [ ] Is the latest version of the legal text cited?
- [ ] Is the enacting body correctly identified?
- [ ] Is the tier correctly placed?

### 9.3 Consistency Check

- [ ] Is the determination consistent with the check process?
- [ ] Is there logical contradiction among determinations for multiple norms?
- [ ] Does confidence marking match the actual check situation?

### 9.4 Risk-Tip Check

- [ ] Were clear warnings given for validity-doubtful provisions?
- [ ] Was further verification recommended for low-confidence determinations?
- [ ] Were pending factors that may affect validity determination tipped?
- [ ] Was the as-of time-point limit of the validity check communicated?

### 9.5 Output-Specification Check

- [ ] Does output format meet the template?
- [ ] Was usage advice provided (may cite / update / must not cite / verify)?
- [ ] For conflicting norms, was a solution given?

---

## X. Complete Examples

### Example 1: Simple Scenario — Single-Norm Validity Check

**Scenario:** The user asks about contractual default liability. The agent retrieved Art. 107 of the *Contract Law of the PRC* as a basis and must run a validity check.

---

#### Validity Check Process

**Step 1: Identify and Locate the Norm**

| Item | Content |
|------|---------|
| Norm title | *Contract Law of the PRC* |
| Enacting body | National People's Congress |
| Document number | Order of the President of the PRC No. 15 |
| Promulgation date | 15 March 1999 |
| Effective date | 1 October 1999 |
| Cited clause | Art. 107 (general provision on default liability) |

**Step 2: Temporal Validity Check**

- Effective date: 1 October 1999 → reached ✓
- Amendment / revision record: no separate amendment
- **Repeal information: *Civil Code of the PRC* Art. 1260 expressly repeals the *Contract Law of the PRC* as of 1 January 2021**
- **Conclusion: ❌ REPEALED — repealed as of 1 January 2021**

**Steps 3–5: Because Step 2 already determined repeal, mark as a blocking result, but still provide an alternative.**

**Alternative search:**
- Former *Contract Law* Art. 107: "Where a party fails to perform its contractual obligations or its performance does not conform to the agreement, it shall bear default liability such as continuing performance, taking remedial measures, or compensating for losses."
- Corresponding *Civil Code* Art. 577: same text in substance.
- *Civil Code* Art. 577 is essentially consistent with former *Contract Law* Art. 107.

**Step 6: Comprehensive Validity Determination**

#### Validity Check Report

```
## Legal Norm Validity Check Report

### Basic Information
- **Norm title:** *Contract Law of the PRC*
- **Enacting body:** National People's Congress
- **Norm tier:** Law (basic law)
- **Document number:** Order of the President of the PRC No. 15
- **Promulgation date:** 1999-03-15
- **Effective date:** 1999-10-01
- **Clause under check:** Art. 107
- **Check date:** [current date]

### Validity Determination

| Dimension | Result | Details |
|-----------|--------|---------|
| Temporal validity | ❌ REPEALED | Expressly repealed by Civil Code Art. 1260 as of 1 January 2021 |
| Hierarchy validity | — | Not checked further because repealed |
| Conflict check | — | Not checked further because repealed |

### Final Determination
- **Validity status:** Repealed
- **Confidence:** 🟢 HIGH (clear repeal information; authoritative source)
- **Usage advice:** ❌ Must not cite. Replace with *Civil Code of the PRC* Art. 577.

### Notes
- Content of former Contract Law Art. 107 is substantially carried forward by Civil Code Art. 577
- If the case facts occurred before 1 January 2021, under the SPC Provisions on the Temporal Effect
  of Applying the Civil Code, the former Contract Law may still apply
- Recommend verifying the fact-occurrence date to determine applicable law
```

---

### Example 2: Complex Scenario — Multi-Norm Validity Check and Conflict Resolution

**Scenario:** An enterprise in City B of Province A (a city divided into districts) discharged pollutants and was fined by the local ecology and environment bureau. The enterprise contests the penalty. The agent retrieved the following norms as analytical bases and must run validity checks:

1. *Environmental Protection Law of the PRC* (2014 revision) Art. 59 — continuous daily penalties
2. *Air Pollution Prevention and Control Law of the PRC* (2018 amendment) Art. 99 — specific fine amounts
3. Province A *Environmental Protection Regulations* (2019 revision) Art. 45 — provincial penalty standards
4. City B *Air Pollution Prevention and Control Administration Measures* (2016) Art. 30 — municipal penalty rules
5. Ministry of Ecology and Environment *Measures for Environmental Administrative Penalties* (2010) Art. 11 — penalty procedure

---

#### Validity Check Process

##### Norm 1: *Environmental Protection Law* Art. 59

**Step 1: Identify and Locate**

| Item | Content |
|------|---------|
| Norm title | *Environmental Protection Law of the PRC* |
| Enacting body | NPC Standing Committee |
| Norm tier | Law |
| Latest revision | Revised 24 April 2014 |
| Effective date | 1 January 2015 |
| Cited clause | Art. 59 (continuous daily penalties) |

**Step 2: Temporal validity** → 2014 revision is the latest version; currently valid ✅

**Step 3: Hierarchy validity** → NPC Standing Committee enactment; tier is law; authority correct ✅

**Step 4: Conflict check** → As the basic law in environmental protection, it is higher-tier law ✅

**Determination:** ✅ VALID | 🟢 HIGH

---

##### Norm 2: *Air Pollution Prevention and Control Law* Art. 99

**Step 1: Identify and Locate**

| Item | Content |
|------|---------|
| Norm title | *Air Pollution Prevention and Control Law of the PRC* |
| Enacting body | NPC Standing Committee |
| Norm tier | Law |
| Latest amendment | Amended 26 October 2018 |
| Effective date | 1 January 2016 (2018 amendment effective immediately) |
| Cited clause | Art. 99 (fines for excess emissions) |

**Step 2: Temporal validity** → 2018 amendment is the latest version. Confirm whether Art. 99 was changed in 2018. Upon check, the 2018 amendment mainly adjusted institutional-reform-related clauses; Art. 99 was not amended. Currently valid ✅

**Step 3: Hierarchy validity** → NPC Standing Committee enactment; tier is law; authority correct ✅

**Step 4: Conflict check** → Relation to *Environmental Protection Law*: *Air Pollution Prevention and Control Law* is the special law for air pollution; *Environmental Protection Law* is the general law. On air-pollution penalties, *Air Pollution Prevention and Control Law* prevails (special over general). No substantive contradiction between the two. ✅

**Determination:** ✅ VALID | 🟢 HIGH

---

##### Norm 3: Province A *Environmental Protection Regulations* Art. 45

**Step 1: Identify and Locate**

| Item | Content |
|------|---------|
| Norm title | Province A Environmental Protection Regulations |
| Enacting body | Standing Committee of Province A People's Congress |
| Norm tier | Local regulation (provincial) |
| Latest revision | 2019 |
| Cited clause | Art. 45 (provincial penalty standards) |

**Step 2: Temporal validity** → 2019 revision; confirm subsequent amendments. Assume none found. ✅

**Step 3: Hierarchy validity** → Provincial people's congress standing committee may enact local regulations; authority correct. Note: local regulations rank below laws and administrative regulations. ✅

**Step 4: Conflict check** → **Key check points:**
- Do Art. 45's penalty standards contradict *Air Pollution Prevention and Control Law* Art. 99?
- Scenario analysis:
  - If provincial fine ranges are within the national statutory range → no conflict ✅
  - If provincial fine ranges exceed the national statutory ceiling → possible conflict with higher-tier law ⚠️
  - If provincial fine ranges fall below the national statutory floor → conflict with higher-tier law ⚠️

Assume comparison shows: Province A Regulations Art. 45 further refines discretion standards within the fine ranges of *Air Pollution Prevention and Control Law* Art. 99 → lawful refinement; no conflict ✅

**Determination:** ✅ VALID | 🟡 MEDIUM (local regulations require higher-law comparison; lower confidence appropriately)

---

##### Norm 4: City B *Air Pollution Prevention and Control Administration Measures* Art. 30

**Step 1: Identify and Locate**

| Item | Content |
|------|---------|
| Norm title | City B Air Pollution Prevention and Control Administration Measures |
| Enacting body | City B People's Government |
| Norm tier | Local government rule (city divided into districts) |
| Promulgation date | 2016 |
| Cited clause | Art. 30 (municipal penalty rules) |

**Step 2: Temporal validity** → Issued 2016; more than 8 years ago. Confirm:
- Subsequent amendments? → Assume none found
- Higher-tier law (*Air Pollution Prevention and Control Law*) amended in 2018 → check consistency with amended higher-tier law

⚠️ **Triggers mandatory re-verification rule**: earlier promulgation and higher-tier law has been amended

**Step 3: Hierarchy validity** → City B is a city divided into districts; its government may enact local government rules on ecological environmental protection (*Legislation Law* Art. 82). Authority correct ✅

**Step 4: Conflict check** →
- Consistency with *Air Pollution Prevention and Control Law* (2018 amendment): compare Art. 30 clause by clause
- Consistency with Province A *Environmental Protection Regulations* (2019 revision): local government rules must not contradict local regulations
- Assume comparison finds: some procedural penalty provisions in City B Measures Art. 30 are inconsistent with the post-2018 *Air Pollution Prevention and Control Law*

**⚠️ Conflict found:**
- Conflict type: lower-tier (local government rule) inconsistent with higher-tier (law)
- Resolution rule: higher law prevails over lower law; apply the *Air Pollution Prevention and Control Law*
- Portions of Measures Art. 30 inconsistent with higher-tier law should not be applied

**Determination:** ⚠️ PARTIAL | 🟡 MEDIUM

---

##### Norm 5: Ministry of Ecology and Environment *Measures for Environmental Administrative Penalties* Art. 11

**Step 1: Identify and Locate**

| Item | Content |
|------|---------|
| Norm title | Measures for Environmental Administrative Penalties |
| Enacting body | Former Ministry of Environmental Protection (now Ministry of Ecology and Environment) |
| Norm tier | Departmental rule |
| Promulgation date | 2010 |
| Cited clause | Art. 11 |

**Step 2: Temporal validity** →
- Issued 2010; more than 14 years ago
- **⚠️ Triggers mandatory re-verification rule**: promulgated more than 10 years ago
- Upon query: replaced by the new *Measures for Ecological and Environmental Administrative Penalties* (MEE Order No. 30, effective 1 July 2023)

**Conclusion: ❌ REPEALED — replaced by the new Measures**

**Alternative:** Cite the corresponding clause of the *Measures for Ecological and Environmental Administrative Penalties* (2023 version).

**Determination:** ❌ REPEALED | 🟢 HIGH

---

#### Batch Check Summary

```
## Legal Norm Validity Batch Check Summary

| No. | Norm title | Cited clause | Temporal | Hierarchy | Conflict | Final determination | Confidence | Advice |
|-----|------------|--------------|----------|-----------|----------|---------------------|------------|--------|
| 1 | Environmental Protection Law (2014) | Art. 59 | ✅ Valid | ✅ Law | ✅ No conflict | ✅ Currently valid | 🟢 HIGH | May cite directly |
| 2 | Air Pollution Prevention and Control Law (2018) | Art. 99 | ✅ Valid | ✅ Law | ✅ No conflict (special law) | ✅ Currently valid | 🟢 HIGH | May cite directly; prevails over general law |
| 3 | Province A Environmental Protection Regulations (2019) | Art. 45 | ✅ Valid | ✅ Local regulation | ✅ Within higher-law range | ✅ Currently valid | 🟡 MEDIUM | May cite; compared with higher law |
| 4 | City B Air Pollution Prevention and Control Administration Measures (2016) | Art. 30 | ⚠️ Re-verify | ✅ Local government rule | ⚠️ Partial inconsistency with higher law | ⚠️ Partially invalid | 🟡 MEDIUM | Portions inconsistent with higher law must not be cited |
| 5 | Measures for Environmental Administrative Penalties (2010) | Art. 11 | ❌ Repealed | — | — | ❌ Repealed | 🟢 HIGH | Must not cite; replace with 2023 version |

### Issues Requiring Special Attention

1. **Norm 5 repealed:** Former Measures for Environmental Administrative Penalties (2010) have been replaced by
   Measures for Ecological and Environmental Administrative Penalties (2023); citation must be updated.

2. **Norm 4 partially invalid:** Portions of City B Measures Art. 30 on penalty procedure are inconsistent
   with the post-2018 Air Pollution Prevention and Control Law and should not be applied.
   Recommend applying the higher-tier law directly.

3. **Special vs. general law:** On air-pollution penalties, Air Pollution Prevention and Control Law (Norm 2)
   as special law prevails over Environmental Protection Law (Norm 1). Both may be cited when consistent;
   when they conflict, Air Pollution Prevention and Control Law controls.

4. **Hierarchy of application:**
   Law (Norms 1, 2) > local regulation (Norm 3) > local government rule (Norm 4)
   When determining fine amounts, use statutory ranges as the standard; local refined standards as reference.

5. **Recommended supplementary retrieval:** Retrieve the clause in Measures for Ecological and Environmental
   Administrative Penalties (2023) corresponding to former Art. 11, to complete the legal basis on penalty procedure.
```

---

## Appendix: Quick Reference of Commonly Cited Repealed Laws (High-Frequency)

| Repealed law | Repeal date | Repeal basis | Replacement |
|--------------|-------------|--------------|-------------|
| *General Principles of the Civil Law* | 2021-01-01 | *Civil Code* Art. 1260 | *Civil Code* General Provisions Book |
| *General Provisions of the Civil Law* | 2021-01-01 | *Civil Code* Art. 1260 | *Civil Code* General Provisions Book |
| *Contract Law* | 2021-01-01 | *Civil Code* Art. 1260 | *Civil Code* Contract Book |
| *Property Law* | 2021-01-01 | *Civil Code* Art. 1260 | *Civil Code* Property Rights Book |
| *Guarantee Law* | 2021-01-01 | *Civil Code* Art. 1260 | *Civil Code* Contract Book (guarantee parts) |
| *Marriage Law* | 2021-01-01 | *Civil Code* Art. 1260 | *Civil Code* Marriage and Family Book |
| *Succession Law* | 2021-01-01 | *Civil Code* Art. 1260 | *Civil Code* Succession Book |
| *Adoption Law* | 2021-01-01 | *Civil Code* Art. 1260 | *Civil Code* Marriage and Family Book |
| *Tort Liability Law* | 2021-01-01 | *Civil Code* Art. 1260 | *Civil Code* Tort Liability Book |
| *Sino-Foreign Equity Joint Venture Law* | 2020-01-01 | *Foreign Investment Law* Art. 42 | *Foreign Investment Law* |
| *Sino-Foreign Contractual Joint Venture Law* | 2020-01-01 | *Foreign Investment Law* Art. 42 | *Foreign Investment Law* |
| *Wholly Foreign-Owned Enterprise Law* | 2020-01-01 | *Foreign Investment Law* Art. 42 | *Foreign Investment Law* |

> **Note:** This table lists only high-frequency repealed laws and is not a complete inventory. In practice, the agent must always verify the latest validity status of legal norms through authoritative databases.
