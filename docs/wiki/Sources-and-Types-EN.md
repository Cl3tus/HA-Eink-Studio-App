# Sources & Type Detection

*🇳🇱 [Nederlands](Sources-and-Types-NL) · 🏠 [Home](Home-EN)*

Open **Sources** (top bar) to manage the list of values your design can bind to. Each
row maps a friendly **id** to a Home Assistant **entity_id**, a **sample** value and a
**type (lambda)**.

> 📷 *Screenshot: the Sources dialog with the id / entity_id / type (lambda) / type (HA)
> columns and the per-row snap icon.* → `docs/screenshots/Sources-Picker.png`
> *(already exists)*

### Columns

| Column | What it does |
|--------|--------------|
| **id** | The name used in the YAML (`id(...)`) and shown in element source pickers. |
| **entity_id** | The Home Assistant entity this source reads. |
| **sample** | A stand-in value used in the preview when **Live** is off. *(Off by default; the show/hide choice is saved per profile.)* |
| **live (HA)** | The real current state, shown when **Live** is on. |
| **type (lambda)** | How the lambda reads the value: **number / bool / time / string**. |
| **type (HA)** | The type Home Assistant detects for the entity (see below). |

### Type detection (lambda ↔ HA)

With **Live** on, each row shows the **type (HA)** that Home Assistant detects from the
entity's domain, `device_class` and live value:

- A green **✓** means your **type (lambda)** dropdown matches what HA reports.
- A red **✗** plus the detected type means they disagree.
- On a mismatch a small **↺** snap icon appears (just left of the row's **✕** delete
  button); click it to set that row to HA's type. **Detect types** (bottom of the
  dialog) fixes every row at once.

Your manual **type (lambda)** dropdown always wins — HA's type is only a suggestion from
the live entity. This is what catches the classic *"an `ai_task` / string entity marked
as a number"* mistake **before** it reaches a graph trace or the ESPHome build (a graph
trace on a non-numeric source can crash ESPHome — see
[Troubleshooting](Troubleshooting-and-FAQ-EN)).

### Sample column

The **sample** column is **off by default**; tick **Sample column** at the bottom to
show it (remembered per profile). Samples drive the value/condition previews while
**Live** is off, so you can design realistic layouts without a live connection.
