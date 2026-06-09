# Rulers, Guides & Snapping

## 🇬🇧 English

Three independent alignment aids, all toggled in the **status bar**.

> 📷 *Screenshot: canvas with rulers on, two guide lines (one vertical, one
> horizontal) crossing, and an element snapped into the cross.* →
> `docs/screenshots/Rulers-Guides.png`

### Grid + Snap grid

- **Grid** draws a dotted grid; **grid size** is 8 / 10 / 16 / 20 / 25 / 40 px.
- **Snap grid** snaps a dragged element's **visible pixels** to the grid lines.
- Turning the grid off also hides/disables Snap grid.

### Rulers

Enable **Ruler** to show rulers along the top and left edges.

- Ticks and labels every 50 px (denser as you zoom in), with a label at the canvas
  edge. Ticks continue into the negative area and past the canvas edge.
- Outside-the-canvas zones are tinted lighter (white in light mode) so the canvas
  bounds are clear.
- Rulers are **theme-aware** (light/dark).

### Guide lines

- **Drag out of a ruler** to drop a guide: the **top** ruler creates a **vertical**
  guide, the **left** ruler a **horizontal** one. A blue line follows on the canvas
  while you drag, and a dotted preview shows in the margin.
- Each guide has a **marker** (triangle) in its ruler. **Drag the marker** to
  reposition the guide; **right-click** a marker to remove that guide.
- **Right-click an empty ruler** → *Remove guides* (clears that axis).
- Guides are stored **per profile** and saved with the design.
- Guide lines sit **behind** your elements, so they never cover your design.

### Snap ruler (pixel-perfect)

With **Snap ruler** on, dragging an element snaps its edges to the guides:

- It snaps the element's **visible-ink box** — the tight box around the actual drawn
  pixels (same box the selection outline hugs) — so it lands exactly where the pixels
  begin, not on the looser font-metric box.
- The two axes snap **independently**: an element can lock onto a **vertical** guide
  (left/right edge) and a **horizontal** guide (top/bottom edge) at the same time —
  i.e. snap into the **cross** where two guides meet.
- The snap box is measured once when the drag starts, so it stays smooth even for
  large text.
- Hold **Shift** to bypass snapping.

### Mutual exclusivity

**Snap grid** and **Snap ruler** are mutually exclusive — enabling one turns the other
off. Use the grid for regular spacing, guides for precise alignment lines.

---

## 🇳🇱 Nederlands

Drie onafhankelijke uitlijn-hulpmiddelen, allemaal te schakelen in de **statusbalk**.

> 📷 *Screenshot: canvas met linialen aan, twee hulplijnen (één verticaal, één
> horizontaal) die kruisen, en een element gesnapt in het kruis.* →
> `docs/screenshots/Rulers-Guides.png`

### Raster + Snap raster

- **Raster** tekent een stippelraster; **rastergrootte** is 8 / 10 / 16 / 20 / 25 / 40 px.
- **Snap raster** snapt de **zichtbare pixels** van een gesleept element op de
  rasterlijnen.
- Het raster uitzetten verbergt/schakelt ook Snap raster uit.

### Linialen

Zet **Lineaal** aan voor linialen langs de boven- en linkerrand.

- Streepjes en labels elke 50 px (dichter naarmate je inzoomt), met een label op de
  canvasrand. Streepjes lopen door in het negatieve gebied en voorbij de canvasrand.
- Zones buiten het canvas zijn lichter getint (wit in lichte modus) zodat de
  canvasgrenzen duidelijk zijn.
- Linialen passen zich aan het **thema** aan (licht/donker).

### Hulplijnen

- **Sleep uit een liniaal** om een hulplijn neer te zetten: de **bovenste** liniaal
  maakt een **verticale** hulplijn, de **linker** een **horizontale**. Een blauwe lijn
  volgt op het canvas tijdens het slepen, en een gestippelde preview in de marge.
- Elke hulplijn heeft een **marker** (driehoek) in z'n liniaal. **Sleep de marker** om
  de hulplijn te verplaatsen; **rechtsklik** een marker om die hulplijn te verwijderen.
- **Rechtsklik op een lege liniaal** → *Verwijder gidsen* (wist die as).
- Hulplijnen worden **per profiel** opgeslagen, samen met het ontwerp.
- Hulplijnen staan **achter** je elementen, zodat ze je ontwerp nooit bedekken.

### Snap lineaal (pixel-perfect)

Met **Snap lineaal** aan snapt een gesleept element z'n randen op de hulplijnen:

- Het snapt de **zichtbare-ink-box** — de strakke box rond de daadwerkelijk getekende
  pixels (dezelfde box als de selectie-omlijning) — dus precies waar de pixels
  beginnen, niet op de lossere font-box.
- De twee assen snappen **onafhankelijk**: een element kan tegelijk op een **verticale**
  hulplijn (linker/rechter rand) én een **horizontale** hulplijn (boven/onder rand)
  vastklikken — oftewel in het **kruis** waar twee hulplijnen samenkomen.
- De snap-box wordt één keer aan het begin van het slepen gemeten, dus het blijft
  soepel, ook bij grote tekst.
- Houd **Shift** vast om snappen over te slaan.

### Sluiten elkaar uit

**Snap raster** en **Snap lineaal** sluiten elkaar uit — de een aanzetten zet de ander
uit. Gebruik het raster voor regelmatige afstanden, hulplijnen voor precieze
uitlijnlijnen.
