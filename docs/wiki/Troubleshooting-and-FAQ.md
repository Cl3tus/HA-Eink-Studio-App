# Troubleshooting & FAQ

## 🇬🇧 English

### Build error: *"Font … is missing N glyphs"*

An **icon (MDI) font** has no text/digit glyphs (space, digits, `%`, `°`, …). If a
build complains about a missing glyph on `materialdesignicons-webfont.ttf`, the font
was carrying text characters it can't render. E-ink Studio now keeps MDI fonts to
**icons only** and auto-migrates older profiles on load. Re-generate the YAML and the
error is gone.

If you see it on a **text font**, that font simply doesn't contain that character —
pick a font that does, or remove the character.

### My font preview looks wrong / approximate

Upload the actual `.ttf` via **Fonts** so the preview uses the real glyphs. Google
Fonts render with a bundled fallback until ESPHome downloads them at build time.

### Text looks shifted on the device vs. the editor

It shouldn't — placement is pixel-accurate (text sits on the real font baseline). Make
sure the **font on the device matches the font in the editor** (same file/size). For
local fonts, the path in the YAML must match your ESPHome `fonts/` folder exactly.

### The waiting screen uses a font that no longer exists

Older profiles could point at `font_klein`. The studio auto-repoints any element
(including the waiting screen and graph axis/legend) onto a valid text font on load, so
the build no longer fails. New default font id is `font_small`.

### Guides aren't visible

Turn on **Ruler** in the status bar. Guide lines sit **behind** your elements — if a
full-canvas background element covers them, that's expected. Remove a guide via its
**ruler marker** (right-click) or *Remove guides*.

### The canvas scrolls off-screen when zoomed in

That's normal at high zoom; the canvas area scrolls. Use **Fit** in the zoom controls
to bring the whole panel back into view.

### Does it write to my ESPHome config or HA states?

**No.** It's preview-only by design — you copy the generated YAML yourself, and live HA
data is read-only.

### Where are my designs stored?

In the add-on config folder, reachable over SAMBA — see
[File Manager & SAMBA](File-Manager-and-SAMBA).

---

## 🇳🇱 Nederlands

### Build-error: *"Font … is missing N glyphs"*

Een **icon-font (MDI)** heeft geen tekst/cijfer-glyphs (spatie, cijfers, `%`, `°`, …).
Als een build klaagt over een ontbrekende glyph op `materialdesignicons-webfont.ttf`,
droeg het font tekst-tekens die het niet kan tekenen. E-ink Studio houdt MDI-fonts nu op
**alleen iconen** en migreert oudere profielen automatisch bij het laden. Genereer de
YAML opnieuw en de fout is weg.

Zie je het bij een **tekstfont**, dan bevat dat font dat teken simpelweg niet — kies een
font dat het wel heeft, of haal het teken weg.

### Mijn font-preview ziet er fout/benaderend uit

Upload de echte `.ttf` via **Fonts** zodat de preview de echte glyphs gebruikt. Google
Fonts tonen een meegeleverde fallback totdat ESPHome ze tijdens de build downloadt.

### Tekst staat verschoven op het device t.o.v. de editor

Dat hoort niet — plaatsing is pixel-nauwkeurig (tekst op de echte font-baseline). Zorg
dat het **font op het device overeenkomt met het font in de editor** (zelfde
bestand/grootte). Voor lokale fonts moet het pad in de YAML exact je ESPHome
`fonts/`-map matchen.

### Het wachtscherm gebruikt een font dat niet meer bestaat

Oudere profielen konden naar `font_klein` wijzen. De studio wijst elk element (incl. het
wachtscherm en grafiek-as/legenda) bij het laden automatisch naar een geldig tekstfont,
zodat de build niet meer faalt. Nieuwe standaard font-id is `font_small`.

### Hulplijnen zijn niet zichtbaar

Zet **Lineaal** aan in de statusbalk. Hulplijnen staan **achter** je elementen — als een
canvas-vullend achtergrondelement ze bedekt, is dat verwacht. Verwijder een hulplijn via
de **liniaal-marker** (rechtsklik) of *Verwijder gidsen*.

### Het canvas scrollt buiten beeld bij inzoomen

Dat is normaal bij hoge zoom; het canvasgebied scrollt. Gebruik **Passend** in de
zoom-bediening om het hele paneel weer in beeld te brengen.

### Schrijft het naar mijn ESPHome-config of HA-states?

**Nee.** Het is bewust alleen-preview — je kopieert de gegenereerde YAML zelf, en live
HA-data is alleen-lezen.

### Waar staan mijn ontwerpen?

In de add-on-config-map, bereikbaar via SAMBA — zie
[File Manager & SAMBA](File-Manager-and-SAMBA).
