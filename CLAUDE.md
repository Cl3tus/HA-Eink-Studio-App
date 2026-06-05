# CLAUDE.md

Project notes for Claude Code. These are the non-obvious conventions — read them
before editing so a fresh session doesn't relearn the hard way.

## What this is

**E-ink Studio** — a Home Assistant add-on: a WYSIWYG editor for ESPHome e-paper
displays. You drag elements onto a paper-accurate canvas, bind them to live HA
sensor values, and generate ready-to-paste ESPHome `display:` lambda + YAML.
It is **preview-only**: it never writes to the device config or HA states.

Repo: `github.com/Cl3tus/HA-Eink-Studio-App` · default branch `main`.

## Layout

```
README.md                     ← GitHub landing page (relative image paths OK)
repository.yaml               ← HA add-on repository manifest
docs/screenshots/             ← screenshots (capitalised filenames!)
eink_studio/
  config.yaml                 ← add-on manifest: version, arch, options, ingress
  build.yaml                  ← base images per arch (KEEP IN SYNC with config arch)
  Dockerfile, run.sh, server.py, requirements.txt
  README.md                   ← add-on store "About" tab
  DOCS.md                     ← add-on "Documentation" tab
  CHANGELOG.md                ← shown in the add-on UI
  translations/{nl,en}.yaml   ← option labels per HA language
  www/                        ← frontend (index.html, files.html, app.js, files.js,
                                lang.js, theme.js, styles.css) + bundled libs
```

## Frontend stack

Vanilla JS — no build step. **Konva** (canvas), **js-yaml**, **Material Design
Icons**, all **bundled locally for fully offline use** (nothing from a CDN). UI is
**bilingual NL/EN** (`lang.js` + `_t('nl', 'en')`); keep both strings in sync.
There is a custom 1-px tooltip system duplicated in both `app.js` and `files.js` —
edit both when you touch it.

## Releasing — bump the version in ALL of these

A version bump is not one edit. Update every spot or HA / the browser cache will
serve stale assets:

1. `eink_studio/config.yaml` → `version: "X.Y.Z"`
2. `eink_studio/run.sh` → `ADDON_VERSION="X.Y.Z"`
3. `README.md` (root) version badge
4. `eink_studio/README.md` version badge
5. `eink_studio/www/index.html` → cache-bust `?v=X.Y.Z` on every script/style tag
6. `eink_studio/www/files.html` → same cache-bust
7. `eink_studio/CHANGELOG.md` → add an entry **before** committing (always)

## Other conventions

- **Supported arch = `aarch64` + `amd64` only.** Keep `config.yaml` `arch:` and
  `build.yaml` `build_from:` and the arch badges in both READMEs all in sync.
- **HA markdown needs absolute image URLs.** `DOCS.md` and `eink_studio/README.md`
  render inside HA, where relative paths don't resolve — use
  `https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/<File>.png`.
  The root `README.md` is GitHub-only, so relative `docs/screenshots/...` is fine.
- **Theme detection uses `--primary-background-color`, NOT `prefers-color-scheme`**
  (the HA iframe doesn't expose the latter reliably). See `theme.js`.
- Screenshot filenames in `docs/screenshots/` are **Capitalised-With-Dashes** —
  match the exact case in `<img>` tags (raw URLs are case-sensitive).

## Git workflow

- **Commit/push only when the user asks.**
- The user frequently edits files directly on GitHub, so the remote is often ahead:
  `git pull --rebase origin main` before `git push origin main`.
- End commit messages with:
  `Co-Authored-By: Claude Opus 4.8 <noreply@anthropic.com>`
- Files are CRLF on this Windows checkout; the LF→CRLF warnings on commit are benign.
