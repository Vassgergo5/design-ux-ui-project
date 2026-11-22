# 2. Elemzés: affinity map, insightok, persona, user journey

**FigJam „2. Kutatás”, 2–6. blokk:** https://www.figma.com/board/jTU7My5cBW91w0COne76H8?node-id=3-120

> Az elemzés a [szintetikus interjújegyzeteken](02-interjuk.md) alapul.

## 2 · Affinity map

Cetliszínek: **sárga = idézet**, **kék = megfigyelés**, **lila = értelmezés**. A csoportok nevei állítások.

| Csoport (állítás) | Cetlik | Résztvevők |
|---|---|---|
| A1 – „A számlálóból indulnak: a fontos kategóriát figyelik” | R1-1, R1-2, R2-1, R4-4, R5-2 | 4/5 |
| A2 – „A teljes térképen elveszik, amit épp keresnek” | R1-3, R1-4, R1-5 | 2/5 |
| A3 – „A haladás több helyen él, és nem bíznak benne” | R2-2, R2-3, R2-4, R1-6, R5-6, R2-5 | 3/5 |
| A4 – „Elakadáskor egy kis segítség kell, ott, ahol épp tartanak” | R4-1, R4-2, R3-5, R5-7, R2-7, R4-7 | 4/5 |
| A5 – „A haladást látni és megmutatni is akarják” | R4-3, R5-1, R5-3, R4-5 | 2/5 |
| A6 – „Kényelemért fizetnének, de nem mindenképp előfizetéssel” | R2-6, R4-6, R5-4, R5-5 | 3/5 |
| A7 – Ellenpélda: „Nem pipálok, csak bejárom a térképet” | R3-1, R3-2, R3-3, R3-4 | 1/5 |

## 3 · Insightok (megfigyelés → értelmezés → tervezési következmény)

### Insight 1 – „Mindent látni akarnak, de a fontosat külön követik.”

- **Megfigyelés:** 4/5 résztvevő egy számlálóból indul (R1-2, R2-1, R4-4, R5-2). A teljes térképen nem látszik a hiányzó (R1-3, R5-2).
- **Értelmezés:** a kérdés nem az, hogy hol van minden, hanem hogy „ebben a kategóriában mi van még hátra, és hol?”. Ez megerősíti az F3-at.
- **Tervezési következmény:**
  - kitűzhető kategóriák a játék oldalán (37/50), egy kattintással a rájuk szűrt térképre;
  - a „még nem jelöltek” csak egy szűrő a sok közül.

### Insight 2 – „A haladásom három helyen van, és egyik sem pontos.”

- **Megfigyelés:** a haladást Excelben, a térképoldalon és a naplóban is vezetik (R2-1, R2-2, R2-4), és tévedtek már (R1-6, R5-6).
- **Értelmezés:** a legnagyobb gond, hogy nem bíznak a saját nyilvántartásukban.
- **Tervezési következmény:**
  - egy „Mark as found” frissítse a listát, a térképet, a számlálót és a kapcsolódó achievementet, és legyen visszavonható;
  - az achievementek is ide kerüljenek (R4-4).

### Insight 3 – „Elakadáskor egy kis lökés kell, ott, ahol épp tartok.”

- **Megfigyelés:**
  - 4/5 résztvevő több helyről szedi össze a segítséget (R2-7, R5-7);
  - a térképponthoz nincs leírás (R3-5);
  - a videó spoilerez (R4-1).
- **Értelmezés:** a segítség a markerhez kötve, fokozatosan kell. A közösség tippjei kiegészítik az alapanyagot.
- **Tervezési következmény:** a marker panelje a marker típusa szerint ad információt (gyűjtenivaló, küldetés, puzzle):
  - leírás;
  - fokozatos tipp;
  - közösségi tippek és kommentek.

## 4 · Personák

### Elsődleges persona – „Bence, a 100%-ra hajtó” (24, PC, este játszik)

| Elem | Tartalom | Forrás |
|---|---|---|
| Helyzet | A főtörténet után összeszedi a hiányzó gyűjtenivalókat, mellette telefon vagy második monitor. | R1-1, R2-2, R5-1 |
| Cél | A fontos kategóriákat követni, és gyorsan odajutni a következő darabhoz. | R1-3, R1-5 |
| Tudás és eszköz | Ismeri a wikiket és az interaktív térképeket, a naplót is használja. | R1-2, R4-4 |
| Korlát | Több helyen van a haladása, tart a spoilertől, és nem akar még egy havidíjat. | R2-3, R4-2, R4-6 |
| Kockázat | Feleslegesen jár be helyeket, rosszul jelöl, feladja a 100%-ot. | R1-6, R5-6 |
| **Feltevés (nincs bizonyíték)** | Hajlandó egy új eszközbe bejelölni a meglévő haladását. A PC-s böngésző az elsődleges eszköz (csak 2/5). | – |

### Másodlagos persona – „Réka, aki elakadt” (27, PS5, hétvégén játszik)

Az R2–R5 interjúkból.

| Elem | Tartalom | Forrás |
|---|---|---|
| Helyzet | Egy küldetésnél vagy puzzle-nél megakadt, vagy egy konkrét tárgyat keres. | R3-5, R4-2 |
| Cél | Egy apró tipp, ami továbblendíti, spoiler nélkül. | R4-1, R4-7 |
| Korlát | Egy gyors kérdés miatt nem akar regisztrálni, és kerüli a videót. | R3-3, R4-2 |
| Hol keres ma | Wiki → YouTube → Reddit-kommentek. | R2-7, R5-7 |

## 5 · User journey – „Hiányzó ősi ereklyék összeszedése Gizehben”

| | 1. Elindul | 2. Lista | 3. Térkép | 4. Melyik hiányzik? | 5. Odamegy | 6. Nyilvántartás |
|---|---|---|---|---|---|---|
| Lépések | Naplóban látja: 9/15 | Wiki-listát nyit | Térképoldal a telefonon | Pontonként összeveti az emlékeivel | Bejárja a helyszínt | Pipál Excelben és a térképen |
| Gondolat | „Csak hat van hátra.” | „Melyik hat?” | „Mind a 15 ki van rakva.” | „Ez megvan már? Nem tudom.” | „Ez megvolt…” | „Megint két helyen pipálok.” |
| Érzés (1–5) | 4 | 3 | 2 | **1 – legrosszabb** | 2 | 2 |
| Fájdalompont | – | Lista ≠ haladás | Nincs „csak a hiányzók” | **Nem tudja, mi hiányzik** | Felesleges út | Kettős nyilvántartás |
| Lehetőség | Kitűzött kategória a játék oldalán | Hiányzólista | Szűrt térkép | Szűrő: még nem jelöltek | Pontleírás + kép | Egy jelölés mindenhol frissít |

**Érzésgörbe:** 4 → 3 → 2 → 1 → 2 → 2.

**★ A legnagyobb fájdalompont** a 4. lépés („Melyik hiányzik?”). Ez az Insight 1-hez kapcsolódik.

## 6 · Feltételezések frissítése a kutatás után

| # | Feltételezés | Eredmény |
|---|---|---|
| F1 | Több eszköz párhuzamosan | **Megerősítve** (4/5) |
| F2 | A térképoldalak nem tudják a haladást | **Megerősítve** |
| F3 | A fontos kategóriát külön követik, a még nem jelöltekre szűrnek | **Megerősítve** (4/5), ellenpélda: R3 |
| F4 | Kényelemért fizetnének | **Részben:** az egyszeri vásárlás is igény (R4-6) |
| F5 | Elakadáskor apró tipp kell | **Megerősítve** (4/5: R2, R3, R4, R5) |
| F7 | Mások tippjei hasznosak | **Részben** (R5-7). Hogy mennyire bíznak bennük, még nyitott. |

**Következő fejezet:** hogyan kezeli egy versenytárs (Gamer Guides) a térképet, az útmutatókat és a fizetős csomagot? Ezt egy használhatósági és akadálymentességi audit vizsgálja.
