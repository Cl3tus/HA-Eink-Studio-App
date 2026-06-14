# Rulers, Guides & Snapping

*🇳🇱 [Nederlands](Rulers-Guides-Snapping-NL) · 🏠 [Home](Home-EN)*

Three independent alignment aids, all toggled in the **status bar**.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Rulers-Guides.png" alt="Rulers-Guides" width="100%">
</p>

### Grid + Snap grid

- **Grid** draws a dotted grid; **grid size** is 8 / 10 / 16 / 20 / 25 / 40 px.
- **Snap grid** snaps a dragged element's **visible pixels** to the grid lines.
- Turning the grid off also hides/disables Snap grid.

### Rulers

Enable **Ruler** to show rulers along the top and left edges.

- Ticks and labels every 50 px (denser as you zoom in), with a label at the canvas
  edge. Ticks continue into the negative area and past the canvas edge.
- Outside-the-canvas zones are tinted lighter (white in light mode) so the canvas
  bounds are clear.
- Rulers are **theme-aware** (light/dark).

### Guide lines

- **Drag out of a ruler** to drop a guide: the **top** ruler creates a **vertical**
  guide, the **left** ruler a **horizontal** one. A blue line follows on the canvas
  while you drag, and a dotted preview shows in the margin.
- Each guide has a **marker** (triangle) in its ruler. **Drag the marker** to
  reposition the guide; **right-click** a marker to remove that guide.
- **Right-click an empty ruler** → *Remove guides* (clears that axis).
- Guides are stored **per profile** and saved with the design.
- Guide lines sit **behind** your elements, so they never cover your design.

### Snap ruler (pixel-perfect)

With **Snap ruler** on, dragging an element snaps its edges to the guides:

- It snaps the element's **visible-ink box** — the tight box around the actual drawn
  pixels (same box the selection outline hugs) — so it lands exactly where the pixels
  begin, not on the looser font-metric box.
- The two axes snap **independently**: an element can lock onto a **vertical** guide
  (left/right edge) and a **horizontal** guide (top/bottom edge) at the same time —
  i.e. snap into the **cross** where two guides meet.
- The snap box is measured once when the drag starts, so it stays smooth even for
  large text.
- Hold **Shift** to bypass snapping.

### Mutual exclusivity

**Snap grid** and **Snap ruler** are mutually exclusive — enabling one turns the other
off. Use the grid for regular spacing, guides for precise alignment lines.
