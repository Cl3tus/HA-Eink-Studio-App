# Fonts & Colours

*🇳🇱 [Nederlands](Fonts-and-Colours-NL) · 🏠 [Home](Home-EN)*

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

### Weight & italic

- **Weight** is a named dropdown — **Thin 100 · Extra Light 200 · Light 300 · Regular
  400 · Medium 500 · Semi Bold 600 · Bold 700 · Extra Bold 800 · Black 900**. For Google
  Fonts the weight is written into the YAML (`weight: 700`).
- **Italic** (Google Fonts) emits `italic: true`.
- Roboto and Noto Sans Display are bundled as **variable fonts**, so every weight 100–900
  (and Roboto italic) renders **distinctly** in the editor — no snapping two cuts
  together.

### Preview

Click a loaded font id in the list for an **inline preview**. In the edit dialog the
preview updates **live** as you change the **size** (including the ▲/▼ steppers), the
**weight** and the **italic** toggle.

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

Set the **model** in [Profile settings](Profiles-and-YAML-Blocks-EN) and the palette
adapts. Each colour becomes a `color:` entry in the YAML. See also **Negative mode** on
the [Profiles & YAML Blocks](Profiles-and-YAML-Blocks-EN) page for a black-screen design.
