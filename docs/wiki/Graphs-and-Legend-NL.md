# Grafieken & legenda

*🇬🇧 [English](Graphs-and-Legend-EN) · 🏠 [Home](Home-NL)*

Een **Grafiek** tekent één of meer sensor-traces via ESPHome's `graph:`-component.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Graph-Legend-NL.png" alt="Graph-Legend" width="100%">
</p>

### Positie & maat

Stel X/Y en breedte/hoogte in. De golf in de preview is een **plaatshouder**; op het
device tekent ESPHome de echte sensorgeschiedenis.

### Traces

Per trace:

- **Sensor** — de bron om te plotten. **Gebruik een numerieke bron** — een
  string/bool/tijd-bron (of een niet-numerieke HA-entiteit zoals een `ai_task`) kan de
  ESPHome-grafiek laten crashen; de pre-generate-check waarschuwt je (zie
  [Bronnen & type-detectie](Sources-and-Types-NL)).
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
