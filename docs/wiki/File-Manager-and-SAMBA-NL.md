# Bestandsbeheer & SAMBA

*🇬🇧 [English](File-Manager-and-SAMBA-EN) · 🏠 [Home](Home-NL)*

Open **📁 Bestanden** (bovenbalk) — of ga naar `files.html`.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/File-Manager-NL.png" alt="File-Manager" width="100%">
</p>

### Wat je kunt doen

- **Boom**-weergave, **standaard volledig uitgeklapt** (klap een map in om de bestanden
  te verbergen).
- **Multi-selectie** met rij-checkboxes; **uploaden**, **downloaden**, **hernoemen**,
  **verplaatsen**, **verwijderen**.
- Ingebouwde **teksteditor** met ongedaan maken/opnieuw (dubbelklik een tekstbestand).
- **Font-preview** — dubbelklik een `.ttf` om de glyphs te bekijken.
- Sleep bestanden op het venster om te uploaden.
- In-app **bevestigingsvensters** (wijzigingen verwerpen, bestanden verwijderen) passen
  bij de editor — geen native browser-pop-ups.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/File-Manager-Editor-NL.png" alt="File-Manager-Editor" width="49%">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/File-Manager-Font-Viewer-NL.png" alt="File-Manager-Font-Viewer" width="49%">
</p>

### Opslagstructuur (SAMBA)

Dezelfde opslag is bereikbaar via **SAMBA** op
`\\<HA-IP>\addon_configs\<slug>_eink_studio\`:

```
projects/   ← opgeslagen ontwerpen (.json)
fonts/      ← geüploade fonts (incl. het meegeleverde MDI-ttf)
profiles/   ← profiel-instellingen (.json)
```

Bewerk en back-up ze vanaf je computer, of gebruik de ingebouwde bestandsbeheerder.
