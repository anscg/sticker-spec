# Sticker Spec

> This project is vibe coded.

Single-file tool for producing sticker printing specs for a factory.

Open `index.html` in a browser (or serve the folder: `python3 -m http.server 8765`).

1. Drop sticker artwork (PNG/JPG/WebP/SVG) anywhere on the page.
2. Set each sticker's width or height in inches or mm. The other dimension follows from the image's aspect ratio.
   - Transparent margins are trimmed automatically (**Trim**).
   - Baked-in drop shadows and glows are detected and stripped (**Shadow**); the slider sets the opacity cutoff between artwork and shadow. Toggle either off per sticker if the artwork is intentionally soft.
3. Fill in order details (project name, material, cut, quantity, notes).
4. **Export spec PNG**: the overview sheet with `#N` labels, red dimension brackets and sizes.
5. **Export bundle**: a ZIP with
   - `spec-sheet.png`: the overview sheet
   - `spec.pdf`: factory spec (summary + overview, sticker table in inches and mm, one page per sticker with the artwork shown at actual size)
   - `stickers/N.png`: lossless artwork, numbered to match the `#` labels (trimmed / de-shadowed where applied)
   - `stickers/N.jpg`: the same artwork as JPEG at quality 100, transparency flattened to white
   - `originals/N.ext`: untouched originals for any sticker that was modified
   - `spec.json`: machine-readable manifest

Stickers (including artwork) and order settings persist across reloads. Use the Reset button to clear everything; it asks for confirmation first.
