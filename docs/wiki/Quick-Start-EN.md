# Quick Start

*🇳🇱 [Nederlands](Quick-Start-NL) · 🏠 [Home](Home-EN)*

From an empty canvas to a ready-to-paste YAML in six steps.

> 📷 *Screenshot: the editor right after opening, empty canvas with the palette on the
> left.* → save as `docs/screenshots/Quick-Start-Empty.png`

1. **Open** E-ink Studio from the sidebar.
2. **Pull live data** — click **○ Live** in the top bar to fetch your real Home
   Assistant entities (read-only).
3. **Add sources** — open **Bronnen / Sources → From Home Assistant**, search and add
   the sensors you want to show (see [Sources & Type Detection](Sources-and-Types-EN)).
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
- Use the [waiting screen](Screens-EN) for a separate *waiting-for-data* design, and
  **Use multiple screens** for several HA-switchable screens.
- Keep the **recovery code** checkbox on when generating, so you can paste the YAML
  back later and restore the whole editable design.
