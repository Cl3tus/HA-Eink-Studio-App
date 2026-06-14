# Snel starten

*🇬🇧 [English](Quick-Start-EN) · 🏠 [Home](Home-NL)*

Van een leeg canvas naar kant-en-klare YAML in zes stappen.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Quick-Start-Empty-Darkmode-NL.png" alt="Quick-Start-Empty-Darkmode" width="49%">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Quick-Start-Empty-Lightmode-NL.png" alt="Quick-Start-Empty-Lightmode" width="49%">
</p>

1. **Open** E-ink Studio in de zijbalk.
2. **Live data ophalen** — klik op **○ Live** in de bovenbalk om je echte Home
   Assistant-entiteiten op te halen (alleen-lezen).
3. **Bronnen toevoegen** — open **Bronnen / Sources → From Home Assistant**, zoek en
   voeg de sensoren toe die je wilt tonen (zie [Bronnen & type-detectie](Sources-and-Types-NL)).
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
- Gebruik het [wachtscherm](Screens-NL) voor een apart *wachten-op-data*-ontwerp, en
  **Meerdere schermen gebruiken** voor meerdere via HA schakelbare schermen.
- Laat het vinkje **herstelcode** aan bij het genereren, zodat je de YAML later kunt
  terugplakken en het hele bewerkbare ontwerp herstelt.
