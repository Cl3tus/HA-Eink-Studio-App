# Elementen

*🇬🇧 [English](Elements-EN) · 🏠 [Home](Home-NL)*

Sleep een element uit het palet op het canvas en bewerk het in de inspector.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Elements-Overview-NL.png" alt="Elements-Overview" width="100%">
</p>

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
  [Waarden, opmaak & transforms](Values-Format-Transforms-NL).
- **Vormopties** — dikte, vulling, straal, zijden, rotatie (vormen).
- **Conditie (if/else)** — elk element kan tonen/verbergen of herkleuren op basis van
  een bron.

### Condities (if/else)

Elk element kan een **conditie** hebben op basis van een bron. Per tak (waar/onwaar)
kun je het element verbergen of de tekst/icoon/kleur overschrijven — de studio zet een
nette `if (…) { … } else { … }` in de lambda.
