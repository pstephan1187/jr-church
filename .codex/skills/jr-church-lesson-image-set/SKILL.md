---
name: jr-church-lesson-image-set
description: Use when creating, regenerating, or refining a cohesive set of 16:9 Junior Church lesson images in this repo, especially when multiple Bible-story scenes must match the same series style, lesson cover, character designs, and kid-friendly visual tone.
---

# Jr Church Lesson Image Set

## Overview

Create a sequence of 16:9 lesson images that support teaching a Junior Church Bible lesson. The images should feel like they belong to the same lesson, match the parent series style, and provide distinct visual beats for the teacher to use during the lesson.

## Required Supporting Skill

Before generating, editing, moving, or validating any image asset, load and follow the `imagegen` skill. Use its built-in image generation path by default, its project-bound save-path rules, and its repeated-generation workflow when creating multiple images in one set.

## Inputs

Required:
- Lesson folder path or enough information to identify the series and lesson.

Helpful but optional:
- Desired image count. If omitted, create one image for the introduction when present and one image for each main lesson point.
- Lesson outline, Bible passage, main point, key scenes, character descriptions, and any scene to avoid.
- Existing `series-image-style.md`, lesson `cover-graphic.png`, nearby `image-*.png`, or exact output naming rules.

If the lesson folder cannot be identified, ask for it. If image count is not provided, derive the count from the lesson outline instead of using a fixed number.

## Repo Workflow

1. Inspect the target lesson folder. Read `lesson-outline.md` when present to extract the introduction, passage, outline points, main point, and teaching sequence.
2. Inspect the parent series folder. Read `series-image-style.md` and view the series and lesson `cover-graphic.png` files when present.
3. View existing `image-*.png` files only if regenerating, extending, or matching an existing set.
4. Plan the image sequence before generating. Save or update a concise `lesson-image-plan.md` in the lesson folder when creating a new set.
5. Generate 16:9 PNG images by following the `imagegen` skill.
6. Save outputs as `image-1.png`, `image-2.png`, and so on unless the user gives different filenames.

Preserve existing PDFs, HTML, coloring pages, take-home files, covers, and non-target lesson images unless the user explicitly asks to replace them.

## Image Set Requirements

- Canvas: every lesson image should be 16:9 PNG. Prefer 1672 x 941 when matching existing generated assets.
- Cohesion: keep the same art style, palette, lighting, character designs, clothing, setting logic, and rendering quality across the whole set.
- Count: create one image for each lesson point, plus the introduction when the outline includes one. Do not lock the set to six images unless the user asks for exactly six.
- Story flow: images should be easy to follow and almost tell the story themselves when viewed in order.
- Point context: draw each image from the context, Bible passage, main point, and purpose of that lesson point, not merely from the point heading or text itself.
- Distinction: each image should show a different teaching beat, not repeated variations of the same poster.
- Continuity: keep the sequence mostly contiguous with the story. Some images may diverge symbolically or compositionally when that helps communicate a particular lesson point, but the set should still feel connected.
- No logo requirement: ordinary lesson scene images usually do not need the series logo unless the user asks for branded slides.
- Text: avoid embedded text unless the user explicitly requests it. Lesson images should work as visuals behind spoken teaching.
- Faithfulness: base scenes on the passage and lesson outline. Do not add unsupported miracles, violence, romance, modern props, or comic exaggeration that changes the meaning.
- Kid-facing tone: colorful, engaging, clear, and emotionally appropriate. Avoid gore, horror, sensualized characters, or humiliating depictions.

## Storyboard Plan

Before generating, create a short plan with this structure:

```markdown
# [Lesson Title] Image Plan

- **Series:** [Series Name]
- **Lesson:** [Lesson Title]
- **Passage:** [Bible passage]
- **Style source:** `series-image-style.md` and/or existing covers

1. `image-1.png` - [introduction or first lesson point, story beat, purpose, key characters]
2. `image-2.png` - [next lesson point, story beat, purpose, key characters]
3. `image-3.png` - [next lesson point, story beat, purpose, key characters]
4. `image-4.png` - [continue for each remaining lesson point]
```

Keep the plan short enough to be useful during generation. Match the numbered list to the lesson structure, adding or removing rows as needed.

## Prompt Pattern

Generate each image from the same style anchor plus a specific scene:

```text
Create image [N] of [COUNT] for a Junior Church lesson image set.
Series: [SERIES TITLE]. Lesson: [LESSON TITLE]. Bible focus: [PASSAGE AND MAIN POINT].
Use this exact shared art direction: [style lock plus character continuity notes].
Scene for this image: [specific beat from lesson-image-plan.md].
Continuity: [same characters, clothing, setting logic, story order, palette, lighting].
Teaching purpose: [how this scene helps communicate the lesson point in context, not just the heading text].
Composition: 16:9 classroom teaching visual, clear focal action, no text, colorful depth, child-friendly expression.
Avoid: extra text, inconsistent faces or costumes, unsupported Bible details, scary imagery, gore, dark mood, photorealistic adults.
```

After each generation, inspect the image before moving to the next. If a character, style, setting, or Bible detail drifts, tighten the continuity note and regenerate that image before continuing.

## Verification

Before reporting completion:
- Confirm all expected `image-*.png` files exist in the lesson folder.
- Check every generated image is PNG and 16:9 or very close to it.
- View the set together enough to confirm style, characters, setting, and story flow are coherent.
- Confirm the image count matches the lesson structure: introduction when present plus each lesson point, unless the user requested a different count.
- Confirm each image matches its `lesson-image-plan.md` scene and the lesson outline or user brief.
- Confirm each image reflects the context and teaching purpose of its point, not just the point text.
- Confirm no non-target lesson assets were renamed or edited unless the user requested it.
