# Quick Start

## 🇬🇧 English

From an empty canvas to a ready-to-paste YAML in six steps.

> 📷 *Screenshot: the editor right after opening, empty canvas with the palette on the
> left.* → save as `docs/screenshots/Quick-Start-Empty.png`

1. **Open** E-ink Studio from the sidebar.
2. **Pull live data** — click **○ Live** in the top bar to fetch your real Home
   Assistant entities (read-only).
3. **Add sources** — open **Bronnen / Sources → From Home Assistant**, search and add
   the sensors you want to show.
4. **Drag a Value** onto the canvas and, in the inspector on the right, bind it to a
   source. Set its **format** (decimals, prefix/suffix) and **transform** if needed.
5. **Generate** — click **&lt;/&gt; Generate YAML**, then **Copy** or
   **Download .yaml**.
6. **Paste** the YAML into your ESPHome device config, and put any **local TTF fonts**
   into your ESPHome `fonts/` folder.

That's it — flash your device and the layout appears.

### Tips

- Pick the right **model** first (Profile settings ⚙) so the canvas size and colour
  palette match your panel.
- Use **Two Screens** to design a separate *waiting-for-data* screen.
- Keep the **recovery code** checkbox on when generating, so you can paste the YAML
  back later and restore the whole editable design.

---

## 🇳🇱 Nederlands

Van een leeg canvas naar kant-en-klare YAML in zes stappen.

> 📷 *Screenshot: de editor net na openen, leeg canvas met het palet links.* →
> opslaan als `docs/screenshots/Quick-Start-Empty.png`

1. **Open** E-ink Studio in de zijbalk.
2. **Live data ophalen** — klik op **○ Live** in de bovenbalk om je echte Home
   Assistant-entiteiten op te halen (alleen-lezen).
3. **Bronnen toevoegen** — open **Bronnen / Sources → From Home Assistant**, zoek en
   voeg de sensoren toe die je wilt tonen.
4. **Sleep een Waarde** op het canvas en koppel hem in de inspector rechts aan een
   bron. Stel z'n **opmaak** (decimalen, prefix/suffix) en eventueel **transform** in.
5. **Genereren** — klik op **&lt;/&gt; Genereer YAML**, daarna **Kopiëren** of
   **Download .yaml**.
6. **Plak** de YAML in je ESPHome-config, en zet eventuele **lokale TTF-fonts** in de
   `fonts/`-map van je ESPHome-config.

Klaar — flash je device en de lay-out verschijnt.

### Tips

- Kies eerst het juiste **model** (Profiel-instellingen ⚙) zodat de canvasgrootte en
  het kleurenpalet bij je paneel passen.
- Gebruik **Twee schermen** voor een apart *wachten-op-data*-scherm.
- Laat het vinkje **herstelcode** aan bij het genereren, zodat je de YAML later kunt
  terugplakken en het hele bewerkbare ontwerp herstelt.
