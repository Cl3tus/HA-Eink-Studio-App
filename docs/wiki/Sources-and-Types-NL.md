# Bronnen & type-detectie

*🇬🇧 [English](Sources-and-Types-EN) · 🏠 [Home](Home-NL)*

Open **Bronnen** (bovenbalk) om de lijst met waarden te beheren waaraan je ontwerp kan
koppelen. Elke rij mapt een herkenbare **id** aan een Home Assistant **entity_id**, een
**sample**-waarde en een **type (lambda)**.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Sources-Picker-NL.png" alt="Sources-Picker" width="100%">
</p>

### Kolommen

| Kolom | Wat het doet |
|-------|--------------|
| **id** | De naam in de YAML (`id(...)`), ook in de bronkiezers van elementen. |
| **entity_id** | De Home Assistant-entiteit die deze bron uitleest. |
| **sample** | Een invulwaarde voor de preview als **Live** uit staat. *(Standaard uit; de keuze wordt per profiel onthouden.)* |
| **live (HA)** | De echte actuele waarde, getoond als **Live** aan staat. |
| **type (lambda)** | Hoe de lambda de waarde leest: **number / bool / time / string**. |
| **type (HA)** | Het type dat Home Assistant voor de entiteit detecteert (zie onder). |

### Type-detectie (lambda ↔ HA)

Met **Live** aan toont elke rij het **type (HA)** dat Home Assistant detecteert uit het
domein, de `device_class` en de live waarde van de entiteit:

- Een groene **✓** betekent dat je **type (lambda)**-dropdown overeenkomt met wat HA
  meldt.
- Een rode **✗** plus het gedetecteerde type betekent dat ze verschillen.
- Bij een verschil verschijnt een klein **↺**-snap-icoon (net links van de **✕**
  verwijderknop van de rij); klik erop om die rij op het HA-type te zetten. **Detect
  types** (onderaan het venster) zet ze allemaal in één keer goed.

Je handmatige **type (lambda)**-dropdown wint altijd — het HA-type is slechts een
suggestie uit de live entiteit. Dit vangt de klassieke *"een `ai_task` / string-entiteit
als number gemarkeerd"*-fout **voordat** die in een grafiek-trace of de ESPHome-build
belandt (een grafiek-trace op een niet-numerieke bron kan ESPHome laten crashen — zie
[Probleemoplossing](Troubleshooting-and-FAQ-NL)).

### Sample-kolom

De **sample**-kolom staat **standaard uit**; vink **Sample column** onderaan aan om hem
te tonen (per profiel onthouden). Samples voeden de waarde-/conditie-previews terwijl
**Live** uit staat, zodat je realistische lay-outs kunt ontwerpen zonder live verbinding.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Sources-Type-Mismatch-NL.png" alt="Sources-Type-Mismatch" width="100%">
  <br><em>Een lambda↔HA type-mismatch: de rode ✗ en het ↺ snap-icoon</em>
</p>

