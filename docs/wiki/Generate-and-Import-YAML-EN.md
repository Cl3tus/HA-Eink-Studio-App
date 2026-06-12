# Generate & Import YAML

*🇳🇱 [Nederlands](Generate-and-Import-YAML-NL) · 🏠 [Home](Home-EN)*

### Generate

Click **&lt;/&gt; Generate YAML** to open the (resizable) code drawer.

> 📷 *Screenshot: the Generate YAML drawer with code and the Copy/Download buttons.* →
> `docs/screenshots/Generate-YAML.png` *(already exists)*

- A **pre-flight check** runs first: if a layer points at a missing/empty **source**
  (the cause of ESPHome's `Couldn't find ID 'undefined'`), a missing **condition/graph**
  source, a **non-numeric graph trace**, or a missing **font**, a popup lists exactly
  which layers are wrong and on which screen. Click a row to jump to it, or
  **Generate anyway**.
- **Copy** or **Download .yaml**.
- Which blocks appear is controlled by
  [Profile settings → Generated YAML Blocks](Profiles-and-YAML-Blocks-EN). With two or
  more [screens](Screens-EN) the display lambda branches per screen and the chosen HA
  controls are added.

#### Recovery code (round-trip)

At the bottom there's a base64 **recovery comment** (`# eink-editor:v…:`) that stores
your full editable design (all screens, profile name, settings). Paste that YAML back via
**Import YAML** to restore everything **1-to-1**. Keep the checkbox on if you want
round-tripping (it's remembered per profile); turn it off for a clean config.

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
- A YAML the studio generated itself (with the recovery code) is restored **1-to-1**,
  including all screens.
