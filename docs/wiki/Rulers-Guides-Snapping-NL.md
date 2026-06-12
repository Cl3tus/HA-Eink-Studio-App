# Linialen, hulplijnen & snappen

*🇬🇧 [English](Rulers-Guides-Snapping-EN) · 🏠 [Home](Home-NL)*

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
