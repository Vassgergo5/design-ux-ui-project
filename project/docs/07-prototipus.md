# 7. Kattintható prototípus

- **Hi-fi prototípus (ezt teszteljük), „09 Hi-fi” oldal:** https://www.figma.com/proto/kN2k74VzXlRbW2lnC9GXMH?node-id=114-5&starting-point-node-id=114%3A5
- **Wireframe-prototípus, „06 Wireframe” oldal:** https://www.figma.com/design/kN2k74VzXlRbW2lnC9GXMH?node-id=98-2. A Prototype panelen ugyanaz az 5 folyamat indítható.
- **Korlátok és jegyzetek, „06–07 Jegyzetek” oldal:** https://www.figma.com/design/kN2k74VzXlRbW2lnC9GXMH?node-id=98-3

## Folyamatok (Figma flow starting point)

Az öt folyamat egymástól független: egyikből sem lehet a másikba kattintani.

| # | Folyamat | Kezdés | Siker / végállapot |
|---|---|---|---|
| 1 | Fő feladat – kitűzött kategória megtalálása | H1 Home | H4: 38/50 minden számlálóban, értesítés „Undo”-val |
| 2 | Kivétel – üres könyvtár (nincs követett játék) | H6 Library | Az üres állapot és a követhető játékok látszanak |
| 3 | Vendég – térkép fiók nélkül (max. 100 jelölés) | H3-G | Megtekintés és helyi jelölés, „1/100” számláló |
| 4 | Kivétel – nem elérhető menüpont | H11 | „This section isn't available yet” |
| 5 | Kivétel – ingyenes jelöléskorlát elérve (100/100) | H12-B | H12 figyelmeztető ablak; Pro vagy Completion Pack → H9 checkout → H10, „Not now” → vissza |

**Működő kapcsolatok az 1. folyamatban:**
- H1 → H2 (kitűzött kategória) → H3 (térkép) → a #10-es pin → „Mark as found” → H4;
- H4: az „Undo” visszavisz 37/50-re;
- H5: achievement-checklist, „Show on map”;
- H3: a „Plan expedition” a H8 paywallt nyitja. Ott a „Not now” vagy a háttérre kattintás bezárja, a Pro kipróbálása pedig H9 checkout → H10 siker.

**Interaktív komponensek:**
- **Oldalsáv:** összecsukható. Az összecsukott állapot oldalváltáskor megmarad, a kijelölt menüpont mindig az aktuális oldalt mutatja.
- **Szűrőpanel:** a „hide” / „show” gombbal összecsukható.
- **Régió-lenyíló:** nyitható és zárható.

## Kivételes állapotok

- **H6 üres könyvtár:** kereső „All / Recommended for you” fülekkel, kategóriaszűrő és 12 követhető játék (pl. GTA VI, Ubisoft, EA és Rockstar címek).
- **H7 offline hiba:** a mentés sikertelen, „Retry”.
- **H3-G vendég:** csak a térkép érhető el, a többi menüpont halványított.
- **H11 nem elérhető menüpont.**
- **H12-B / H12 jelöléskorlát:** ingyenes fiókkal játékonként 100 elem jelölhető meg. A markerpanel alja mutatja az állást (a fő folyamatban 94 of 100, jelölés után 95). 100/100-nál a „Mark as found” a paywallhoz hasonló felugró ablakot nyit: a jelölések megmaradnak, a folytatáshoz Pro vagy Completion Pack kell.

## Ismert korlátok

Ezek a Figmában is szerepelnek, a „06–07 Jegyzetek” oldal 5. szakaszában.

- Csak a #10-es pin interaktív. A kereső és a szűrő-pipák nem működnek. A checkout nem validál, a CVC-hiba statikus példa.
- A wireframe-en a régió-lenyíló, az oldalsáv és a szűrőpanel nem csukható össze, mert a szürke másolat nem komponens. Mobilon csak a Progress képernyő van meg.
- A Community, Settings, Help és a kitöltött Library nincs megtervezve: ezek a menüpontok halványítottak és nem kattinthatók. A „nem elérhető” állapotot a 4. folyamat mutatja be.
- A kivétel- és vendégképernyők szándékosan zsákutcák.
- A Log in / Sign up és a regisztráció nem működik.

## Forgatókönyv és feladat

- **Forgatókönyv:** „Este az Indiana Jones and the Great Circle-lel játszol, épp Gizában vagy. Korábban kitűzted az ősi ereklyéket (Ancient Relics), mert ezeket akarod mind összegyűjteni.”
- **Feladat:** „Nézd meg, melyik ereklye hiányzik még Gizában, és jelöld meg azt, amelyiket a játékban épp megtaláltad (a nagy piramisnál).”

A feladat nem nevezi meg a gombokat és a menüpontokat, tehát nem árulja el a megoldást. A teljes feladatsor (F1–F5) a [8. házi tesztcsomagjában](08-teszt-es-ui-iranyelv.md#tesztterv) van.

## Megfigyelések (legalább 1 évfolyamtárssal)

> **Kitöltendő a valódi teszt után.** A korábbi, szintetikus (AI-generált) próba egy régebbi prototípusra vonatkozott. Az a git-előzményekben megtalálható (`81343d1`), de a mostani tervre nem érvényes.

| # | Megfigyelés (mit csinált) | Idézet (szó szerint) | Értelmezés |
|---|---|---|---|
| O1 | … | „…” | … |
| O2 | … | „…” | … |
| O3 | … | „…” | … |

## Reflexió

> Kitöltendő a teszt után, három kérdés mentén: mi lepett meg, mi volt hasznos, és mit változtatnál.
