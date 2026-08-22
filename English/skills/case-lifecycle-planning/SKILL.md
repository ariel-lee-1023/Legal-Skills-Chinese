---
name: case-lifecycle-planning
description: |
  Case full-lifecycle planning skill. Triggered when the user needs to plan a case preparation timeline, create or inquire about case preparation milestones, or generate a case litigation roadmap and key-date overview. Typical trigger keywords: "case preparation", "case preparation planning", "case preparation timeline", "plan case preparation pace", "schedule hearing". Does not handle assignment of cases to lawyers, nor general programming tasks unrelated to case management.
---

> **Chinese source (authoritative):** [`../../skills/case-lifecycle-planning/SKILL.md`](../../skills/case-lifecycle-planning/SKILL.md)

## Case Full-Lifecycle Planning

### Overview Table

| Item | Content |
|------|------|
| **Capability name** | Case full-lifecycle planning |
| **Trigger conditions** | User needs to plan a case preparation timeline; create or inquire about case preparation milestones; generate a case litigation roadmap and key-date overview |
| **Typical trigger scenarios** | Mentions keywords such as "case preparation", "case preparation planning", "case preparation timeline", "plan case preparation pace", "schedule hearing" |
| **Exclusions** | Does not handle assigning cases to lawyers; does not handle general programming tasks unrelated to case management |

### Legal Disclaimer

> **Important notice:** The case full-lifecycle planning provided by this skill is an assistive service and does not constitute formal legal advice. Final case management should be reviewed and confirmed by a qualified legal professional.

### I. Core Concepts

#### Trigger Conditions

- User mentions keywords such as "case preparation", "case preparation planning", "case preparation timeline", "plan case preparation pace", "schedule hearing"
- Need to generate a case preparation schedule or case litigation roadmap, including filing date, pretrial conference time and place, hearing time and place, enforcement time, etc.
- Add, inquire about, modify, or delete a case’s preparation progress, hearing time, pretrial conference time, case status, etc.
- Inquire how many cases in a given month are in preparation, how many have hearings, how many are in enforcement, etc.

#### Exclusions

- Does not handle assignment of cases to lawyers, paralegals, or interns
- Does not handle general programming tasks unrelated to case management

### Workflow

1. Name the case, including the names of both parties and the cause of action
2. Upload summons, arbitration notices, or other documents; specify focus points, or directly state the hearing time and place or the pretrial conference time and place
3. When supplementing key dates for a case, state the full case name
4. Wait for generation of this case’s litigation roadmap, this month’s litigation roadmap, this case’s key-date overview, and this month’s key-date overview

### Example Usage

**Scenario: Add a case hearing date**

User input: “Company Jia v. Company Yi tort dispute, hearing on March 12”

**Processing flow:**

1. Identify the case name as Company Jia v. Company Yi tort dispute
2. Identify the time category as hearing time
3. Add to the key-date overview for Company Jia v. Company Yi tort dispute
4. Add to the March key-date overview for all cases
5. Ask the user whether to supplement the hearing location and other time/place information
6. Display this case’s litigation roadmap, this case’s key-date overview, the updated litigation roadmap for all cases (classified by cases in progress that month and by city), and the updated key-date overview for all cases (ordered by dates in the current month)

### Best Practices

1. Upload multiple files or archives in batches
2. If the case name is incomplete, ask about all possibilities and have the user select the correct case
3. If time or place is incomplete, prompt the user to supplement information, or upload a summons for recognition

### Limitations

1. Does not handle the legal analysis portion of a case
2. Does not handle timed reminders for case key dates

The above is the detailed content of the case full-lifecycle planning skill.
