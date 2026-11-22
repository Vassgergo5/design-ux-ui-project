# 4. Problémadefiniálás és lehetőségkeresés

**FigJam „4. Probléma és irányok”:** https://www.figma.com/board/jTU7My5cBW91w0COne76H8?node-id=13-520

Jelölés a boardon: **zöld cetli** = kutatási bizonyíték (forrásjellel), **narancs cetli** = még nem ellenőrzött feltevés.

## 1 · Projektbrief (egyoldalas)

| Elem | Tartalom | Forrás |
|---|---|---|
| Probléma | A játékos nem látja egy helyen, mi van még hátra és hol, a haladását több helyen vezeti, és elakadva nem kap gyors, spoilermentes segítséget. | Insight 1–3 |
| Célfelhasználó | Elsődleges: Bence, a completionist. Másodlagos: Réka, aki elakadt vagy egy konkrét dolgot keres. | Persona |
| Elsődleges feladat | Egy kitűzött kategóriából a következő, még meg nem jelölt darab megkeresése a szűrt térképen, és megjelölése. Másodlagos: egy markerre kattintva fokozatos tippet kapni. | Journey 4. |
| Szervezeti cél | Visszatérő használat és aktív közösség. Bevétel Pro-előfizetésből (fő) és egyszeri Completion Packből. | Brief, R4-6 |
| Korlátok | Csak Figma-design. Gyűjtenivaló-szintű szinkron nincs (achievement-import csak Pro-ban, ahol az API engedi). Spoilervédelem, ingyenes alapfunkció, WCAG AA. | 1. házi, audit |
| Sikerkritérium | 90 mp alatt, segítség nélkül: kitűzött kategória → szűrt térkép → „Mark as found”, 37/50 → 38/50. | 1. házi |
| **Hatókör** | Lásd a lista alatt. | Insight 1–3, A5 |
| **Pro-csomag** (havi / éves) | Lásd a lista alatt. | A6 (R2-6, R4-6, R5-5), brief |
| **Kizárások** | Gyűjtenivaló-szintű automatikus szinkron (az API-k nem adják), képernyőképes import, natív mobilapp, profilkozmetika, élő chat. | – |

**A hatókörbe tartozik:**
- dashboard;
- játékoldal kitűzött kategóriákkal és Achievements füllel;
- teljes térkép szűrőkkel;
- marker-panel: leírás, fokozatos tipp, közösségi tippek, kapcsolódó achievement;
- kézi „Mark as found” visszavonással;
- vezetett checklist a számlálós achievementekhez;
- megosztás;
- vendégmód (csak megtekintés);
- paywall és checkout.

**A Pro-csomag tartalma:**
1. Achievement-import, ahol az API engedi (pl. Steam). A gyűjtenivalók továbbra is kézzel jelölendők.
2. Keresőexpedíció a kiválasztott kategóriák még nem jelölt pontjain át, megadott kiindulópontból.
3. Korlátlan követés (ingyen: 3 játék).
4. Korlátlan kitűzés (ingyen: 3 kategória játékonként).
5. Korlátlan jelölés (ingyen: játékonként 100 megtaláltnak jelölt elem).
6. 7 napos próbaidő: az első limitnél vagy expedíció indításakor ajánljuk fel.
7. PRO badge a kommentekben. Ez csak jelzés, a tippek sorrendjét a „Hasznos” szavazatok adják.
8. Reklámmentesség.
9. Időszakos ajándékakció (pl. ünnepek, nagy megjelenések): egy Pro-felhasználó 1 hónap Prót ajándékozhat.
   - Kártya nélkül fogadható, és nem újul meg.
   - Lejárat előtt értesít, utána semmi nem vész el.

## 2 · Érintettek – hatás × érdekeltség

| | Kisebb érdekeltség | Nagy érdekeltség |
|---|---|---|
| **Nagy hatás** | **Oktató (kurzus):** a követelmények teljesülése | **Completionist (Bence):** gyorsan megtalálni a hiányzót. ? Bejelöli-e a meglévő haladását? · **Üzleti tulajdonos:** előfizetési bevétel. ? Elég vonzó-e a Pro? |
| **Kisebb hatás** | **Alkalmi / elakadt játékos:** egy darabot gyorsan, regisztráció nélkül. → Fiók nélkül kereshet és nézhet, a jelöléshez kell fiók (R3-3). · **Kiadó:** nincs spoiler, márkahasználat. ? Kell-e engedély a térképanyaghoz? | **Streamer (R5):** látványos haladás, reklám nélkül. ? Mennyire fontos a megosztás? · **Tartalomszerkesztő:** pontos adatok. ? Ki ellenőrzi a pontokat? |

## 3 · User storyk és problémaállítás

| # | User story | Elfogadási feltétel (Given / When / Then) |
|---|---|---|
| US1 | Completionistként ki szeretném tűzni a fontos kategóriákat, hogy a játék oldalán rögtön lássam őket, és egy kattintással a térképre szűrjek. | GIVEN kitűztem az Ancient Relics kategóriát (Gizeh 9/15) WHEN „Show on map” THEN a térkép Gizehre áll, csak az ereklyék látszanak, és a még meg nem jelöltekre szűrhetek |
| US2 | Egy kattintással szeretném megjelölni a megtalált darabot, hogy mindenhol frissüljön, és vissza tudjam vonni, ha tévedtem. | GIVEN egy hiányzó ereklye részletei nyitva WHEN „Mark as found” THEN a pont kipipálva elhalványul, 37/50 → 38/50, 8 mp-ig „Undo” |
| US3 | Elakadt játékosként egy markerre kattintva először csak egy apró tippet szeretnék, és csak ha kell, a teljes megoldást vagy mások tanácsait. | GIVEN a térképen egy puzzle-marker WHEN rákattintok THEN „Hint 1” látszik, a megoldás rejtve, alatta a közösség tippjei |
| US4 | Ha kész egy kategória, egy kattintással meg akarom osztani, és tippet is adnék másoknak. | GIVEN Gizeh 15/15 WHEN „Share progress” THEN kész haladáskártya a feedben, szöveggel kiegészíthető |
| US5 | Ha csak egy dolgot keresek, fiók nélkül szeretném megnézni, hol van és hogyan szerzem meg. | GIVEN nem vagyok bejelentkezve WHEN rákeresek: „Ancient Relic #10” THEN látom a markert és a panelt; a „Mark as found” helyén: „Jelentkezz be a haladás mentéséhez” |
| US6 | Az achievementeket is itt követném: ami helyhez kötött, mutassa a térképen; a „győzz le minden ellenséget” típushoz kapjak vezetett checklistet. | – |

**★ Problémaállítás:** a játékos problémája az, hogy a lista, a térkép, a segítség és a saját haladása külön oldalakon van. Ezért:
- nem látja egy helyen, mi van még hátra és hol;
- a fontos kategóriákat sehol nem tudja külön követni;
- elakadva nem kap gyors, spoilermentes segítséget.

Emiatt feleslegesen keres, kettős nyilvántartást vezet, és feladja a játékot vagy a 100%-ot. *(Kapcsolódik: Insight 1, 2 és 3.)*

## 4 · How Might We kérdések

- **H1:** Hogyan érhetnénk el, hogy a játékos a neki fontos kategóriákat azonnal lássa? ✓
- **H2:** Hogyan tarthatnánk egy helyen a haladást úgy, hogy bízzon benne? ✓
- **H3:** Hogyan csökkenthetnénk egy téves jelölés kárát? ✓
- **H4:** Hogyan igazíthatnánk a hiányzó darabot a játékos helyzetéhez? ✓
- **H5:** Hogyan köthetnénk a közösség tudását a megfelelő markerhez, spoiler nélkül? ✓

## 5 · Megoldásötletek (13) és szavazás

Egy • egy szavazat. Szavazott: én és 2 szintetikus résztvevő. Az Ö13 a szavazás után került be.

| # | Ötlet | Szavazat |
|---|---|---|
| Ö1 | Kitűzhető kategóriák számlálóval (37/50) a játék oldalán | ••• |
| Ö2 | „Show on map”: a térkép a kategóriára szűrve nyílik | •• |
| Ö3 | „Mark as found” a pontrészletben, mindent frissít | ••• |
| Ö4 | Visszavonható értesítés + „Not found after all” | • |
| Ö5 | Import a napló képernyőképéből (OCR) | – |
| Ö6 | Achievement-import (Steam, ahol az API engedi) – Pro | – |
| Ö7 | Keresőexpedíció: kiválasztott kategóriák, megadott kiindulópontból (Pro) | •• |
| Ö8 | „Legközelebbi hiányzó” a régióban | – |
| Ö9 | Második képernyős stream-mód | – |
| Ö10 | Közösségi tippek és kommentek a markeren | •• |
| Ö11 | Fokozatos tipp: Hint 1 → Hint 2 → megoldás | •• |
| Ö12 | Haladás megosztása a feedben (kész kártya) | • |
| Ö13 | Achievements fül: térkép + vezetett checklist (R4-4, A5) | – |

## 6 · Hatás–kivitelezhetőség mátrix

| | Könnyű | Nehéz |
|---|---|---|
| **Nagy hatás** | **Gyors győzelem:** Ö1 + Ö2 + Ö3 + Ö4 (bizonyíték: A1, A2, A3, 3–4/5 résztvevő) · Ö10 + Ö11 marker-tippek, fokozatosan (A4, 4/5, Insight 3; feltevés: induláskor mi írjuk az alapot) | Ö6 achievement-import (feltevés: csak achievementet ad, gyűjtenivalót nem) · Ö7 keresőexpedíció (feltevés: ez a Pro fő húzóereje) · Ö13 Achievements fül |
| **Kis hatás** | Ö9 stream-mód (csak R5-1 kérte) · Ö12 megosztás (A5, 2/5; feltevés: új felhasználókat hoz) | Ö5 OCR-import (feltevés: pontatlan lenne) · Ö8 legközelebbi hiányzó (feltevés: a játékos helyét nem ismerjük) |

## 7 · Kiválasztott irány

**★ Kiválasztott irány:** egy folyamat, amely így halad:
1. kitűzött kategória;
2. szűrt térkép;
3. marker-panel;
4. „Mark as found”.

**Ehhez kapcsolódik:**
- fokozatos és közösségi tippek (Ö10, Ö11);
- Achievements fül checklisttel (Ö13);
- a haladás megosztható (Ö12);
- vendégként fiók nélkül is lehet nézni;
- Pro: keresőexpedíció (Ö7) és achievement-import (Ö6), a részletek a briefben.

**Mit hagyunk el:** gyűjtenivaló-szintű automatikus szinkron, képernyőképes import, legközelebbi hiányzó (Ö8), stream-mód (Ö9).

**Mi bizonytalan (feltevés):**
- Felviszik-e kézzel a meglévő haladásukat?
- Lesz-e elég jó közösségi tipp az elején?
- Elég bevételt hoz-e a Pro és a Completion Pack?

| Ellenőrizendő feltevés | Hogyan ellenőrizzük |
|---|---|
| Bejelölik a meglévő haladásukat | Prototípus-teszt: megpróbálják-e az onboarding után |
| A szűrt térkép gyorsabb | Időmérés a 8. házi tesztjén (cél: 90 mp) |
| A paywall nem zavarja a fő feladatot | Tesztfeladat: találkozik a paywallal, visszatalál-e |
| A közösségi tippek megbízhatók | Teszt: a „Hasznos” jelölésű tippet választják-e először, és továbbjutnak-e vele |
