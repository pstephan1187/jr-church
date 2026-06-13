---
name: jr-church-series-background
description: Use when creating, regenerating, or refining a 16:9 Junior Church presentation background image for a lesson series in this repo, especially when slide software needs a less-busy background that matches the series logo, cover, lesson images, and style lock.
---

# Jr Church Series Background

## Overview

Create a 16:9 presentation background for a Junior Church lesson series. The background should match the series art style while staying quiet enough for slide text, Bible verses, memory verses, questions, or teaching notes to remain readable.

## Inputs

Required:
- Series name or target series folder.

Helpful but optional:
- Presentation software constraints, text-safe area, dark or light variant preference, and whether the logo should be included.
- Existing `series-image-style.md`, `series-logo.png`, series `cover-graphic.png`, and lesson image examples.
- Desired output filename. Default to `Series/<Series Name>/presentation-background.png`.

If the series name is missing, ask for it. If no layout constraints are provided, create a general-purpose background with broad central safe space and low-detail areas for text.

## Repo Workflow

1. Inspect `Series/<Series Name>/`. Read `series-image-style.md` when present.
2. View `series-logo.png`, series `cover-graphic.png`, and representative lesson `image-*.png` files when present.
3. Generate a 16:9 PNG presentation background using the image generation/editing tool available in the session.
4. Save the final image at `Series/<Series Name>/presentation-background.png` unless the user gave another path.
5. If the background establishes reusable slide rules, append a short presentation-background note to `series-image-style.md`.

Preserve existing PDFs, HTML, coloring pages, lesson images, covers, and take-home assets unless the user explicitly asks to replace them.

## Background Requirements

- Canvas: 16:9 PNG. Prefer 1672 x 941 when matching existing generated assets; otherwise use a clean 16:9 size supported by the tool.
- Purpose: support projected presentation slides. This is not a cover, title slide, or story illustration.
- Readability: keep broad low-detail safe areas for slide text. Avoid busy focal action behind likely text zones.
- Logo: do not include the series logo by default unless the user asks for a branded background or title-slide background. If included, use the transparent `series-logo.png` cleanly and keep it subordinate to slide readability.
- Style: match `series-image-style.md`, the series cover, and lesson imagery through palette, lighting, motifs, texture, and mood.
- Motifs: use subtle recurring series motifs as borders, corners, foreground silhouettes, sky shapes, scenery, texture, or soft patterning.
- Text: do not embed words, Bible references, labels, or decorative lettering unless explicitly requested.
- Tone: colorful, cheerful, kid-engaging, and calm enough for repeated use during teaching.

## Variants

Create one general-purpose background unless the user asks for variants. Useful variants:
- `presentation-background.png` - balanced default with central safe space.
- `presentation-background-title.png` - more visual energy, optional logo area.
- `presentation-background-verse.png` - quieter, high-readability text area.
- `presentation-background-question.png` - playful but uncluttered.

Only create variants requested by the user or clearly needed for the presentation workflow.

## Prompt Pattern

Build the image prompt from this structure:

```text
Create a 16:9 Junior Church presentation background for the series "[SERIES TITLE]".
Use this established art direction: [style lock summary].
Purpose: projected slide background with readable text areas, not a cover image.
Motifs: [subtle recurring series motifs].
Composition: [central/left/right text-safe area], soft visual framing, low-detail background, colorful but not busy.
Logo: [none by default, or exact placement if requested].
Avoid: embedded text, title lettering, clutter, high-contrast details in text area, scary imagery, dark mood, photorealistic adults.
```

After generation, inspect at full size and thumbnail size. If the background competes with text, has unwanted lettering, or reads like a cover poster, regenerate with stronger safe-area and low-detail instructions.

## Style Lock Note

If useful, append this to `series-image-style.md`:

```markdown
- **Presentation background pattern:** [safe area, logo use, motif placement, quietness level]
```

Do not rewrite the whole style lock just to add the background note.

## Verification

Before reporting completion:
- Confirm the background file exists at the intended path.
- Check the background is a PNG with 16:9 dimensions or very close to it.
- Visually inspect that it has usable text-safe space and no unwanted embedded text.
- Confirm it matches the series style without duplicating the cover composition.
- If the logo is included, confirm it uses the approved transparent logo and remains subordinate to readability.
- Confirm no unrelated lesson assets were renamed or edited unless the user requested it.
