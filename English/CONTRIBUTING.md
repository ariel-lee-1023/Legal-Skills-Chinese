# Contributing (English)

Thank you for contributing to **Legal-Skills-Chinese**.

## Source of truth

New skills and edits belong in the **Chinese** tree:

- Skills: [`../skills/`](../skills/)
- Contributing (authoritative Chinese): [`../CONTRIBUTING.md`](../CONTRIBUTING.md)

This English page is a parallel summary for international readers. Follow the Chinese guide when submitting.

## How to submit

### Path A · Form (recommended, no Git)

Open the issue form from the Chinese contributing guide:
👉 [Submit a new Skill](https://github.com/THUYRan/Legal-Skills-Chinese/issues/new?template=submit-skill.yml)

### Path B · Pull Request

1. Fork the repository.
2. Under `skills/`, create a directory named with the skill **slug** (lowercase, hyphenated).
3. Add `SKILL.md` with YAML frontmatter (`name`, `description`).
4. Open a PR describing the problem and use case.

## `SKILL.md` requirements

```yaml
---
name: skill-slug          # must match directory name
description: |            # triggers, scenarios, boundaries
  ...
---
```

Include clear **trigger conditions · applicable scenarios · capability boundaries**. Compound skills must list which atomic skills they call and in what order.

## Review criteria

1. **Safety** — no malicious or unsafe content.
2. **Legal quality** — fit for PRC statutory reasoning and practice norms.
3. **Practical value** — useful in real workflows.

Full detail: [`../CONTRIBUTING.md`](../CONTRIBUTING.md).
