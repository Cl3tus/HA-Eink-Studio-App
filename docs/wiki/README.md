# E-ink Studio — Wiki source

These Markdown files are the **source** for the project's GitHub Wiki. They're kept
here in the main repo (versioned alongside the code), then published to the GitHub Wiki.

## How to publish to the GitHub Wiki

The GitHub Wiki is a **separate git repository** (`…/HA-Eink-Studio-App.wiki.git`). To
publish:

1. Create the wiki once: go to the repo on GitHub → **Wiki** tab → **Create the first
   page** (any content) → Save. This initialises the `.wiki` repo.
2. Clone it and copy these files in:

   ```bash
   git clone https://github.com/Cl3tus/HA-Eink-Studio-App.wiki.git
   cp docs/wiki/*.md HA-Eink-Studio-App.wiki/
   cd HA-Eink-Studio-App.wiki
   git add -A
   git commit -m "Update wiki"
   git push
   ```

GitHub Wiki naming rules:

- `Home.md` is the landing page.
- `_Sidebar.md` is the navigation sidebar (already included).
- Page filenames map to URLs by replacing spaces with `-`. These files already use the
  hyphenated names the inter-page links expect (e.g. `Rulers-Guides-Snapping.md`).

## Pages

`Home`, `Installation`, `Quick-Start`, `Interface-Tour`, `Elements`,
`Values-Format-Transforms`, `Rulers-Guides-Snapping`, `Fonts-and-Colours`,
`Graphs-and-Legend`, `Two-Screens`, `Profiles-and-YAML-Blocks`,
`Generate-and-Import-YAML`, `File-Manager-and-SAMBA`, `Keyboard-Shortcuts`,
`Troubleshooting-and-FAQ`, plus `_Sidebar`.

## Screenshots

The pages reference images under `docs/screenshots/`. Some already exist; the ones still
to be captured are listed in **[SCREENSHOTS-TODO.md](SCREENSHOTS-TODO.md)**.

Wiki pages load images via absolute raw URLs, e.g.
`https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/<File>.png`
— so commit the PNGs to the main repo first, then they render in the wiki.
