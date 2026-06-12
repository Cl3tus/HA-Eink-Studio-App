# File Manager & SAMBA

*🇳🇱 [Nederlands](File-Manager-and-SAMBA-NL) · 🏠 [Home](Home-EN)*

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
- In-app **confirm dialogs** (discard unsaved changes, delete files) match the editor —
  no native browser pop-ups.

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
