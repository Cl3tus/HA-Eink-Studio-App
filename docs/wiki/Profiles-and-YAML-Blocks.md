# Profiles & YAML Blocks

## 🇬🇧 English

A **profile** is one display design. Keep several side by side with the profile picker;
**+** adds one and **⚙** opens its settings.

> 📷 *Screenshot: Profile settings open, with the model picker and the "Generated YAML
> Blocks" toggles.* → `docs/screenshots/Profile-Yaml-Blocks.png` *(already exists)*

### Device

- **Profile name**.
- **Model** — the colour palette adapts to the panel's colour type; for known panels
  the **width/height** are pre-filled to the native resolution (rotation-aware).
- **Rotation**, **width/height**, **canvas background** (preview only).
- **Use waiting screen** on/off (see [Two Screens](Two-Screens)).

### Generated YAML Blocks

Choose exactly which blocks the generator emits — handy when some of these already live
elsewhere in your config:

- **Refresh logic** — `esphome` on_boot + `script` + `time`, with boot priority, delay,
  wait timeout and the refresh interval (minutes).
- **globals**, **font**, **color**, **sensor**, **text_sensor** — each on/off.
- **SPI bus** — `clk_pin` / `mosi_pin`.
- **Display pins** — `data_rate`, `cs_pin` (+ ignore_strapping), `dc_pin`, `busy_pin`
  (+ inverted), `reset_pin`, `reset_duration` — each individually on/off.

### Duplicate / delete

**Duplicate profile** copies the whole design (the copy gets `(1)`, `(2)`, …).
**Delete profile** removes it. Profiles are saved as JSON (see
[File Manager & SAMBA](File-Manager-and-SAMBA)).

---

## 🇳🇱 Nederlands

Een **profiel** is één display-ontwerp. Houd er meerdere naast elkaar met de
profielkiezer; **+** voegt er een toe en **⚙** opent de instellingen.

> 📷 *Screenshot: Profiel-instellingen open, met de modelkiezer en de "Generated YAML
> Blocks"-schakelaars.* → `docs/screenshots/Profile-Yaml-Blocks.png` *(bestaat al)*

### Device

- **Profielnaam**.
- **Model** — het kleurenpalet past zich aan het kleurtype van het paneel aan; voor
  bekende panelen worden **breedte/hoogte** voorgevuld met de native resolutie
  (rotatie-bewust).
- **Rotatie**, **breedte/hoogte**, **canvas-achtergrond** (alleen preview).
- **Wachtscherm gebruiken** aan/uit (zie [Two Screens](Two-Screens)).

### Generated YAML Blocks

Kies precies welke blokken de generator uitschrijft — handig als sommige al elders in
je config staan:

- **Refresh-logica** — `esphome` on_boot + `script` + `time`, met boot-prioriteit,
  vertraging, wacht-timeout en het ververs-interval (minuten).
- **globals**, **font**, **color**, **sensor**, **text_sensor** — elk aan/uit.
- **SPI-bus** — `clk_pin` / `mosi_pin`.
- **Display-pinnen** — `data_rate`, `cs_pin` (+ ignore_strapping), `dc_pin`, `busy_pin`
  (+ inverted), `reset_pin`, `reset_duration` — elk apart aan/uit.

### Dupliceren / verwijderen

**Profiel dupliceren** kopieert het hele ontwerp (de kopie krijgt `(1)`, `(2)`, …).
**Profiel verwijderen** haalt het weg. Profielen worden als JSON opgeslagen (zie
[File Manager & SAMBA](File-Manager-and-SAMBA)).
