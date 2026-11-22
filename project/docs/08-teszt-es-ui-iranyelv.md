# 8. Használhatósági teszt és mini UI-irányelv

- **Tesztelt prototípus (hi-fi, „1 · Fő feladat” folyamat):** https://www.figma.com/proto/kN2k74VzXlRbW2lnC9GXMH?node-id=114-5&starting-point-node-id=114%3A5
- **Mini UI-irányelv, „08 UI guideline” oldal:** https://www.figma.com/design/kN2k74VzXlRbW2lnC9GXMH?node-id=3-3

> **Állapot:** a tesztterv, a beleegyező szöveg és a sablonok készen állnak. A valódi teszt 3 résztvevővel **még hátravan**, ezért az eredményrészek kitöltendők. A korábbi, szintetikus (AI-generált) tesztkör egy régebbi prototípusra vonatkozott. Az a git-előzményekben van (`397c5c3`), az eredményeit nem használjuk bizonyítékként.

## Tesztterv

**Tanulási célok:**
1. Megtalálja és megjelöli-e a játékos a hiányzó ereklyét a térképen, és észreveszi-e, hogy a jelölés elmentődött (számláló, értesítés)?
2. Érti-e a Pro-ajánlatot (ár, próbaidő, lemondás) úgy, hogy nyomás nélkül vissza tud lépni?

**A teszt körülményei:**
- **Résztvevők:** 3 évfolyamtárs, akik játszanak nyílt világú játékokkal. Legalább egyikük használt már térképoldalt (pl. MapGenie). A projektben nem vettek részt.
- **Forma:** laptop, a prototípus böngészőben, teljes képernyőn. Kb. 15 perc fejenként, hangos gondolkodással.
- **Segítség:** szóban nem segítünk. Csak 2 perc elakadás után kérdezünk rá: „Mit keresnél most?”

**Forgatókönyv (felolvasva):** „Este az Indiana Jones and the Great Circle-lel játszol, épp Gizában vagy. Korábban kitűzted az ősi ereklyéket (Ancient Relics), mert ezeket akarod mind összegyűjteni.”

| # | Feladat (szó szerint) | Kezdés | Sikerkritérium |
|---|---|---|---|
| F1 | „Nézd meg, melyik ereklye hiányzik még Gizában, és jelöld meg azt, amelyiket a játékban épp megtaláltad (a nagy piramisnál).” | H1 | 38/50, és szóban jelzi a változást |
| F2 | „Rájöttél, hogy rosszat jelöltél. Javítsd ki.” | H4 | vissza 37/50-re |
| F3 | „Nézd meg a Himalája régió állását a térképen.” | H3 | megtalálja a régió-lenyílót |
| F4 | „Kíváncsi vagy, mit tud az expedíció funkció – nézd meg, mennyibe kerülne, de most ne fizess.” | H3 | kimondja az árat vagy a próbaidőt, és visszajut a térképre |
| F5 | „Ellenőrizd, hogyan állsz az Exterminator achievementtel.” | H1 | megnyílik a checklist (H5) |

**Mért adatok feladatonként:**
- siker (igen / részben / nem);
- idő (mp);
- hibás kattintások száma;
- 5 mp-nél hosszabb habozás helye;
- SEQ 1–7 („Mennyire volt könnyű?”).

**Siker a teljes tesztre:** az F1-et legalább 2 résztvevő a 3-ból segítség nélkül, 60 mp-en belül teljesíti, és megemlíti a frissült számlálót.

## Beleegyező szöveg (szóban felolvasva)

> „Köszönöm, hogy segítesz. Egy egyetemi UX-projekt prototípusát nézzük meg. Nem téged tesztelünk, hanem a tervet, nincs rossz válasz. Kérlek, mondd hangosan, mit gondolsz, mit keresel. A prototípus nem teljes, néhány gomb nem működik. Jegyzetelek, de a nevedet nem írom le, a megjegyzéseidet névtelenül (R1, R2, R3) használom fel a házi feladatban. Bármikor abbahagyhatod. Rendben van így?”

A választ (igen / nem) a jegyzetben rögzítjük.

## Megfigyelési jegyzetek (kitöltendő)

| Résztvevő | Feladat | Siker | Idő | Megfigyelés | Idézet | Értelmezés |
|---|---|---|---|---|---|---|
| R1 | F1 | | | | | |
| R2 | F1 | | | | | |
| R3 | F1 | | | | | |

A megfigyelés viselkedést ír le, az idézet szó szerinti, az értelmezés külön oszlopba kerül.

## Leletek súlyosság szerint (kitöltendő)

Súlyossági skála (Nielsen 0–4): 4 megakadályoz · 3 nagy nehézség · 2 lassít · 1 kozmetikai · 0 nem probléma.

| # | Lelet | Bizonyíték (R#, feladat, idézet) | Érintett feladat | Következmény | Súlyosság |
|---|---|---|---|---|---|
| L1 | | | | | |

## Javítások indoklása (kitöltendő)

| Lelet | Javítás | Miért ez (érthetőség / akadálymentesség) | Elvetett alternatíva |
|---|---|---|---|
| L1 | | | |

## Mini UI-irányelv (Figma, „08 UI guideline” oldal)

### Színszerepek

„Color” változógyűjtemény, Dark (alapértelmezett) és Light mód. A kontrasztot a változók értékéből számoltuk (WCAG 2.1: szöveg ≥ 4,5 : 1, UI-elem ≥ 3 : 1).

| Szerep | Használat | Dark | Light | Kontraszt (Dark / Light) |
|---|---|---|---|---|
| `bg/canvas` | oldal háttere | #100C0B | #F7F3F1 | – |
| `bg/surface` | panel, kártya | #1A1412 | #FFFFFF | – |
| `bg/surface-raised` | kiemelt felület | #261D1A | #EFE8E4 | – |
| `text/primary` | fő szöveg | #F7F2EF | #1A1412 | 16,4 / 18,2 |
| `text/secondary` | meta | #B5A69E | #5E504A | 7,7 / 7,7 |
| `text/accent` | link, kiemelés | #FF8752 | #A8361A | 7,7 / 6,5 |
| `text/on-accent` | szöveg a fő színen | #FFFFFF | #FFFFFF | 5,0 / 5,7 |
| `accent/primary` | fő gomb, aktív elem | #C8401E | #B83A1B | 3,7 / 5,7 |
| `border/strong` | input, másodlagos gomb | #7A675E | #8C7A72 | 3,4 / 4,1 |
| `border/subtle` | dekoratív elválasztó | #3A2E29 | #E0D6D1 | dekoratív |
| `status/success` | kész (+ ✓) | #3ECF8E | #177A4E | 9,1 / 5,3 |
| `status/warning` | hiányzók száma | #F2C14E | #8A6A00 | 10,9 / 5,1 |
| `status/error` | hiba (+ szöveges ok) | #FF5A5F | #C73232 | 6,0 / 5,3 |
| `premium/gold` | PRO jelölés | #D9B45A | #8A6A1C | 9,2 / 5,0 |
| `focus/ring` | billentyűzetfókusz | #FFFFFF | #13201F | 19,5 / 15,2 |

**A menü kijelölése külön gyűjteményből jön.** A „Nav state” gyűjtemény módjai Home, Progress, Map, Pro, Library és None. Változói:
- `nav/<pont>/bg`;
- `nav/<pont>/label`;
- `nav/<pont>/icon` (az aktív ikon `text/accent` színű).

### Szövegstílusok

| Stílus | Betű | Használat |
|---|---|---|
| Display/56 · Display/40 · Title/36 | Barlow Condensed SemiBold | játékcím, oldalcím, szekciócím |
| Heading/22 · Overline/13 | Barlow Condensed SemiBold | panelcím, szekciócímke (nagybetűs) |
| Body/15 (150%) · Label/14 · Caption/12 | IBM Plex Sans | leírás · gomb, menüpont · meta |
| Data/28 · Data/13 | IBM Plex Mono | csak számok (37/50) |

### Térközök

„Spacing & radius” változók, 4-es rácsra:

| Változó | Érték |
|---|---|
| `space/xs` … `space/3xl` | 4 / 8 / 12 / 16 / 24 / 32 / 40 px |
| `radius/sm` / `md` / `lg` | 4 / 8 / 12 px |
| `size/touch-min` | 44 px |

### Használati szabályok

- **Gomb:**
  - Képernyőnként legfeljebb egy Primary. A többi Secondary, a harmadlagos művelet Ghost.
  - 40 px magas, 8 px lekerekítéssel.
  - Disabled csak akkor, ha a művelet tényleg nem érhető el, és az ok szövegben is ott van.
- **Beviteli mező:**
  - A címke mindig látható.
  - Állapotok:
    - Default: `border/strong`;
    - Focus: 2 px `focus/ring`;
    - Error: `status/error` keret és szöveges ok;
    - Disabled.
  - A hiba nem csak színnel jelzett (WCAG 3.3.1, 1.4.1).
- **Ikon:**
  - 20 px, `text/secondary`, aktív menüpontnál `text/accent`.
  - Mindig felirattal jelenik meg. Kivétel az értesítés, az összecsukó gomb és a zoom: ezek tooltipet vagy aria-labelt kapnak.
- **Állapotjelzés:** soha nem csak szín. Kíséri ✓ jel, szám, kiemelés vagy felirat.
- **Szövegtörés:** a szöveg nem vágódik le, hanem új sorba tör. A hosszú listák egy maximális magasság után görgetnek.
- **Prémium:** egységes PRO chip. Fizetés előtt mindig látszik az ár, a próbaidő vége, a lemondás módja és egy „Not now” kilépés.
