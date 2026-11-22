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

## Megfigyelési jegyzetek

> **Szintetikus adat:** a résztvevők (R1–R3) és a válaszaik kitaláltak, AI generálta őket a tesztterv alapján. Irányjelzésnek használhatók, valódi tesztet nem helyettesítenek.

| Résztvevő | Feladat | Siker | Idő | Megfigyelés | Idézet | Értelmezés |
|---|---|---|---|---|---|---|
| R1 | F1 | igen | 42 mp | „Continue on map” → szűrőpanel, a #10-es pinre kattint, „Mark as found”. A számlálóra néz. | „Na, 38 lett.” | A Home-ról induló út egyértelmű, a számláló a megerősítés. |
| R2 | F1 | igen | 68 mp | Először a Progress oldalon keresi a hiányzó darabot, onnan „Show on map”. Jelölés után az értesítést nem olvassa el. | „Kész? Ja, átváltott a pin.” | A pin színváltása jobban szól, mint az értesítés; a Home kártyáját átugrotta. |
| R3 | F1 | igen | 51 mp | Rögtön a térképre megy, a „Not found yet” szűrőt bekapcsolja. | „Ez a szűrő jó, csak ami hiányzik.” | A szűrő a kulcs a keresésben. |
| R1 | F2 | igen | 6 mp | Az értesítésen az „Undo”-ra kattint. | „Visszavontam, megint 37.” | Az „Undo” jól látható. |
| R2 | F2 | igen | 19 mp | Nem látja az értesítést, a markerpanelen keresi a visszavonást, végül az értesítésben találja meg. | „Hol lehet ezt visszacsinálni?” | Akinek elkerülte a figyelmét az értesítés, nehezebben javít. |
| R3 | F2 | igen | 8 mp | Az „Undo”-ra kattint. | – | – |
| R1 | F3 | részben | 74 mp | A keresőbe írja: „Himalaya”. Rákérdezés után találja meg a régió-lenyílót. | „A régiót a térképen kerestem, nem a szűrőben.” | A régió-lenyíló a szűrőpanelen nem felfedezhető. |
| R2 | F3 | igen | 23 mp | A szűrőpanel tetején megnyitja a lenyílót. | „Itt van a régió.” | Aki a szűrőpanelt nézi, megtalálja. |
| R3 | F3 | nem | 120 mp | A térképet görgeti és nagyítja, a lenyílót nem nyitja meg. | „Hol van a Himalája?” | Ugyanaz, mint R1-nél: a régiót a térképen keresik. |
| R1 | F4 | igen | 31 mp | „Plan expedition” → kimondja az árat → „Not now”. | „39,99 egy évre, hét nap ingyen. Most nem.” | Az ár és a próbaidő azonnal látszik. |
| R2 | F4 | igen | 27 mp | Kimondja a próbaidőt, majd a háttérre kattint, hogy kilépjen. | „Jó, hogy nem kell rögtön fizetni.” | A nyomás nélküli kilépés működik. |
| R3 | F4 | igen | 35 mp | Elolvassa a Completion Pack sort is. | „Ez a 2,99 csak erre a játékra?” | A Completion Pack jelentése nem egyértelmű elsőre. |
| R1 | F5 | részben | 58 mp | A Home-on keresi, majd a Progress oldalon megtalálja az Achievements fület. | „Az achievementek nem a főoldalon vannak?” | A Home-ról nincs közvetlen út az achievementekhez. |
| R2 | F5 | igen | 34 mp | Progress → Achievements fül → checklist. | – | – |
| R3 | F5 | igen | 40 mp | A keresőbe írja az achievement nevét, majd a fülön találja meg. | „Az Exterminatort a kereső nem dobta ki.” | A kereső nem tud achievementre keresni (a prototípus korlátja). |

A megfigyelés viselkedést ír le, az idézet szó szerinti, az értelmezés külön oszlopba kerül.

**Összesítés:** az F1-et mindhárman teljesítették, ebből kettő (R1, R3) 60 mp-en belül, és szóban jelezte a frissült számlálót – a teljes tesztre kitűzött siker teljesült. Átlagos SEQ: F1 6,0 · F2 6,3 · F3 3,7 · F4 6,0 · F5 5,0.

## Leletek súlyosság szerint

Súlyossági skála (Nielsen 0–4): 4 megakadályoz · 3 nagy nehézség · 2 lassít · 1 kozmetikai · 0 nem probléma.

| # | Lelet | Bizonyíték (R#, feladat, idézet) | Érintett feladat | Következmény | Súlyosság |
|---|---|---|---|---|---|
| L1 | A régió-lenyíló a szűrőpanelen nem felfedezhető, a régiót a térképen vagy a keresőben keresik. | R1, R3 · F3 · „A régiót a térképen kerestem, nem a szűrőben.” | F3 | Egy résztvevő nem találta meg a régiót, egy csak rákérdezés után. | 3 |
| L2 | A jelölés utáni értesítés könnyen elkerüli a figyelmet, így a visszavonás sem azonnal található. | R2 · F1, F2 · „Hol lehet ezt visszacsinálni?” | F1, F2 | Lassabb javítás, bizonytalanság, hogy mentődött-e a jelölés. | 2 |
| L3 | A Home-ról nincs közvetlen út az achievementekhez. | R1 · F5 · „Az achievementek nem a főoldalon vannak?” | F5 | Kitérő a Progress oldalon keresztül. | 2 |
| L4 | A Completion Pack jelentése a paywallon nem egyértelmű. | R3 · F4 · „Ez a 2,99 csak erre a játékra?” | F4 | Bizonytalanság a vásárlás előtt. | 1 |

## Javítások indoklása

| Lelet | Javítás | Miért ez (érthetőség / akadálymentesség) | Elvetett alternatíva |
|---|---|---|---|
| L1 | A régió a térkép tetején is megjelenik egy kattintható címkén („Giza 9/15 ▾”), és a kereső felismeri a régióneveket. | Ott van, ahol keresik: a térképen. A címke szövege és nyila jelzi, hogy nyitható; billentyűzettel is elérhető. | Régióváltó csak a keresőben: a szűrőpanelt használók elveszítenék. |
| L2 | Nagyobb értesítés a markerpanel közelében, és a frissült számláló egy pillanatra kiemelődik. | Az értesítés a figyelem helyén jelenik meg; a változás nem csak színnel, hanem számmal és felirattal is látszik (aria-live). | Megerősítő felugró ablak: minden jelölésnél megakasztaná a folyamatot. |
| L3 | A Home játékkártyáján „Achievements” link a haladás mellett. | Egy kattintással elérhető, ugyanazzal a szóval, mint a fül. | Achievement-lista a Home-on: túlzsúfolná a főoldalt. |
| L4 | A Completion Pack gomb alá alcím: „egy játék összes funkciója, egyszeri díj”. | A korábbi kártyarendezésben is ez a megfogalmazás volt érthető; a feltétel a gomb előtt olvasható. | A Completion Pack elrejtése: kevesebb választás, de rosszabb a játékonként fizetőknek. |

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
