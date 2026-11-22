# 5. Információs architektúra és user flow

**FigJam „5. IA és user flow”:** https://www.figma.com/board/jTU7My5cBW91w0COne76H8?node-id=14-729

> A kártyarendezés 3 résztvevője (P1–P3) **szintetikus** (AI-generált). A felület angol nyelvű, ezért a menüpontok is angolok.

## 1 · Tartalomleltár – 25 kártya, fontosság szerint

| Prioritás | Tartalom / funkció |
|---|---|
| **Elsődleges** | Követett játékok · Completion % · kategória-számláló (37/50) · kitűzött kategóriák (pin) · „Show on map” (kategóriára szűrve) · térkép szűrőkkel (típus, régió, nem jelölt) · marker-panel (típus szerinti infó) · „Mark as found” · visszavonás (Undo) |
| **Másodlagos** | Régióválasztó · rétegek ki/be · keresés a térképen · achievements (térképhez kötve, checklist) · paywall (keresőexpedíció) · Pro csomagok · checkout · fokozatos tipp (Hint 1–2, megoldás) · közösségi tippek és kommentek |
| **Harmadlagos** | Fiók (a jelöléshez kell) és beállítások · előfizetés-kezelés · súgó · értesítések · feed · haladás megosztása · poszt / tipp írása |

## 2 · Címkék validálása – nyílt kártyarendezés (3 fő)

| Résztvevő | Saját csoportnevei |
|---|---|
| P1 (completionist) | „Játékaim” · „Mi van még hátra?” · „Térkép és segítség” · „Fiók” |
| P2 (alkalmi) | „Játékok” · „Térkép és tippek” · „Közösség” · „Előfizetés” |
| P3 (streamer) | „Haladás” · „Térkép és pontok” · „Közösség” · „Profil és Pro” |

**Összegzés:**
- A „Térkép” 3/3-nál külön csoport lett, ebből lett a Map menüpont.
- A számlálót mindhárman a játékhoz kötötték, ezért a kitűzött kategóriák a játék oldalán vannak.
- A feed és a megosztás 2/3-nál „Közösség” alá került, ebből lett a Community.
- A tippeket 2/3 a térképhez tette, ezért a marker-panelen vannak.

**Meglepetés:**
- P2 és P3 a Pro csomagot a fiókhoz tette, nem „Bolt” alá. Ezért a Pro a profilmenüben és a paywallban jelenik meg.
- A „Completion Pack” nevet 2/3 nem értette. Ezért alcímet kapott: „egy játék összes prémium rétege, egyszeri áron”.

## 3 · Sitemap (desktop web)

Oldalsó menü: Home · Progress · Map · Community · Library · Pro.

```
Landing
├── Guest: search & map (view only, no account) ──► Map (all games)
└── Login / Sign up
    └── Home (followed games)
        ├── Progress (all games)
        ├── Map (all games)
        ├── Community (feed) ──► Share progress / write a post
        ├── Account → Subscription
        └── Game page (100% + pins)              ◄── Notification (new collectibles)
            ├── Achievements tab (map-linked, checklists) ──location──► Map
            └── Pinned category (Ancient Relics)
                └── Map – filtered to category
                    ├── Marker panel: info, hints, tips → Mark as found
                    │   └── Hints + community tips
                    └── Paywall: Expedition (Pro)
                        └── Pricing / Pro plans → Checkout → Purchase success
```

A fő feladat legrövidebb útja (a boardon vastag piros nyíl, 3 kattintás): Home → Game page → Pinned category → Map → Marker panel → Mark as found.

## 4 · Fő képernyők és funkcióik

| # | Képernyő | Funkciók |
|---|---|---|
| S1 | Home | Követett játékok completion %-kal, „Continue” a legutóbbi kategóriához |
| S2 | Game page – Progress | Teljes haladás (%), felül a kitűzött kategóriák számlálóval, kategórialista, „Show on map”, régiószűrő |
| S3 | Map | Minden pont látszik. Szűrők: típus, régió, „Not found yet”. Rétegek, keresés |
| S4 | Point detail (oldalpanel) | Lásd a táblázat alatt. |
| S5 | Paywall (modal) | Mit nyit meg a Pro (expedíció, import, korlátlan követés, kitűzés és jelölés, reklámmentesség), ár, 7 napos próbaidő, lemondási feltétel, „Not now” |
| S6 | Pricing | Free / Pro havi / Pro éves (kiemelve) / Completion Pack; időszakos „Gift Pro” akció |
| S7 | Checkout | Választott csomag, bruttó ár forintban, fizetési adatok, összesítő |
| S8 | Purchase success | Mi aktiválódott, következő terhelés, vissza a térképhez |
| S9 | Community (feed) | Haladáskártyák, tippek, kérdések; szűrés játékra és típusra; reakció, komment, mentés; spoilercímke |
| S10 | Game page – Achievements | Lásd a táblázat alatt. |

**S4 – Point detail (oldalpanel):**
- kép és leírás;
- a marker típusától függő infó: gyűjtenivalónál, hogy hol van; küldetésnél és puzzle-nél fokozatos tipp;
- kapcsolódó achievement;
- közösségi tippek és kommentek;
- „Mark as found”, amely fiók nélkül belépésre kér.

**S10 – Game page – Achievements:**
- lista: kész, folyamatban vagy zárolt, ritkasággal;
- a helyhez kötött achievementnél „Show on map”;
- a számlálós achievementnél vezetett checklist infókkal (pl. Defeat every enemy type 37/120).

## 5 · User flow – „A következő ősi ereklye megtalálása Gizehben”

Jelmagyarázat a boardon:
- téglalap = képernyő vagy lépés;
- rombusz = döntés;
- zöld = siker;
- sárga = részleges siker;
- piros = hiba vagy kivétel.

**Fő út:**
1. **CÉL:** megtalálni a még hiányzó gizehi ereklyéket.
2. **Q1 Követi már a játékot?**
   - Nem → E1, üres könyvtár → egy játék követése → Game page.
   - Igen → Game page (100% + pinned).
3. **Q2 Melyik kategória?** → Kitűzött: Ancient Relics 37/50 (13 még nincs megjelölve).
4. **Q3 Melyik régió?** → Gizeh → Map: Gizeh, ereklyék, „Not found yet”, 6 pont.
5. **Q4 Melyik pontot nézi?** → Marker panel (info, tips).
6. **Q5 Megtalálta a játékban?**
   - Nem találja → kép és leírás, tovább a következőre (vissza Q4-re).
   - Igen → „Mark as found” → 38/50, értesítés „Undo”-val.
7. **Q6 Tévedett?** Igen → E2, Undo → 37/50, vissza a marker panelre.
8. **Q7 Van még hiányzó?**
   - Igen → vissza Q4-re.
   - Nem → **SIKER:** Gizeh 15/15, a kategória kész.

**Kivételes ágak:**
- **E3 Paywall (Expedition) a térképről:**
  - „Not now” → vissza a térképre;
  - Pro → Checkout → **részleges siker:** a Pro aktív, az expedíció indul.
- **E4 Mentés sikertelen (offline):** a „Mark as found”-ból indul. A jelölés helyben megmarad, a „Retry” újrapróbálja.
- **E5 Ingyenes jelöléskorlát elérve (100/100):** a „Mark as found”-ból indul, ha a játékban már 100 elem meg van jelölve.
  - Figyelmeztető ablak: a jelölések megmaradnak, a térkép, a szűrők és a tippek ingyenesek maradnak;
  - Pro vagy Completion Pack → Checkout;
  - „Not now” → vissza a térképre, a jelölés nem jön létre.

| Döntés | Szükséges információ | Forrás |
|---|---|---|
| Q1 Követi már a játékot? | Követett játékok listája | Rendszer |
| Q2 Melyik kategória? | Kitűzött kategóriák számlálója | Insight 1 |
| Q3 Melyik régió? | Régiónkénti hiányzószám | Journey |
| Q4 Melyik pont van közel? | Szűrő: csak a még nem jelöltek | A2 csoport |
| Q5 Megtalálta? | Pontkép és leírás | R1-4 |
| Q6 Tévedett? | Értesítés visszavonással | R5-6 |
| Q7 Van még hiányzó? | Frissült számláló | Insight 2 |

**Képernyők a 6. házi wireframe-jéhez:**

| Wireframe | Képernyő |
|---|---|
| W1 | Home |
| W2 | Game page – Progress (fő döntési képernyő) |
| W3 | Map – szűrőpanel + markerpanel |
| W4 | Mark as found megerősítés (38/50, értesítés + Undo) |
| W6 | Üres könyvtár – nincs követett játék (E1) |
| W8 | Paywall – Expedition (E3) |
| W7 | Mentési hiba (E4) |
| W12 | Jelöléskorlát elérve – figyelmeztető ablak (E5) |
| W2-M | W2 mobilon (390 px) |

## 6 · Második flow – „Elakadtam egy puzzle-nél” (Réka)

Fiók nélkül is végigmehet, csak a jelölés kér belépést.

1. **CÉL:** továbbjutni spoiler nélkül.
2. Map: puzzle-marker kiválasztása.
3. Marker panel: leírás + „Hint 1”.
4. **Elég volt?**
   - Igen → **SIKER:** továbbjutott.
   - Nem → „Hint 2”, majd a megoldás (elmosva).
5. **Még mindig nem megy?**
   - Nem, megvan → **SIKER.**
   - Igen → közösségi tippek („Hasznos” szerint) → **SIKER.**
