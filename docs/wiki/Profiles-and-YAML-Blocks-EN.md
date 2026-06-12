# Profiles & YAML Blocks

*🇳🇱 [Nederlands](Profiles-and-YAML-Blocks-NL) · 🏠 [Home](Home-EN)*

A **profile** is one display design. Keep several side by side with the profile picker;
**+** adds one and **⚙** opens its settings.

> 📷 *Screenshot: Profile settings open, with the model picker and the "Generated YAML
> Blocks" toggles.* → `docs/screenshots/Profile-Yaml-Blocks.png` *(already exists)*

### Device

- **Profile name**.
- **Model** — the colour palette adapts to the panel's colour type; for known panels
  the **width/height** are pre-filled to the native resolution (rotation-aware).
- **Rotation**, **width/height**, **canvas background** (preview only). New profiles
  default to a **20 px grid**.
- **Use waiting screen** on/off and **Use multiple screens** on/off — see
  [Screens](Screens-EN).

### Negative mode

**Negative mode** (per profile, remembered) fills the screen with the **ink** colour and
draws everything in the **paper** colour — a black screen with white content. The canvas
preview turns dark with a light grid, and the YAML gets an `it.fill(id(color_text))` with
the two base colours (`color_text` ↔ `color_bg`) swapped, so your design stays readable.

### Generated YAML Blocks

Choose exactly which blocks the generator emits — handy when some of these already live
elsewhere in your config:

- **Refresh logic** — `esphome` on_boot + `script` + `time`, with boot priority, delay,
  wait timeout and the refresh interval (minutes).
- **Screen control in HA** (dropdown / buttons / both / none) and **Screen rotation
  (HA switch)** — greyed out unless *Use multiple screens* is on (see [Screens](Screens-EN)).
- **globals**, **font**, **color**, **sensor**, **text_sensor** — each on/off.
- **SPI bus** — `clk_pin` / `mosi_pin`.
- **Display pins** — `data_rate`, `cs_pin` (+ ignore_strapping), `dc_pin`, `busy_pin`
  (+ inverted), `reset_pin`, `reset_duration` — each individually on/off.

### Footer: save / duplicate / delete

**Save** stays greyed out until you actually change something. The footer is laid out as
**Duplicate profile** / **Delete profile** on the left and **Close** / **Save** on the
right. Duplicate copies the whole design (the copy gets `(1)`, `(2)`, …); profiles are
saved as JSON (see [File Manager & SAMBA](File-Manager-and-SAMBA-EN)).
