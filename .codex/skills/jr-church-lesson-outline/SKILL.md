---
name: jr-church-lesson-outline
description: Use when creating a Junior Church Bible lesson outline, lesson plan, children's church outline, memory verse options, salvation segue, or kid-focused Bible teaching document in this repo.
---

# Junior Church Lesson Outline

Create a markdown lesson-outline document for a Junior Church lesson. Keep the lesson Bible-centered, concrete for children, and consistent with this repo's `Series/<Series Name>/<Lesson Folder>/` structure.

## Inputs

Required:
- Subject or theme.
- Bible focus: story, lesson, character, doctrine, symbol, type, object lesson, or passage focus.
- Main point the children should learn.

Optional:
- Main scripture passage.
- Series theme.
- Save path, lesson number, target age range, desired length, translation preference, or existing lesson folder.

If a required input is missing, ask only for the missing information. If the user gives enough to proceed, do not ask preference questions.

## Repo Context

- Existing series live in `Series/`.
- Existing lesson folders may contain PDFs, take-home HTML, images, and coloring pages. Do not modify those assets unless the user asks.
- When a series theme is provided, inspect `Series/` and nearby lessons to match the series naming style, lesson tone, and repeated themes.
- If no save path is provided, create `lesson-outline.md` in the best matching lesson folder:
  - Existing lesson folder if the user references one.
  - Otherwise `Series/<Series Theme>/<NN Lesson Title>/lesson-outline.md` when a series theme is provided, using the next two-digit lesson number if the series already uses numbers.
  - Otherwise `Series/_Unassigned/<Lesson Title>/lesson-outline.md`.

## Teaching Guardrails

- Let the main passage control the lesson. Do not force symbolism onto details that the passage does not support.
- For symbolism or types, label what is explicit, what is a reasonable connection, and what is only an illustration.
- Avoid moralism. Show that good choices matter, but they do not save anyone; children need Jesus to save them from sin.
- Keep language concrete and teachable for children. Use everyday illustrations, short applications, and clear transitions.
- Default to KJV references and verse wording when quoting, because existing take-home materials use KJV-style wording. Use a different translation only if the user requests it.

## Workflow

1. Parse the user's brief into: subject/theme, Bible focus, main passage, main point, series theme, and save path.
2. Inspect the relevant `Series/` folder when present.
3. Create the output path if needed.
4. Write a complete markdown outline using the required structure below.
5. Check that every outline point includes all required fields before finishing.

## Markdown Structure

Use this structure exactly, adapting headings only when the user requests a different format:

```markdown
# [Working Lesson Title]

## Lesson Brief

- **Series:** [series or "Unassigned"]
- **Subject/Theme:** [theme]
- **Bible Focus:** [story, lesson, symbolism, character, or doctrine]
- **Main Passage:** [reference or "To be selected"]
- **Main Point:** [one clear sentence]

## Possible Lesson Titles

- [title option]
- [title option]
- [title option]

## Memory Verse Options

- **[Reference]** - [short verse text or summary]. [Why it fits.]
- **[Reference]** - [short verse text or summary]. [Why it fits.]
- **[Reference]** - [short verse text or summary]. [Why it fits.]

## Lesson Outline

### 1. [Point Title]

**Summary/Lesson:** [One or two short paragraphs explaining this point from the passage.]

**Main Passage:** [Corresponding verse(s) from the main passage.]

**Supporting Scriptures:** [Possible supporting scriptures elsewhere in the Bible, each with a short reason.]

**Practical Application for Children:** [Concrete child-level application.]

**Illustration:** [Simple illustration, object lesson, or classroom example.]

### 2. [Point Title]

[Repeat the same fields.]

## Segue Into The Plan Of Salvation

[Natural transition from the lesson to sin, our need, Jesus' death and resurrection, and the call to believe on Him. Keep it faithful to the passage without forcing the story details.]

## Main Applications For The Kids

- [application]
- [application]
- [application]

## Teacher Notes

- [Optional pacing, questions, caution about difficult details, or ideas for review.]
```

## Quality Check

Before presenting the result, verify:
- The document was written to a markdown file.
- Each lesson point has a title, summary, supporting scriptures, main-passage verses, child application, and illustration.
- The memory verse options are plausible for children and fit the main point.
- The salvation segue is clear, gospel-centered, and not tacked on.
- The final applications match the stated main point.

## Invocation Examples

```text
/jr-lesson-outline subject="choosing right when pressured" bible_focus="Daniel refusing the king's meat" passage="Daniel 1" main_point="God helps us decide ahead of time to obey Him" series="Good Choices Bad Choices"
```

```text
Create a Junior Church lesson outline about Jesus being the Bread of Life. Use John 6, focus on children learning that only Jesus can satisfy and save, and put it in the Jesus Is series.
```
