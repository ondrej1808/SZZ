# 30 Buňkové mobilní sítě, GSM, GPRS, EDGE a UMTS

## Tahák

- GSM je digitální buňkový mobilní systém 2. generace; území je rozděleno na buňky obsluhované základnovými stanicemi BTS. [[12.přednáška (B2B32TSI)_print.pdf#page=5|TSI 12 s. 5]]
- Mobilní stanice MS se připojuje k BTS s nejsilnějším nebo nejkvalitnějším signálem; při pohybu mezi buňkami se spojení automaticky předá pomocí handoveru. [[12.přednáška (B2B32TSI)_print.pdf#page=5|TSI 12 s. 5]], [[12.přednáška (B2B32TSI)_print.pdf#page=11|TSI 12 s. 11]]
- V jedné buňce se používají metody vícenásobného přístupu FDMA, TDMA a CDMA; GSM kombinuje frekvenční a časové dělení. [[12.přednáška (B2B32TSI)_print.pdf#page=9|TSI 12 s. 9]]
- GSM síť má subsystémy BSS, NSS a OSS; hlavní prvky jsou MS, BTS, BSC, MSC, HLR, VLR, AuC a EIR. [[12.přednáška (B2B32TSI)_print.pdf#page=12|TSI 12 s. 12]], [[12.přednáška (B2B32TSI)_print.pdf#page=13|TSI 12 s. 13]], [[12.přednáška (B2B32TSI)_print.pdf#page=14|TSI 12 s. 14]]
- Pro data v GSM: CSD kolem $9{,}6\,\mathrm{kbit/s}$, HSCSD až $57{,}6\,\mathrm{kbit/s}$, GPRS paketově až $85{,}6\,\mathrm{kbit/s}$ downlink a EDGE s 8-PSK až kolem $384\,\mathrm{kbit/s}$. [[12.přednáška (B2B32TSI)_print.pdf#page=19|TSI 12 s. 19]], [[12.přednáška (B2B32TSI)_print.pdf#page=24|TSI 12 s. 24]]
- UMTS je síť 3. generace zaměřená hlavně na multimédia a vysokorychlostní data; používá W-CDMA/WB-CDMA, UTRAN, Node-B a RNC. [[12.přednáška (B2B32TSI)_print.pdf#page=26|TSI 12 s. 26]], [[12.přednáška (B2B32TSI)_print.pdf#page=28|TSI 12 s. 28]]

## Princip buňkové sítě

Buňková mobilní síť rozděluje obsluhované území na elementární oblasti, tedy buňky. Každá buňka je obsluhována základnovou stanicí BTS a mobilní stanice MS komunikuje s tou BTS, která v daném místě poskytuje nejsilnější nebo nejkvalitnější signál. Při pohybu účastníka se probíhající spojení automaticky předává na vhodnější sousední BTS. [[12.přednáška (B2B32TSI)_print.pdf#page=5|TSI 12 s. 5]]

Smysl buňkového principu:

- efektivnější využití omezeného rádiového spektra,
- opakované použití frekvencí v dostatečně vzdálených buňkách,
- možnost pokrýt různě hustá a různě zatížená území různou velikostí buněk,
- podpora mobility pomocí lokalizace stanice a handoveru. [[12.přednáška (B2B32TSI)_print.pdf#page=6|TSI 12 s. 6]], [[12.přednáška (B2B32TSI)_print.pdf#page=11|TSI 12 s. 11]]

Podle velikosti a použití se uvádějí:

- **pikobuňky** pro kancelářské a bytové prostředí, dosah nejvýše stovky metrů,
- **mikrobuňky** pro městské aglomerace, dosah jednotky kilometrů,
- **makrobuňky** pro velké a řidší oblasti, průměr až desítky kilometrů,
- **satelitní buňky** pro oblasti dosažitelné z družice. [[12.přednáška (B2B32TSI)_print.pdf#page=6|TSI 12 s. 6]]

Sektorizace rozděluje pokrytí základnové stanice na sektory. Prakticky tím pomáhá řídit rušení a kapacitu, protože antény nepokrývají celou buňku všesměrově, ale po směrech. [[12.přednáška (B2B32TSI)_print.pdf#page=8|TSI 12 s. 8]]

## Generace mobilních systémů

Podklady rozlišují tyto generace:

- **1G**: analogové národní systémy, například NMT, AMPS, TACS; hlavně hovor,
- **2G**: digitální systémy, zejména GSM, DAMPS/IS136, IS95/cdmaOne; hovor a data,
- **2,5G**: GPRS a EGPRS/EDGE; rozšíření datových služeb nad GSM,
- **3G**: UMTS a cdma2000; multimédia a vyšší datové rychlosti. [[12.přednáška (B2B32TSI)_print.pdf#page=3|TSI 12 s. 3]]

GSM představuje 2. generaci digitálních buňkových radiotelefonních systémů. UMTS je 3. generace pracující v pásmu kolem $2\,\mathrm{GHz}$ a zaměřená na sjednocení bezdrátových přístupových technologií do infrastruktury s multimediálními službami a garantovanou kvalitou. [[12.přednáška (B2B32TSI)_print.pdf#page=5|TSI 12 s. 5]]

## Metody vícenásobného přístupu a modulace

V jedné buňce musí být možné současně obsloužit více mobilních stanic. K tomu slouží metody vícenásobného přístupu:

- **FDMA**: frekvenční pásmo se rozdělí na subpásma, kterým se přiřadí kanály,
- **TDMA**: v daném frekvenčním pásmu se vytvoří časový rámec a kanály se přidělují jako časové intervaly,
- **CDMA**: uživatelé sdílejí stejné frekvenční pásmo i čas a rozlišují se různými kódovými předpisy. [[12.přednáška (B2B32TSI)_print.pdf#page=9|TSI 12 s. 9]]

U GSM 1800 je v podkladech uvedeno 374 frekvenčních kanálů a 8 kanálových intervalů na kanál, tedy kombinace FDMA a TDMA. [[12.přednáška (B2B32TSI)_print.pdf#page=9|TSI 12 s. 9]]

Pro digitální modulace obecně platí, že vícestavové modulace lépe využívají pásmo, ale jsou citlivější na rušení. V podkladech k modemům je uvedeno například PSK, QAM, OFDM/DMT; pro EDGE je v mobilní přednášce zmíněna modulace 8-PSK. [[07.přednáška (B2B32TSI)_print.pdf#page=3|TSI 7 s. 3]], [[07.přednáška (B2B32TSI)_print.pdf#page=7|TSI 7 s. 7]], [[12.přednáška (B2B32TSI)_print.pdf#page=19|TSI 12 s. 19]]

## Handover a lokalizace

Mobilní stanice musí síti poskytovat informaci o své poloze, aby bylo možné směrovat příchozí spojení do oblasti, kde se stanice nachází. Při pohybu přes hranice buněk se aktivní spojení přepojí na jinou BTS. [[12.přednáška (B2B32TSI)_print.pdf#page=6|TSI 12 s. 6]], [[12.přednáška (B2B32TSI)_print.pdf#page=12|TSI 12 s. 12]]

Druhy handoveru:

- **mezibuňkový handover**: přeladění při přechodu přes hranice dvou buněk,
- **vnitrobuňkový handover**: přeladění v rámci jedné buňky na kanál s lepší kvalitou spojení. [[12.přednáška (B2B32TSI)_print.pdf#page=11|TSI 12 s. 11]]

Protože sousední buňky používají odlišné frekvence, musí se při přechodu mobilní stanice přeladit. Cílem je udržet spojení bez zásahu uživatele. [[12.přednáška (B2B32TSI)_print.pdf#page=11|TSI 12 s. 11]]

## Architektura GSM

GSM síť se dělí na tři hlavní subsystémy:

- **BSS**: Base Station Subsystem,
- **NSS**: Network Switching Subsystem,
- **OSS**: Operation Subsystem. [[12.přednáška (B2B32TSI)_print.pdf#page=12|TSI 12 s. 12]], [[12.přednáška (B2B32TSI)_print.pdf#page=14|TSI 12 s. 14]]

### BSS

BSS tvoří rádiovou část sítě. Mobilní stanice MS komunikují se základnovými stanicemi BTS. Několika BTS je přiřazena řídicí jednotka BSC, která přiděluje a uvolňuje rádiové kanály a zajišťuje správnou funkci handoveru. MS obvykle zachytí více BTS a pro spojení se vybere optimální základnová stanice. [[12.přednáška (B2B32TSI)_print.pdf#page=12|TSI 12 s. 12]]

### NSS

NSS obsahuje spojovací a databázovou část mobilní sítě. Základním prvkem je ústředna MSC, tedy Mobile Switching Centre. MSC je telefonní ústředna doplněná o funkce související s mobilitou účastníků. [[12.přednáška (B2B32TSI)_print.pdf#page=12|TSI 12 s. 12]]

Identifikační databáze:

- **HLR**: domovský registr, uchovává informace o účastnících v dané oblasti; každý účastník je uložen jen v jednom HLR,
- **AuC**: centrum autentičnosti, ověřuje identitu účastníka,
- **VLR**: návštěvnický registr, dočasně uchovává údaje o účastnících v oblasti příslušné MSC,
- **EIR**: registr mobilních zařízení, obsahuje informace o mobilních stanicích, například autorizované nebo zcizené stanice. [[12.přednáška (B2B32TSI)_print.pdf#page=13|TSI 12 s. 13]]

Při přístupu do sítě vyšle mobilní stanice identifikaci IMSI přes BTS a BSC do MSC. AuC vyšle náhodné číslo, SIM karta podle individuálních údajů vytvoří odezvu a VLR ji porovná s databázovými údaji. Při shodě je stanici povolen přístup. [[12.přednáška (B2B32TSI)_print.pdf#page=13|TSI 12 s. 13]]

### OSS

OSS zajišťuje provoz a správu BSS a NSS. Obsahuje například administrativní centrum ADC, centrum řízení sítě NMC a provozní a servisní centrum OMC. GSM zároveň navazuje na další sítě, například PSTN, ISDN a družicové telekomunikace. [[12.přednáška (B2B32TSI)_print.pdf#page=14|TSI 12 s. 14]]

## GSM standardy a rádiové prostředky

Základní GSM bylo realizováno v pásmu $900\,\mathrm{MHz}$; s růstem provozu vznikly další varianty:

- **GSM 900**: pásmo $900\,\mathrm{MHz}$, až $2 \times 124$ kanálů, šířka pásma $2 \times 25\,\mathrm{MHz}$,
- **GSM 1800**: pásmo $1800\,\mathrm{MHz}$, až $2 \times 374$ kanálů, šířka pásma $2 \times 75\,\mathrm{MHz}$,
- **GSM 1900**: pásmo $1900\,\mathrm{MHz}$, až $2 \times 298$ kanálů, šířka pásma $2 \times 75\,\mathrm{MHz}$. [[12.přednáška (B2B32TSI)_print.pdf#page=18|TSI 12 s. 18]]

GSM 1800 a GSM 1900 se označují také jako DCS. [[12.přednáška (B2B32TSI)_print.pdf#page=18|TSI 12 s. 18]]

## Přenos dat a signalizace v 2G a 2,5G

Základní rychlost mezi GSM mobilní stanicí a sítí je $13\,\mathrm{kbit/s}$ obousměrně; pro data se běžně používalo $9{,}6\,\mathrm{kbit/s}$, později $14{,}4\,\mathrm{kbit/s}$ díky snížení redundantní ochranné informace. Tento okruhový přenos se označuje CSD. [[12.přednáška (B2B32TSI)_print.pdf#page=19|TSI 12 s. 19]]

**HSCSD** sdružuje více okruhových kanálů a umožňuje rychlosti až $57{,}6\,\mathrm{kbit/s}$. Nevýhodou okruhového přístupu je blokování přenosových prostředků po dobu spojení. [[12.přednáška (B2B32TSI)_print.pdf#page=19|TSI 12 s. 19]], [[12.přednáška (B2B32TSI)_print.pdf#page=24|TSI 12 s. 24]]

**GPRS** zavádí paketový přenos. Přenosové prostředky se stanici přidělují jen tehdy, když odesílá nebo přijímá data, takže nejsou trvale blokované jako u HSCSD. Pro rádiovou část slouží SGSN, pro přístup do paketových sítí a Internetu GGSN, který funguje jako směrovač. Přístup do definovaných sítí se váže na APN. [[12.přednáška (B2B32TSI)_print.pdf#page=24|TSI 12 s. 24]]

GPRS může zvýšit rychlost sdružením více kanálů pro jednoho účastníka a volbou kódovacího schématu. Uváděné konfigurace jsou například 3+1, 4+1 nebo 4+2, tedy asymetrický přenos. Teoreticky je v podkladech uvedeno až $85{,}6\,\mathrm{kbit/s}$ downstream a $42{,}8\,\mathrm{kbit/s}$ upstream; zpoždění paketů může být od stovek milisekund až po několik sekund podle délky paketu a zatížení. [[12.přednáška (B2B32TSI)_print.pdf#page=24|TSI 12 s. 24]]

**EDGE/EGPRS** zvyšuje rychlost použitím modulace 8-PSK místo konvenčnějšího přístupu GSM. Podklady uvádějí celkové přenosové rychlosti datových přenosů až kolem $384\,\mathrm{kbit/s}$. [[12.přednáška (B2B32TSI)_print.pdf#page=19|TSI 12 s. 19]]

Signalizace v GSM je nezbytná pro registraci polohy, autentizaci, přidělování kanálů, sestavení spojení a handover. V popisu přístupu do sítě je signalizační výměna uvedena jako úvodní krok aktivního volání. [[12.přednáška (B2B32TSI)_print.pdf#page=13|TSI 12 s. 13]]

## UMTS a 3G

UMTS je síť 3. generace začleněná do existujících sítí 2. generace. Podklady uvádějí, že zpočátku se počítalo s úplným pokrytím GSM a menšími oblastmi UMTS, takže telefonní služba měla být nadále realizována přes GSM, zatímco UMTS se soustředí hlavně na vysokorychlostní datový přenos. [[12.přednáška (B2B32TSI)_print.pdf#page=26|TSI 12 s. 26]]

Pro 3G byla zvolena technologie CDMA, konkrétně varianta WB-CDMA/W-CDMA. Všichni uživatelé používají přidělené frekvenční pásmo po celou dobu a odlišují se jedinečným binárním kódem. [[12.přednáška (B2B32TSI)_print.pdf#page=26|TSI 12 s. 26]]

Spektrum UMTS v podkladech:

- párové pásmo $1920$ až $1980\,\mathrm{MHz}$ a $2110$ až $2170\,\mathrm{MHz}$,
- nepárové pásmo $1910$ až $1920\,\mathrm{MHz}$ a $2010$ až $2025\,\mathrm{MHz}$,
- FDD pro párové pásmo,
- TDD pro nepárové pásmo. [[12.přednáška (B2B32TSI)_print.pdf#page=26|TSI 12 s. 26]]

Architektura UMTS:

- **CN**: Core Network, páteřní síť pro spojování hovorů, směrování paketů, databázové a řídicí funkce,
- **UTRAN**: rádiová přístupová síť, která propojuje uživatelské terminály UE s UMTS sítí,
- **Node-B**: základnová stanice UMTS, obdoba BTS,
- **RNC**: Radio Network Controller, řídicí jednotka rádiové sítě, obdoba BSC,
- **RNS**: Radio Network Subsystem, subsystém rádiové sítě. [[12.přednáška (B2B32TSI)_print.pdf#page=28|TSI 12 s. 28]]

Standardizace 3G systémů je v podkladech rozdělena na 3GPP pro UMTS a rozšíření GSM/GPRS/EDGE, 3GPP2 pro cdma2000 a ITU, kde jsou 3G systémy označovány jako IMT-2000. [[12.přednáška (B2B32TSI)_print.pdf#page=30|TSI 12 s. 30]]

## Vazby na další otázky

- Přenosová kapacita, PCM, spojovací systémy, VoIP a xDSL jsou v [[29 Komunikacni kanal digitalni prenosy telefonie xDSL]].
- Modulace, QAM, OFDM/DMT a pásmové signály souvisejí s [[20 Soustavy LTI konvoluce stabilita pasmove signaly modulace]].
