---
name: jr-lesson-outline
description: Use when the user invokes a Junior Church lesson outline slash command or asks for a children's Bible lesson markdown outline in this repo.
---

# Junior Church Lesson Outline Slash Trigger

Use the repo-local canonical workflow at `.codex/skills/jr-church-lesson-outline/SKILL.md`.

Treat `$ARGUMENTS` as the lesson brief. Parse whatever the user provided, ask only for missing required inputs, then generate the markdown lesson-outline document in the repo following the canonical skill.

Expected command shape:

```text
/jr-lesson-outline subject="..." bible_focus="..." passage="..." main_point="..." series="..."
```

Plain-language briefs are also valid:

```text
/jr-lesson-outline Create a lesson about Joseph forgiving his brothers. Main point: God wants us to forgive because He forgave us. Series: Good Choices Bad Choices.
```
