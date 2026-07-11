# Repository Guidelines

This repo stores Junior Church lesson materials.

- Series live under `Series/<Series Name>/`.
- Individual lessons live inside their series folder.
- Existing PDFs, images, coloring pages, and take-home HTML are lesson assets. Do not edit or rename them unless the user asks.
- For ANY image work (logos, covers, lesson images, backgrounds, text on images), read `.codex/skills/shared/jr-church-image-standards.md` first and use the matching `jr-church-*` image skill. All artwork and lettering is rendered with the `imagegen` skill; scripts (Pillow/ImageMagick) are only for mechanical file operations, never for drawing text or content.
- For new lesson outlines, use the local skill at `.codex/skills/jr-church-lesson-outline/SKILL.md`.
- The Claude slash trigger is `/jr-lesson-outline ...`, backed by `.claude/skills/jr-lesson-outline/SKILL.md` and `.claude/commands/jr-lesson-outline.md`.
