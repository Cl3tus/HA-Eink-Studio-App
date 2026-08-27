# Profiles & YAML Blocks

*🇳🇱 [Nederlands](Profiles-and-YAML-Blocks-NL) · 🏠 [Home](Home-EN)*

A **profile** is one display design. Keep several side by side with the profile picker;
**+** adds one and **⚙** opens its settings.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Profile-Yaml-Blocks.png" alt="Profile-Yaml-Blocks" width="100%">
</p>

### Device

- **Profile name**.
- **Model** — the colour palette adapts to the panel's colour type; for known panels
  the **width/height** are pre-filled to the native resolution (rotation-aware).
- **Rotation**, **width/height**, **canvas background** (preview only). New profiles
  default to a **20 px grid**.
- **Use waiting screen** on/off and **Use multiple screens** on/off — see
  [Screens](Screens-EN). With multiple screens on, a **Screen controls in HA** dropdown
  (none / dropdown only / buttons only / both) appears right below it.
- **Use Away screen** / **Use Holiday screen** on/off — static override screens that
  freeze the panel while active (Home Assistant **Display Override** select + buttons,
  Holiday wins, survives a reboot). An **Away/Holiday controls in HA** dropdown appears
  once either is on. See [Screens](Screens-EN).

### Negative mode

**Negative mode** (per profile, remembered) fills the screen with the **ink** colour and
draws everything in the **paper** colour — a black screen with white content. The canvas
preview turns dark with a light grid, and the YAML gets an `it.fill(id(color_text))` with
the two base colours (`color_text` ↔ `color_bg`) swapped, so your design stays readable.

### Generated YAML Blocks

Choose exactly which blocks the generator emits — handy when some of these already live
elsewhere in your config:

- **Refresh logic** — with boot priority, delay, wait timeout and the refresh interval
  (minutes). The **esphome on_boot**, **script** and **time** blocks can each be ticked
  individually (greyed out when Refresh logic is off, but remembered). Also generates the
  **Auto Refresh** / **Static Display** mode switches (and **Screen Rotation** with ≥2
  screens) — see [Screens](Screens-EN). They use `entity_category: config`, so they appear
  under **Configuration** in Home Assistant.
- **globals**, **font**, **color**, **sensor**, **text_sensor** — each on/off.
- **SPI bus** — `clk_pin` / `mosi_pin`.
- **Display pins** — `data_rate`, `cs_pin` (+ ignore_strapping), `dc_pin`, `busy_pin`
  (+ inverted), `reset_pin`, `reset_duration` — each individually on/off.

### Footer: save / duplicate / delete

**Save** stays greyed out until you actually change something. The footer is laid out as
**Duplicate profile** / **Delete profile** on the left and **Close** / **Save** on the
right. Duplicate copies the whole design (the copy gets `(1)`, `(2)`, …); profiles are
saved as JSON (see [File Manager & SAMBA](File-Manager-and-SAMBA-EN)).

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Negative-Mode.png" alt="Negative-Mode" width="100%">
  <br><em>Negative mode — a black screen with white content</em>
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Profile-Settings-Footer.png" alt="Profile-Settings-Footer" width="100%">
  <br><em>Footer: Duplicate/Delete left, Close/Save right (Save greyed out)</em>
</p>

