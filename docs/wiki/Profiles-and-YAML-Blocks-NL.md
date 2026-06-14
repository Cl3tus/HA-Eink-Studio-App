# Profielen & YAML-blokken

*🇬🇧 [English](Profiles-and-YAML-Blocks-EN) · 🏠 [Home](Home-NL)*

Een **profiel** is één display-ontwerp. Houd er meerdere naast elkaar met de
profielkiezer; **+** voegt er een toe en **⚙** opent de instellingen.

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Profile-Yaml-Blocks-NL.png" alt="Profile-Yaml-Blocks" width="100%">
</p>

### Device

- **Profielnaam**.
- **Model** — het kleurenpalet past zich aan het kleurtype van het paneel aan; voor
  bekende panelen worden **breedte/hoogte** voorgevuld met de native resolutie
  (rotatie-bewust).
- **Rotatie**, **breedte/hoogte**, **canvas-achtergrond** (alleen preview). Nieuwe
  profielen starten met een **20 px-raster**.
- **Wachtscherm gebruiken** aan/uit en **Meerdere schermen gebruiken** aan/uit — zie
  [Schermen](Screens-NL).

### Negatief-modus

**Negatief-modus** (per profiel, onthouden) vult het scherm met de **ink**-kleur en
tekent alles in de **paper**-kleur — een zwart scherm met witte inhoud. De canvas-preview
wordt donker met een licht raster, en de YAML krijgt een `it.fill(id(color_text))` met de
twee basiskleuren (`color_text` ↔ `color_bg`) omgewisseld, zodat je ontwerp leesbaar
blijft.

### Generated YAML Blocks

Kies precies welke blokken de generator uitschrijft — handig als sommige al elders in
je config staan:

- **Refresh-logica** — `esphome` on_boot + `script` + `time`, met boot-prioriteit,
  vertraging, wacht-timeout en het ververs-interval (minuten).
- **Schermbediening in HA** (dropdown / buttons / beide / geen) en **Schermrotatie
  (HA-switch)** — grijs tenzij *Meerdere schermen gebruiken* aan staat (zie
  [Schermen](Screens-NL)).
- **globals**, **font**, **color**, **sensor**, **text_sensor** — elk aan/uit.
- **SPI-bus** — `clk_pin` / `mosi_pin`.
- **Display-pinnen** — `data_rate`, `cs_pin` (+ ignore_strapping), `dc_pin`, `busy_pin`
  (+ inverted), `reset_pin`, `reset_duration` — elk apart aan/uit.

### Footer: opslaan / dupliceren / verwijderen

**Opslaan** blijft grijs tot je echt iets verandert. De footer staat zo: **Profiel
dupliceren** / **Profiel verwijderen** links en **Sluiten** / **Opslaan** rechts.
Dupliceren kopieert het hele ontwerp (de kopie krijgt `(1)`, `(2)`, …); profielen worden
als JSON opgeslagen (zie [Bestandsbeheer & SAMBA](File-Manager-and-SAMBA-NL)).

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Negative-Mode-NL.png" alt="Negative-Mode" width="100%">
  <br><em>Negatief-modus — een zwart scherm met witte inhoud</em>
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/Cl3tus/HA-Eink-Studio-App/main/docs/screenshots/nl/Profile-Settings-Footer-NL.png" alt="Profile-Settings-Footer" width="100%">
  <br><em>Footer: Dupliceren/Verwijderen links, Sluiten/Opslaan rechts (Opslaan grijs)</em>
</p>

