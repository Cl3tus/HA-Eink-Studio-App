# Interface Tour

*🇳🇱 [Nederlands](Interface-Tour-NL) · 🏠 [Home](Home-EN)*

> 📷 *Screenshot: the full editor with callouts on the top bar, left panel, canvas,
> status bar and inspector.* → `docs/screenshots/Interface-Overview.png`

### Top bar

Profile picker · **Import YAML** · **Sources** · **Fonts** · **Files** · **Live**
(+ refresh ↻ and auto-refresh interval) · **theme** (◐) · **language** (NL/EN) ·
**Save / Open** · **&lt;/&gt; Generate YAML**.

### Left panel

- **Element palette** — drag any element onto the canvas.
- **Layers** list — every element, top of the list = top of the stack. Drag the handle
  to reorder, click 👁 to toggle visibility, double-click to rename, 🗑 to delete. Tick
  the checkboxes for multi-select. **T** marks a text element, **#** a value.

### Canvas toolbar (above the canvas)

- **Screen selector** — switch between the **Waiting** screen, the **Main** screen and
  any extra screens. With **Use multiple screens** on, the **add / duplicate / rename /
  delete** buttons appear next to it (see [Screens](Screens-EN)). A single-screen design
  shows a static **Single Page** label.
- **Device rotation read-out** (↻ 90°) — shows the profile's rotation at a glance.
- **Alignment** (left/center/right/top/middle/bottom of the panel) · **layer order**
  (bring to front / send to back / step forward / step backward) · **undo/redo** ·
  **copy/cut/paste** · **duplicate** · **delete**.

### Canvas status bar (sticky, bottom)

- **Zoom** — `−` / editable `%` field / `+` / **Fit**. Type a percentage and press
  Enter; `−`/`+` snap to the nearest 10 %. Max 500 %.
- **Grid** on/off + **grid size** (8 / 10 / 16 / 20 / 25 / 40 px).
- **Ruler** on/off (Figma-style rulers + guides).
- **Snap grid** and **Snap ruler** (mutually exclusive).

### Inspector (right panel)

All properties of the selected element: position & anchor, font, colour, source,
format & transform, shape options, conditions — depending on the element type.

Hover any control for a tooltip (NL/EN).
