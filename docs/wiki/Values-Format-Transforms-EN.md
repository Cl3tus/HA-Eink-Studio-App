# Values, Format & Transforms

*🇳🇱 [Nederlands](Values-Format-Transforms-NL) · 🏠 [Home](Home-EN)*

Select a **Value** element → inspector → **Source** + **Format & transform**.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/Inspector-Value.png" alt="Inspector-Value" width="100%">
</p>

### Source

Pick a Home Assistant sensor you added under **Sources** (see
[Sources & Type Detection](Sources-and-Types-EN)). With **Live** on, the preview shows
the real current state; otherwise it uses the source's **sample** value.

### Format

- **Builder** — prefix, suffix and decimals. A **space is inserted before the suffix
  automatically** (`1065` + `L/h` → `1065 L/h`); units that hug the number (`°`, `%`,
  `‰`) stay attached.
- **Raw printf** — full control over the format string (e.g. `%.1f °C`).

### Transforms

| Transform | Result |
|-----------|--------|
| **Number → round** | Round to N decimals. |
| **Number → scale** | Multiply by a factor. |
| **on/off → labels** | Map `on`/`off` to your own text. |
| **Time** | `HH:MM` or `HH:MM:SS` (works with or without a date prefix). |
| **Date** | `YYYY-MM-DD`, `DD-MM-YYYY`, `DD/MM/YYYY`, `DD-MM`, `DD/MM`. |
| **Custom format** | A pattern with tokens + NL/EN names. |

### Custom date/time format

Type a pattern with these tokens (and pick NL or EN for names):

`{wd}` weekday short · `{wday}` weekday long · `{mon}` month short · `{month}` month
long · `{dd}` day · `{mm}` month number · `{yyyy}`/`{yy}` year · `{hh}` hour ·
`{min}` minute · `{ss}` second.

Example: `{wd} {dd} {mon}` → **Sun 19 Apr** / **Zo 19 apr**.

> Date/time transforms assume an **ISO** input (`YYYY-MM-DD` / `HH:MM:SS` /
> `YYYY-MM-DD HH:MM:SS`), as Home Assistant provides. Set a realistic **sample** on the
> source to preview it. These transforms generate a small helper block in the lambda
> with a length guard, so an empty/unknown value at boot can't crash the device.
