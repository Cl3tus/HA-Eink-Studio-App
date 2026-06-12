# Bestandsbeheer & SAMBA

*🇬🇧 [English](File-Manager-and-SAMBA-EN) · 🏠 [Home](Home-NL)*

Open **📁 Bestanden** (bovenbalk) — of ga naar `files.html`.

> 📷 *Screenshot: de bestandsbeheerder met de boom en een bestand geselecteerd.* →
> `docs/screenshots/File-Manager.png` *(zie ook de bestaande File-Manager-screenshots)*

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

> 📷 *Screenshots staan al in de repo: `E-ink-Studio-File-Manager-Editor.png`,
> `E-ink-Studio-File-Manager-Font-Viewer.png`.*

### Opslagstructuur (SAMBA)

Dezelfde opslag is bereikbaar via **SAMBA** op
`\\<HA-IP>\addon_configs\<slug>_eink_studio\`:

```
projects/   ← opgeslagen ontwerpen (.json)
fonts/      ← geüploade fonts (incl. het meegeleverde MDI-ttf)
profiles/   ← profiel-instellingen (.json)
```

Bewerk en back-up ze vanaf je computer, of gebruik de ingebouwde bestandsbeheerder.
