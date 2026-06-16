# AVT 1 – Vidění, snímání a reprodukce obrazu, zdrojové kódování, digitální fotografie

**Oficiální otázka:** Fyziologie a anatomie vidění. Snímání a reprodukce obrazu. Zdrojové kódování obrazové informace a přenosové video systémy. Digitální fotografie, metody předzpracování.

## Fyziologie a anatomie vidění

Světlo prochází okem postupně přes **rohovku → komorový mok → vstupní pupilu → čočku → sklivec** a vytváří obraz na **sítnici** (obrácený vzhůru nohama). Elastická čočka mění svůj tvar ciliárními svaly (akomodace) a ostří na blízko i na dálku.

Na sítnici jsou dva druhy fotoreceptorů — jako „dva senzory v jednom místě":

- **Tyčinky** – skotopické (černobílé) vidění, vysoká citlivost a rychlá odezva, ~120 milionů, hlavně periferní a noční vidění.
- **Čípky** – fotopické (barevné) vidění, pomalejší, ~7 milionů, nejvíce v oblasti **žluté skvrny** (fovea). Tři typy podle vlnové délky: **L (long), M (medium), S (short)** ≈ R, G, B.

V místě vstupu zrakového nervu (~800 tis. vláken) je **slepá skvrna** bez receptorů. Světlocitlivé buňky jsou na sítnici rozmístěny **náhodně** (jako zrna na filmu), proto oko na rozdíl od pravidelné čtvercové mřížky senzoru **netrpí aliasingem**.

### Vnímání barev

- **Trichromatická teorie:** barvu vnímáme kombinací odezvy tří typů čípků (L, M, S).
- **Oponentní zpracování:** už v sítnici se signál převádí na tři oponentní kanály — černá–bílá, červená–zelená, modrá–žlutá.
- **Metamerismus:** dvě různá spektra (např. spojité denní světlo vs. nespojité LED) se jeví jako stejná barva, protože dají čípkům stejnou odezvu.
- **Chromatická adaptace:** oko se přizpůsobuje intenzitě a barvě osvětlení, aby barvy vypadaly neměnné (obdoba vyvážení bílé).

**Weber–Fechnerův zákon** říká, že vnímání jasu neroste lineárně, ale logaritmicky — vnímaný rozdíl závisí na *poměrné* změně intenzity:

$$
\Delta S = k\,\frac{\Delta L}{L}.
$$

**Prahový kontrast** (nejmenší rozeznatelný rozdíl jasu) je přibližně $\Delta L/L \approx 2\,\%$; menší změnu člověk nezaregistruje. Tento práh určuje, kolik jasových úrovní stačí (viz kvantování níže).

## Optická soustava a multiplex snímání barev

Před snímačem je optická soustava: **objektiv (čočky)**, **IR filtr** (odřízne neviditelné záření, na které je křemík citlivý), **antialiasingový (optický dolnopropustný) filtr** a **barevné filtry**. AA-filtr obraz mírně rozmaže, aby nebyla porušena podmínka prostorového vzorkování (max. $0{,}5$ cyklu na pixel) a nevznikl **aliasing / moaré**.

Barvu lze ze samo o sobě černobílého snímače získat dvěma způsoby multiplexu:

- **Polohový (prostorový) multiplex** – jednotlivé barvy se snímají na *různých místech*:
  - **Bayerova maska** na jednom snímači (viz níže), nebo
  - **3 snímače + dichroický hranol** (3-CCD/3-CMOS): hranol rozdělí světlo na R, G, B a každou složku zachytí vlastní snímač. Vyšší kvalita a plné rozlišení každé barvy, ale dražší a objemnější (profesionální kamery).
- **Časový multiplex** – jeden snímač snímá barvy *postupně v čase* přes **rotující barevné kolo** (color wheel) s R/G/B segmenty. Používá se např. u DLP projektorů a některých starších kamer; nevýhodou jsou barevné artefakty u rychlého pohybu.

## Snímání obrazu – CCD a CMOS

### CCD

Každý pixel je v podstatě **MOS** struktura, kde horní (průhledná) elektroda je světlocitlivá. Dopadající foton vygeneruje náboj, který se hromadí v **potenciálové (kvantové) jámě**; množství náboje odpovídá expozici (osvětlení × doba × plocha). Náboj se pak **fázovou změnou potenciálu na elektrodách posouvá** po řádcích „jako vlny pod surfařem" do sériového registru na kraji, kde proběhne převod $Q\to U$ a A/D převod.

- **Výhody:** nízký šum, dobrá uniformita.
- **Nevýhody:** pomalejší, vyšší příkon, obvykle potřebuje **fyzickou (globální) uzávěrku**.

Dva typické artefakty CCD (ověřeno – viz Zdroje):

- **Smear** – při čtení matice (readout) na osvětlený snímač stále dopadá světlo a elektrony „prosakují" do vertikálního posuvného registru → **svislý světlý pruh**. Potlačuje se **mechanickou uzávěrkou** během vyčítání.
- **Blooming** – přeexponovaný pixel přeteče přebytečným nábojem do sousedních pixelů/registru → opět svislý pruh / rozlití. Potlačuje se **přepadovým kanálem (overflow drain / antiblooming)**, typicky *vertical overflow drain* pod fotodiodou; cenou bývá mírně nižší citlivost a dynamický rozsah.

### CMOS

Nemá posuv náboje — **každý pixel má vlastní obvod** (zesilovač) vedle/pod sebou a je **adresovatelný**. Funguje na principu **akumulačního snímání**: kapacita pixelu se na začátku cyklu nabije, **fotoproud ji během expozice vybíjí** (čím více světla, tím větší vybití), zbylé napětí na konci cyklu = hodnota pixelu; doba vybíjení = **doba expozice**. A/D převod bývá **po sloupcích**.

- **Výhody:** rychlejší, nižší příkon, vyšší integrace na čipu, levnější → dominuje v moderních fotoaparátech.
- **Nevýhody:** vyšší šum, často **rolling shutter** (postupné čtení řádků → zkreslení rychlého pohybu, „jello").

**Šumy snímačů:** **fotonový šum** (statistická povaha světla, fyzikální limit), **tepelný šum / proud za tmy** (klesá s teplotou, proto chlazené senzory), **fixed-pattern noise** (různá citlivost pixelů daná výrobou).

### Fyzikální limit velikosti pixelu

Zmenšování pixelu nelze hnát donekonečna — naráží na **difrakční limit**. Bodový zdroj se i ideální optikou zobrazí jako rozmazaný **Airyho disk** o průměru $D_A = 2{,}44\,\lambda F_{\#}$. Jakmile se rozměr pixelu blíží **vlnové délce světla** (modrá ~450 nm, tj. zhruba $0{,}4\text{–}0{,}5\ \mu\mathrm m$), mluvíme o **sub-difrakčních pixelech**: další zmenšování už nepřináší více detailu, jen víc šumu a problémů s přeslechy (crosstalk) mezi pixely. (Ověřeno – viz Zdroje.)

## Barva, míšení a zobrazovače

**Míšení barev:**

- **Aditivní** – displeje skládají R + G + B, jejich součet dává bílou.
- **Subtraktivní** – tisk skládá **CMY** (Cyan, Magenta, Yellow), součet dává černou (prakticky se přidává K).

**Bayerova maska.** Před pixely je mozaika barevných filtrů v opakujícím se vzoru **RGGB** (2×2): poměr R : G : B = **1 : 2 : 1**, tedy **50 % zelené**. Více zelené proto, že lidský zrak je nejcitlivější kolem ~555 nm a **zelená nejvíce odpovídá vnímanému jasu** (ostrosti). Každý pixel zaznamená jen jednu barvu; chybějící dvě složky se dopočítají **demozaikou** (interpolací z okolních pixelů). Snímače obsahují i **IR filtr**.

> 🔬 **Interaktivní simulace:** Bayerova maska a demozaika — `sim/avt_bayer.html` (sekce *AVT → Simulace* ve wiki). Ukazuje scénu, RAW mozaiku a rekonstrukci. Vyčítání CCD vs CMOS: `sim/avt_ccd_cmos.html`.

**Zobrazovače:**

- **Přímo vyzařující** (samy svítí): CRT, **OLED** — každý subpixel je vlastní zdroj světla (organická vrstva na PN přechodu). Výhody: nekonečný kontrast, široký gamut, pozorovací úhly; nevýhoda: vypalování.
- **Nepřímo vyzařující** (jen modulují cizí světlo): **LCD** — podsvícení + vrstva tekutých krystalů, která s polarizačními filtry a elektrodami řídí průchod světla pro každý RGB subpixel. Výhody: cena, bez vypalování.

**Barevný prostor** je standardizovaný trojúhelník v **diagramu CIE xy** (gamut), na který se zobrazovače kalibrují, aby barvy vypadaly všude stejně.

## Zdrojové kódování obrazu a přenosové video systémy

**Bitová hloubka jasu.** Z prahu ~2 % a požadovaného dynamického rozsahu vyjde, že stačí ~230 jasových úrovní → v praxi **8 bitů = 256 úrovní** (logaritmicky/gama rozložených dle vnímání).

**Jas a barvonosné složky.** Kvůli zpětné kompatibilitě s černobílou TV se přenáší **jasová složka $Y$** (černobílý obraz) a k ní **barvové rozdíly** $R-Y$ a $B-Y$ ($C_R, C_B$). Digitalizace dle **ITU-R BT.601**: $13{,}5$ MHz pro jas, poloviční $6{,}75$ MHz pro každou barvovou složku, 8/10 bitů → tok až 270 Mb/s.

**Chroma subsampling $J{:}a{:}b$** využívá nižší citlivosti oka na barvu (snižuje rozlišení barvonosných složek):

- $J$ = jasová složka (vždy 4),
- $a$ = počet barvových vzorků v 1. řádku,
- $b$ = počet barvových vzorků ve 2. řádku.

$4{:}4{:}4$ bez komprese barev, $4{:}2{:}2$ poloviční vodorovné rozlišení barev, $4{:}2{:}0$ poloviční v obou směrech (běžné u videa).

### Komprese obrazu

- **Bezeztrátová** – výstup je shodný s originálem. Využívá nerovnoměrné pravděpodobnosti hodnot: **Huffmanovo kódování** přiřadí nejkratší kódy nejčastějším symbolům a délkou se blíží **entropii zdroje** $H=\sum_i p_i\log_2\frac1{p_i}$ (minimální počet bitů na symbol).
- **Ztrátová (JPEG)** – využívá **2D diskrétní kosinovou transformaci (DCT)**:
  1. jas se vycentruje kolem nuly (0–255 → −128…127),
  2. obraz se dělí na bloky **8×8**,
  3. na blok se aplikuje 2D DCT → frekvenční koeficienty 8×8 (vlevo nahoře stejnosměrná složka = celkový jas, na kterou je oko nejcitlivější),
  4. **kvantizace** – koeficienty se dělí kvantizační maticí a zaokrouhlí; vysoké frekvence (vpravo dole) se zaokrouhlí na nulu (zde vzniká ztráta),
  5. dlouhé řady nul se efektivně zakódují (RLE + entropie).
  Nastavení **kvality** mění kvantizační matici. Barvové složky se komprimují silněji než jas.

### Komprese videa

Využívá **redundanci**:

- **prostorová** – uvnitř snímku (např. JPEG/intra),
- **časová** – sousední snímky bývají podobné, přenáší se jen **rozdíly**.

Pokročilá metoda: **Motion Estimation (ME)** s **pohybovými vektory (MV)** — obraz se dělí na bloky a v předchozím snímku se hledá, kam se shodný blok posunul. Snímky: **I** (intra, jako JPEG), **P** a **B** (predikované pomocí MV).

**Hodnocení kvality:** objektivní (matematické) — např. **PSNR**; subjektivní (skupina pozorovatelů) — věrnější vnímání, ale časově i finančně náročné.

## Digitální fotografie a předzpracování

- **Vyvážení bílé** upravuje barvy tak, aby vypadaly přirozeně za libovolného nasvícení (obdoba chromatické adaptace oka). Nejjednodušší metoda **„šedý svět"** vyrovná průměrný jas složek: $Y_R = Y_G = Y_B$.
- **IR filtr** odstraní záření mimo viditelné spektrum.
- **Bayerova maska + demozaika** (viz výše) zajistí barevný obraz.
- Další předzpracování: korekce gama, redukce šumu, ostření, korekce vinětace a zkreslení objektivu.

## Co umět u zkoušky

- Cesta světla okem, tyčinky vs. čípky, trichromatická vs. oponentní teorie, Weber–Fechner a práh ~2 %.
- CCD vs CMOS: princip, vyčítání, výhody/nevýhody, **smear**, **blooming**, šumy, difrakční limit pixelu.
- Polohový (Bayer, 3-CCD hranol) vs. časový (barevné kolo) multiplex barev.
- Bayerova maska RGGB a proč 2× zelená; demozaika.
- $Y C_B C_R$, chroma subsampling $4{:}2{:}0$, JPEG (DCT + kvantizace), video (I/P/B, ME/MV), PSNR.

**Zdroje:** AVT skripta (`avt1.pdf`, `avt2.pdf`), HEX-compost; CCD smear/blooming a antiblooming drain ([DPReview: Smear vs. blooming](https://www.dpreview.com/forums/thread/777399)); difrakční limit a sub-difrakční pixely ([Cambridge in Colour: Diffraction-limited photography](https://www.cambridgeincolour.com/tutorials/diffraction-photography.htm)).
