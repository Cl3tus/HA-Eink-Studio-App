# YAML genereren & importeren

*🇬🇧 [English](Generate-and-Import-YAML-EN) · 🏠 [Home](Home-NL)*

### Genereren

Klik op **&lt;/&gt; Genereer YAML** om de (verstelbare) code-lade te openen.

> 📷 *Screenshot: de Genereer YAML-lade met code en de Kopiëren/Download-knoppen.* →
> `docs/screenshots/Generate-YAML.png` *(bestaat al)*

- Er draait eerst een **pre-flight-check**: als een laag naar een ontbrekende/lege
  **bron** wijst (de oorzaak van ESPHome's `Couldn't find ID 'undefined'`), een
  ontbrekende **conditie/grafiek**-bron, een **niet-numerieke grafiek-trace**, of een
  ontbrekend **font**, toont een popup precies welke lagen fout zijn en op welk scherm.
  Klik een rij om ernaartoe te springen, of **Toch genereren**.
- **Kopiëren** of **Download .yaml**.
- Welke blokken verschijnen, bepaal je bij
  [Profiel-instellingen → Generated YAML Blocks](Profiles-and-YAML-Blocks-NL). Bij twee
  of meer [schermen](Screens-NL) vertakt de display-lambda per scherm en worden de
  gekozen HA-bedieningen toegevoegd.

#### Herstelcode (round-trip)

Onderaan staat een base64 **herstel-commentaar** (`# eink-editor:v…:`) dat je hele
bewerkbare ontwerp opslaat (alle schermen, profielnaam, instellingen). Plak die YAML
terug via **YAML importeren** om alles **1-op-1** te herstellen. Laat het vinkje aan voor
round-tripping (per profiel onthouden); zet het uit voor een schone config.

Voorbeeld-output:

```yaml
font:
  - file:
      type: gfonts
      family: Roboto
      weight: 400
    id: font_small
    size: 25
    glyphs: [' ', '!', '"', '#', '$', '%', '&', '0', '1', '°', …]

  - file: 'fonts/materialdesignicons-webfont.ttf'
    id: font_mdi_small
    size: 30
    glyphs: [
      "\U000F044C", # mdi:recycle
      "\U000F0928", # mdi:wifi-strength-4
      ]

display:
  - platform: waveshare_epaper
    id: eink_display
    model: 7.50in-bV3
    rotation: 90°
    update_interval: never
    lambda: |-
      it.printf(120, 60, id(font_small), color_text, TextAlign::TOP_CENTER,
                "%.1f °C", id(aquarium_temp).state);
```

> Let op: een **MDI-icon-font bevat alléén z'n iconen** — geen tekst/cijfer-glyphs (die
> zouden de build laten falen). Een normaal tekstfont krijgt de printbare-ASCII-set.

### Importeren

Plak een bestaande ESPHome-config via **YAML importeren**:

> 📷 *Screenshot: het importsamenvatting-venster.* → `docs/screenshots/Import-Summary.png`
> *(bestaat al)*

- Alleen `font:`, `color:` en `homeassistant`-platform `sensor:` / `text_sensor:`
  worden gelezen; al het andere (wifi, api, secrets, …) wordt genegeerd — geen errors.
- De studio **reverse-engineert ook de `display:`-lambda** naar bewerkbare elementen
  (standaard `it.*`-aanroepen met letterlijke coördinaten, best-effort) en toont een
  **samenvatting** van wat wel/niet is geïmporteerd, plus welke YAML-blokken aanwezig
  zijn.
- Een YAML die de studio zelf genereerde (met de herstelcode) wordt **1-op-1** hersteld,
  inclusief alle schermen.
