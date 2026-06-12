# E-ink Studio — Wiki source

These Markdown files are the **source** for the project's GitHub Wiki. They're kept
here in the main repo (versioned alongside the code), then published to the GitHub Wiki.

## Language structure

The wiki is **split per language**. `Home.md` is a small **language picker** (English /
Nederlands); from there each topic exists as two single-language pages with a `-EN` or
`-NL` suffix. Every page has a one-click language switch at the top, and `_Sidebar.md`
lists both languages in separate sections.

- `Home.md` — language picker (links to `Home-EN` / `Home-NL`).
- `Home-EN.md` / `Home-NL.md` — the per-language landing/index pages.
- `_Sidebar.md` — navigation, grouped **English** and **Nederlands**.
- Each topic: `<Topic>-EN.md` + `<Topic>-NL.md`. Inter-page links always carry the same
  suffix (an EN page links to other `-EN` pages, an NL page to `-NL`).

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
  hyphenated, language-suffixed names the inter-page links expect (e.g. `Screens-EN.md`).

## Pages

Per language (`-EN` / `-NL`): `Installation`, `Quick-Start`, `Interface-Tour`,
`Elements`, `Values-Format-Transforms`, `Sources-and-Types`, `Rulers-Guides-Snapping`,
`Fonts-and-Colours`, `Graphs-and-Legend`, `Screens`, `Profiles-and-YAML-Blocks`,
`Generate-and-Import-YAML`, `File-Manager-and-SAMBA`, `Keyboard-Shortcuts`,
`Troubleshooting-and-FAQ`. Plus `Home`, `Home-EN`, `Home-NL` and `_Sidebar`.

## Screenshots

The pages reference images under `docs/screenshots/`. Some already exist; the ones still
to be captured are listed in **[SCREENSHOTS-TODO.md](SCREENSHOTS-TODO.md)**.

Wiki pages load images via absolute raw URLs, e.g.
`https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/<File>.png`
— so commit the PNGs to the main repo first, then they render in the wiki.
