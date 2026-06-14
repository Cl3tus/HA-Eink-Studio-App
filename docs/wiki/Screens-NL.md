# Schermen

*🇬🇧 [English](Screens-EN) · 🏠 [Home](Home-NL)*

Een ontwerp heeft altijd een **Hoofd**-scherm en een optioneel **Wachten-op-data**-scherm,
en kan **tot 10** via Home Assistant schakelbare schermen hebben. Wissel ertussen met de
kiezer boven het canvas.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Screens-NL.png" alt="Screens" width="100%">
</p>

### Wachtscherm

- **Wachten** is een *wachten-op-data*-scherm, getoond tot de eerste sensorwaarde na het
  booten binnenkomt. Een nieuw profiel zet standaard een **"WACHTEN OP DATA…"**-tekst
  (font `font_small`).
- Zet het aan/uit bij **Profiel-instellingen → Wachtscherm gebruiken**. Als het uit
  staat, wordt de boot-`if/else` helemaal weggelaten.
- De gegenereerde lambda verpakt de wacht-elementen in:

  ```cpp
  if (id(initial_data_received) == false) {
    // Elementen wachtscherm
  } else {
    // Elementen hoofd-/actief scherm
  }
  ```

### Meerdere schermen

Zet **Meerdere schermen gebruiken** aan in [Profiel-instellingen](Profiles-and-YAML-Blocks-NL)
(per profiel onthouden). De kiezer toont dan knoppen om schermen **toe te voegen**, te
**dupliceren**, te **hernoemen** en te **verwijderen** (het hoofdscherm kan niet hernoemd
of verwijderd worden). Elk scherm heeft eigen elementen; **kopiëren/plakken werkt tussen
schermen** (Ctrl+C op het ene, Ctrl+V op het andere — de positie blijft behouden).

Bij twee of meer schermen vertakt de display-lambda per scherm en leest hij het actieve
scherm uit de HA-bediening, en een scherm wisselen forceert een **directe hertekening**
(onafhankelijk van nieuwe sensordata).

### Home Assistant-bediening

Kies die bij **Profiel-instellingen → Generated YAML Blocks → Schermbediening in HA**:

| Optie | Wat het genereert |
|-------|-------------------|
| **Dropdown (select)** | Een template `select`; de opties zijn je schermnamen. |
| **Buttons** | Eén template `button` per scherm (handig op een dashboard). |
| **Beide** | De dropdown *én* de buttons. |
| **Geen** | Geen HA-bediening — de schermselect blijft `internal: true`, zodat het display blijft werken terwijl je hem vanuit je eigen automations aanstuurt. |

### Display-mode-switches (Automatisch verversen / Statisch / Rotatie)

Met **Refresh-logica** aan genereert de YAML ook gekoppelde Home Assistant-**switches**
die bepalen wat het display elk interval doet. **Er staat altijd precies één aan**
(standaard **Automatisch verversen**, onthouden over reboots):

| Switch | Wat het elk interval doet |
|--------|---------------------------|
| **Automatisch verversen** | Ververst het display *als een gekoppelde sensor nieuwe data heeft* (logt + slaat de ronde anders over). |
| **Statisch Display** | Bevriest het scherm — na de eerste render stopt het verversen. |
| **Scherm rotatie** | Schuift naar het volgende scherm (vereist ≥2 schermen + de rotatie-optie). Aanzetten zet ook Automatisch verversen aan. |

Eén aanzetten zet de conflicterende uit, en je kunt nooit alle drie uit laten staan — er
is dus altijd een gedefinieerde modus. Automatisch verversen en Statisch horen bij
**Refresh-logica**; Scherm rotatie is de **Schermrotatie**-optie (alleen multi-screen).

> Schermbediening en rotatie zijn grijs tenzij *Meerdere schermen gebruiken* aan staat.
> Ontwerpen met één scherm genereren exact dezelfde YAML als voorheen, je bestaande
> lay-out migreert automatisch naar het eerste scherm, en de base64-herstelcode
> round-trip't alle schermen.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Screen-Control-Blocks-NL.png" alt="Screen-Control-Blocks" width="100%">
  <br><em>Schermbediening in HA + de rotatie-switch</em>
</p>

