---
name: legal-risk-assessment
description: |
  Assess an enterprise’s regulatory penalty risk across four dimensions: licensing/qualifications, compliance with regulatory rules, and historical penalty/credit records.
---

> **Chinese source (authoritative):** [`../../skills/legal-risk-assessment/SKILL.md`](../../skills/legal-risk-assessment/SKILL.md)

# Identifying External Regulatory Risk

## Capabilities
**List what this skill can do:**
**1. Licensing and qualification review:** Review whether the enterprise holds the various administrative licenses, filings, and certification qualifications required for its operations, and their compliance status.
**2. Regulatory compliance review:** Review whether the enterprise meets mandatory requirements of industry regulatory rules in each business area.
**3. Historical penalty and credit risk assessment:** Screen historical administrative penalty records and credit status, and assess the real impact of dishonest-conduct sanctions on the enterprise’s operations.

## How to Use
**Step-by-step instructions:**
**1. Licensing and qualification review**
Step1: Obtain the enterprise’s business-scope description and list of business activities.
Step2: Based on business type, determine against laws and regulations the full list of licenses/qualifications that should be held.
Step3: Check one by one the actual holding status, validity period, and annual inspection/renewal status of each license.
Step4: Check for operating beyond licensed scope, expired licenses not renewed, inconsistency between actual operations and approved content, and similar situations.
Step5: Output a list of licensing/qualification compliance gaps and remediation recommendations.

**2. Regulatory compliance review**
Step1: Identify the main business areas involved in the enterprise’s operations (e.g., work safety, environmental protection, product quality, tax, labor and employment).
Step2: For each business area, compile the applicable core regulatory rules and a list of mandatory requirements.
Step3: Through interviews, document review, on-site inspection, and similar methods, check item by item the gap between the enterprise’s actual practice and regulatory requirements. (Organize interview, review, and inspection findings into documents so the model can read and use them.)
Step4: Flag non-compliant items and assess the types and ranges of administrative penalties that may be faced.
Step5: Output a list of regulatory compliance gaps and remediation recommendations.

**3. Historical penalty and credit risk assessment**
Step1: Look up the National Enterprise Credit Information Publicity System website and query the enterprise’s administrative penalty records. (Practical issue: the model may be unable to log in and access pages automatically; the credit system may require account credentials, so the user must provide login information.)
Step2: Check whether the enterprise has been listed on the abnormal business operations directory, the list of seriously dishonest entities, the list of judgment debtors subject to enforcement for dishonesty, etc.
Step3: Assess the actual impact of existing penalty records on business qualifications, bidding, financing and credit, policy applications, and similar matters.
Step4: For remediable dishonest records, assess remediation conditions and propose remediation recommendations.
Step5: Output a list of historical penalty and credit risks and response recommendations.

> Credit remediation conditions for enterprises under the *Measures for the Administration of Credit Remediation in Market Regulation*:
Article 5. A party listed on the abnormal business operations directory or marked as in an abnormal business status may apply for credit remediation under these Measures if any of the following applies:
(1) The annual reports for the years not filed have been made up and publicized;
(2) Immediate information publicity obligations have already been performed;
(3) Publicized information that concealed the truth or involved falsification has already been corrected;
(4) A change of domicile or business premises has been registered in accordance with law, or the party proposes that contact can again be made through the registered domicile or business premises.
Article 6. Except for administrative penalties under Paragraph 3 of Article 14 of the *Provisions on the Publicity of Market Regulation Administrative Penalty Information*, or where only a warning, circulating a notice of criticism, or a relatively low fine was imposed, where other administrative penalty information has been publicized for six months—or for one year for administrative penalties in the food, drug, or special equipment fields—and the party meets all of the following, it may apply for credit remediation:
(1) Obligations stipulated in the administrative penalty decision have already been consciously performed;
(2) Harmful consequences and adverse effects have already been actively eliminated;
(3) The party has not again received an administrative penalty from the market regulation authority for the same type of violation;
(4) The party is not on the abnormal business operations directory or the list of serious illegal and dishonest entities.
Article 7. Where a party has been listed on the list of serious illegal and dishonest entities for one full year and meets all of the following, it may apply for credit remediation under these Measures:
(1) Obligations stipulated in the administrative penalty decision have already been consciously performed;
(2) Harmful consequences and adverse effects have already been actively eliminated;
(3) The party has not again received a relatively severe administrative penalty from the market regulation authority.
Where the period for implementing corresponding management measures under laws or administrative regulations has not yet expired, early removal may not be applied for.

## Input Format
Describe expected input:
**1. Licensing and qualification review**
 - Description of the enterprise’s business scope and list of business activities;
 - List of existing licenses, filing certificates, and certification certificates (including numbers, validity periods, and issuing authorities).

**2. Regulatory compliance review**

 - Description of the enterprise’s main business areas and current compliance management system documents for each area (upload the compliance management files built internally by the enterprise);
 - Records of inspections by regulatory authorities over the past three years (if any; the enterprise should also consider whether documents involve confidential information).

**3. Historical penalty and credit risk assessment**
     Full enterprise name and Unified Social Credit Code

## Output Format
**Describe what will be produced:**
**1.	Licensing and qualification review**
  Required qualification: XX
  Actual status: XX
  Issue description: XX
Legal basis: XX
  Remediation recommendation: XX
 ……
Required qualification: XX
  Actual status: XX
  Issue description: XX
  Legal basis: XX
  Remediation recommendation: XX
  
**2.	Regulatory compliance review**
Business area:
Non-compliant item:
Legal basis:
Possible penalty:
Remediation recommendation:
  ……
Business area:
Non-compliant item:
Legal basis:
Possible penalty:
Remediation recommendation:

**3.	Historical penalty and credit risk assessment output**
   Penalty/dishonesty record:
  Issuing authority:
   Penalty date:
   Remediable:
   Remediation/response recommendation:
……
   Penalty/dishonesty record:
   Issuing authority:
   Penalty date:
   Remediable:
   Remediation/response recommendation:

## Example Usage
Provide concrete examples:
**1.	Licensing and qualification review**
**Input:**
Enterprise business: Cross-border e-commerce retail import (“global shopping” business).
Existing qualifications: Business license (including import/export business scope); Customs consignee/consignor of import/export goods filing receipt.

**Output:**
Required qualification: Customs consignee/consignor of import/export goods filing
Actual status: Held
Issue description: No anomaly
Legal basis: Article 11 of the *Customs Law*
Remediation recommendation: None

Required qualification: Cross-border e-commerce enterprise qualification (Customs)
Actual status: Not held
Issue description: Conducting cross-border e-commerce retail import business without completing cross-border e-commerce enterprise filing with Customs
Legal basis: Article 2 of the *Notice on Improving Supervision of Cross-Border E-Commerce Retail Imports*
Remediation recommendation: Apply to the competent Customs for cross-border e-commerce enterprise qualification filing

Required qualification: ICP commercial license (if a self-operated platform is involved)
Actual status: Not verified
Issue description: ICP license information not provided; if a self-built website provides information services to domestic users and involves commercial activities, an ICP commercial license is required
Legal basis: Articles 3 and 7 of the *Measures for the Administration of Internet Information Services*
Remediation recommendation: Verify the website operating model; if a license is required, apply promptly to the communications administration authority

**2.	Regulatory compliance review
Input:**
Enterprise type: Manufacturing enterprise with a spraying workshop, using about 50 tons of solvent-based paint per year.
Compliance system: Work safety management system established, but no dedicated volatile organic compounds (VOCs) management ledger.
Inspection records: In 2025, ordered once by the ecology and environment authority to rectify due to excess unorganized VOCs emissions.

**Output:**
Business area: Environmental protection
Non-compliant item: No VOCs management ledger established; quantities of raw/auxiliary materials used, wasted, and their destinations not truthfully recorded
Legal basis: Article 46 of the *Atmospheric Pollution Prevention and Control Law*
Possible penalty: Order to correct; fine of RMB 20,000 to 200,000
Remediation recommendation: Establish a VOCs management ledger; designate a person to record daily and periodically consolidate and archive

Business area: Environmental protection
Non-compliant item: Previously ordered to rectify for excess unorganized VOCs emissions; if still non-compliant upon re-inspection, risk of daily continuous penalties
Legal basis: Articles 99 and 123 of the *Atmospheric Pollution Prevention and Control Law*
Possible penalty: Order to correct; fine of RMB 100,000 to 1,000,000; if refusal to correct, daily continuous penalties
Remediation recommendation: Complete upgrade of exhaust gas collection and treatment facilities; engage a third-party testing institution to issue a compliant emission test report

Business area: Environmental protection
Non-compliant item: Previously ordered to rectify for excess unorganized VOCs emissions; if still non-compliant upon re-inspection, risk of daily continuous penalties
Legal basis: Articles 99 and 123 of the *Atmospheric Pollution Prevention and Control Law*
Possible penalty: Order to correct; fine of RMB 100,000 to 1,000,000; if refusal to correct, daily continuous penalties
Remediation recommendation: Complete upgrade of exhaust gas collection and treatment facilities; engage a third-party testing institution to issue a compliant emission test report

**3. Historical penalty and credit risk assessment**
**Input:**
Full enterprise name: XX Trading Co., Ltd.
Unified Social Credit Code: 91440101XXXXXXXXXX

**Output:**
Penalty/dishonesty record: Listed on the abnormal business operations directory for failure to publicize the annual report on time
Issuing authority: Guangzhou Municipal Market Regulation Bureau
Penalty date: 2024-07-15
Remediable: Yes
Remediation/response recommendation: Make up the filing per procedure and seek removal from the abnormal directory

## Limitations
1. Not a final legal opinion; only a preliminary screen of external regulatory risk; does not replace professional counsel’s judgment.
2. Conclusions depend on the completeness and truthfulness of information provided by the user; undisclosed information may lead to missed risks.
3. Regulatory policy is dynamically changing; conclusions may be affected by subsequent new rules and require periodic re-review and prudent use.
