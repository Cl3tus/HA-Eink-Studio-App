# Graphs & Legend

*🇳🇱 [Nederlands](Graphs-and-Legend-NL) · 🏠 [Home](Home-EN)*

A **Graph** draws one or more sensor traces via ESPHome's `graph:` component.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Graph-Legend.png" alt="Graph-Legend" width="100%">
</p>

### Position & size

Set X/Y and width/height. The wave in the preview is a **placeholder**; on the device
ESPHome draws the real sensor history.

### Traces

Per trace:

- **Sensor** — the source to plot. **Use a numeric source** — a string/bool/time source
  (or a non-numeric HA entity like an `ai_task`) can crash the ESPHome graph; the
  pre-generate check warns you (see [Sources & Type Detection](Sources-and-Types-EN)).
- **Line type** — solid / dashed / dotted.
- **Thickness** and **colour**.
- **Continuous** on/off.

Add more traces for multi-line graphs; remove with *Remove trace*.

### Axes

Optionally draw axis titles and scale values (ESPHome's `graph:` doesn't draw these
itself — the studio generates them as text). **Y-axis numbers only appear once you set
a fixed Y-min and Y-max** (with auto-scale the editor can't know the real bounds).

### Legend

Enable **Draw legend (it.legend)** to render a separate legend box:

- **Per-trace label** — a **free-text** field; type any name. Empty = the sensor id.
- **Name font** (required) and **Value font** (optional; empty = no values).
- **Show values** — NONE / AUTO / BESIDE / BELOW.
- **Direction** — AUTO / HORIZONTAL / VERTICAL.
- **Legend X / Y** — pixel position; empty = automatically to the right of the graph.
- **Border**, **Show line samples**, **Show units** toggles.

The legend is placed independently with `it.legend(x, y, …)`.
