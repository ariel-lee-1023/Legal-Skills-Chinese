# AGENTS.md · English tree

This directory is the **English parallel** of the Chinese source tree. It is for readers and reviewers who need English pages.

**Operational rules for agents** (jurisdiction, skill selection, no fabricated authority, retrieval failure, instruction priority) live in the authoritative **[`../AGENTS.md`](../AGENTS.md)**. Follow that file; do not treat this English tree as the source of truth.

---

## Actual resource (source of truth)

Do **not** treat files under `English/` as authoritative for skill behavior or legal content.

| What you need | Go here |
|---------------|---------|
| Skill definitions (`SKILL.md`) | [`../skills/`](../skills/) |
| Chinese landing / project docs | [`../README.md`](../README.md), [`../CONTRIBUTING.md`](../CONTRIBUTING.md), [`../MCP-PKULAW.md`](../MCP-PKULAW.md) |
| Agent rules (usage + coding) | [`../AGENTS.md`](../AGENTS.md) |

## Parallel layout

Every important Chinese page should have a matching path under `English/`, for example:

- `README.md` → `English/README.md`
- `skills/<slug>/SKILL.md` → `English/skills/<slug>/SKILL.md`
- `skills/<slug>/README.md` → `English/skills/<slug>/README.md` (when present)

When updating translations: edit the Chinese source first, then mirror the change here (or regenerate the English page from it).

---

## Skill-use rules (summary · see Chinese `AGENTS.md` for full text)

- **Jurisdiction**: PRC mainland statutory law by default; other jurisdictions only after explicit premise change and user confirmation.
- **Role**: auxiliary drafts for licensed lawyers — not legal advice or final conclusions.
- **Selection**: narrow / single-purpose tasks → **atomic** skills; end-to-end tasks (full judgment drafting, judgment prediction) → **compound** skills.
- **Authority**: **never fabricate** statutes, interpretations, case numbers, holdings, or validity status.
- **If retrieval fails / tools unavailable**: say so; mark unverified cites as `[待检索]` / `[待查]`; do not pass model memory off as current law.
- **Conflict priority** (high → low): safety & non-fabrication → user’s explicit task instructions → [`../AGENTS.md`](../AGENTS.md) → active Chinese `SKILL.md` → other Chinese docs → English mirrors / model priors.
