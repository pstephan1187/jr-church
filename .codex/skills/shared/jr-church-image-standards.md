# Jr Church Image Standards

Shared rules for all `jr-church-*` image skills (series logo, series cover, lesson cover, lesson image set, presentation background). Read this before doing any image work in this repo.

## Tool Policy: imagegen vs Scripts

**All visible artwork and lettering is produced by imagegen. Scripts never draw content.**

Scripts (Pillow, ImageMagick, etc.) are allowed only for mechanical file operations:

- Compositing the existing approved `series-logo.png` file onto an image at full fidelity, unchanged.
- Resizing or cropping to 16:9, format conversion, checking dimensions or alpha channels.
- Copying, backing up, or renaming files.

Scripts are never allowed to:

- Draw text with any font — lesson titles, scripture references, labels, anything. System-font text breaks the series art style and is a hard failure even when perfectly readable and correctly spelled.
- Paint, patch, recolor, erase, blur, add gradients or bands behind text, or add shadows or outlines to lettering.

Lesson titles and scripture references must be rendered by imagegen — either generated as part of the artwork or added with an imagegen edit pass — in the series lettering style defined in `series-image-style.md`.

### Rationalizations That Do Not Apply

| Excuse | Reality |
|--------|---------|
| "imagegen mangles words like 'Gadara'" | Misspellings are caught by required inspection and fixed with one targeted regeneration. A system-font overlay is wrong 100% of the time because it breaks the series art style. |
| "The skill says generated text needs inspection, so avoid generated text" | Inspection is a required step in the imagegen workflow, not a reason to switch tools. |
| "No time — this is needed in a few minutes" | Say so and let the user choose: wait for imagegen, or ship without the text. Never ship script-drawn text as a stopgap. |
| "Pillow is deterministic and pixel-perfect" | Pixel-perfect wrongness. The deliverable is illustrated lettering that belongs to the artwork, not typeset text on top of it. |
| "I'll do a proper imagegen pass later" | "Later" means script text gets projected in class. Do it right the first time. |
| "The skill endorses local overlay compositing" | That allowance covers exactly one thing: placing the unmodified `series-logo.png` file. It does not extend to text or any other drawn content. |

### Red Flags — Stop Immediately

If you are about to do any of these, you are on the script-text path. Stop and use imagegen instead:

- Importing `ImageFont` or calling `ImageDraw.text`
- Using `magick` / `convert` with `-annotate`, `-draw "text ..."`, or `caption:`
- Listing or searching system font directories
- Adding a semi-transparent band or gradient so overlay text will be legible

## Canvas and File Conventions

- All series and lesson images: 16:9 PNG. Prefer 1672 x 941 when matching existing generated assets.
- Exception: `series-logo.png` is a transparent-alpha PNG that fits a roughly square placement area.
- Default paths: series cover `Series/<Series Name>/cover-graphic.png`; lesson cover `<lesson folder>/cover-graphic.png`; lesson images `<lesson folder>/image-1.png`, `image-2.png`, ...; background `Series/<Series Name>/presentation-background.png`; style lock `Series/<Series Name>/series-image-style.md`.
- When regenerating an existing asset, keep its existing filename even if it differs from the default (some lessons use `cover-image.png`).

## Asset Preservation

Existing PDFs, take-home HTML, coloring pages, covers, and non-target lesson images are finished lesson assets. Do not edit, rename, or delete them unless the user explicitly asks.

## Generation Economy

imagegen is slow (minutes per image), so spend generations carefully:

1. Read first, generate second. Load the lesson outline, `series-image-style.md`, and reference images before the first prompt so it carries the full style lock. Most wasted generations come from prompting before reading.
2. Inspect each image before generating the next one in a set, so drift is caught after one image, not five.
3. When something fails, regenerate only the failing image — never the whole set.
4. For a localized flaw (misspelled lettering, one off-model character), prefer a targeted imagegen edit over regenerating from scratch.
5. Budget about two regeneration attempts per image. If it still fails, stop, keep the best attempt, and report the remaining problem to the user instead of looping.

## Shared Verification

Every image skill's completion check includes:

- The file exists at the intended path, is a PNG, and has the required aspect ratio (16:9, or transparent roughly-square for the logo).
- Every generated or edited image was visually inspected.
- Any lettering is readable, correctly spelled, and rendered in the series lettering style — not a system or script font.
- Where the logo is required, it is the approved `series-logo.png`, undistorted and unmodified.
- No non-target assets were edited or renamed.
