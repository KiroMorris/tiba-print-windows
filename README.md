# 🐢 Tiba Print — Windows Edition

A fully local web app to organize brand designs and pack them into DTF roll
print files with minimal wasted length. This is the **Windows-focused** build —
double-click one file and it installs everything for you.

## Run it (Windows)

1. Click the green **Code** button above → **Download ZIP** → unzip it
   (or `git clone https://github.com/KiroMorris/tiba-print-windows.git`)
2. Double-click **`Start Tiba Print.bat`**
3. First run installs **Node.js** (if missing) and all dependencies automatically —
   just wait a few minutes. A User Account Control prompt may appear → click **Yes**.
4. Your browser opens to the app at **http://localhost:4040**
5. Keep the black window open while using the app. Close it to stop.

After the first run, double-clicking the launcher starts the app in seconds.

> The launcher installs Node.js via **winget** (built into Windows 10/11), and if
> that's unavailable it downloads the **official Node.js installer** automatically.
> Nothing else to set up.

## How to use

1. **Import** — drag designs (PNG · JPG · PDF · SVG) into the Library, or click to
   browse. Auto-trims transparent padding so designs nest tightly. Click a design
   to edit its size (cm), toggle rotation, or delete it.
2. **Build a job** — click **+ Job** on designs, set a **quantity** each, or tick
   **fill rest of roll**.
3. **Auto-pack** — designs nest into the roll (57 cm wide by default), rotating 90°
   to save length, auto-splitting into File 2, 3… past the max length. Drag blocks
   to arrange manually (they snap into place, no overlaps).
4. **Export** — pick DPI (default 300) and format (PNG / tiled TIFF / PDF) →
   **Export Print File**. Output is trim-to-content at full print resolution.

## Canvas controls

| Input | Action |
|---|---|
| Mouse wheel | Zoom toward cursor |
| Ctrl / Alt + wheel | Scroll up/down the roll |
| Double-click a design | Rotate 90° |
| Drag a design | Move (snaps into place) |
| Hover a design | Info: name, size, rotation |

## Where your files live (stays on your PC)

- `data\library.db` — your design library (SQLite)
- `data\files\` — your original uploaded designs
- `data\exports\` — rendered print files

## Tech

Next.js · react-konva · bottom-left nesting · sharp/libvips (300-DPI compositing)
· resvg (SVG) · pdfjs (PDF) · pdf-lib (PDF output) · better-sqlite3.

MyTurtle branding — Deep Emerald `#1A4231` + Gilded Gold `#C9A227`,
Bagel Fat One headings + Prompt body.

---

🍎 Mac user? The cross-platform version is at
**https://github.com/KiroMorris/tiba-print** (use `Start Tiba Print.command`).
