# HA E-ink Studio — Home Assistant Add-on

WYSIWYG-editor voor ESPHome e-ink displays, als Home Assistant add-on (Ingress, zijbalk).

## Repo-structuur
```
HA-Eink-Studio-App/
├── repository.yaml            ← maakt dit een add-on repository
├── README.md                 ← dit bestand
└── eink_studio/              ← de add-on
    ├── config.yaml            ← manifest (ingress, homeassistant_api)
    ├── build.yaml             ← base images per architectuur
    ├── Dockerfile
    ├── requirements.txt
    ├── run.sh                 ← start de server
    ├── server.py              ← serveert frontend + /api (states proxy, opslag)
    ├── DOCS.md                ← documentatie in de HA add-on UI
    └── www/                   ← de editor + meegebundelde libraries
        ├── index.html
        ├── app.js
        ├── styles.css
        └── vendor/            ← Konva, js-yaml, MDI, IBM Plex, Noto, Roboto (offline)
```

## Stap 1 — Code in je GitHub-repo zetten
Je repo: `https://github.com/Cl3tus/HA-Eink-Studio-App`

**Optie A — via de GitHub-website (geen installatie):**
1. Open je repo in de browser → **Add file → Upload files**.
2. Sleep de volledige inhoud van de map `ha-addon/` hierheen (dus `repository.yaml`,
   `README.md` en de map `eink_studio/`). Behoud de mappenstructuur.
3. **Commit changes**.

**Optie B — via VS Code / git (of laat Claude Code het doen):**
```bash
git clone https://github.com/Cl3tus/HA-Eink-Studio-App.git
cd HA-Eink-Studio-App
# kopieer de inhoud van ha-addon/ in deze map
git add .
git commit -m "E-ink Studio add-on v1.0.0"
git push origin main
```

## Stap 2 — Add-on toevoegen in Home Assistant
1. **Settings → Add-ons → Add-on Store**.
2. Rechtsboven **⋮ → Repositories**.
3. Plak: `https://github.com/Cl3tus/HA-Eink-Studio-App` → **Add** → sluiten.
4. Ververs de pagina; onderaan verschijnt **E-ink Studio**. Klik erop → **Install**.
5. Na installatie: **Start**. Open daarna **E-ink Studio** in de zijbalk.

> De eerste build duurt enkele minuten (de add-on bouwt de Docker-image op je HAOS).

## Updaten
- **Frontend-wijziging** (editor zelf): vervang de bestanden in `eink_studio/www/`, commit/push,
  verhoog `version` in `eink_studio/config.yaml`, en in HA: **⋮ → Check for updates → Update**.
- **Server/Dockerfile-wijziging**: idem, maar HA bouwt de image opnieuw bij Update.

Tip: verhoog altijd het `version`-veld in `config.yaml`, anders ziet HA geen update.

## Wat de add-on wel/niet doet
- ✅ Editor in de zijbalk, live read-only preview van HA-states, opslag van projecten/fonts
  in de add-on (`/data`), volledig offline (libs meegebundeld).
- ❌ Schrijft niet naar je ESPHome-config of fonts-map (bewust preview-only).
