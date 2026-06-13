---
name: jr-church-series-cover
description: Use when creating, regenerating, or refining a 16:9 Junior Church series cover image in this repo, especially when the cover must include the series logo and establish or preserve a cohesive kid-friendly art style for later lesson images and presentation backgrounds.
---

# Jr Church Series Cover

## Overview

Create a 16:9 series-level cover image for a Junior Church lesson series. The cover should feel like the main poster for the whole series, include the transparent series logo, and lock in visual cues that later lesson covers, lesson image sets, and presentation backgrounds can reuse.

## Inputs

Required:
- Series name or target series folder.

Helpful but optional:
- Series theme, main Bible focus, target age range, mood words, key symbols, and exact subtitle text.
- Existing `series-logo.png`, `series-image-style.md`, or prior series reference images.
- Desired output filename. Default to `Series/<Series Name>/cover-graphic.png`.

If the series name is missing, ask for it. If the logo is missing, use `jr-church-series-logo` first or ask the user whether to create the logo before the cover.

## Repo Workflow

1. Inspect `Series/<Series Name>/`. Read `series-image-style.md` if it exists.
2. Locate `series-logo.png`. Confirm it is a transparent PNG suitable for overlay.
3. View existing series or lesson cover images when present. `Series/Good Choices Bad Choices/cover-graphic.png` is a useful benchmark for colorful, kid-facing polish, not a required style.
4. Generate or composite a 16:9 PNG cover image using the image generation/editing tool available in the session.
5. Save the final image at `Series/<Series Name>/cover-graphic.png` unless the user gave another path.
6. Update `Series/<Series Name>/series-image-style.md` if the cover establishes new palette, motifs, lighting, composition rules, or texture details.

Preserve existing PDFs, HTML, coloring pages, lesson images, and take-home assets unless the user explicitly asks to replace them.

## Cover Requirements

- Canvas: 16:9 PNG. Prefer 1672 x 941 when matching existing generated assets; otherwise use a clean 16:9 size supported by the tool.
- Logo: include the exact transparent `series-logo.png` visibly on the cover. Do not redraw or re-letter the logo if the logo file already exists.
- Composition: make the series identity the first read, with the logo large enough for classroom projection. Use clear foreground, midground, and background staging.
- Style: colorful, cheerful, kid-engaging, and polished. Match `series-image-style.md` when present.
- Cohesion: introduce reusable visual motifs that can repeat on lesson covers and presentation backgrounds without making every image identical.
- Text: avoid extra small text. Only include subtitle or supporting words when requested or already part of the approved logo.
- Theology and tone: keep imagery child-appropriate and faithful to the series theme. Avoid scary, violent, grotesque, or flippant depictions.

## Prompt Pattern

When generating the base cover, build the image prompt from this structure:

```text
Create a 16:9 Junior Church series cover image for "[SERIES TITLE]".
Use this established art direction: [style lock summary or new style direction].
Scene: [series-level symbolic scene, not a specific lesson moment unless the series requires it].
Motifs: [3-5 reusable symbols or environments tied to the series].
Composition: open area reserved for the existing transparent series logo, strong classroom readability, colorful depth, polished children's ministry poster.
Avoid: misspelled words, extra text, clutter, scary imagery, dark mood, photorealistic adults.
```

After generation, place or edit in the approved `series-logo.png` as an overlay if the tool did not preserve it exactly. If the generated image includes a distorted, misspelled, or alternate logo, regenerate or edit it out before placing the approved logo.

## Style Lock Update

If `series-image-style.md` does not exist, create it. If it exists, update only fields clarified by the cover:

```markdown
# [Series Name] Image Style

- **Logo file:** `series-logo.png`
- **Logo format:** transparent PNG that fits comfortably inside a roughly square placement area
- **Series cover file:** `cover-graphic.png`
- **Series image canvas:** 16:9 PNG, preferred 1672 x 941
- **Art style:** [concise style description]
- **Palette:** [dominant colors and accent colors]
- **Lettering:** [logo typography and any non-logo text rules]
- **Motifs:** [recurring objects, environments, symbols]
- **Cover composition:** [where logo sits, focal structure, safe areas]
- **Lighting and mood:** [direction]
- **Do reuse:** [specific reusable traits]
- **Avoid:** [specific things that would break cohesion]
```

## Verification

Before reporting completion:
- Confirm the cover file exists at the intended path.
- Check the cover is a PNG with 16:9 dimensions or very close to it.
- Visually inspect that the approved series logo appears clearly and is not misspelled, distorted, cropped, or replaced by generated text.
- Confirm the cover matches or updates `series-image-style.md`.
- Confirm no existing lesson assets were renamed or edited unless the user requested it.
