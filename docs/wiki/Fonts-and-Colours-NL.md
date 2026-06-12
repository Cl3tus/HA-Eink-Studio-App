# Fonts & kleuren

*🇬🇧 [English](Fonts-and-Colours-EN) · 🏠 [Home](Home-NL)*

Open **Fonts** (bovenbalk).

> 📷 *Screenshot: het Fonts-venster met de fontlijst en het "Font toevoegen"-formulier,
> een inline preview open.* → `docs/screenshots/Fonts-Dialog.png`

### Een font toevoegen

Kies een **Font Source**:

- **Upload font** — een lokaal `.ttf/.otf/.woff/.pcf/.bdf`. Upload het bestand zodat de
  preview klopt en het in je `fonts/`-map komt. Zet de `id`, `size` en `path`.
- **MDI Fonts** — het meegeleverde Material Design Icons-font (v7.4.47). Een link naar
  de [MDI-iconenbibliotheek](https://pictogrammers.com/library/mdi/) opent in een nieuw
  tabblad.
- **Google Fonts** — zet `family` + `weight`. ESPHome downloadt het tijdens de build.
- **Web Fonts** — een directe download-URL naar een `.ttf/.otf/.woff`.

Dezelfde TTF-bestandsnaam wordt maar één keer geüpload (ontdubbeld).

### Weight & italic

- **Weight** is een dropdown met namen — **Thin 100 · Extra Light 200 · Light 300 ·
  Regular 400 · Medium 500 · Semi Bold 600 · Bold 700 · Extra Bold 800 · Black 900**.
  Voor Google Fonts komt de weight in de YAML (`weight: 700`).
- **Italic** (Google Fonts) zet `italic: true`.
- Roboto en Noto Sans Display zijn gebundeld als **variabele fonts**, dus elke weight
  100–900 (en Roboto italic) rendert **apart herkenbaar** in de editor — geen twee
  coupures die op elkaar lijken.

### Preview

Klik een geladen font-id in de lijst voor een **inline preview**. In het bewerk-venster
ververst de preview **live** terwijl je de **grootte** aanpast (ook met de ▲/▼-knopjes),
de **weight** en de **italic**-schakelaar.

### Fonts downloaden (.zip)

De knop **Download Fonts (.zip)** — linksonder in het Fonts-venster, naast *Annuleren* /
*Opslaan* — bundelt elk bestand uit de `fonts/`-map van de add-on in één
`eink-fonts.zip`. Pak die uit in je ESPHome `config/fonts/`-map, zodat de build precies
de bestanden vindt waar je ontwerp naar verwijst.

E-ink Studio schrijft zelf nooit in de ESPHome-config: ESPHome laadt alleen fonts die
naast zijn eigen YAML staan, en in de config van een andere add-on schrijven zou een
brede lees/schrijf-mount vereisen — een security-risico dat we bewust vermijden. De zip
houdt het kopiëren een snelle maar **handmatige** stap aan jouw kant.

### Glyphs (wat in de YAML komt)

- **Tekstfonts** krijgen de printbare-ASCII-set (zodat getypte tekst nooit als "tofu"
  verschijnt), plus eventuele speciale tekens die je ontwerp gebruikt.
- **Icon-fonts (MDI)** krijgen **alleen de iconen die je echt gebruikt**, één per regel
  met een `# mdi:<naam>`-commentaar. Ze bevatten **geen** tekst/cijfer-glyphs — een
  icon-font heeft die niet, en ze toevoegen laat de ESPHome-build falen met *"Font … is
  missing N glyphs"*.

### Kleuren

Kleuren volgen automatisch het **kleurtype** van het display:

- **mono** (zwart/wit), **zwart-wit-rood** (B-W-R), of **7-kleuren**.

Stel het **model** in bij [Profiel-instellingen](Profiles-and-YAML-Blocks-NL) en het
palet past zich aan. Elke kleur wordt een `color:`-entry in de YAML. Zie ook
**Negatief-modus** op de [Profielen & YAML-blokken](Profiles-and-YAML-Blocks-NL)-pagina
voor een ontwerp met een zwart scherm.
