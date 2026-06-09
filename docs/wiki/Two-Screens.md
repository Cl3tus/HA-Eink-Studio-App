# Two Screens

## 🇬🇧 English

Each design has two screens, switched with the selector above the canvas:

- **Main** — your normal layout, drawn once data has arrived.
- **Waiting** — a *waiting-for-data* screen, shown until the first sensor value comes
  in after boot.

> 📷 *Screenshot: the screen selector with the Waiting screen active, showing the
> default "WAITING FOR DATA…" text.* → `docs/screenshots/Two-Screens.png`

### How it works

The generated lambda wraps your elements in:

```cpp
if (id(initial_data_received) == false) {
  // Waiting screen elements
} else {
  // Main screen elements
}
```

- A new profile seeds a default **"WAITING FOR DATA…"** text on the waiting screen,
  using the default text font (`font_small`).
- You can design the waiting screen freely, just like the main screen.
- **Copy/paste works between the two screens** (Ctrl+C on one, Ctrl+V on the other —
  the position is kept).
- Turn the waiting screen on/off in **Profile settings → Use waiting screen**. When
  off, the `if/else` is omitted entirely.

---

## 🇳🇱 Nederlands

Elk ontwerp heeft twee schermen, te wisselen met de kiezer boven het canvas:

- **Hoofd** — je normale lay-out, getekend zodra er data is.
- **Wachten** — een *wachten-op-data*-scherm, getoond tot de eerste sensorwaarde na het
  booten binnenkomt.

> 📷 *Screenshot: de schermkiezer met het Wachten-scherm actief, met de standaard
> "WACHTEN OP DATA…"-tekst.* → `docs/screenshots/Two-Screens.png`

### Hoe het werkt

De gegenereerde lambda verpakt je elementen in:

```cpp
if (id(initial_data_received) == false) {
  // Elementen wachtscherm
} else {
  // Elementen hoofdscherm
}
```

- Een nieuw profiel zet standaard een **"WACHTEN OP DATA…"**-tekst op het wachtscherm,
  met het standaard tekstfont (`font_small`).
- Je kunt het wachtscherm vrij ontwerpen, net als het hoofdscherm.
- **Kopiëren/plakken werkt tussen de twee schermen** (Ctrl+C op het ene, Ctrl+V op het
  andere — de positie blijft behouden).
- Zet het wachtscherm aan/uit bij **Profiel-instellingen → Wachtscherm gebruiken**. Als
  het uit staat, wordt de `if/else` helemaal weggelaten.
