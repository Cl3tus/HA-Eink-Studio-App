# File Manager & SAMBA

## 🇬🇧 English

Open **📁 Files** (top bar) — or browse to `files.html`.

> 📷 *Screenshot: the file manager with the tree and a file selected.* →
> `docs/screenshots/File-Manager.png` *(see also the existing File-Manager screenshots)*

### What you can do

- **Tree** view, **fully expanded by default** (collapse a folder to hide its files).
- **Multi-select** with row checkboxes; **upload**, **download**, **rename**, **move**,
  **delete**.
- Built-in **text editor** with undo/redo (double-click a text file).
- **Font preview** — double-click a `.ttf` to preview the glyphs.
- Drag files onto the window to upload.

> 📷 *Screenshots already in the repo: `E-ink-Studio-File-Manager-Editor.png`,
> `E-ink-Studio-File-Manager-Font-Viewer.png`.*

### Storage layout (SAMBA)

The same storage is reachable over **SAMBA** at
`\\<HA-IP>\addon_configs\<slug>_eink_studio\`:

```
projects/   ← saved designs (.json)
fonts/      ← uploaded fonts (incl. the bundled MDI ttf)
profiles/   ← profile settings (.json)
```

Edit and back them up from your computer, or use the built-in file manager.

---

## 🇳🇱 Nederlands

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
