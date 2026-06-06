<p align="center">
  <img src="eink_studio/banner.png" alt="E-ink Studio" width="100%">
</p>

# E-ink Studio — Home Assistant Add-on

A **WYSIWYG editor for ESPHome e-paper displays**, running as a Home Assistant
add-on with its own sidebar panel (Ingress). Drag elements onto a paper-accurate
canvas, bind them to **live Home Assistant sensor values**, and generate
ready-to-paste ESPHome `display:` lambda + YAML — no more hand-counting pixels.

[![GitHub release](https://img.shields.io/badge/version-3.2.1-blue)](https://github.com/Cl3tus/HA-Eink-Studio-App/releases)
[![Project Stage](https://img.shields.io/badge/project%20stage-experimental-yellow.svg)](https://github.com/Cl3tus/HA-Eink-Studio-App/releases)
[![Maintained](https://img.shields.io/badge/maintained-yes-brightgreen.svg)](https://github.com/Cl3tus/HA-Eink-Studio-App/commits/main)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

![Supports aarch64](https://img.shields.io/badge/aarch64-yes-green.svg)
![Supports amd64](https://img.shields.io/badge/amd64-yes-green.svg)

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2FCl3tus%2FHA-Eink-Studio-App)

---

<p align="center">
  <img src="docs/screenshots/E-ink-Studio-Editor-Screenshot-Dark-Light.png" alt="E-ink Studio editor — dark & light" width="100%">
</p>

## ✨ Why

Hand-writing ESPHome `it.print()` / `it.printf()` lambdas for an e-paper display
is tedious: you count pixels, guess alignment, juggle fonts and glyph lists, and
re-flash to see the result. E-ink Studio turns that into a **visual design task** —
you see exactly what the panel will show, bind values to your real entities, and
copy the generated YAML straight into your device.

## 🎨 Features

**Design**
- Drag-and-drop canvas with a **paper-accurate** preview of your panel.
- Elements: **Text**, **Value** (sensor + format/transform), **MDI icon**, **line**,
  **rectangle**, **circle / oval**, **triangle**, **polygon**, **ring**, **gauge**,
  **QR code**, **graph**, **refresh clock**, **Wi-Fi signal icon**.
- **Rotate, resize, fill** shapes with on-canvas handles; **align** the whole
  selection (left/center/right/top/middle/bottom).
- **Grid + snap** (8 / 10 / 16 / 20 / 25 / 40 px), snapping the visible pixels to
  the grid lines; hold **Shift** to move freely.
- **Multi-select** (rubber-band, Ctrl/Shift-click, layer checkboxes), **layers**
  panel with drag-to-reorder, visibility toggle, rename and delete.
- **Undo/redo**, **duplicate**, and **cut / copy / paste** (Ctrl+X / C / V) — paste
  even works **between the main and waiting screen**.
- **Two screens** per design: the **main** screen and a **waiting-for-data** screen.
- **Conditions (if/else)** on any element — show/hide or recolour per branch.

**Data & values**
- Pick real **Home Assistant entities** from a searchable list and bind them to
  value elements.
- **Live preview** of the actual sensor states while you design (read-only), with a
  refresh button and an auto-refresh interval (off / 1–30 min / custom).
- **Transforms**: round/scale numbers, on/off → custom labels, time → `HH:MM`,
  dates in many formats, weekday/month **names** (NL & EN), and a **custom
  date/time format** with tokens like `{wd} {dd} {mon}` → `Sun 19 Jun`.
- **Prefix/suffix** with an automatic space before units (`1065` → `1065 L/h`).

**Fonts & colours**
- Manage **Google Fonts** and **local TTF/OTF** (upload + dedupe + live preview).
- **Material Design Icons** (v7.4.47) bundled and seeded into your `fonts/` folder.
- Colours follow the display's colour type automatically (mono / B-W-R / 7-colour).

**YAML output**
- One click produces the ESPHome **lambda + matching blocks**.
- **Per-block toggles** (Profile settings → *Generated YAML Blocks*): refresh logic
  (`esphome` on_boot + `script` + `time`), `globals`, `font`, `color`, `sensor`,
  `text_sensor`, the `spi` bus, and the **display pins** (each pin individually).
- A compact **base64 recovery comment** lets you paste the YAML back later to
  restore the whole editable design.

**Import**
- Paste a complete ESPHome config — only `font:`, `color:` and `homeassistant`
  `sensor:`/`text_sensor:` are read, the rest is ignored.
- The studio also **reverse-engineers the `display:` lambda** back into editable
  elements (best-effort) and shows a summary of what was/wasn't imported.

**Files & the rest**
- Built-in **file manager**: collapsible tree, multi-select, text editor
  (undo/redo), font preview, upload/download/rename/move/delete — also reachable
  over **SAMBA**.
- **Profiles** to keep multiple designs side by side, with **duplicate** and a
  **model picker** that pre-fills width/height for known panels.
- **Light / dark** theme and **English / Dutch** — automatically following Home
  Assistant, or fixed in the add-on options.
- **Fully offline** — Konva, js-yaml, MDI and all fonts are bundled.

---

## 📸 Screenshots

**Editor — dark & light**

<p align="center">
  <img src="docs/screenshots/E-ink-Studio-Editor-Screenshot.png" alt="Editor — dark mode" width="49%">
  <img src="docs/screenshots/E-ink-Studio-Editor-Screenshot-Lightmode.png" alt="Editor — light mode" width="49%">
</p>

**Built-in file manager**

<p align="center">
  <img src="docs/screenshots/E-ink-Studio-File-Manager-Screenshot1.png" alt="File manager" width="100%">
</p>

<p align="center">
  <img src="docs/screenshots/E-ink-Studio-File-Manager-Editor.png" alt="File manager — text editor" width="49%">
  <img src="docs/screenshots/E-ink-Studio-File-Manager-Font-Viewer.png" alt="File manager — font viewer" width="49%">
</p>

**Inspector — a Value element** (source + format & transform), **Element palette & layers**

<p align="center">
  <img src="docs/screenshots/Inspector-Value.png" alt="Inspector — value element" width="49%">
  <img src="docs/screenshots/Palette-Layers.png" alt="Element palette and layers" width="49%">
</p>

**Profile settings — per-block YAML toggles** &nbsp;·&nbsp; **Value sources picker**

<p align="center">
  <img src="docs/screenshots/Profile-Yaml-Blocks.png" alt="Generated YAML blocks" width="49%">
  <img src="docs/screenshots/Sources-Picker.png" alt="Value sources picker" width="49%">
</p>

**Generate YAML** &nbsp;·&nbsp; **Import summary**

<p align="center">
  <img src="docs/screenshots/Generate-YAML.png" alt="Generate YAML drawer" width="49%">
  <img src="docs/screenshots/Import-Summary.png" alt="YAML import summary" width="49%">
</p>

---

## 🚀 Installation

1. Add this repository to your Home Assistant add-on store:

   [![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2FCl3tus%2FHA-Eink-Studio-App)

   *(Or manually: **Settings → Add-ons → Add-on Store → ⋮ → Repositories**, paste
   `https://github.com/Cl3tus/HA-Eink-Studio-App` and click **Add**.)*

2. Refresh the store, open **E-ink Studio**, click **Install** (the first build
   takes a few minutes), then **Start**.

3. Open **E-ink Studio** from the sidebar.

## ⚡ Quick start

1. Click **○ Live** to pull your real Home Assistant entities.
2. In **Bronnen / Sources → From Home Assistant**, add the sensors you want to show.
3. Drag a **Value** onto the canvas and bind it to a source (set format/transform).
4. Click **&lt;/&gt; Generate YAML**, then **Copy** or **Download** and paste it into
   your ESPHome device config.
5. Put your local TTF fonts in your ESPHome `fonts/` folder.

## ⚙️ Configuration

| Option | Values | Description |
|--------|--------|-------------|
| `language` | `auto` · `nl` · `en` | UI language. `auto` follows Home Assistant / browser. |
| `theme` | `auto` · `light` · `dark` | Colour theme. `auto` follows Home Assistant. |

Both can also be toggled on the fly inside the editor; the add-on option is the
default.

## 🗄️ Storage & SAMBA

Projects, fonts and profiles live in the add-on config folder, exposed over SAMBA at:

```
\\<HA-IP>\addon_configs\<slug>_eink_studio\
├── projects/   ← saved designs (.json)
├── fonts/      ← uploaded fonts (incl. the bundled MDI ttf)
└── profiles/   ← profile settings (.json)
```

Edit and back them up from your computer, or use the built-in **📁 File manager**.

## 🔄 Updating

Update notifications appear automatically in Home Assistant. Open the add-on and
click **Update**; the changelog is shown in the add-on UI.

## ⚠️ What it does *not* do

- It does **not** write to your ESPHome config or your fonts folder, and never
  writes to your HA states — the live data is preview-only by design. You copy the
  generated YAML into your device config yourself.

## 🤝 Contributing

Bug reports and ideas are welcome — open an
[issue](https://github.com/Cl3tus/HA-Eink-Studio-App/issues/new/choose) or read the
[contributing guide](CONTRIBUTING.md).

## 📝 License & credits

Released under the [MIT License](LICENSE).

Built with [Konva](https://konvajs.org/), [js-yaml](https://github.com/nodeca/js-yaml)
and [Material Design Icons](https://pictogrammers.com/library/mdi/), all bundled
locally for fully offline use. UI available in English and Dutch.

---

<p align="center">
  Proudly vibecoded by <b>Cletus</b> &amp; <a href="https://claude.com/claude-code">Claude Code</a> 🤖✨
</p>
