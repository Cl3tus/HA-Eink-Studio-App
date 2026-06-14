# File Manager & SAMBA

*🇳🇱 [Nederlands](File-Manager-and-SAMBA-NL) · 🏠 [Home](Home-EN)*

Open **📁 Files** (top bar) — or browse to `files.html`.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/File-Manager.png" alt="File-Manager" width="100%">
</p>

### What you can do

- **Tree** view, **fully expanded by default** (collapse a folder to hide its files).
- **Multi-select** with row checkboxes; **upload**, **download**, **rename**, **move**,
  **delete**.
- Built-in **text editor** with undo/redo (double-click a text file).
- **Font preview** — double-click a `.ttf` to preview the glyphs.
- Drag files onto the window to upload.
- In-app **confirm dialogs** (discard unsaved changes, delete files) match the editor —
  no native browser pop-ups.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/File-Manager-Editor.png" alt="File-Manager-Editor" width="49%">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/en/File-Manager-Font-Viewer.png" alt="File-Manager-Font-Viewer" width="49%">
</p>

### Storage layout (SAMBA)

The same storage is reachable over **SAMBA** at
`\\<HA-IP>\addon_configs\<slug>_eink_studio\`:

```
projects/   ← saved designs (.json)
fonts/      ← uploaded fonts (incl. the bundled MDI ttf)
profiles/   ← profile settings (.json)
```

Edit and back them up from your computer, or use the built-in file manager.
