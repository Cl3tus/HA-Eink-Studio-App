# Schermen

*🇬🇧 [English](Screens-EN) · 🏠 [Home](Home-NL)*

Een ontwerp heeft altijd een **Hoofd**-scherm en een optioneel **Wachten-op-data**-scherm,
en kan **tot 10** via Home Assistant schakelbare schermen hebben. Wissel ertussen met de
kiezer boven het canvas.

> 📷 *Screenshot: de schermkiezer met de knoppen toevoegen / dupliceren / hernoemen /
> verwijderen en de device-rotatie.* → `docs/screenshots/Screens.png`

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

### Schermrotatie (HA-switch)

**Schermrotatie (HA-switch)** (zelfde paneel) voegt een template `switch` toe die aan
Home Assistant wordt aangeboden. Zolang die aan staat, springt het display bij elk
ververs-interval naar het volgende scherm — geen `input_boolean` of
`configuration.yaml`-bewerking nodig.

> Schermbediening en rotatie zijn grijs tenzij *Meerdere schermen gebruiken* aan staat.
> Ontwerpen met één scherm genereren exact dezelfde YAML als voorheen, je bestaande
> lay-out migreert automatisch naar het eerste scherm, en de base64-herstelcode
> round-trip't alle schermen.
