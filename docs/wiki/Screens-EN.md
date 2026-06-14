# Screens

*🇳🇱 [Nederlands](Screens-NL) · 🏠 [Home](Home-EN)*

A design always has a **Main** screen and an optional **Waiting-for-data** screen, and
can have **up to 10** Home Assistant–switchable screens. Switch between them with the
selector above the canvas.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Screens.png" alt="Screens" width="100%">
</p>

### Waiting screen

- **Waiting** is a *waiting-for-data* screen, shown until the first sensor value arrives
  after boot. A new profile seeds a default **"WAITING FOR DATA…"** text (font
  `font_small`).
- Turn it on/off in **Profile settings → Use waiting screen**. When off, the boot
  `if/else` is omitted entirely.
- The generated lambda wraps the waiting elements in:

  ```cpp
  if (id(initial_data_received) == false) {
    // Waiting screen elements
  } else {
    // Main / active screen elements
  }
  ```

### Multiple screens

Turn on **Use multiple screens** in [Profile settings](Profiles-and-YAML-Blocks-EN)
(remembered per profile). The selector then shows buttons to **add**, **duplicate**,
**rename** and **delete** screens (the main screen can't be renamed or removed). Each
screen has its own elements; **copy/paste works across screens** (Ctrl+C on one, Ctrl+V
on another — the position is kept).

With two or more screens the display lambda branches per screen and reads the active
screen from the HA control, and switching a screen forces an **immediate redraw**
(independent of new sensor data).

### Home Assistant controls

Choose them under **Profile settings → Generated YAML Blocks → Screen control in HA**:

| Option | What it generates |
|--------|-------------------|
| **Dropdown (select)** | A template `select`; its options are your screen names. |
| **Buttons** | One template `button` per screen (great for dashboards). |
| **Both** | The dropdown *and* the buttons. |
| **None** | No HA controls — the screen select stays `internal: true` so the display still works while you drive it from your own automations. |

### Screen rotation (HA switch)

**Screen rotation (HA switch)** (same panel) adds a template `switch` exposed to Home
Assistant. While it's on, the display advances to the next screen on every refresh
interval — no `input_boolean` or `configuration.yaml` edit needed.

> Screen controls and rotation are greyed out unless *Use multiple screens* is on.
> Single-screen designs generate exactly the same YAML as before, your existing layout
> migrates into the first screen automatically, and the base64 recovery code round-trips
> all screens.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Screen-Control-Blocks.png" alt="Screen-Control-Blocks" width="100%">
  <br><em>Screen control in HA + the rotation switch</em>
</p>

