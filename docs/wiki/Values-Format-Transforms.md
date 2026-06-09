# Values, Format & Transforms

## 🇬🇧 English

Select a **Value** element → inspector → **Source** + **Format & transform**.

> 📷 *Screenshot: the inspector of a Value element showing Source + Format & transform.*
> → `docs/screenshots/Inspector-Value.png` *(already exists)*

### Source

Pick a Home Assistant sensor you added under **Sources**. With **Live** on, the preview
shows the real current state; otherwise it uses the source's **sample** value.

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

---

## 🇳🇱 Nederlands

Selecteer een **Waarde**-element → inspector → **Bron** + **Opmaak & transform**.

> 📷 *Screenshot: de inspector van een Waarde-element met Bron + Opmaak & transform.*
> → `docs/screenshots/Inspector-Value.png` *(bestaat al)*

### Bron

Kies een Home Assistant-sensor die je onder **Bronnen** hebt toegevoegd. Met **Live**
aan toont de preview de echte actuele waarde; anders de **sample**-waarde van de bron.

### Opmaak

- **Builder** — prefix, suffix en decimalen. Er wordt **automatisch een spatie vóór de
  suffix** gezet (`1065` + `L/u` → `1065 L/u`); eenheden die tegen het getal plakken
  (`°`, `%`, `‰`) blijven vastzitten.
- **Raw printf** — volledige controle over de format-string (bijv. `%.1f °C`).

### Transforms

| Transform | Resultaat |
|-----------|-----------|
| **Getal → afronden** | Afronden op N decimalen. |
| **Getal → schalen** | Vermenigvuldigen met een factor. |
| **aan/uit → labels** | `on`/`off` naar je eigen tekst. |
| **Tijd** | `HH:MM` of `HH:MM:SS` (met of zonder datum-prefix). |
| **Datum** | `YYYY-MM-DD`, `DD-MM-YYYY`, `DD/MM/YYYY`, `DD-MM`, `DD/MM`. |
| **Custom format** | Een patroon met tokens + NL/EN-namen. |

### Eigen datum/tijd-format

Typ een patroon met deze tokens (en kies NL of EN voor namen):

`{wd}` weekdag kort · `{wday}` weekdag lang · `{mon}` maand kort · `{month}` maand
lang · `{dd}` dag · `{mm}` maandnummer · `{yyyy}`/`{yy}` jaar · `{hh}` uur ·
`{min}` minuut · `{ss}` seconde.

Voorbeeld: `{wd} {dd} {mon}` → **Zo 19 apr** / **Sun 19 Apr**.

> Datum/tijd-transforms gaan uit van een **ISO**-invoer (`YYYY-MM-DD` / `HH:MM:SS` /
> `YYYY-MM-DD HH:MM:SS`), zoals Home Assistant levert. Zet een realistische **sample**
> op de bron om het voorbeeld te zien. Deze transforms genereren een klein helper-blok
> in de lambda met een lengtecontrole, zodat een lege/onbekende waarde bij het booten
> het device niet kan laten crashen.
