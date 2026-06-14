# Elements

*🇳🇱 [Nederlands](Elements-NL) · 🏠 [Home](Home-EN)*

Drag an element from the palette onto the canvas, then edit it in the inspector.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Elements-Overview.png" alt="Elements-Overview" width="100%">
</p>

| Element | What it is | Generates |
|---------|------------|-----------|
| **Text** | Static text only. | `it.print` / `it.printf` |
| **Value** | A Home Assistant sensor value with format & transform. | `it.printf` |
| **MDI icon** | A Material Design Icon (glyph from the MDI font). | `it.printf` |
| **Line** | A straight line (thickness, dashed/dotted). | `it.line` |
| **Rectangle** | Outline or filled box. | `it.rectangle` / `it.filled_rectangle` |
| **Circle / oval** | Outline or filled. | `it.circle` / `it.filled_circle` |
| **Triangle** | Three points, outline or filled. | `it.line` / filled |
| **Polygon** | Regular N-gon. | lines / filled |
| **Ring** | Filled ring (outer + inner radius). | filled circles |
| **Gauge** | Meter / progress arc. | arcs |
| **QR code** | Generated on the device. | `qr_code:` + `it.qr_code` |
| **Graph** | Sensor-history graph, optional legend. | `graph:` + `it.graph` (+ `it.legend`) |
| **Refresh clock** | `strftime` timestamp of the last refresh, with an icon. | `it.strftime` / `it.printf` |
| **Wi-Fi icon** | Signal-strength icon driven by `wifisignal`. | `it.printf` |

### Selecting

- **Click** to select. Clicking a stack selects the **topmost** element (highest in
  the Layers list); pick a lower one from the Layers list.
- **Rubber-band**: drag on the empty canvas (or the margin around it) to select
  everything fully inside the box.
- **Ctrl/Shift-click** to add to a selection, or tick the **Layers** checkboxes.

### Common properties

- **Position & anchor** — X/Y plus, for text/value/icon/Wi-Fi, a **9-block anchor**
  picker that sets how the content sits around its anchor point (ESPHome `TextAlign`).
  Changing the anchor keeps the element visually in place.
- **Font** and **colour** (text/icon/Wi-Fi/clock).
- **Source / format / transform** (value) — see
  [Values, Format & Transforms](Values-Format-Transforms-EN).
- **Shape options** — thickness, fill, radius, sides, rotation (shapes).
- **Condition (if/else)** — every element can show/hide or recolour based on a source.

### Conditions (if/else)

Each element can have a **condition** based on a source. Per branch (true/false) you
can hide the element or override its text/icon/colour — the studio emits a proper
`if (…) { … } else { … }` in the lambda.
