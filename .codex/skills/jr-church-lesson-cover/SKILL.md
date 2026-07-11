---
name: jr-church-lesson-cover
description: Use when creating, regenerating, or refining a 16:9 Junior Church lesson cover image in this repo, especially when the cover must match an existing series style, include the transparent series logo, and depict the specific Bible lesson without changing lesson assets.
---

# Jr Church Lesson Cover

## Overview

Create a 16:9 lesson-level cover image for a Junior Church lesson. The cover should match the series image style, include the approved transparent series logo, and depict the lesson's specific Bible focus clearly enough to distinguish it from the series cover and other lesson covers.

## Required Reading

Before generating, editing, compositing, moving, or validating any image asset:

1. Load and follow the `imagegen` skill. Use its built-in image generation path, its project-bound save-path rules, and its guidance for using local images as references or overlay assets.
2. Read `.codex/skills/shared/jr-church-image-standards.md` and follow its tool policy, canvas conventions, asset-preservation rules, generation-economy rules, and shared verification.

Hard rule from the tool policy: all artwork and all lettering (lesson title, scripture reference) is rendered by imagegen. Scripts are only for mechanical operations such as compositing the unmodified `series-logo.png` file or checking dimensions — never for drawing text or content.

## Inputs

Required:
- Lesson folder path or enough information to identify the series and lesson.

Helpful but optional:
- Lesson title, Bible passage, main point, preferred scene, mood words, and exact subtitle text.
- Existing `lesson-outline.md`, `series-logo.png`, `series-image-style.md`, series `cover-graphic.png`, or prior lesson covers.
- Desired output filename. Default to `Series/<Series Name>/<Lesson Folder>/cover-graphic.png`.

If the lesson folder cannot be identified, ask for it. If the lesson outline is missing, use the user's brief and nearby lesson assets instead of inventing theological details.

## Repo Workflow

1. Inspect the target lesson folder. Read `lesson-outline.md` when present to extract the lesson title, main passage, main point, and key visual moment.
2. Inspect the parent series folder. Read `series-image-style.md`, locate `series-logo.png`, and view the series `cover-graphic.png` when present.
3. View nearby lesson `cover-graphic.png` files to match style while keeping this cover visually distinct.
4. Generate or composite a 16:9 PNG lesson cover by following the `imagegen` skill.
5. Save the final image at the lesson folder's `cover-graphic.png` unless the user gave another path.

## Lesson Cover Requirements

Canvas, file paths, and asset preservation follow the shared standards. In addition:

- Logo: include the transparent `series-logo.png` visibly, usually smaller than on the series cover. Preserve the approved series identity, but it is acceptable to add lesson-specific title or scripture-reference elements to the logo area when the logo is designed to support those additions naturally.
- Lesson focus: depict one clear lesson-specific scene, symbol, setting, or character group tied to the passage and main point.
- Composition: make the lesson scene the first read and the series logo the brand anchor. Leave safe space for projection cropping and future slide use.
- Style: match `series-image-style.md` when present, including palette, rendering style, lighting, motifs, and texture treatment.
- Text: avoid extra small text. The lesson title and scripture reference, when included, must be rendered by imagegen — generated as part of the cover art or added with an imagegen edit pass — in the series lettering style. Integrate them with the logo system when the logo design supports it; otherwise place them elsewhere in a graphically pleasing, cohesive way. Never draw title or reference text with a script or system font, regardless of time pressure; if there is not enough time for imagegen, tell the user and let them choose between waiting or shipping without the text. Inspect all generated lettering and fix misspellings with a targeted regeneration or imagegen edit.
- Theology and tone: keep imagery child-appropriate and faithful to the passage. Avoid adding unsupported miraculous effects, anachronisms, violence, gore, or mocking characterizations.

## Prompt Pattern

Build the image prompt from this structure:

```text
Create a 16:9 Junior Church lesson cover image for "[LESSON TITLE]" in the series "[SERIES TITLE]".
Bible focus: [passage and main point].
Use this established series art direction: [style lock summary].
Scene: [one lesson-specific moment, symbol, or setting].
Composition: strong lesson focal scene, approved transparent series logo placed as a clean overlay area, optional lesson title and scripture reference integrated with the logo if natural or placed elsewhere if not, colorful depth, classroom readability.
Avoid: misspelled words, extra text, clutter, scary imagery, unsupported Bible details, dark mood, photorealistic adults.
```

After generation, composite the approved `series-logo.png` file as an overlay if the tool did not preserve it cleanly — this exact-file placement is the one operation a script may do. Lesson title or scripture reference additions are content, not overlays: produce them with imagegen, integrated with the artwork and subordinate to the series identity. If the generated image includes a distorted, misspelled, or alternate logo, regenerate or edit it out with imagegen before placing the approved logo.

## Style Notes

If the lesson cover clarifies a recurring series pattern, append a short note to `series-image-style.md` rather than rewriting the whole file. Useful notes include:

```markdown
- **Lesson cover pattern:** [logo placement, recurring framing, title treatment, or motif use]
- **Lesson-specific variation:** [how individual lessons should differ while staying cohesive]
```

## Verification

Run the shared verification from `jr-church-image-standards.md`, plus:

- If lesson title or scripture reference text is present, confirm it is readable, correctly spelled, rendered in the series lettering style by imagegen (not a script or system font), and either naturally integrated with the logo or placed elsewhere cohesively.
- Confirm the scene reflects the lesson outline or user brief without unsupported details.
