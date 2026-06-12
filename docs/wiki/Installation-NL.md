# Installatie

*🇬🇧 [English](Installation-EN) · 🏠 [Home](Home-NL)*

### 1. Repository toevoegen

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2FCl3tus%2FHA-Eink-Studio-App)

Of handmatig: **Instellingen → Add-ons → Add-on-store → ⋮ (rechtsboven) →
Repositories**, plak `https://github.com/Cl3tus/HA-Eink-Studio-App` en klik **Toevoegen**.

### 2. Installeren & starten

1. Ververs de store en open **E-ink Studio**.
2. Klik op **Installeren** (de eerste build duurt een paar minuten — draait op
   `aarch64` en `amd64`).
3. Klik op **Starten** en open **E-ink Studio** in de zijbalk (Ingress).

### 3. Add-on-opties

| Optie | Waarden | Omschrijving |
|-------|---------|--------------|
| `language` | `auto` · `nl` · `en` | UI-taal. `auto` volgt Home Assistant. |
| `theme` | `auto` · `light` · `dark` | Kleurthema. `auto` volgt Home Assistant. |

Beide kun je ook live in de editor omzetten (bovenbalk). De add-on-optie is alleen de
standaard.

### 4. Updaten

Update-meldingen verschijnen automatisch in Home Assistant. Open de add-on en klik op
**Update**; de changelog staat in de add-on-UI. Doe na een update één keer een
**harde refresh** van het editor-tabblad als assets oud lijken (de app doet al
cache-busting per versie).

### Ondersteunde architecturen

Alleen `aarch64` en `amd64`.
