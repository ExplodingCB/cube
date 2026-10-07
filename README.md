# cube

An interactive 3D shape viewer in a single `index.html`. No build step; open the file in a browser.

Shapes: cube, sphere, a 60-face hexagon ball, and a tesseract (4D hypercube).

Controls:

- Drag to rotate, release to fling. Auto-spin eases back in after 3 seconds of no input.
- On the tesseract, Shift + drag (or a two-finger drag on touch screens) rotates through the fourth dimension. Left alone, it keeps turning in 4D on its own, which is why the inner cube appears to pass through the outer one.

Everything is drawn on a single 2D canvas with a small hand-rolled projector, not CSS 3D transforms. The old CSS version stacked dozens of intersecting, clipped 3D layers, which Safari had to split and re-sort every frame. The tesseract's 16 vertices at (±1, ±1, ±1, ±1) are rotated in the XW and YW planes, projected from 4D to 3D, then rotated and projected to 2D like the other shapes. Color follows the w coordinate, cyan for the far cube and magenta for the near one.
