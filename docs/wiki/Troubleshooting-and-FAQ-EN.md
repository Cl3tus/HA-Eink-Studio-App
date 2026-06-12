# Troubleshooting & FAQ

*🇳🇱 [Nederlands](Troubleshooting-and-FAQ-NL) · 🏠 [Home](Home-EN)*

### Build error: *"Font … is missing N glyphs"*

An **icon (MDI) font** has no text/digit glyphs (space, digits, `%`, `°`, …). If a
build complains about a missing glyph on `materialdesignicons-webfont.ttf`, the font
was carrying text characters it can't render. E-ink Studio keeps MDI fonts to **icons
only** and auto-migrates older profiles on load. Re-generate the YAML and the error is
gone.

If you see it on a **text font**, that font simply doesn't contain that character —
pick a font that does, or remove the character.

### A graph crashes the device / reboots

A **graph trace must use a numeric source.** Binding a trace to a string/bool/time
source — or a non-numeric Home Assistant entity such as an `ai_task` — can corrupt
memory and crash the ESPHome graph at runtime. The pre-generate check flags this, and
[Sources & Type Detection](Sources-and-Types-EN) shows the entity's real type so you can
fix it before flashing.

### Font weights all look the same in the preview

Roboto and Noto Sans Display are bundled as **variable fonts**, so weights 100–900 each
render distinctly. If everything still looks identical after an update, **hard-refresh**
the editor tab once so the browser drops the old cached font files.

### My font preview looks wrong / approximate

Upload the actual `.ttf` via **Fonts** so the preview uses the real glyphs. Google
Fonts render with a bundled fallback until ESPHome downloads them at build time.

### Text looks shifted on the device vs. the editor

It shouldn't — placement is pixel-accurate (text sits on the real font baseline). Make
sure the **font on the device matches the font in the editor** (same file/size). For
local fonts, the path in the YAML must match your ESPHome `fonts/` folder exactly.

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
[File Manager & SAMBA](File-Manager-and-SAMBA-EN).
