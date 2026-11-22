# Student Catalogue

An offline, single-file web app that turns phone photos of student sheets into a catalogue of cropped photo and signature files, named `rollnumber-name-photo.jpg` and `rollnumber-name-signature.jpg`.

No server, no AI, no OCR, no install. Everything runs on the device in the browser.

**Live app:** https://dvynsh3.github.io/Student-Catalogue/ (after enabling GitHub Pages, see below)

## Features

- Add several page photos at once; pages are auto-rotated upright (landscape and upside-down handled).
- Detects each student's photo (with name and date strip) and signature using canvas image processing.
- Photo crops are fitted to the sticker's rectangle with perspective correction.
- Fast data-entry flow: type roll number, press Next, type name, press Next, and the next card is shown.
- Large photo and signature previews on each card, with real file names and sizes.
- Configurable size cap (default 30 KB) applied to every crop, with "Apply to all".
- Zoomable manual recrop editor with draggable photo corners and a signature box.
- Duplicate roll number warnings, "Unfilled only" filter, and sort by roll number.
- Autosave to the browser's IndexedDB, including the original page photos (for recropping).
- ZIP export (`photos/`, `signatures/`, `catalogue.csv`, `catalogue.json`) and ZIP import, with a hand-written CRC-32 store-mode ZIP writer and reader (no libraries).

## Usage

1. Open the live page (or `index.html`) in Chrome on Android.
2. Tap **+ Add pages** and select all your page photos.
3. Type the roll number and name for each card, pressing Next to move on.
4. Check crops; tap **Recrop** to fix any that are off.
5. Tap **Export ZIP** at the end of each session. Use **Import** to restore a backup.

## Notes

- Autosave lives in browser storage, which can be cleared. Export regularly.
- Opened as a local file, Android may keep storage separate per app used to open it; hosting on GitHub Pages gives a stable address and reliable autosave.
- Exported ZIPs do not contain the original page photos, and entries restored from a ZIP cannot be recropped.
- Detection is heuristic. Plain, well-lit, flat backgrounds work best.

## Hosting on GitHub Pages

Repository **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`**. The site is then served from `index.html`.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app (HTML, CSS and JavaScript in one file) |
| `README.md` | This file |
| `LICENSE` | MIT licence |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |
| `.gitignore` | Ignores OS and editor clutter |

## Licence

Released under the [MIT License](LICENSE).
