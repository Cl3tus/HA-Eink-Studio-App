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

### Afwezig- & Vakantie-override-schermen

- Twee optionele **statische** schermen, per profiel aan te zetten via
  **Profiel-instellingen → Afwezig-scherm gebruiken / Vakantie-scherm gebruiken**. Ze
  staan in de kiezer direct na **Wachten** en vóór Scherm 1. Een leeg scherm valt terug
  op een gecentreerde **"AFWEZIG"** / **"VAKANTIE"**-tekst (font `font_small`).
- Geen aparte "Display Override"-entity — Away en Holiday zijn gewoon extra opties
  **toegevoegd aan dezelfde Home Assistant `Screen`-select** naast je ontworpen schermen,
  plus optionele knoppen per optie — stijl via de gedeelde dropdown **HA-bediening
  (scherm & override)** (geen / alleen dropdown / alleen knoppen / beide).
- Away of Holiday kiezen **bevriest het scherm**: de interval-verversing **én** Scherm
  rotatie worden overgeslagen tot je weer een ontworpen scherm kiest. Kiezen zet ook
  **Statisch Display** aan; **Automatisch verversen** weer aanzetten zet de kiezer terug
  op het hoofdscherm — die twee kunnen nooit tegelijk actief zijn.
- Bij beide van toepassing wint **Vakantie** (eerst gecheckt in de lambda). De
  boot-*wachten-op-data*-tak draait nog steeds eerst.
- `screen_select` heeft `restore_value: yes` — een lopende Away/Holiday-status overleeft
  een herstart. Dat blijft crash-veilig omdat de `on_value`-hertekening op
  `initial_data_received` gate't.

  ```cpp
  if (id(initial_data_received) == false) {
    // Wachtscherm
  } else {
    int cs = id(screen_select).active_index().value_or(0);
    if (cs == 2) {        // Holiday
      // Vakantie-scherm
    } else if (cs == 1) { // Away
      // Afwezig-scherm
    } else {
      // ontworpen scherm(en)
    }
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

Eén **HA-bediening (scherm & override)**-dropdown in Profiel-instellingen bepaalt de stijl
voor **zowel** de scherm-keuze (bij meerdere schermen) *als* de Away/Holiday **Display
Override**. Zichtbaar zodra meerdere schermen, Afwezig of Vakantie aan staat:

| Optie | Wat het genereert |
|-------|-------------------|
| **Geen** | Geen HA-bediening — de selects blijven `internal: true`, zodat het display blijft werken terwijl je ze vanuit je eigen automations aanstuurt. |
| **Alleen dropdown** | Een template `select` — schermnamen voor de keuze, *Normal / Away / Holiday* voor de override. |
| **Alleen knoppen** | Eén template `button` per optie (handig op een dashboard). |
| **Dropdown & knoppen** | De dropdown *én* de buttons. |

### Display-mode-switches (Automatisch verversen / Statisch / Rotatie)

Met **Refresh-logica** aan genereert de YAML ook gekoppelde Home Assistant-**switches**
die bepalen wat het display elk interval doet. **Er staat altijd precies één aan**
(standaard **Automatisch verversen**, onthouden over reboots):

| Switch | Wat het elk interval doet |
|--------|---------------------------|
| **Automatisch verversen** | Ververst het display *als een gekoppelde sensor nieuwe data heeft* (logt + slaat de ronde anders over). |
| **Statisch Display** | Bevriest het scherm — na de eerste render stopt het verversen. |
| **Scherm rotatie** | Schuift elk interval naar het volgende scherm; komt automatisch bij ≥2 schermen. Aanzetten zet ook Automatisch verversen aan. |

Eén aanzetten zet de conflicterende uit, en je kunt nooit alle drie uit laten staan — er
is dus altijd een gedefinieerde modus. Automatisch verversen en Statisch horen bij
**Refresh-logica**; Scherm rotatie komt automatisch bij ≥2 schermen. De HA-mode-switches
hebben `entity_category: config`, dus ze staan in HA onder **Configuratie**.

> De scherm-wissel-onderdelen (rotatie, knop per scherm) vereisen *Meerdere schermen
> gebruiken*; de HA-bediening-dropdown verschijnt ook voor alleen Afwezig/Vakantie.
> Ontwerpen met één scherm genereren exact dezelfde YAML als voorheen, je bestaande
> lay-out migreert automatisch naar het eerste scherm, en de base64-herstelcode
> round-trip't alle schermen.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Screen-Control-Blocks-NL.png" alt="Screen-Control-Blocks" width="100%">
  <br><em>Schermbediening in HA + de rotatie-switch</em>
</p>

