# Waarden, opmaak & transforms

*🇬🇧 [English](Values-Format-Transforms-EN) · 🏠 [Home](Home-NL)*

Selecteer een **Waarde**-element → inspector → **Bron** + **Opmaak & transform**.

> 📷 *Screenshot: de inspector van een Waarde-element met Bron + Opmaak & transform.*
> → `docs/screenshots/Inspector-Value.png` *(bestaat al)*

### Bron

Kies een Home Assistant-sensor die je onder **Bronnen** hebt toegevoegd (zie
[Bronnen & type-detectie](Sources-and-Types-NL)). Met **Live** aan toont de preview de
echte actuele waarde; anders de **sample**-waarde van de bron.

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
