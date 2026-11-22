# 3. Használhatósági és akadálymentességi audit – Gamer Guides Premium

**Vizsgált szolgáltatás:** [Gamer Guides](https://www.gamerguides.com) – útmutatók, interaktív térképek, checklistek és achievementlisták játékosoknak, ingyenes alapszolgáltatással és fizetős csomagokkal (Ad Free, Map Explorer, Premium, egyszeri Legend). A Completely közvetlen versenytársa.

**Vizsgált feladat:** Bence (a 2. házi personája) a térképes funkciók miatt a **Map Explorer éves csomagot** választja, és eljut a regisztrációig. A fiók létrehozása előtt megálltunk. Ez a feladat közvetlenül hasznos a Completely saját paywall- és checkout-döntéseihez.

**Módszer:** Nielsen-heurisztikák, WCAG 2.1 AA. Kézi billentyűzetes próba (Tab, Shift+Tab, Escape), kontrasztmérés a számított CSS-színekből a WCAG relatív fényesség képletével. Dátum: 2026. november 16., asztali böngésző, 1280×860 px nézet.

**Képernyőképek:** [03-audit-kepek/](03-audit-kepek/)

## Leletek

| # | Lelet (megfigyelhető jelenség) | Alapelv | Következmény Bencének | Javítási irány | Súlyosság |
|---|---|---|---|---|---|
| L1 | A fejléc keresőmezője **fókuszra** megnyit egy átfedő panelt. Az Escape nem zárja be, a Tab a panel 10 játékcsempéje, a keresőmező és a bezárógomb között **körbe jár** (12 Tab után újra a 2. csempén). A csomagválasztóhoz csak egérrel lehet eljutni. *(Kézi Tab-próba, [05](03-audit-kepek/05-kereso-fokuszcsapda.jpg), [06](03-audit-kepek/06-fokusz-koroz.jpg))* | WCAG 2.1.2 (nincs billentyűzetcsapda), 3.2.1 (fókuszra nincs kontextusváltás) | Billentyűzettel nem tud csomagot választani. | A panel gombnyomásra nyíljon, az Escape zárja be, és a fókusz a bezárás után térjen vissza a mezőre. | **Nagy** · akadálymentesség |
| L2 | A Map Explorer éves csomag és a kártyás fizetés kiválasztása után a következő oldal címe **„FREE ACCOUNT”**, a szövege „Always free. No card required.” A választott csomag és ár sehol nem látszik. ([07](03-audit-kepek/07-fizetesi-mod.jpg) → [08](03-audit-kepek/08-ingyenes-regisztracio.jpg)) | Nielsen 1. (a rendszer állapotának láthatósága), 4. (következetesség) | Elbizonytalanodik, hogy jó helyen jár-e, és hogy mit fog fizetni. | A regisztrációs lépés fejlécében maradjon ott a választott csomag és ár („Map Explorer, évi 34,99 $ – 1/2. lépés: fiók”). | **Nagy** |
| L3 | A „Save 50%” felirat az éves fülön minden csomagra vonatkozónak tűnik, de csak a Premiumra igaz (9,99 $ × 12 = 119,88 $ → 59,99 $). Az Ad Free (35,88 $ → 24,99 $) kb. **30%**, a Map Explorer (47,88 $ → 34,99 $) kb. **27%** megtakarítás. Az egyszeri fülön „Save ∞%” szerepel. ([01](03-audit-kepek/01-csomagok-eves.jpg), [02](03-audit-kepek/02-csomagok-havi.jpg), [03](03-audit-kepek/03-egyszeri-legend.jpg)) | Nielsen 2.; **megtévesztő minta** (félrevezető kedvezmény) | Túlbecsüli a választott csomag megtakarítását. | Csomagonként a valós megtakarítás („Évente 12,89 $-t spórolsz”). | Közepes · **megtévesztő minta** |
| L4 | **Kontrasztmérés (szöveg):** aktív fizetési ciklus fül fehér szöveg rózsaszín (#E75971) alapon **3,05 : 1** (16 px); „NEW” címke **3,46 : 1** (10 px, félkövér); a fő gomb („Sign up & Subscribe now”) fehér a zöld (#1C8B1A) alapon **4,41 : 1** (16 px félkövér). Mindhárom 4,5 : 1 alatt. | WCAG 1.4.3 | Gyengébb látással vagy erős napfényben a választott ciklus és a fő gomb nehezen olvasható. | Sötétebb alapszín (pl. #B8344B → kb. 5,8 : 1), a címke legalább 12 px. | Közepes · akadálymentesség |
| L5 | **Kontrasztmérés (felületi elem):** a regisztrációs mezők kerete kb. **1,77 : 1** a háttérhez, a helyőrző szöveg **3,29 : 1**. A „Create my account” gomb letiltva (átlátszóság 0,45, kb. **2,28 : 1**), és nem derül ki, miért. ([08](03-audit-kepek/08-ingyenes-regisztracio.jpg)) | WCAG 1.4.11, 1.4.3; Nielsen 9. | Nem látja, hol vannak a mezők, és nem tudja, mitől lesz aktív a gomb. | A keret legalább 3 : 1. A gomb maradjon aktív, és küldéskor jelezze mezőnként a hibát. | Közepes · akadálymentesség |
| L6 | Az árak csak USD-ben jelennek meg, bár a regisztráció Magyarországot tölti ki előre („used for tax”). A végösszeg (ÁFA, forint) a döntés pontján nem látszik. | Nielsen 2. (illeszkedés a valós világhoz); a rejtett költség kockázata | Nem tudja, mennyit von le a bank forintban. | Helyi pénznem és bruttó ár a csomagkártyán. | Kicsi |

## Kötelező elemek

- **Kézi akadálymentességi ellenőrzés:** az L1 billentyűzetes próbával (Tab, Escape) készült, nem automatikus eszközzel.
- **Kontrasztmérés:** 7 mérés, ebből 6 nem éri el az AA szintet. Kivétel a 13,6 px-es szürke segédszöveg (4,42 : 1), ami szintén határeset.
- **Megtévesztő minták külön jelölve:**
  - L3 – félrevezető kedvezmény. Tisztességes alternatíva: csomagonként a valós összeg.
  - L2 – a csomag „eltűnik”, és az oldal „ingyenest” kommunikál a fizetős folyamat közepén. Tisztességes alternatíva: a csomag és az ár végig látszik.
- **Pozitív példák is:**
  - A „Cancel anytime” és a számlázási ciklus már a csomagkártyán ott van.
  - A fizetési módnál szerepel, hogy a lemondás a beállításokban történik.
  - Az ország előtöltése meg van indokolva.

## Állapotok ellenőrzése

| Állapot | Megfigyelés | Értékelés |
|---|---|---|
| Normál | A csomagok, a ciklusváltás és a fizetési mód választása működik. | Jó |
| Betöltő | Nem volt megfigyelhető késleltetés. | Nem értékelhető |
| Üres | Nem releváns. | – |
| Hiba | Üres mezőkkel nem lehet küldeni, mert a gomb le van tiltva, így hibaüzenet sem jelenik meg. | **Gyenge** |
| Siker | A fiók létrehozása előtt megálltunk. | Nem vizsgált |
| Tiltott | A „Create my account” gomb tiltott, de az ok nem látszik. | **Gyenge** |

## Persona-frissítés

- **Új kockázat:** ha a fizetési folyamat közben „ingyenes”-t lát, elbizonytalanodik és kilép. (L2)
- **Új igény:** billentyűzettel is végig tudjon menni a vásárláson, mert stream közben gyakran billentyűparancsokkal navigál (R5-1 alapján is valószínű). (L1)

## Négy kockázat a Completelynél, és hogyan előzzük meg

| # | Kockázat | Megelőző javítási irány |
|---|---|---|
| K1 | A térkép pontjai csak színnel jelzik, hogy egy darab megvan-e vagy hiányzik (WCAG 1.4.1). | Ikon + felirat (pipa / üres kör) és a „Csak a hiányzók” szűrő. |
| K2 | A paywall keresés közben szakítja meg a fő feladatot (mint a Gamer Guides 50 jelölős korlátja). | A hiányzólista, a szűrt térkép, a „Megtaláltam” és az alap tippek mindig ingyenesek; paywall csak kényelmi funkciónál, mindig „Not now” gombbal. |
| K3 | Téves „Megtaláltam” jelölés, visszavonás nélkül (R5-6). | Visszavonható értesítés 8 másodpercig, és a darabnál „Mégse találtam meg” művelet. |
| K4 | A közösségi tippek között lehet hibás vagy spoileres (a Gamer Guides kommentjeinél is előfordul). | Spoilercímke, „Hasznos” szavazás, jelentés gomb; az ellenőrzött alapanyag mindig a tippek felett áll. |

## Mit tanulunk belőle?

1. A választott csomag és a bruttó ár forintban kísérje végig a checkoutot.
2. A kedvezmény mindig a valós összeget mutassa.
3. A paywall nem állhat a fő feladat útjába.
4. Minden lenyíló és átfedő elem billentyűzettel is nyitható és zárható legyen.
