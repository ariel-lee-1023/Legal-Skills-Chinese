---
name: trial-scheduling-and-deadline-monitoring
description: |
  Use this skill when the user needs to track or be reminded of hearing schedules, enforcement schedules, evidence-submission deadlines, appeal deadlines, service deadlines, preservation renewal, and other statutory procedural time limits.
  Typical triggers include but are not limited to:
  - Mentions of keywords such as “上诉期限” (appeal period), “证据提交期限” (evidence-submission deadline), “送达期限” (service deadline), “保全期限” (preservation period)
  - Adding, modifying, or inquiring about case deadlines
---

> **Chinese source (authoritative):** [`../../skills/trial-scheduling-and-deadline-monitoring/SKILL.md`](../../skills/trial-scheduling-and-deadline-monitoring/SKILL.md)

# Trial Scheduling and Procedural Deadline Monitoring

> Track court schedules, evidence-submission deadlines, appeal deadlines, and service deadlines to avoid procedural risk.

## Trigger Conditions

Including but not limited to:

- Mentions of “上诉期限” (appeal period), “证据提交期限” (evidence-submission deadline), “送达期限” (service deadline), “保全期限” (preservation period), and similar keywords
- Adding, modifying, or inquiring about case deadlines

If the user asks for a __procedural deadline monitoring schedule, evidence-submission deadline schedule, service deadline schedule, appeal deadline schedule, or preservation deadline schedule__, also use this skill.

## Exclusion Situations

__Do not use__ this skill for:

- Adding, modifying, or managing a schedule of case-related times and places
- Managing or inquiring about working hours of lawyers, paralegals, or interns
- General programming tasks unrelated to case deadlines and scheduling

# Skill Title

Track court schedules, evidence-submission deadlines, appeal deadlines, service deadlines, preservation periods, and other statutory time limits to avoid procedural risk

## Capabilities

- When the user adds, deletes, or modifies statutory starting points such as case-filing time, summons service time, judgment service time, or preservation time, calculate determinable statutory deadline nodes under the Civil Procedure Law (民事诉讼法) and related judicial interpretations
- For each case, when the user has not fully entered all statutory starting points, proactively ask whether relevant information is missing
- Remind judges, prosecutors, arbitrators, lawyers, and others of a case’s litigation deadlines 5 days and 3 days before each statutory deadline
- When the user asks about a case’s deadlines, provide that case’s deadline schedule
- When the user asks about a type of deadline (e.g., evidence-submission deadline), provide a schedule for that deadline type, including all cases requiring evidence submission and the corresponding deadlines
- When the user asks about upcoming deadlines, provide a legal-deadline schedule through 30 days later, including all deadline dates in that window, corresponding cases, and corresponding work items

## How to Use

When adding or modifying a case that needs deadline monitoring:

1. Create a new case name, or select an existing case by name
2. Enter known starting points, such as time of filing materials delivered to court, case-filing time, judgment service time, hearing time, preservation time, etc.
3. Under the Civil Procedure Law and related judicial interpretations, calculate determinable statutory deadline nodes
4. Show calculated results to the user and ask whether any dates need adjustment
5. Output the user-confirmed procedural monitoring deadline schedule

When the user needs a schedule for a particular legal deadline type:

1. Retrieve all cases involving that legal deadline
2. Using today’s date as the node, include only cases whose statutory deadline falls after today
3. Check whether any case lacks a starting date for that legal deadline and needs user supplementation
4. Output cases filtered in steps 2 and 3 together in that legal-deadline schedule

When the user needs an upcoming legal-deadline schedule:

1. Ask the user for the screening window
2. If the user provides a clear period (e.g., 15 days) or date (e.g., March 2), using today as the node, screen the legal-deadline schedule through that period or date
3. If the user does not provide a clear period, using today as the node, screen the legal-deadline schedule through 30 days later

When reminding the user that a statutory deadline for a case is approaching:

1. Identify which case the user is currently discussing and retrieve that case’s procedural monitoring deadline schedule
2. Check whether the current date has reached 5 days or 3 days before the statutory deadline
3. Output a reminder in the form: “Note: Case XX will reach the XX deadline in 5 days (YYYY-MM-DD).”

## Input Format

__Required__

- Case name
- Type of statutory deadline
- Starting date of the statutory deadline

__Optional__

- Length of the statutory deadline
- Special deadline rules (e.g., judge or arbitrator extending the evidence-submission period)

## Output Format

1. Procedural monitoring deadline schedule

__Case name__

__Case of Company Jia v. Company Yi Tort Dispute__

Case-filing date

YYYY-MM-DD

Summons service date

YYYY-MM-DD

Evidence-submission deadline

YYYY-MM-DD

Hearing date

YYYY-MM-DD

Supplementary-materials submission deadline

YYYY-MM-DD

Preservation date

YYYY-MM-DD

Preservation-renewal deadline

YYYY-MM-DD

Judgment service date

YYYY-MM-DD

Appeal deadline

YYYY-MM-DD

……

……

1. Schedule for a particular legal deadline type (evidence-submission deadline as example)

__Evidence-Submission Deadline Schedule__

__Current date: YYYY-MM-DD__

Time

Case name

YYYY-MM-DD

Bank Yi v. Jia private lending dispute — first-instance evidence

YYYY-MM-DD

Company Ding claim dispute — second-instance evidence

YYYY-MM-DD

……

1. Upcoming deadline schedule

__Upcoming Deadline Schedule__

__Current date: YYYY-MM-DD__

__Cutoff date: YYYY-MM-DD__

Time

Case name

YYYY-MM-DD

Bank Yi v. Jia private lending dispute — first-instance evidence-submission deadline

YYYY-MM-DD

Company Ding claim dispute — preservation-renewal deadline

YYYY-MM-DD

……

1. Reminder message

xxxx (preceding text)

Note: Case XX will reach the XX deadline in X days (YYYY-MM-DD).

## Example Usage

__Scenario: Add a statutory starting date for a case__

User input: “For that Company Jia claim dispute, we received the first-instance judgment on March 2.”

SKILL process:

1. Match case name: Company Jia v. Company Yi bond/claim dispute case
2. Identify task: Add a statutory deadline end date for an existing case
3. Retrieve the Civil Procedure Law and related judicial interpretations; locate Article 171 of the Civil Procedure Law
4. Ask the user to confirm whether “the appeal period in this case expires on March 17” is correct
5. After user confirmation, add the deadline to the case’s procedural monitoring schedule and show the updated schedule

## Scripts (if applicable)

- script1.py: Description
- script2.py: Description

## Best Practices

1. If the user mentions multiple case names and deadline dates at once, first confirm the association between case names and dates, then sort case by case
2. If multiple related provisions are retrieved and the statutory deadline cannot be confirmed, ask the user for supplementary information (e.g., ordinary first-instance procedure, summary procedure, or small-claims procedure)
3. When the user adds a non-statutory deadline, confirm with the user twice before writing it into the schedule
4. When the user creates a case, proactively ask whether additional reminders should be set earlier than 5 days before the statutory deadline (e.g., 10 or 15 days)

## Limitations

1. This skill does not organize case-related places
2. This skill does not assign work tasks
3. This skill does not manage work expenses
