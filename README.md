# Sticker Spec

> This project is vibe coded.

Single-file tool for producing sticker printing specs for a factory.

Open `index.html` in a browser (or serve the folder: `python3 -m http.server 8765`).

1. Drop sticker artwork (PNG/JPG/WebP/SVG) anywhere on the page.
2. Set each sticker's width in inches or mm. Height is computed from the image's aspect ratio.
3. Fill in order details (project name, material, cut, quantity, notes).
4. **Export spec PNG**: the overview sheet with `#N` labels, red dimension brackets and sizes.
5. **Export bundle**: a ZIP with
   - `spec-sheet.png`: the overview sheet
   - `spec.pdf`: factory spec (summary + overview, sticker table in inches and mm, one page per sticker with the artwork shown at actual size)
   - `stickers/N.ext`: the original artwork files, untouched, numbered to match the `#` labels
   - `spec.json`: machine-readable manifest

Stickers (including artwork) and order settings persist across reloads. Use the Reset button to clear everything; it asks for confirmation first.
