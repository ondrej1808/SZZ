
## 2026-05-30 LAGA otázky 1-2

Zpracovány první dvě otázky z `SZZ - Teoretické okruhy.md` pro předmět LAGA. Použitý jediný PDF zdroj: `LAGA/akla_2023_09_15.pdf`.

Vytvořené poznámky:
- `LAGA/01 Struktura linearniho prostoru, baze a dimenze.md`
- `LAGA/02 Maticovy pocet, determinant, inverze, vlastni cisla.md`

Dodrženo: zdroje po sekcích, wikilinky mezi souvisejícími otázkami, bez doplňování mimo PDF podklad.

## 2026-05-30 Úprava matematické notace

Na žádost uživatele doplněno pravidlo: matematiku v poznámkách psát jako Obsidian LaTeX (`$...$`, `$$...$$`) a nepoužívat textové code bloky pro rovnice.

Přepracované soubory:
- `LAGA/01 Struktura linearniho prostoru, baze a dimenze.md`
- `LAGA/02 Maticovy pocet, determinant, inverze, vlastni cisla.md`

## 2026-05-30 Oprava LAGA podle zpětné vazby

Doplněno pravidlo: zdroje uvádět jako Obsidian wikilinky na PDF (`[[...pdf#page=...|...]]`). `hex_compost.pdf` používat jako kontrolní kompas rozsahu pro studenta mířícího na B, ale faktické definice ověřovat proti předmětovým PDF.

Přepracováno:
- `LAGA/01 Struktura linearniho prostoru, baze a dimenze.md`: doplněny plné axiomy lineárního prostoru, opraveno a zpřesněno lineární zobrazení, jádro/obraz, skalární součin včetně metrického tensoru `G`, zdroje přes wikilinky.
- `LAGA/02 Maticovy pocet, determinant, inverze, vlastni cisla.md`: zpřesněn maticový součin, determinant, inverze přes GEM/adjungovanou matici, Cramerova věta, vlastní hodnoty, podobnost a diagonalizace; zdroje přes wikilinky.

Kontrola: v poznámkách nezůstaly staré textové code bloky ani backtick zdroje typu `akla_...`.

## 2026-05-30 GitHub setup guide

Přidán `README.md` s rychlým návodem pro ostatní: instalace `pdf-mcp[semantic]`, registrace `pdf-mcp` v Codexu a registrace Obsidian MCP endpointu přes `OBSIDIAN_TOKEN`.

## 2026-05-30 MA2A otazky 7-8

- Zpracovana slozka `MA2A` pro otazky 7 a 8 ze `SZZ - Teoretické okruhy.md`.
- Vytvoreno: [[MA2A/07 Funkce vice promennych, gradient, extremy]] a [[MA2A/08 Vicerozmerne integraly a integralni vety]].
- Pouzite podklady: [[MA2A/dipocet.pdf]] pro diferencialni pocet vice promennych, [[MA2A/integralni_pocet_vice_prom.pdf]] pro integralni pocet vice promennych.
- Zachovano: matematika v Obsidian LaTeXu, zdroje po sekcich jako wikilinky na PDF, vzajemne odkazy mezi gradientem/potencialem, znacky `> [!todo] DOPLNIT OBRÁZEK:` pro mista vhodna pro diagramy.
- Poznamka k nastrojum: PDF MCP pri prvnim cteni poskytl metadata a obsah/TOC stran, nasledne spadl na `Transport closed`; dalsi text byl nouzove extrahovan lokalne z tech samych PDF pres `pdftotext`, bez pouziti externich zdroju.

## 2026-05-30 oprava diakritiky

- Přidáno pravidlo do [[ai/agent-pravidla]]: běžný český text psát s háčky a čárkami.
- Přepsány poznámky [[MA2A/07 Funkce vice promennych, gradient, extremy]] a [[MA2A/08 Vicerozmerne integraly a integralni vety]] tak, aby prose text, nadpisy a aliasy zdrojů používaly českou diakritiku.
- Zachovány technické identifikátory, názvy souborů, LaTeX a odkazy na PDF.


## 2026-05-30 - MA1A otázky 3-4

- Zpracovány otázky 3 a 4 do složky `MA1A`:
  - [[03 Funkce jedne promenne, limita, derivace, prubeh]]
  - [[04 Primitivni funkce a integraly]]
- Použité podklady: [[ma1a-23k2.pdf]], [[ma1a-23k3.pdf]], [[ma1a-23k4.pdf]], [[ma1a-23k6.pdf]], [[ma1a-23k7.pdf]], [[ma1a-23k8.pdf]], [[ma1a-23k9.pdf]], [[ma1a-23k10.pdf]].
- Taylorův polynom doplněn z [[hex_compost.pdf#page=22]], protože v adresáři MA1A není dodaná kapitola 5.
- Poznámky používají Obsidian LaTeX rovnice, českou diakritiku v běžném textu, zdroje u sekcí a wikilinky mezi souvisejícími tématy.


## 2026-05-30 - DRN otázky 5-6

- Zpracovány otázky 5 a 6 do složky `DRN`:
  - [[05 Linearni diferencialni rovnice a soustavy]]
  - [[06 Numericke metody rovnic integralu a diferencialnich rovnic]]
- Použitý podklad: [[dnbook.pdf]]. Originální text je anglicky, výstup je česky.
- Otázka 5 čerpá hlavně z kapitol 15, 16, 26 a 27.
- Otázka 6 čerpá hlavně z kapitol 5, 11-13, 18-20 a 23-25.
- Poznámky používají Obsidian LaTeX, český text s diakritikou, wikilinky a zdroje u sekcí.


## 2026-05-30 - KANA otázky 9-10

- Zpracovány otázky 9 a 10 do složky `KANA`:
  - [[09 Komplexni funkce integral singularity rezidua]]
  - [[10 Fourier Laplace Z transformace]]
- Použité podklady: [[KANA/testkom.pdf]] pro komplexní analýzu a [[KANA/transformace.pdf]] pro Fourierovy řady, Fourierovu transformaci, Laplaceovu transformaci a Z-transformaci.
- Poznámky používají Obsidian LaTeX, český text s diakritikou, zdroje po sekcích jako wikilinky na PDF a odkazy mezi souvisejícími tématy.
- Poznámka k nástrojům: PDF MCP v této části nebyl stabilní, proto byl text extrahován lokálně z dodaných PDF pomocí `pdftotext`; nebyly použity externí zdroje.


## 2026-05-30 - PST otázky 11-12

- Zpracovány otázky 11 a 12 do složky `PST`:
  - [[11 Nahodna velicina vektor rozdeleni charakteristiky]]
  - [[12 CLV MLE testovani hypotez]]
- Použitý podklad: [[PST/01PST_zapisky.pdf]].
- Otázka 11 čerpá hlavně z definic náhodné veličiny, distribuční funkce, diskrétního a spojitého rozdělení, momentů, rozptylu, náhodného vektoru, korelace a nezávislosti.
- Otázka 12 čerpá z CLV, bodových odhadů, metody maximální věrohodnosti, principu testování hypotéz, t-testů a chí-kvadrát testu dobré shody.
- Poznámky používají Obsidian LaTeX, český text s diakritikou, wikilinky a zdroje u sekcí.


## 2026-05-31 - EMPA otázky 13-14

- Zpracovány odborné otázky 13 a 14 do složky `EMPA`:
  - [[13 Elektricke a magneticke pole elektrostatika kapacita]]
  - [[14 Stacionarni magneticke pole indukcnost Faraday]]
- Použitý podklad: [[empa_complete_edition.pdf]].
- Otázka 13 čerpá hlavně z kapitol 1-5: klasifikace polí, vodiče a dielektrika, veličiny $\mathbf E,\mathbf D,\mathbf P$, Gaussova věta, potenciál, kapacita, energie a metoda zrcadlení.
- Otázka 14 čerpá hlavně z kapitol 7-10: stacionární magnetické pole, Biotův-Savartův zákon, Ampérův zákon, magnetické materiály, energie pole, indukčnost, magnetické obvody a Faradayův zákon.
- `hex_compost.pdf` použit pouze kontrolně pro rozsah. U indukčností základních uspořádání ponechán todo blok, protože hlavní EMPA text odkazuje detailní vztahy na příklady MG/35.


## 2026-05-31 - ELD otázky 15-16

- Zpracovány odborné otázky 15 a 16 do složky `ELD`:
  - [[15 Elektromagneticka vlna v neomezenem prostredi a rozhrani]]
  - [[16 Vedene a evanescentni vlny vlnovody vedeni]]
- Použitý podklad: [[Elektromagnetická vlna_13_5_2021.pdf]].
- Otázka 15 čerpá hlavně z kapitol 1 a 2: Maxwellovy rovnice, rovinná harmonická vlna, vlnová impedance, vlnová délka, rychlosti, Poyntingův vektor, polarizace, rozhraní, Snellovy zákony, totální odraz, evanescentní vlna a Brewsterův úhel.
- Otázka 16 čerpá hlavně z kapitol 2.6.4, 2.6.6, 3 a 4: vedená a evanescentní vlna, obdélníkový vlnovod, módy TE/TM, dominantní mód TE10, impedance ve vlnovodu, výkon, vlna TEM na vedení, odraz a stojaté vlnění.
- `hex_compost.pdf` použit kontrolně pro rozsah. Ponechány todo bloky pro Gaussův svazek, válcovou vlnu, elementární zářiče, blízké/přechodné/vzdálené pole a anizotropní prostředí, protože tyto části nejsou v dodaném ELD PDF samostatně doložené.


## 2026-05-31 - Oprava KANA značení transformací

- Upraveno [[09 Komplexni funkce integral singularity rezidua]]: odstraněn zbytečný index křivky `Ind` z reziduové věty, ponechána jednodušší verze pro kladně orientovanou jednoduchou křivku a singularity uvnitř.
- Upraveno [[10 Fourier Laplace Z transformace]]: Z-transformace značena jako $\mathbb Z$, Laplaceova transformace zůstává $\mathcal L$, Fourierova transformace $\mathcal F$.
- Opravena rozbitá LaTeX sekvence v inverzní Fourierově větě.
- Přidán přehled [[10a Srovnani transformaci Fourier Laplace Z]] se sloupci značka, transformace, přímá transformace, inverzní transformace a spojitá/diskrétní povaha.


## 2026-05-31 - SAS otázky 19-20

- Zpracovány odborné otázky 19 a 20 do složky `SAS`:
  - [[19 Signaly casova spektralni reprezentace vzorkovani nahodne procesy]]
  - [[20 Soustavy LTI konvoluce stabilita pasmove signaly modulace]]
- Použitý podklad: [[SAS/sas_cviceni_v0.96_250225.pdf]].
- Otázka 19 čerpá hlavně z kapitol 2, 4, 5 a 11: energie, výkon, autokorelace, Fourierovy reprezentace, vzorkování, stacionární a ergodické procesy a bílý šum.
- Otázka 20 čerpá hlavně z kapitol 7, 8 a 9: klasifikace soustav, LTI soustavy, impulsová odezva, konvoluce, stabilita, popis Laplaceovou a Z-transformací a kmitočtový popis.
- Podle požadavku přidány TikZ grafy k definovaným konceptům. `hex_compost.pdf` použit kontrolně: doplněna klasifikace deterministický/stochastický signál a potvrzen rozsah k pásmovému signálu, komplexní obálce a analogovým modulacím.
- Část Hilbertovy transformace, komplexní obálky a analogových modulací je označena jako TODO, protože dodané SAS PDF obsahuje hlavně zadání teoretických otázek, nikoli výklad.


## 2026-05-31 - MA2A TikZ grafy

- Upraveny poznámky `MA2A`, aby nevyžadovaly externí obrázky:
  - [[07 Funkce vice promennych, gradient, extremy]]
  - [[08 Vicerozmerne integraly a integralni vety]]
- Původní todo bloky „DOPLNIT OBRÁZEK“ nahrazeny TikZ náčrty: graf funkce a vrstevnice, gradient a vrstevnice, Lagrangeovy vázané extrémy, základní integrační oblast, tok přes orientovanou plochu a orientace ve Stokesově větě.


## 2026-05-31 - SAS přehled spektrálních reprezentací

- Přidán samostatný přehled [[19a Srovnani spektralnich reprezentaci signalu]].
- Tabulka srovnává spojitý/diskrétní a periodický/neperiodický signál, odpovídající typ spektra, opačný směr inverze a používanou reprezentaci FS/FT/DFS/DtFT.
- Z [[19 Signaly casova spektralni reprezentace vzorkovani nahodne procesy]] přidán odkaz na nový přehled.


## 2026-06-05 - TSI otázky 29-30

- Před zahájením práce přečtena složka `ai`; poslední dokončená práce byla SAS otázky 19-20 a přehled spektrálních reprezentací.
- Zpracovány odborné otázky 29 a 30 do složky `TSI`:
  - [[29 Komunikacni kanal digitalni prenosy telefonie xDSL]]
  - [[30 Bunkove mobilni site GSM GPRS EDGE UMTS]]
- Použité podklady: přednášky `TSI/01`, `TSI/02`, `TSI/04`, `TSI/07`, `TSI/08`, `TSI/10`, `TSI/12` a kontrolně `TSI/13`.
- Otázka 29 čerpá hlavně z informační propustnosti a E-modelu, telefonního kanálu, PCM 30/32, PDH/SDH/OTH, digitálních spojovacích systémů, VoIP signalizace a xDSL.
- Otázka 30 čerpá hlavně z buňkového principu, metod FDMA/TDMA/CDMA, handoveru, architektury GSM, datových služeb CSD/HSCSD/GPRS/EDGE a UMTS.
- TikZ grafy nebyly přidány; u těchto dvou otázek byly přednáškové diagramy nahrazeny stručným textovým popisem struktur a procesů.


## 2026-06-07 - CZS otázky 23-24

- Zpracovány odborné otázky 23 a 24 do složky `CZS`:
  - [[CZS/23 Konvoluce DFT vahovani casove frekvencni analyza filtry kvantovani]]
  - [[CZS/24 Filtrace ve frekvencni oblasti prevzorkovani banky filtru odhady analyza predikce]]
- Použité podklady: handouty `b2b31czs_pr1`, `pr2_correlation`, `pr3_DFT`, `pr4_spectrum`, `pr6_filters_II`, `pr8_FIR`, `pr9_FiltFrek`, `pr10_OLA_general`, `pr11_multirate` a `pr12_multirate_apps_recurrent`.
- Dodrženo: jen otázky podle okruhů, zdroje přes wikilinky na PDF, Obsidian LaTeX, český text s diakritikou a TikZ schémata pro klíčové postupy.
- U lineární predikce ponechán omezený rozsah podle dodaných podkladů: handout explicitně uvádí ACF jako vstup pro LPC analýzu, ale nerozvádí detailní LPC/AR rovnice.
