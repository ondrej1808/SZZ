# 29 Komunikační kanál, digitální přenosové systémy, telefonie a xDSL

## Tahák

- Komunikační kanál je jednosměrná cesta pro přenos signálu; okruh je obousměrná cesta a spoj je obecný soubor prostředků pro přenos zpráv mezi dvěma místy. [[01.přednáška (B2B32TSI)_print.pdf#page=10|TSI 1 s. 10]]
- Teoretická kapacita kanálu je omezena šířkou pásma a šumem:

$$
C = B \log_2 \left(1 + \frac{S}{N}\right)
$$

- Telefonní kanál má v základním pásmu typicky $300$ až $3400\,\mathrm{Hz}$; digitální telefonní signál PCM podle G.711 má $64\,\mathrm{kbit/s}$. [[02.přednáška (B2B32TSI)_print.pdf#page=6|TSI 2 s. 6]], [[02.přednáška (B2B32TSI)_print.pdf#page=12|TSI 2 s. 12]]
- Digitalizace hlasu: vzorkování, kvantování, binární kódování. Pro telefonii se používá $f_s = 8000\,\mathrm{Hz}$ a 8 bitů na vzorek. [[02.přednáška (B2B32TSI)_print.pdf#page=8|TSI 2 s. 8]], [[02.přednáška (B2B32TSI)_print.pdf#page=9|TSI 2 s. 9]]
- E1 neboli PCM 30/32 má 32 kanálových intervalů po 8 bitech, rámec $125\,\mu\mathrm{s}$ a rychlost $2{,}048\,\mathrm{Mbit/s}$. [[02.přednáška (B2B32TSI)_print.pdf#page=15|TSI 2 s. 15]], [[02.přednáška (B2B32TSI)_print.pdf#page=16|TSI 2 s. 16]]
- Digitální hierarchie: PDH multiplexuje E1 do vyšších toků asynchronně se stuffingem; SDH zavádí synchronní rámce STM-N a přímější přístup k datům; OTH/OTN posouvá transport do transparentní optické vrstvy nad WDM. [[04.přednáška (B2B32TSI)_print.pdf#page=13|TSI 4 s. 13]]
- Digitální spojovací systém pracuje s kanály $64\,\mathrm{kbit/s}$; prostorové pole S mění výstupní multiplex, časové pole T mění kanálový interval. [[10.přednáška (B2B32TSI)_print.pdf#page=7|TSI 10 s. 7]], [[10.přednáška (B2B32TSI)_print.pdf#page=8|TSI 10 s. 8]]
- xDSL využívá existující metalická účastnická vedení; u ADSL/VDSL jsou typické modulace DMT/QAM a oddělení telefonního a datového provozu. [[07.přednáška (B2B32TSI)_print.pdf#page=8|TSI 7 s. 8]], [[07.přednáška (B2B32TSI)_print.pdf#page=36|TSI 7 s. 36]]

## Komunikační kanál a informační propustnost

Informace je zpráva vytvořená zdrojem; signál je tato zpráva převedená do fyzikální formy vhodné pro přenos prostředím. Přenosovým prostředím může být metalické vedení, optické vlákno nebo volný prostor. [[01.přednáška (B2B32TSI)_print.pdf#page=5|TSI 1 s. 5]], [[01.přednáška (B2B32TSI)_print.pdf#page=6|TSI 1 s. 6]]

Základní pojmy:

- **kanál**: soubor prostředků umožňující jednosměrný přenos signálu mezi dvěma místy,
- **telekomunikační okruh**: soubor prostředků umožňující obousměrný přenos signálu,
- **spoj**: obecný soubor prostředků pro telekomunikační přenos zpráv mezi dvěma místy. [[01.přednáška (B2B32TSI)_print.pdf#page=10|TSI 1 s. 10]]

Teoretická informační propustnost kanálu je dána Shannonovým-Hartleyovým vztahem:

$$
C = B \log_2 \left(1 + \frac{S}{N}\right)
$$

kde $C$ je mez kapacity kanálu v $\mathrm{bit/s}$, $B$ je šířka pásma a $S/N$ je poměr výkonu užitečného signálu k šumu. Z praktického hlediska tedy nestačí zvětšovat jen modulační rychlost; kapacita je současně omezena použitelným pásmem a odstupem signálu od šumu. [[01.přednáška (B2B32TSI)_print.pdf#page=5|TSI 1 s. 5]]

Kvalita přenosu hovoru se často hodnotí parametrem MOS nebo R-faktorem E-modelu. E-model shrnuje vliv šumu, lineárního zkreslení, zpoždění, kodeků a očekávání uživatele:

$$
R = R_0 - I_s - I_d - I_e + A
$$

Používá se hlavně tam, kde je třeba odhadnout subjektivně vnímanou kvalitu hovoru z technických parametrů sítě. [[01.přednáška (B2B32TSI)_print.pdf#page=16|TSI 1 s. 16]], [[01.přednáška (B2B32TSI)_print.pdf#page=19|TSI 1 s. 19]]

## Telefonní kanál a digitalizace hlasu

Telefonní kanál je jednosměrná cesta pro přenos hovorového nebo jiného signálu pomocí telefonních systémů. V základním pásmu používá rozsah $300$ až $3400\,\mathrm{Hz}$, tedy šířku přibližně $3100\,\mathrm{Hz}$. Dolní mez je volena s ohledem na energeticky významné složky hlasu, horní mez hlavně s ohledem na srozumitelnost. [[02.přednáška (B2B32TSI)_print.pdf#page=6|TSI 2 s. 6]]

Digitalizace analogového telefonního signálu v PCM má tři kroky:

1. vzorkování: vzniká signál diskrétní v čase,
2. kvantování: vzorky jsou ohodnoceny diskrétními amplitudovými úrovněmi,
3. kódování: kvantované hodnoty se převedou na binární kód. [[02.přednáška (B2B32TSI)_print.pdf#page=8|TSI 2 s. 8]]

Vzorkování se řídí Shannonovým-Kotelnikovovým, respektive Nyquistovým-Shannonovým teorémem:

$$
f_s \ge 2 f_{\max}
$$

Pro telefonní kanál s horní mezí $3400\,\mathrm{Hz}$ byla s rezervou zvolena vzorkovací frekvence $f_s = 8000\,\mathrm{Hz}$. [[02.přednáška (B2B32TSI)_print.pdf#page=9|TSI 2 s. 9]]

Kvantování vnáší kvantizační zkreslení. Aby se zlepšila kvalita pro malé úrovně signálu, používá se nelineární kvantování a komprese/expanze, tedy kompanze. V Evropě je uveden A-zákon, v Americe a Japonsku $\mu$-zákon. [[02.přednáška (B2B32TSI)_print.pdf#page=11|TSI 2 s. 11]], [[02.přednáška (B2B32TSI)_print.pdf#page=12|TSI 2 s. 12]]

Přenosová rychlost jednoho digitalizovaného telefonního kanálu je:

$$
v_p = N f_s = 8 \cdot 8000 = 64\,\mathrm{kbit/s}
$$

To je základní kanál používaný i ve spojovacích systémech a digitálních hierarchiích. [[02.přednáška (B2B32TSI)_print.pdf#page=12|TSI 2 s. 12]], [[10.přednáška (B2B32TSI)_print.pdf#page=7|TSI 10 s. 7]]

## PCM 30/32 a E1

Evropský signál 1. řádu E1, označovaný také PCM 30/32, sdružuje vzorky do rámce podle ITU-T G.704. Jeden rámec obsahuje 32 osmibitových kanálových intervalů, tedy 256 bitů. Doba rámce je rovna periodě vzorkování:

$$
T_F = \frac{1}{f_s} = \frac{1}{8000} = 125\,\mu\mathrm{s}
$$

Přenosová rychlost rámce je:

$$
v_p = \frac{256}{125 \cdot 10^{-6}} = 2{,}048\,\mathrm{Mbit/s}
$$

Z 32 intervalů nese typicky 30 intervalů hovorové kanály, další intervaly slouží pro rámcovou synchronizaci, dohled a signalizaci. Uvedeny jsou FAS pro rámcový souběh, NFAS pro dohled a poplachy, CAS jako signalizace přidružená hovorovým kanálům a CCS jako centralizovaná signalizace. [[02.přednáška (B2B32TSI)_print.pdf#page=15|TSI 2 s. 15]], [[02.přednáška (B2B32TSI)_print.pdf#page=16|TSI 2 s. 16]]

Rámcový souběh je proces, který umožňuje jednoznačně rozeznat začátek rámce a význam jednotlivých bitů v rámci. Při poruchách se sleduje například LOS, LOF/LOM a AIS. [[02.přednáška (B2B32TSI)_print.pdf#page=17|TSI 2 s. 17]], [[02.přednáška (B2B32TSI)_print.pdf#page=19|TSI 2 s. 19]]

## Hierarchie digitálních přenosových systémů

Smyslem digitálních hierarchií je multiplexovat požadované digitální toky do vysokorychlostního signálu, který lze přenést jediným spojem. Výchozí strukturou v Evropě je E1/PCM 30/32. [[04.přednáška (B2B32TSI)_print.pdf#page=13|TSI 4 s. 13]]

### PDH

PDH, plesiochronní digitální hierarchie, vytváří signály vyšších řádů pro přenos většího počtu telefonních kanálů než umožňuje jeden tok E1. Hlavní vlastnosti:

- asynchronní sdružování bez jednotného centrálního taktování,
- vyrovnávání odchylek přenosových rychlostí pomocí stuffingu,
- volné prokládání bit po bitu,
- komplikovanější obnova dílčího signálu z vyšších řádů. [[04.přednáška (B2B32TSI)_print.pdf#page=14|TSI 4 s. 14]], [[04.přednáška (B2B32TSI)_print.pdf#page=15|TSI 4 s. 15]]

Muldex v evropské PDH sdružuje vždy čtyři signály nižšího řádu a pomocné informace. Stuffing může být kladný, záporný nebo oboustranný podle vztahu rychlosti nadřazeného toku k multiplexnímu násobku nižších toků. [[04.přednáška (B2B32TSI)_print.pdf#page=16|TSI 4 s. 16]]

### SDH

SDH vznikla kvůli růstu nároků na kapacitu a neefektivitě dalších stupňů PDH. Základním signálem je STM-N, délka rámce je $125\,\mu\mathrm{s}$ kvůli kompatibilitě s PCM a multiplexní násobek je přesný čtyřnásobek. [[04.přednáška (B2B32TSI)_print.pdf#page=20|TSI 4 s. 20]]

Klíčové vlastnosti SDH:

- řízené prokládání po bytech,
- ukazatele pro přímější přístup k datům ve vyšších řádech,
- synchronní sdružování s centrálním taktováním,
- optické vlákno jako standardní přenosové médium,
- standardizované řízení a ochrana provozu při poruchách. [[04.přednáška (B2B32TSI)_print.pdf#page=21|TSI 4 s. 21]]

### OTH/OTN

OTH je optická transportní hierarchie pro plně optické páteřní sítě OTN. Cílem je transparentní optická vrstva nezávislá na přenášeném klientském signálu, například SDH, IP nebo Ethernetu, a současně vlastní dohled, monitorování výkonnosti a ochranné přepínání na optické úrovni. [[04.přednáška (B2B32TSI)_print.pdf#page=37|TSI 4 s. 37]]

Základním signálem je optický transportní modul OTM. Plnohodnotný OTM-n.m pracuje s více vlnovými délkami; $n$ vyjadřuje počet optických kanálů a $m$ typ přenášených digitálních toků. [[04.přednáška (B2B32TSI)_print.pdf#page=38|TSI 4 s. 38]]

## Telefonní komunikace a digitální spojovací systémy

Telefonní ústředna propojuje účastnické přípojky a vedení podle analýzy volaného čísla, které se předává signalizací. Signalizace se přenáší mezi účastníkem a ústřednou, uvnitř ústředny i mezi ústřednami. Každý spojovací systém obsahuje spojovací pole a řízení. [[10.přednáška (B2B32TSI)_print.pdf#page=2|TSI 10 s. 2]]

Digitální spojovací systémy IV. generace používají programové řízení a spojovací pole s časovým dělením založeným na PCM. Klasické analogové telefonní přístroje lze používat proto, že analogově-digitální převod provádí účastnická sada v účastnické skupině. [[10.přednáška (B2B32TSI)_print.pdf#page=3|TSI 10 s. 3]], [[10.přednáška (B2B32TSI)_print.pdf#page=5|TSI 10 s. 5]]

Účastnická sada plní funkce BORSCHT:

- **B**: napájení účastnického vedení,
- **O**: ochrana proti přepětí,
- **R**: vyzvánění,
- **S**: dohled,
- **C**: kódování do PCM,
- **H**: vidlice pro oddělení směrů přenosu,
- **T**: testování a diagnostika. [[10.přednáška (B2B32TSI)_print.pdf#page=6|TSI 10 s. 6]]

Digitální spojovací pole DSN spojuje kanály s rychlostí $64\,\mathrm{kbit/s}$. Pro jedno obousměrné spojení se sestavují dvě jednosměrné cesty, proto má digitální spojování čtyřdrátový charakter. [[10.přednáška (B2B32TSI)_print.pdf#page=7|TSI 10 s. 7]]

Základní typy digitálního spojovacího pole:

- **S pole**: prostorové pole směruje slova z daného vstupního multiplexu do výstupního multiplexu bez změny časové polohy,
- **T pole**: časové pole mění kanálový interval, tedy časovou polohu hovorového vzorku,
- vícečlánková pole **STS**, **TST** nebo **TSSST** kombinují S a T články kvůli kapacitě a omezení vnitřního blokování. [[10.přednáška (B2B32TSI)_print.pdf#page=8|TSI 10 s. 8]], [[10.přednáška (B2B32TSI)_print.pdf#page=9|TSI 10 s. 9]], [[10.přednáška (B2B32TSI)_print.pdf#page=11|TSI 10 s. 11]], [[10.přednáška (B2B32TSI)_print.pdf#page=14|TSI 10 s. 14]]

## Signalizace a VoIP

V E1 se rozlišuje CAS, kde je signalizace přidružena hovorovým kanálům, a CCS, kde se signalizace přenáší společným nezávislým signalizačním kanálem. [[02.přednáška (B2B32TSI)_print.pdf#page=16|TSI 2 s. 16]]

VoIP přenáší hlas přes datové sítě založené na IP. Hlavní motivací je konvergence původně oddělených hlasových a datových sítí. Hovor se digitalizuje, komprimuje kodekem a přenáší paketově podle protokolového modelu TCP/IP. [[08.přednáška (B2B32TSI)_print.pdf#page=2|TSI 8 s. 2]], [[08.přednáška (B2B32TSI)_print.pdf#page=3|TSI 8 s. 3]], [[08.přednáška (B2B32TSI)_print.pdf#page=10|TSI 8 s. 10]]

Příklady kodeků:

- G.711: $8\,\mathrm{kHz}$, 8 bitů po kompresi, $64\,\mathrm{kbit/s}$, MOS přibližně 4,1,
- G.723.1: 5,3 nebo $6{,}3\,\mathrm{kbit/s}$ podle použitého algoritmu,
- G.729: typicky $8\,\mathrm{kbit/s}$,
- GSM HR/FR/EFR pro mobilní sítě. [[08.přednáška (B2B32TSI)_print.pdf#page=7|TSI 8 s. 7]], [[08.přednáška (B2B32TSI)_print.pdf#page=8|TSI 8 s. 8]]

SIP je signalizační protokol pro sestavení a řízení multimediálních spojení ve VoIP. V podkladech je uveden i vztah k mobilním IP sítím a ke klasickým pevným či mobilním sítím používajícím SS7. [[08.přednáška (B2B32TSI)_print.pdf#page=15|TSI 8 s. 15]]

## Klasické telefonní a xDSL přípojky

Telefonní modem je prostředek pro přenos dat přes stávající telefonní vedení a telefonní síť. Výhodou je využití existující infrastruktury; limitem je šířka pásma telefonního kanálu $3{,}1\,\mathrm{kHz}$, proto se uvádí maximum přibližně $56\,\mathrm{kbit/s}$. Při vytáčeném přístupu se před datovým spojením nejprve sestavuje spojení přes telefonní síť. [[07.přednáška (B2B32TSI)_print.pdf#page=11|TSI 7 s. 11]]

xDSL rozšiřuje využití metalického účastnického vedení pro vysokorychlostní data. V podkladech jsou pro xDSL důležité hlavně vícestavové modulace a modulace s více nosnými:

- QAM kombinuje amplitudové a fázové klíčování; vyšší počet stavů šetří pásmo, ale zvyšuje nároky na odstup signálu od šumu,
- DMT rozděluje dostupné pásmo na mnoho subkanálů a pro každý může nezávisle volit parametry modulace podle stavu vedení. [[07.přednáška (B2B32TSI)_print.pdf#page=6|TSI 7 s. 6]], [[07.přednáška (B2B32TSI)_print.pdf#page=8|TSI 7 s. 8]], [[07.přednáška (B2B32TSI)_print.pdf#page=9|TSI 7 s. 9]]

U ADSL je přístup obvykle řešen přes účastnický modem ATU-R, koncentrátor DSLAM a agregaci směrem k poskytovateli. Starší architektura používala ATM a PPPoA, modernější Ethernet a PPPoE. V agregačním bodě se koncentrují toky z lokality; agregační poměr vyjadřuje, kolikrát je agregovaný tok nižší než součet smluvních rychlostí účastníků. [[07.přednáška (B2B32TSI)_print.pdf#page=30|TSI 7 s. 30]], [[07.přednáška (B2B32TSI)_print.pdf#page=31|TSI 7 s. 31]], [[07.přednáška (B2B32TSI)_print.pdf#page=32|TSI 7 s. 32]]

VDSL je určeno hlavně pro poslední úsek účastnického vedení v délce asi $0{,}3$ až $1{,}5\,\mathrm{km}$. Zachovává koexistenci telefonního a datového provozu a podobný princip DMT jako ADSL, ale používá širší frekvenční pásmo. Podklady uvádějí až $52\,\mathrm{Mbit/s}$ downstream, u VDSL2 až $100\,\mathrm{Mbit/s}$, upstream až $6{,}4\,\mathrm{Mbit/s}$ a symetricky až $34\,\mathrm{Mbit/s}$ v obou směrech. [[07.přednáška (B2B32TSI)_print.pdf#page=36|TSI 7 s. 36]], [[07.přednáška (B2B32TSI)_print.pdf#page=39|TSI 7 s. 39]]

## Vazby na další otázky

- Mobilní kodeky, GSM, GPRS, EDGE a UMTS pokračují v [[30 Bunkove mobilni site GSM GPRS EDGE UMTS]].
- Teorie vzorkování a spektrální popis navazují na [[19 Signaly casova spektralni reprezentace vzorkovani nahodne procesy]].
- Konvoluce, LTI systémy a modulace jsou související s [[20 Soustavy LTI konvoluce stabilita pasmove signaly modulace]].
