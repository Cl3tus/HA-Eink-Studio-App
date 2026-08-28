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

### Away & Holiday override screens

- Two optional **static** screens, enabled per profile in **Profile settings → Use Away
  screen / Use Holiday screen**. They sit in the selector right after **Waiting** and
  before Screen 1. Empty screens fall back to a centred **"AWAY"** / **"HOLIDAY"** label
  (font `font_small`).
- They generate a Home Assistant **Display Override** `select` (options *Normal / Away /
  Holiday*) plus optional per-option buttons — style set by the shared **HA controls
  (screen & override)** dropdown (none / dropdown only / buttons only / both).
- While the override is on *Away* or *Holiday* the panel **freezes on that screen**: the
  interval refresh **and** Screen Rotation are skipped until you set it back to *Normal*.
- If both would apply, **Holiday wins** (checked first in the lambda). The boot
  *waiting-for-data* branch still runs first.
- Unlike `screen_select`, `display_override` has `restore_value: yes` — a running
  Away/Holiday state survives a reboot. It stays crash-safe because the `on_value`
  redraw is gated on `initial_data_received`.

  ```cpp
  if (id(initial_data_received) == false) {
    // Waiting screen
  } else {
    int ov = id(display_override).active_index().value_or(0);
    if (ov == 2) {        // Holiday
      // Holiday screen
    } else if (ov == 1) { // Away
      // Away screen
    } else {
      // Normal: designed screen(s)
    }
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

One **HA controls (screen & override)** dropdown in Profile settings sets the style for
**both** the screen picker (with multiple screens) *and* the Away/Holiday **Display
Override**. It shows whenever multiple screens, Away, or Holiday is on:

| Option | What it generates |
|--------|-------------------|
| **Dropdown (select)** | A template `select` — screen names for the picker, *Normal / Away / Holiday* for the override. |
| **Buttons** | One template `button` per option (great for dashboards). |
| **Both** | The dropdown *and* the buttons. |
| **None** | No HA controls — the selects stay `internal: true` so the display still works while you drive them from your own automations. |

### Display-mode switches (Auto Refresh / Static / Rotation)

When **Refresh logic** is on, the YAML also generates interlocked Home Assistant
**switches** that decide what the display does each interval. **Exactly one is always on**
(default **Auto Refresh**, remembered across reboots):

| Switch | What it does on each interval |
|--------|-------------------------------|
| **Auto Refresh** | Refreshes the display *when a bound sensor has new data* (logs + skips the round otherwise). |
| **Static Display** | Freezes the screen — after the first render it stops refreshing. |
| **Screen Rotation** | Advances to the next screen each interval; generated automatically with ≥2 screens. Turning it on also turns Auto Refresh on. |

Turning one on turns the conflicting ones off, and you can never leave all three off, so
there's always a defined mode. Auto Refresh and Static come with **Refresh logic**; Screen
Rotation is added automatically with ≥2 screens. The HA mode switches use
`entity_category: config`, so they appear under **Configuration** in Home Assistant.

> The screen-switching parts (rotation, per-screen buttons) need *Use multiple screens*;
> the HA-controls dropdown also appears for Away/Holiday alone.
> Single-screen designs generate exactly the same YAML as before, your existing layout
> migrates into the first screen automatically, and the base64 recovery code round-trips
> all screens.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Screen-Control-Blocks.png" alt="Screen-Control-Blocks" width="100%">
  <br><em>Screen control in HA + the rotation switch</em>
</p>

