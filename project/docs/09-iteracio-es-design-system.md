# 9. Iteráció és mini design system

- **Hi-fi prototípus, „09 Hi-fi” oldal:** https://www.figma.com/proto/kN2k74VzXlRbW2lnC9GXMH?node-id=114-5&starting-point-node-id=114%3A5
- **Design system, „09 Design system” oldal:** https://www.figma.com/design/kN2k74VzXlRbW2lnC9GXMH?node-id=3-4
- **Handoff, „09 Handoff” oldal:** https://www.figma.com/design/kN2k74VzXlRbW2lnC9GXMH?node-id=3-6

**Vizuális irány:** sötét, meleg vörös–narancs játékos felület. Valódi borítók helyett tipografikus borítók és saját rajzolású Giza-térkép szerepel, szerzői jogi okból.

## Döntési napló

**Honnan jönnek az iterációk?**
- tervezői átnézések;
- automatikus ellenőrzések: kilógó szöveg, átfedés, kontraszt, pozíciók;
- egy korábbi, szintetikus tesztkör.

A valódi teszt (8. házi) eredményei a nyitott kérdéseket zárják le.

### I1 – A szöveg nem vágódhat le

- **Bizonyíték:** a H5 achievement-táblában levágódtak a „Show on map” gombok. A hosszú játékcím („Indiana Jones and the Great Circle”) kilógott a fejlécből és a kártyákról.
- **Hipotézis:** ha minden szöveg tördel, a táblában pedig a név oszlop rugalmas és a műveleti oszlop fix, egyetlen szöveg sem vész el.
- **Változtatás:**
  - egységes tördelési szabály;
  - a H5-ben rugalmas név oszlop és fix 124 px-es műveleti oszlop;
  - a hosszú listák egy maximális magasság után görgetnek.
- **Elvetett alternatíva:** levágás „…”-tal és tooltippel. A játékcímeknél és tippeknél ez információvesztés.
- **Várt hatás:** 0 kilógó vagy levágott szöveg.
- **Nyitott kérdés:** 390 px-es mobilon nem tolják-e túl lejjebb a fő műveletet a hosszú, lokalizált címek?

### I2 – Kontraszt és keretek

- **Bizonyíték:** a számolt kontraszt szerint a `border/strong` 2,6 : 1 volt, a WCAG 1.4.11 viszont 3 : 1-et kér. Világos módban a „kész” zöld 4,3 : 1 volt.
- **Hipotézis:** két token módosításával AA szintre hozható a felület, a többi elem változtatása nélkül.
- **Változtatás:** `border/strong` #7A675E (3,4 : 1), világos `status/success` #177A4E (5,3 : 1). A világos mód meleg palettát kapott.
- **Elvetett alternatíva:** 2 px-es keret. Zajosabb, és összetéveszthető a fókuszgyűrűvel.
- **Várt hatás:** minden szöveg legalább 4,5 : 1, minden UI-elem legalább 3 : 1, mindkét módban.
- **Nyitott kérdés:** színtévesztőknek elég-e a sárga / zöld pin és a ✓ jel?

### I3 – A régióválasztás a szűrőbe, lenyíló listával

- **Bizonyíték:** a térkép tetején lévő régiósáv ütközött a szűrőpanellel és az értesítéssel. A régió és a szűrők két külön helyen voltak.
- **Hipotézis:** ha a régió a szűrőpanel első eleme, a játékos egy helyen állítja be, mit lát.
- **Változtatás:** „REGION” lenyíló (Dropdown komponens) régiónkénti számlálóval. A régiósávot töröltem, az értesítés középre került.
- **Elvetett alternatívák:**
  - fülek a térkép tetején: ütköznek a panelekkel;
  - 2×2-es szegmentált választó: négynél több régiónál nem skálázódik.
- **Várt hatás:** nincs átfedés, és a régió egy kattintással váltható.
- **Nyitott kérdés:** a panelben keresik-e a régiót? Ezt a valódi teszt F3 feladata méri.

### I4 – A jelölés visszajelzése

- **Bizonyíték:**
  - a szintetikus tesztkörben a résztvevők nem látták, hogy a jelölés elmentődött;
  - a „Mark as found” utáni Smart animate átmenet villogott.
- **Hipotézis:** ha minden számláló egyszerre frissül, és az értesítés villogás nélkül, mindig ugyanott jelenik meg, a mentést észreveszik.
- **Változtatás:**
  - 38/50 a számlálóban, a szűrőben és a régió-lenyílóban;
  - értesítés felül középen, „Undo”-val;
  - azonnali váltás animáció helyett.
- **Elvetett alternatíva:** Smart animate (villogott).
- **Várt hatás:** a résztvevők szóban jelzik a változást (F1), és megtalálják az „Undo”-t (F2).
- **Nyitott kérdés:** elég-e a 8 másodperc a visszavonásra?

### I5 – Egységes váz, ugrálás nélkül

- **Bizonyíték:** lapváltáskor a kereső és az avatar elmozdult, a menüelemek 1–2 px-et ugrottak.
- **Hipotézis:** azonos felső sorral és fix méretű menüelemekkel a váltás „helyben” történik.
- **Változtatás:**
  - a kereső mindenhol 264 / 24 px-ről indul, és 780 px széles;
  - az avatar 32 px-re van a jobb széltől;
  - a menü Nav item komponensből épül;
  - a felső sor statikus, csak a tartalom görget, alatta 20 px-es átmenet.
- **Elvetett alternatíva:** oldalanként eltérő felső sor.
- **Várt hatás:** 0 px eltérés a képernyők között.
- **Nyitott kérdés:** a nagyon hosszú oldalakon elég-e a 20 px-es átmenet, hogy ne tűnjön levágottnak a tartalom?

### I6 – Navigáció: összecsukható menü és tiszta folyamatok

- **Bizonyíték:**
  - összecsukott menüből navigálva a kijelölés az előző oldalon ragadt (a prototípus átvitte a komponens állapotát);
  - a kivételképernyőkről át lehetett kattintani a fő szálba, ami összekeverte a teszt folyamatait.
- **Hipotézis:**
  - ha a kijelölést változó adja (az oldal saját módja), az összecsukott állapot megmaradhat, a kijelölés pedig mindig helyes;
  - ha a folyamatok függetlenek, a teszt eredménye egyértelműen egy feladathoz köthető.
- **Változtatás:**
  - „Nav state” változógyűjtemény, az aktív ikon narancssárga;
  - a négy folyamat (fő feladat, üres könyvtár, vendég, nem elérhető menüpont) nem linkel egymásra;
  - a nem tervezett menüpontok halványítottak és nem kattinthatók.
- **Elvetett alternatívák:**
  - minden képernyőnek összecsukott másolata: 11-gyel több képernyő;
  - „not available” oldal minden menüpontnak: összekapcsolta volna a folyamatokat.
- **Várt hatás:** a résztvevő nem téved ki a feladatból, és a menü kijelölése mindig az aktuális oldalt mutatja.
- **Nyitott kérdés:** zavarja-e a résztvevőket, hogy néhány menüpont halvány?

## Ellenőrzés

| Változtatás | Módszer | Eredmény | Korlát |
|---|---|---|---|
| I1 | Script: minden szöveg és elem befoglaló doboza a szülőn belül van-e, mind a 10 asztali hi-fi képernyőn | **0 hiba** (kritérium: 0) | csak a kilógást méri, az olvashatóságot nem |
| I2 | A UI-irányelv színtáblája a változók aktuális értékéből számol | **mind ✓** (kritérium: 0 ✗) | valódi kijelzőn nem mértük |
| I3 | Átfedés-ellenőrzés a térképes képernyőkön, nyitott lenyílóval is (a panel legfeljebb 660 px) | **0 átfedés** | a felfedezhetőséget a valódi teszt F3 feladata méri |
| I5 | A felső sor elemeinek koordinátái 9 asztali képernyőn | **0 px eltérés** | – |
| I6 | Linkellenőrzés a hi-fi és a wireframe oldalon | **0 folyamatok közötti link** | – |
| I4 | Valódi teszt, F1–F2 | **még hátravan** | – |

## Mini design system (Figma, „09 Design system” oldal)

Minden komponens a 8. házi változóihoz és szövegstílusaihoz van kötve.

| Komponens | Variánsok |
|---|---|
| Button | Type: Primary / Secondary / Ghost × State: Default / Hover / Pressed / Focus / Disabled (15) |
| Input | Default / Focus / Error / Disabled |
| Checkbox, Radio | Off / On / Disabled |
| Segment | Default / Selected |
| Dropdown | Closed / Open (interaktív) |
| Chip | Neutral / Success / Pro |
| Nav item | Default / Active, ikoncsere (INSTANCE_SWAP) és Label tulajdonság |
| Search, Toast | – |
| Ikonok (12) | home, progress, map, community, library, pro, settings, help, bell, search, collapse, chevron-down |
| Sidebar (a „09 Hi-fi” oldalon) | Active: Home / Progress / Map / Pro / Library × State: Expanded / Collapsed, „Pro card” logikai tulajdonság, interaktív |
| Filter panel (a „09 Hi-fi” oldalon) | Expanded / Collapsed, interaktív, legfeljebb 660 px, görget |

## Handoff – „Map · marker detail (H3)” (Figma, „09 Handoff” oldal)

- **Képernyő:** a térkép szűrőpanellel és markerpanellel, 9 számozott jelölővel.
- **Annotációk:** régió-lenyíló, szűrőpanel, „Show” kapcsoló, pin, markerpanel, „Mark as found”, tippmező, kitűzött számláló, értesítés, oldalsáv. Mindegyiknél le van írva a viselkedés, a tokenek és az akadálymentesség (szerepek, aria-expanded, aria-live, aria-current, fókusz).
- **Állapotok:** Mark as found gomb, régió-lenyíló, réteg-checkbox, „Show” szegmens, tippmező, értesítés, pin.
- **Változónevek:** a teljes lista a frame alján, beleértve a „Nav state” változókat.
- **„✓ Ready for development” címke:** a Dev Mode-státuszt kézzel kell beállítani.

## Javasolt következő lépés

**Valódi használhatósági teszt 3 résztvevővel**, a 8. házi F1–F5 feladataival. Ez csökkenti a legnagyobb bizonytalanságot: az I3 (megtalálják-e a régió-lenyílót) és az I4 (észreveszik-e a mentést, megtalálják-e az „Undo”-t) hatását valódi felhasználóval még nem mértük.

**Siker:** az F1-et legalább 2 résztvevő a 3-ból segítség nélkül, 60 mp-en belül teljesíti, és megemlíti a frissült számlálót.
