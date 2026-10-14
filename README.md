# Roomwright

**A browser-based 2D/3D room planner. Lay out a room, drop in furniture, and walk around it in 3D, all from a single HTML file.**

**[Open Roomwright →](https://patrickdleduc.github.io/roomwright/)**

Roomwright is a lightweight interior design modeling tool. It sits between graph paper and full CAD: you get a measured floor plan and a live 3D model that stay in sync, with editing that feels closer to *The Sims* than to an architecture suite. Click to pick something up, see if it fits, set it down.

---

## Features

### Plan and model, side by side
- **Three views:** 3D, 2D floor plan, or split. The 3D view comes with a mini floor plan in the corner; click or drag it to move the camera.
- **Toggleable grid** with measurements in **feet or meters**.
- **Dimension labels** on furniture, so you always know what you're working with.

### Rooms
- **Preset rooms:** living room, dining room, kitchen, bedroom, bathroom, office, hallway, and patio.
- **Resize rooms** by dragging handles, in the plan or directly in 3D. Moving a room moves its furniture with it.
- **Eight floor finishes:** oak, walnut, parquet, checker, marble, slate, carpet, and concrete.
- **Doors and windows** that sit in the walls, with flippable door swings.
- **Start fresh or from a sample:** the *New* menu opens a blank project or reloads the sample apartment.

### Furniture
A library of common pieces, grouped by room:

| Category | Pieces |
|---|---|
| Living room | Sofa, loveseat, armchair, coffee table, side table, TV stand, rug, shelf, lamp, plant |
| Dining room | Dining table, round table, chair, bench, sideboard |
| Kitchen | Counter, sink, range, fridge, island, stool |
| Bedroom & office | King, queen and single beds, nightstand, dresser, wardrobe, desk, office chair |
| Bathroom | Toilet, tub, vanity, shower |

### Sims-style editing
- **Pick up and place.** Drag a piece, or double-click it (or press **M**) to carry it. While held, it floats over a footprint: **green** means it fits, **red** means it overlaps something or sits outside a room. Click to drop; **Esc** puts it back.
- **Overlap warns, it doesn't block.** A red footprint is advice, not a rule, because real layouts need things like chairs tucked under tables.
- **Snap and collision checks** keep layouts tidy.
- **Resize furniture** by dragging any edge or corner, in plan or 3D (hold **Alt** for free sizing).
- **Floating action bar** on the selected item: rotate, move, duplicate, change finish, focus camera, delete.
- **Colour tools:** copy and paste a colour between pieces, type a hex value, keep a project palette, or use the eyedropper.
- **Library drag with live 3D preview** before you drop a new piece.

### Camera and walls
- **WASD / arrow keys** to pan, **Q / E** to rotate in 45° steps, scroll to zoom toward the cursor. Movement eases smoothly.
- **Wall modes:** *Walls up*, *Cutaway*, and *Walls down*. Cutaway works like the Sims: walls facing the camera drop down while the back walls stay up, and it updates as you rotate.

### Export
- Save your layout as a **PNG image** or a **PDF**.

---

## Keyboard shortcuts

| Key | Action |
|---|---|
| `W` `A` `S` `D` / arrows | Pan the 3D camera |
| `Q` / `E` | Rotate the camera 45° |
| `+` / `-` | Zoom in / out |
| `M` or double-click | Pick up the selected piece |
| `,` / `.` | Rotate a held piece by 45° |
| `R` / `Shift+R` | Rotate 90° clockwise / counter-clockwise |
| `F` | Focus the camera on the selection (flips the swing on a selected door) |
| `G` | Toggle the grid |
| `Ctrl+D` | Duplicate |
| `Ctrl+C` / `Ctrl+V` | Copy / paste a colour |
| `Ctrl+Z` / `Ctrl+Y` (or `Ctrl+Shift+Z`) | Undo / redo |
| `Delete` / `Backspace` | Delete the selection |
| `Esc` | Cancel / put a held piece back |

On macOS, `Cmd` works in place of `Ctrl`.

---

## How it's built

Roomwright is deliberately simple to run and host:

- **One file.** The whole app is a single `index.html`: markup, styles, and vanilla JavaScript. No build step, no framework, no backend.
- **[three.js](https://threejs.org/) (r128)** renders the 3D model. Floor textures are generated procedurally on canvas, so there are no image assets to load.
- **[jsPDF](https://github.com/parallax/jsPDF) (2.5.1)** handles PDF export.
- Both libraries load from the cdnjs CDN.
- **Hosting:** GitHub Pages serves the file as-is (`.nojekyll` skips Jekyll processing).

### Run it locally

```bash
git clone https://github.com/PatrickDLeduc/roomwright.git
cd roomwright
python3 -m http.server 8000
# then open http://localhost:8000
```

Opening `index.html` directly in a browser also works; you just need an internet connection for the CDN libraries.

---

## Status and roadmap

Roomwright is a working prototype built mainly for personal use. Layouts are not saved between sessions yet; export a PNG or PDF to keep one.

Ideas on the list:
- Saving and loading projects
- Importing real furniture 3D models (e.g. IKEA)
- Option to make overlapping placements a hard block rather than a warning

---

## Author

Built by [Patrick Leduc](https://github.com/PatrickDLeduc).
