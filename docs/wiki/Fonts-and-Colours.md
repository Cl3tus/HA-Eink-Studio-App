# Fonts & Colours

## 🇬🇧 English

Open **Fonts** (top bar).

> 📷 *Screenshot: the Fonts dialog with the font list and the "Add font" form, an
> inline preview open.* → `docs/screenshots/Fonts-Dialog.png`

### Adding a font

Pick a **Font Source**:

- **Upload Font** — a local `.ttf/.otf/.woff/.pcf/.bdf`. Upload the file so the preview
  is accurate and it lands in your `fonts/` folder. Set the `id`, `size` and `path`.
- **MDI Fonts** — the bundled Material Design Icons font (v7.4.47). A link to the
  [MDI icon library](https://pictogrammers.com/library/mdi/) opens in a new tab.
- **Google Fonts** — set `family` + `weight`. ESPHome downloads it at build time.
- **Web Fonts** — a direct download URL to a `.ttf/.otf/.woff`.

The same TTF filename is uploaded only once (de-duplicated).

### Preview

Click a loaded font id in the list for an **inline preview**. In the edit dialog the
preview updates **live** as you change the **size** (including the ▲/▼ steppers) and,
for Google Fonts, the **weight**.

### Download fonts (.zip)

The **Download Fonts (.zip)** button — bottom-left of the Fonts dialog, next to
*Cancel* / *Save* — bundles every file in the add-on's `fonts/` folder into a single
`eink-fonts.zip`. Unpack it into your ESPHome `config/fonts/` folder so the build finds
the exact files your design references.

E-ink Studio never writes into the ESPHome config itself: ESPHome only loads fonts that
live next to its own YAML, and reaching into another add-on's config would require a
broad read/write mount — a security risk we deliberately avoid. The zip keeps copying
the fonts a quick but **manual** step on your side.

### Glyphs (what ends up in the YAML)

- **Text fonts** get the printable-ASCII set (so typed text never renders as "tofu"),
  plus any special characters your design uses.
- **Icon (MDI) fonts** get **only the icons you actually use**, one per line with a
  `# mdi:<name>` comment. They carry **no** text/digit glyphs — an icon font doesn't
  contain them, and adding them makes the ESPHome build fail with *"Font … is missing
  N glyphs"*.

### Colours

Colours follow the display's **colour type** automatically:

- **mono** (black/white), **black-white-red** (B-W-R), or **7-colour**.

Set the **model** in [Profile settings](Profiles-and-YAML-Blocks) and the palette
adapts. Each colour becomes a `color:` entry in the YAML.

---

## 🇳🇱 Nederlands

Open **Fonts** (bovenbalk).

> 📷 *Screenshot: het Fonts-venster met de fontlijst en het "Font toevoegen"-formulier,
> een inline preview open.* → `docs/screenshots/Fonts-Dialog.png`

### Een font toevoegen

Kies een **Font Source**:

- **Upload font** — een lokaal `.ttf/.otf/.woff/.pcf/.bdf`. Upload het bestand zodat de
  preview klopt en het in je `fonts/`-map komt. Zet de `id`, `size` en `path`.
- **MDI Fonts** — het meegeleverde Material Design Icons-font (v7.4.47). Een link naar
  de [MDI-iconenbibliotheek](https://pictogrammers.com/library/mdi/) opent in een nieuw
  tabblad.
- **Google Fonts** — zet `family` + `weight`. ESPHome downloadt het tijdens de build.
- **Web Fonts** — een directe download-URL naar een `.ttf/.otf/.woff`.

Dezelfde TTF-bestandsnaam wordt maar één keer geüpload (ontdubbeld).

### Preview

Klik een geladen font-id in de lijst voor een **inline preview**. In het bewerk-venster
ververst de preview **live** terwijl je de **grootte** aanpast (ook met de ▲/▼-knopjes)
en, bij Google Fonts, de **weight**.

### Fonts downloaden (.zip)

De knop **Download Fonts (.zip)** — linksonder in het Fonts-venster, naast *Annuleren* /
*Opslaan* — bundelt elk bestand uit de `fonts/`-map van de add-on in één
`eink-fonts.zip`. Pak die uit in je ESPHome `config/fonts/`-map, zodat de build precies
de bestanden vindt waar je ontwerp naar verwijst.

E-ink Studio schrijft zelf nooit in de ESPHome-config: ESPHome laadt alleen fonts die
naast zijn eigen YAML staan, en in de config van een andere add-on schrijven zou een
brede lees/schrijf-mount vereisen — een security-risico dat we bewust vermijden. De zip
houdt het kopiëren een snelle maar **handmatige** stap aan jouw kant.

### Glyphs (wat in de YAML komt)

- **Tekstfonts** krijgen de printbare-ASCII-set (zodat getypte tekst nooit als "tofu"
  verschijnt), plus eventuele speciale tekens die je ontwerp gebruikt.
- **Icon-fonts (MDI)** krijgen **alleen de iconen die je echt gebruikt**, één per regel
  met een `# mdi:<naam>`-commentaar. Ze bevatten **geen** tekst/cijfer-glyphs — een
  icon-font heeft die niet, en ze toevoegen laat de ESPHome-build falen met *"Font … is
  missing N glyphs"*.

### Kleuren

Kleuren volgen automatisch het **kleurtype** van het display:

- **mono** (zwart/wit), **zwart-wit-rood** (B-W-R), of **7-kleuren**.

Stel het **model** in bij [Profiel-instellingen](Profiles-and-YAML-Blocks) en het
palet past zich aan. Elke kleur wordt een `color:`-entry in de YAML.
