# Installation

*🇳🇱 [Nederlands](Installation-NL) · 🏠 [Home](Home-EN)*

### 1. Add the repository

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2FCl3tus%2FHA-Eink-Studio-App)

Or manually: **Settings → Add-ons → Add-on Store → ⋮ (top right) → Repositories**,
paste `https://github.com/Cl3tus/HA-Eink-Studio-App` and click **Add**.

### 2. Install & start

1. Refresh the store and open **E-ink Studio**.
2. Click **Install** (the first build takes a few minutes — it runs on `aarch64`
   and `amd64`).
3. Click **Start**, then open **E-ink Studio** from the sidebar (Ingress).

### 3. Add-on options

| Option | Values | Description |
|--------|--------|-------------|
| `language` | `auto` · `nl` · `en` | UI language. `auto` follows Home Assistant. |
| `theme` | `auto` · `light` · `dark` | Colour theme. `auto` follows Home Assistant. |

Both can also be toggled live inside the editor (top bar). The add-on option is just
the default.

### 4. Updating

Update notifications appear automatically in Home Assistant. Open the add-on and click
**Update**; the changelog is shown in the add-on UI. After an update, **hard-refresh**
the editor tab once if assets look stale (the app already cache-busts on each version).

### Supported architectures

`aarch64` and `amd64` only.
