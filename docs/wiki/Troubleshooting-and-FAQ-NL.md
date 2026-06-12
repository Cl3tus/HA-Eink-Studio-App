# Probleemoplossing & FAQ

*🇬🇧 [English](Troubleshooting-and-FAQ-EN) · 🏠 [Home](Home-NL)*

### Build-error: *"Font … is missing N glyphs"*

Een **icon-font (MDI)** heeft geen tekst/cijfer-glyphs (spatie, cijfers, `%`, `°`, …).
Als een build klaagt over een ontbrekende glyph op `materialdesignicons-webfont.ttf`,
droeg het font tekst-tekens die het niet kan tekenen. E-ink Studio houdt MDI-fonts op
**alleen iconen** en migreert oudere profielen automatisch bij het laden. Genereer de
YAML opnieuw en de fout is weg.

Zie je het bij een **tekstfont**, dan bevat dat font dat teken simpelweg niet — kies een
font dat het wel heeft, of haal het teken weg.

### Een grafiek laat het device crashen / herstarten

Een **grafiek-trace moet een numerieke bron gebruiken.** Een trace koppelen aan een
string/bool/tijd-bron — of een niet-numerieke Home Assistant-entiteit zoals een `ai_task`
— kan geheugen corrupten en de ESPHome-grafiek tijdens runtime laten crashen. De
pre-generate-check markeert dit, en [Bronnen & type-detectie](Sources-and-Types-NL) toont
het echte type van de entiteit zodat je het vóór het flashen kunt fixen.

### Alle font-weights zien er hetzelfde uit in de preview

Roboto en Noto Sans Display zijn gebundeld als **variabele fonts**, dus weights 100–900
renderen elk apart. Lijkt alles na een update nog identiek, doe dan één keer een
**harde refresh** van het editor-tabblad zodat de browser de oude cache-fonts loslaat.

### Mijn font-preview ziet er fout/benaderend uit

Upload de echte `.ttf` via **Fonts** zodat de preview de echte glyphs gebruikt. Google
Fonts tonen een meegeleverde fallback totdat ESPHome ze tijdens de build downloadt.

### Tekst staat verschoven op het device t.o.v. de editor

Dat hoort niet — plaatsing is pixel-nauwkeurig (tekst op de echte font-baseline). Zorg
dat het **font op het device overeenkomt met het font in de editor** (zelfde
bestand/grootte). Voor lokale fonts moet het pad in de YAML exact je ESPHome
`fonts/`-map matchen.

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
[Bestandsbeheer & SAMBA](File-Manager-and-SAMBA-NL).
