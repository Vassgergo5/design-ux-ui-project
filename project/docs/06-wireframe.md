# 6. Low-fi wireframe

- **Figma, „06 Wireframe” oldal:** https://www.figma.com/design/kN2k74VzXlRbW2lnC9GXMH?node-id=98-2
- **Jegyzetek és annotációk, „06–07 Jegyzetek” oldal:** https://www.figma.com/design/kN2k74VzXlRbW2lnC9GXMH?node-id=98-3

A wireframe az [5. házi](05-ia-es-user-flow.md) sitemapjére és user flow-jára épül.

## Szabályok

- **Ugyanazok a képernyők, mint a prototípusban.** A wireframe-oldal a „09 Hi-fi” képernyőinek fekete-fehér párja: minden H-képernyőnek van W-párja, ugyanazzal a szerkezettel, szöveggel és linkekkel. Így a teszt és a dokumentáció mindig ugyanarra a tervre vonatkozik.
- **Fekete-fehér.** Nincs végleges szín, fotó vagy dekoratív ikon.
  - Az ikonok helyén szürke keretes helyőrző áll.
  - A térkép pinjei szürke körök.
  - A borítók és a képek szürke dobozok.
- **Auto Layout:** minden konténer Auto Layoutot használ. Kivétel a térképvászon, ott a pinek koordinátája maga a tartalom.
- **Reszponzivitás:** asztali (1440 × 800) és mobil (390 px, W2-M) változat.

## Képernyők

| Kód | Képernyő | Szerep |
|---|---|---|
| W1 | Home | Belépési pont: a folytatható játék és a kitűzött kategória |
| W2 | Game page · Progress (pinned) | **Döntési képernyő:** melyik kategóriát és régiót nézze a térképen |
| W3 | Map · szűrők + markerpanel | A fő munkafelület: régió-lenyíló, rétegek, „Show” kapcsoló, pin-részlet |
| W4 | Marked as found (38/50) | **Megerősítő képernyő:** frissült számlálók, értesítés „Undo”-val |
| W5 | Game page · Achievements + checklist | Másodlagos feladat (achievement-checklist) |
| W6 | Library · üres | **Kritikus állapot 1:** nincs követett játék |
| W7 | Error · could not save (offline) | **Kritikus állapot 2:** a mentés sikertelen, „Retry” |
| W8 | Paywall · Expedition | Pro-ajánlat modálban, nyomás nélküli kilépéssel |
| W9 | Checkout | Pro próbaidő vagy Completion Pack |
| W10 | Pro activated | Sikeres vásárlás |
| W3-G | Map · vendég | Fiók nélkül: csak a térkép, legfeljebb 100 jelölés |
| W2-M | Game page · Progress, mobil | A döntési képernyő mobilon |
| W11 | Not available yet | A prototípusban nem tervezett menüpontok jelzése |
| W12-B | Map · jelöléskorlát elérve | A markerpanel alján „100 of 100 marks” figyelmeztetés |
| W12 | Limit reached (modal) | **Kritikus állapot 3:** az ingyenes 100 jelölés elfogyott; Pro, Completion Pack vagy „Not now” |

## Annotációk

Az annotációk a „06–07 Jegyzetek” oldalon vannak, képernyőnként. Ezeket rögzítik:
- **feltevések**, például hogy a kitűzött kategória a Home tetején jelenik meg;
- **viselkedés**, például hogy a „Mark as found” minden számlálót egyszerre frissít, és az értesítés 8 másodpercig visszavonható;
- **akadálymentesség**, például hogy a pin állapotát ikon és felirat is jelzi, nem csak a szín;
- **vendégszabály:** fiók nélkül a térkép megtekinthető, és legfeljebb 100 jelölés tárolható az eszközön. Tipp írásához bejelentkezés kell;
- **jelöléskorlát:** ingyenes fiókkal játékonként legfeljebb 100 elem jelölhető meg. Az állás a markerpanel alján látszik (pl. 94 of 100), a 100. után a „Mark as found” a W12 figyelmeztető ablakot nyitja. Pro-val korlátlan.

## Rövid jegyzet: layout, fő művelet, hierarchia

- **Layout:**
  - Bal oldalt rögzített menü, amely összecsukható (232 ↔ 72 px).
  - Felül statikus felső sor: kereső és profil. Görgetéskor csak a tartalom mozog.
  - A térképen balra szűrőpanel, jobbra markerpanel.
- **Fő művelet:** képernyőnként egy elsődleges gomb.
  - W1: folytatás.
  - W2: „Show on map”.
  - W3: „Mark as found”.
  - W8: „Start 7 days free”, mellette jól látható „Not now” kilépés.
- **Hierarchia:**
  1. a számláló (pl. 37/50, „hiányzik 6 Gizában”);
  2. a hiányzó elemek a térképen;
  3. a kijelölt elem részletei (leírás, tipp);
  4. a Pro-ajánlat, csak a saját helyén.
