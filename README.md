# cube

An interactive 3D shape viewer in a single `index.html`. No build step; open the file in a browser.

Shapes: cube, glass sphere, soccer ball (truncated icosahedron), and a tesseract (4D hypercube). Picking a new shape morphs the old one into it: its outline breaks into points that flow, top to bottom, onto the new shape's outline.

Controls:

- Drag to rotate, release to fling. Auto-spin eases back in after 3 seconds of no input.
- Scroll wheel (or trackpad pinch) zooms in and out on desktop.
- On phones, tilt to spin: tilting rolls the shape like a ball going downhill. Android turns this on automatically; on iPhone, tap the tilt button and allow motion access. The tilt button turns it off. Tilt needs the page served over HTTPS (GitHub Pages is fine).
- On a computer, the + button opens a lump of clay made of about 2,400 beads. Grab it and drag to mush it around: the beads you grab follow the mouse and the rest shove out of the way, so the lump keeps its volume and you can flatten it, pinch it, pull out ropes or tear bits off. Fourteen white anchor dots sit on the lump; drag one to pull a wide, smooth area for clean, even shapes. When you press Done the beads melt into one smooth sculpture (each bead is a soft blob of density, and the surface is traced where they add up); pressing + again breaks it back into beads. Drag empty space (or right-drag) to turn it. Pick a color, Cmd/Ctrl+Z undoes a move, and Done (or Enter) saves it in your browser as its own shape button. Right-click that button to delete it.
- On the tesseract, Shift + drag (or a two-finger drag on touch screens) rotates through the fourth dimension. Left alone, it keeps turning in 4D on its own, which is why the inner cube appears to pass through the outer one.

Everything is drawn on a single 2D canvas with a small hand-rolled projector, not CSS 3D transforms. The old CSS version stacked dozens of intersecting, clipped 3D layers, which Safari had to split and re-sort every frame. The tesseract's 16 vertices at (±1, ±1, ±1, ±1) are rotated in the XW and YW planes, projected from 4D to 3D, then rotated and projected to 2D like the other shapes. Edges nearer the viewer are drawn brighter and thicker.
