# Elements

## 🇬🇧 English

Drag an element from the palette onto the canvas, then edit it in the inspector.

> 📷 *Screenshot: the element palette (left) next to the canvas with one of each
> element placed.* → `docs/screenshots/Elements-Overview.png`

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
  [Values, Format & Transforms](Values-Format-Transforms).
- **Shape options** — thickness, fill, radius, sides, rotation (shapes).
- **Condition (if/else)** — every element can show/hide or recolour based on a source.

### Conditions (if/else)

Each element can have a **condition** based on a source. Per branch (true/false) you
can hide the element or override its text/icon/colour — the studio emits a proper
`if (…) { … } else { … }` in the lambda.

---

## 🇳🇱 Nederlands

Sleep een element uit het palet op het canvas en bewerk het in de inspector.

> 📷 *Screenshot: het element-palet (links) naast het canvas met van elk element
> één geplaatst.* → `docs/screenshots/Elements-Overview.png`

| Element | Wat het is | Genereert |
|---------|------------|-----------|
| **Tekst** | Alleen statische tekst. | `it.print` / `it.printf` |
| **Waarde** | Een Home Assistant-sensorwaarde met opmaak & transform. | `it.printf` |
| **MDI-icoon** | Een Material Design Icon (glyph uit het MDI-font). | `it.printf` |
| **Lijn** | Rechte lijn (dikte, gestreept/gestippeld). | `it.line` |
| **Rechthoek** | Open of gevulde rechthoek. | `it.rectangle` / `it.filled_rectangle` |
| **Cirkel / ovaal** | Open of gevuld. | `it.circle` / `it.filled_circle` |
| **Driehoek** | Drie punten, open of gevuld. | `it.line` / gevuld |
| **Veelhoek** | Regelmatige N-hoek. | lijnen / gevuld |
| **Ring** | Gevulde ring (buiten- + binnenstraal). | gevulde cirkels |
| **Meter** | Meter / voortgangsboog. | bogen |
| **QR-code** | Op het device gegenereerd. | `qr_code:` + `it.qr_code` |
| **Grafiek** | Sensor-historie-grafiek, optioneel legenda. | `graph:` + `it.graph` (+ `it.legend`) |
| **Refresh Time** | `strftime`-tijdstempel van de laatste refresh, met icoon. | `it.strftime` / `it.printf` |
| **WiFi-icoon** | Signaalsterkte-icoon via `wifisignal`. | `it.printf` |

### Selecteren

- **Klik** om te selecteren. Bij een stapel selecteer je het **bovenste** element
  (hoogste in de Lagen-lijst); kies een lager element via de Lagen-lijst.
- **Rubber-band**: sleep op het lege canvas (of de marge eromheen) om alles te
  selecteren dat volledig in het kader valt.
- **Ctrl/Shift-klik** om toe te voegen, of vink de **Lagen**-checkboxes aan.

### Algemene eigenschappen

- **Positie & anker** — X/Y plus, voor tekst/waarde/icoon/WiFi, een **9-vaks anker**
  dat bepaalt hoe de inhoud rond het ankerpunt valt (ESPHome `TextAlign`). Het anker
  wisselen houdt het element visueel op z'n plek.
- **Font** en **kleur** (tekst/icoon/WiFi/klok).
- **Bron / opmaak / transform** (waarde) — zie
  [Values, Format & Transforms](Values-Format-Transforms).
- **Vormopties** — dikte, vulling, straal, zijden, rotatie (vormen).
- **Conditie (if/else)** — elk element kan tonen/verbergen of herkleuren op basis van
  een bron.

### Condities (if/else)

Elk element kan een **conditie** hebben op basis van een bron. Per tak (waar/onwaar)
kun je het element verbergen of de tekst/icoon/kleur overschrijven — de studio zet een
nette `if (…) { … } else { … }` in de lambda.
