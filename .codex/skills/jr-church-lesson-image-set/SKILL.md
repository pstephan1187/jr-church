---
name: jr-church-lesson-image-set
description: Create or refine cohesive 16:9 Junior Church lesson images, including one image per inline image tag and insertion at each tag's location. Match the series style, approved lesson cover, and character designs.
---

# Jr Church Lesson Image Set

## Overview

Create 16:9 lesson images from the outline's `<image: ...>` tags and insert each image where its tag appears. Read each description with the surrounding lesson point so the picture serves that teaching moment. Keep the set consistent with the series style and approved characters.

## Required Reading

Before generating, editing, moving, or validating any image asset:

1. Load and follow the `imagegen` skill. Use its built-in image generation path, its project-bound save-path rules, and its repeated-generation workflow when creating multiple images in one set.
2. Read `.codex/skills/shared/jr-church-image-standards.md` and follow its tool policy, canvas conventions, asset-preservation rules, generation-economy rules, and shared verification. Its generation-economy rules matter most here: sets multiply the cost of every wasted generation.

Hard rule from the tool policy: all artwork is rendered by imagegen. Scripts are only for mechanical operations such as checking dimensions or renaming files — never for drawing, patching, recoloring, or adding text.

## Inputs

Required:
- Lesson folder path or enough information to identify the series and lesson.

Helpful but optional:
- Inline `<image: ...>` scene descriptions in the lesson outline. By default, these tags determine both the image count and placement.
- An explicit scene list or image count, when the user requests images without tags.
- Lesson outline, Bible passage, main point, key scenes, character descriptions, and any scene to avoid.
- Existing `series-image-style.md`, lesson `cover-graphic.png`, nearby `image-*.png`, or exact output naming rules.

If the lesson folder cannot be identified, ask for it. Scan the current outline for tags on every invocation. When tags are present, create one image per tag occurrence in document order. A split scene described inside one tag is one image. Do not add an introduction image or images for untagged points unless requested. If there are no tags, follow any explicit scene list or count; otherwise ask which scenes or locations need images before generating.

## Repo Workflow

1. Read the current `lesson-outline.md`. When it is open in Writing Room, use the app's document tools to include unsaved text, and keep the returned revision for edits.
2. Find every `<image: ...>` tag, including multiline descriptions. Record each occurrence's full text, document order, containing point, and nearby teaching context. Give repeated identical tags separate entries.
3. Read the parent `series-image-style.md` and view the approved lesson cover. Use the shared **Character Identity and Historical Fit** rules to retain each person's face, complexion, clothing, and other approved traits. View existing scene images when matching or extending them.
4. Save or update a concise `lesson-image-plan.md` with one row per requested image: source tag or explicit scene request, lesson point, output filename, scene purpose, and any illustration-only details. Preserve an existing plan's unrelated entries. Choose unused `image-N.png` names unless the user authorizes replacing particular files.
5. Generate each 16:9 PNG with imagegen using the tag description and its point's context. Inspect it before generating the next image. A teaching illustration of an unrecorded event or a possible choice must be identified as an illustration in the plan and image alt text.
6. Save each accepted image in the lesson folder before linking it. Keep completed images if a later generation fails; leave the failing image's tag in place and report the unfinished item.
7. Re-read the current outline before editing. Replace each completed tag at its exact location with a relative Markdown image, such as `![Cain plants a seed while Abel cares for a sheep](image-1.png)`. Use the latest revision and narrowly scoped replacements. For identical tags, use surrounding text to target each occurrence separately. If a tag changed during generation, check the new description before replacing it.
8. Preserve all other prose, YAML frontmatter, headings, and existing image links. On later invocations, process remaining tags; regenerate linked images only when requested. Verify the saved images and their placements.

## Image Set Requirements

Canvas, file paths, and asset preservation follow the shared standards. In addition:

- Cohesion: keep the same art style, palette, lighting, character designs, clothing, setting logic, and rendering quality across the whole set.
- Count and placement: each tag occurrence gets one image at that tag's location. Follow an explicit alternative request when given. Untagged lesson sections do not require images by default.
- Story flow: images should be easy to follow and almost tell the story themselves when viewed in order.
- Point context: draw each image from the context, Bible passage, main point, and purpose of that lesson point, not merely from the point heading or text itself.
- Distinction: each image should show a different teaching beat, not repeated variations of the same poster.
- Continuity: keep the sequence mostly contiguous with the story. Some images may diverge symbolically or compositionally when that helps communicate a particular lesson point, but the set should still feel connected.
- No logo requirement: ordinary lesson scene images usually do not need the series logo unless the user asks for branded slides.
- Text: avoid embedded text unless the user explicitly requests it. Lesson images should work as visuals behind spoken teaching. If text is requested, render it with imagegen in the series lettering style — never with a script or system font.
- Faithfulness: base scenes on the passage and lesson outline. Do not add unsupported miracles, violence, romance, modern props, or comic exaggeration that changes the meaning.
- Kid-facing tone: colorful, engaging, clear, and emotionally appropriate. Avoid gore, horror, sensualized characters, or humiliating depictions.

## Storyboard Plan

Keep the plan short. Include the lesson, passage, style source, approved character traits, and a mapping in this form:

| Source tag or request | Lesson point and teaching purpose | File | Status |
| --- | --- | --- | --- |
| Exact tag text, occurrence 1 | Point and scene in context | `image-1.png` | Planned |

Use one row per tag occurrence or explicit scene request. Update status after saving and inserting each image. Preserve the mapping so the work can resume without duplicate generations.

## Prompt Pattern

Generate each image from the same style anchor plus a specific scene:

```text
Create image [N] of [COUNT] for a Junior Church lesson image set.
Series: [SERIES TITLE]. Lesson: [LESSON TITLE]. Bible focus: [PASSAGE AND MAIN POINT].
Use this exact shared art direction: [style lock plus character continuity notes].
Source tag: [exact tag description, or explicit scene request].
Lesson point and context: [surrounding passage and teaching purpose].
Scene for this image: [specific beat from lesson-image-plan.md].
Continuity: [same characters, clothing, setting logic, story order, palette, lighting].
Teaching purpose: [how this scene helps communicate the lesson point in context, not just the heading text].
Composition: 16:9 classroom teaching visual, clear focal action, no text, colorful depth, child-friendly expression.
Avoid: extra text, inconsistent faces or costumes, unsupported Bible details, scary imagery, gore, dark mood, photorealistic adults.
```

After each generation, inspect the image before moving to the next. If a character, style, setting, or Bible detail drifts, tighten the continuity note and regenerate only that image before continuing — never restart the whole set for one drifted image, and follow the shared per-image regeneration budget.

## Verification

Run the shared verification from `jr-church-image-standards.md`, plus:

- Confirm all expected `image-*.png` files exist in the lesson folder.
- View the set together enough to confirm style, characters, setting, and story flow are coherent.
- Confirm every requested tag occurrence has exactly one saved image at its original location, with useful alt text and a working relative path. Check that no fulfilled tag remains and no unrequested images were added. For a request without tags, check the explicit scene list or count.
- Confirm each image matches its `lesson-image-plan.md` scene and the lesson outline or user brief.
- Confirm each image reflects the context and teaching purpose of its point, not just the point text.
- Confirm other lesson text, YAML frontmatter, and existing image links were preserved, allowing for the user's live edits.
