---
name: jr-church-series-logo
description: Use when creating, regenerating, or refining a transparent PNG Junior Church series logo for a lesson series in this repo, especially when later 16:9 series covers, lesson covers, lesson images, or presentation backgrounds must reuse the same kid-friendly art style.
---

# Jr Church Series Logo

## Overview

Create a reusable transparent PNG logo that becomes the visual anchor for a Junior Church lesson series. The logo should be colorful, readable at classroom-screen distance, and easy for later 16:9 cover-image skills to place inside larger scenes.

## Inputs

Required:
- Series name or target series folder.

Helpful but optional:
- Series theme, Bible focus, target age range, mood words, and exact subtitle text.
- Existing image references or a prior series to match. For this repo, `Series/Good Choices Bad Choices/cover-graphic.png` is a useful benchmark for colorful, kid-facing energy, not a required style.
- Desired output filename. Default to `Series/<Series Name>/series-logo.png`.

If the series name is missing, ask for it. If the art direction is missing, inspect the series folder and create a reasonable kid-friendly direction without asking preference questions.

## Repo Workflow

1. Inspect `Series/<Series Name>/` when it exists. Read nearby lesson outline titles and view any existing `cover-graphic.png`, `image-*.png`, or `series-logo.png` files before prompting.
2. Preserve existing PDFs, HTML, coloring pages, and lesson images unless the user explicitly asks to replace them.
3. Generate or refine a transparent PNG logo image. Use the image generation/editing tool available in the session.
4. Save the final image at `Series/<Series Name>/series-logo.png` unless the user gave another path.
5. Create or update `Series/<Series Name>/series-image-style.md` with the style lock so later image skills can match it.

## Logo Requirements

- Canvas: transparent-background PNG. This logo is the exception to the series-wide 16:9 image rule.
- Shape: the artwork does not need to be square or badge-shaped, but the full logo should fit comfortably inside a roughly square placement area so it can be placed cleanly over later 16:9 covers, lesson images, and presentation backgrounds. Good options can include circles, banners, shields, clouds, trees, triangular compositions, framed signs, stacked lettering, or other theme-appropriate silhouettes.
- Content: exact series title text, styled as the logo. Include a short subtitle only when provided or clearly useful.
- Composition: centered, high-contrast, and readable when scaled down. Leave a small transparent margin so later cover images can overlay the logo without clipping.
- Style: colorful, cheerful, kid-engaging, and polished. Prefer bold dimensional lettering, clear silhouettes, and simple symbolic props tied to the series theme.
- Cohesion: define a reusable art style, palette, typography direction, motifs, lighting, and texture treatment for the full series image set.
- Theology and tone: keep imagery child-appropriate and faithful to the Bible story or doctrine. Avoid scary, violent, grotesque, or flippant depictions.

## Prompt Pattern

Build the image prompt from this structure:

```text
Create a transparent-background PNG Junior Church series logo for "[SERIES TITLE]".
Use exact readable title text: "[SERIES TITLE]".
Style: [kid-friendly art style, dimensional lettering, palette, lighting, texture].
Motifs: [2-4 visual symbols tied to the series].
Composition: centered logo that fits inside a roughly square placement area, high contrast, no small text, small transparent safe margin.
Background: fully transparent alpha background, no solid color, no scene, no white box.
Avoid: misspelled words, extra text, clutter, scary imagery, photorealistic adults, dark mood.
```

After generation, inspect the image. If text is misspelled, cropped, too small, lacks transparency, has a white/colored background, or is inconsistent with the style lock, regenerate or edit before finishing.

## Style Lock

Write `series-image-style.md` with these fields:

```markdown
# [Series Name] Image Style

- **Logo file:** `series-logo.png`
- **Logo format:** transparent PNG that fits comfortably inside a roughly square placement area
- **Logo silhouette:** [circle, banner, shield, cloud, tree, triangle, sign, stacked lettering, or other chosen shape]
- **Series image canvas:** later cover, lesson, and background images should use 16:9
- **Art style:** [concise style description]
- **Palette:** [dominant colors and accent colors]
- **Lettering:** [logo typography and treatment]
- **Motifs:** [recurring objects, environments, symbols]
- **Lighting and mood:** [direction]
- **Do reuse:** [specific reusable traits]
- **Avoid:** [specific things that would break cohesion]
```

## Verification

Before reporting completion:
- Confirm the image file exists at the intended path.
- Check the image is a PNG with a real alpha channel and transparent background.
- Check the logo fits comfortably inside a roughly square placement area and can be placed cleanly over 16:9 images.
- Visually inspect that the exact series title is readable and not misspelled.
- Confirm `series-image-style.md` exists and describes the reusable style for future series and lesson imagery.
