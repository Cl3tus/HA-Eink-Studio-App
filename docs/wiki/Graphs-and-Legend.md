# Graphs & Legend

## 🇬🇧 English

A **Graph** draws one or more sensor traces via ESPHome's `graph:` component.

> 📷 *Screenshot: a Graph element selected, inspector showing traces + legend
> settings.* → `docs/screenshots/Graph-Legend.png`

### Position & size

Set X/Y and width/height. The wave in the preview is a **placeholder**; on the device
ESPHome draws the real sensor history.

### Traces

Per trace:

- **Sensor** — the source to plot.
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

---

## 🇳🇱 Nederlands

Een **Grafiek** tekent één of meer sensor-traces via ESPHome's `graph:`-component.

> 📷 *Screenshot: een Grafiek-element geselecteerd, inspector met traces +
> legenda-instellingen.* → `docs/screenshots/Graph-Legend.png`

### Positie & maat

Stel X/Y en breedte/hoogte in. De golf in de preview is een **plaatshouder**; op het
device tekent ESPHome de echte sensorgeschiedenis.

### Traces

Per trace:

- **Sensor** — de bron om te plotten.
- **Lijntype** — solid / dashed / dotted.
- **Dikte** en **kleur**.
- **Continu** aan/uit.

Voeg meer traces toe voor grafieken met meerdere lijnen; verwijderen met *Trace
verwijderen*.

### Assen

Teken optioneel astitels en schaalwaarden (ESPHome's `graph:` doet dit niet zelf — de
studio genereert ze als tekst). **Y-as-getallen verschijnen pas als je een vaste
Y-min én Y-max invult** (bij auto-schaal kent de editor de echte grenzen niet).

### Legenda

Zet **Legenda tekenen (it.legend)** aan voor een apart legenda-kader:

- **Label per trace** — een **vrij tekstveld**; typ elke naam. Leeg = de sensor-id.
- **Naam-font** (verplicht) en **Waarde-font** (optioneel; leeg = geen waarden).
- **Waarden tonen** — NONE / AUTO / BESIDE / BELOW.
- **Richting** — AUTO / HORIZONTAL / VERTICAL.
- **Legenda X / Y** — pixelpositie; leeg = automatisch rechts van de grafiek.
- **Rand**, **Lijnvoorbeelden tonen**, **Eenheden tonen** schakelaars.

De legenda wordt los geplaatst met `it.legend(x, y, …)`.
