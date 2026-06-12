# Contributing to E-ink Studio

Thanks for your interest! This is a Home Assistant add-on — a visual editor for
ESPHome e-paper displays. Contributions, bug reports and ideas are welcome.

## Reporting bugs / requesting features

Open an issue using one of the [templates](https://github.com/Cl3tus/HA-Eink-Studio-App/issues/new/choose).
Please include your **add-on version**, **architecture** (aarch64 / amd64) and, for
bugs, the **add-on log** and any **browser console** errors.

## Project layout

```
docs/screenshots/        screenshots used in the docs
eink_studio/
  config.yaml            add-on manifest (version, arch, options)
  build.yaml             base images per architecture
  server.py, run.sh      Python backend + entrypoint
  README.md / DOCS.md    the "About" and "Documentation" tabs in HA
  CHANGELOG.md           shown in the add-on UI
  www/                   the frontend (vanilla JS + Konva + js-yaml + MDI)
```

The frontend has **no build step** — plain HTML/JS/CSS with all libraries bundled
locally for offline use. Edit the files in `eink_studio/www/` directly.

## Running locally

The simplest path is to install the add-on from a fork of this repository in a Home
Assistant test instance (the add-on store can add a Git repo URL). For pure frontend
tweaks you can also open `eink_studio/www/index.html` in a browser, though live
Home Assistant data and the file manager need the Python backend (`server.py`)
running behind Supervisor.

## Conventions (please follow)

- **Bilingual UI (NL/EN).** User-facing strings go through `_t('nederlands', 'english')`
  in `lang.js`; keep both languages in sync.
- **Supported architectures are `aarch64` and `amd64` only.** If that ever changes,
  update `config.yaml` `arch:`, `build.yaml` `build_from:` and the badges together.
- **Bumping the version touches several files** — see the checklist below.
- **Update `CHANGELOG.md`** with every version bump, before the commit.

### Version-bump checklist

1. `eink_studio/config.yaml` → `version:`
2. `eink_studio/run.sh` → `ADDON_VERSION`
3. Version badges in `README.md` and `eink_studio/README.md`
4. Cache-bust `?v=X.Y.Z` on the script/style tags in `www/index.html` and `www/files.html`
5. A new `eink_studio/CHANGELOG.md` entry

## Pull requests

- Branch off `main`, keep PRs focused, and describe what changed and why.
- Make sure the add-on still starts and the editor loads before opening the PR.

## License

By contributing you agree that your contributions are licensed under the project's
[MIT License](LICENSE).
