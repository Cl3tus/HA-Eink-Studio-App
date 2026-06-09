# Generate & Import YAML

## 🇬🇧 English

### Generate

Click **&lt;/&gt; Generate YAML** to open the (resizable) code drawer.

> 📷 *Screenshot: the Generate YAML drawer with code and the Copy/Download buttons.* →
> `docs/screenshots/Generate-YAML.png` *(already exists)*

- **Copy** or **Download .yaml**.
- Which blocks appear is controlled by
  [Profile settings → Generated YAML Blocks](Profiles-and-YAML-Blocks).

#### Recovery code (round-trip)

At the bottom there's a base64 **recovery comment** (`# eink-editor:v…:`) that stores
your full editable design. Paste that YAML back via **Import YAML** to restore
everything **1-to-1**. Keep the checkbox on if you want round-tripping; turn it off for
a clean config.

Example output:

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

> Note: an **MDI icon font lists only its icons** — no text/digit glyphs (those would
> fail the build). A normal text font gets the printable-ASCII set.

### Import

Paste an existing ESPHome config via **Import YAML**:

> 📷 *Screenshot: the import summary dialog.* → `docs/screenshots/Import-Summary.png`
> *(already exists)*

- Only `font:`, `color:` and `homeassistant`-platform `sensor:` / `text_sensor:`
  blocks are read; everything else (wifi, api, secrets, …) is ignored — no errors.
- The studio also **reverse-engineers the `display:` lambda** into editable elements
  (standard `it.*` calls with literal coordinates, best-effort) and shows a **summary**
  of what was and wasn't imported, plus which YAML blocks are present.
- A YAML the studio generated itself (with the recovery code) is restored **1-to-1**.

---

## 🇳🇱 Nederlands

### Genereren

Klik op **&lt;/&gt; Genereer YAML** om de (verstelbare) code-lade te openen.

> 📷 *Screenshot: de Genereer YAML-lade met code en de Kopiëren/Download-knoppen.* →
> `docs/screenshots/Generate-YAML.png` *(bestaat al)*

- **Kopiëren** of **Download .yaml**.
- Welke blokken verschijnen, bepaal je bij
  [Profiel-instellingen → Generated YAML Blocks](Profiles-and-YAML-Blocks).

#### Herstelcode (round-trip)

Onderaan staat een base64 **herstel-commentaar** (`# eink-editor:v…:`) dat je hele
bewerkbare ontwerp opslaat. Plak die YAML terug via **YAML importeren** om alles
**1-op-1** te herstellen. Laat het vinkje aan voor round-tripping; zet het uit voor een
schone config.

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
- Een YAML die de studio zelf genereerde (met de herstelcode) wordt **1-op-1** hersteld.
