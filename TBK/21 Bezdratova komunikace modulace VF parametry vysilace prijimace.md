# 21 Bezdrátová komunikace, modulace, VF parametry, vysílače a přijímače

> Hlavní podklady: [[TBK 1 úvod 25.ppt [režim kompatibility].pdf]], [[TBK 2 teoretické základy 25.pdf]], [[TBK 3 parametry 25.pdf]], [[TBK 4 komponenty 25.pdf]], [[TBK 5 signály 25 .pdf]], [[TBK 6 systémy 20.pdf]]. Znění okruhu: [[SZZ - Odborné okruhy|odborný okruh 21]].

## Základní principy bezdrátové komunikace

Bezdrátová komunikace přenáší informaci pomocí elektromagnetických vln šířících se volným prostředím. Na rozdíl od metalického vedení se energie ve volném prostoru rozprostírá, takže s rostoucí vzdáleností prudce klesá výkonová hustota. Rádiový systém proto potřebuje antény, vhodné frekvenční pásmo, modulaci, výkonový zesilovač, přijímač s dostatečnou citlivostí a výkonovou bilanci spoje.

V rádiovém zařízení se běžně střídají dva popisy stejného elektromagnetického děje:

- **vlna na vedení**: šíří se podél metalické nebo jiné vedené struktury, typicky koaxiál, mikropásek, vlnovod,
- **vlna ve volném prostoru**: šíří se mezi anténami a nese užitečný signál přes rádiový kanál.

Volba vyšší nosné frekvence umožňuje menší antény a větší dostupná pásma, ale obvykle zvyšuje nároky na přesnost, ztráty, šum, linearitu a směrování.

**Zdroj:** [[TBK 1 úvod 25.ppt [režim kompatibility].pdf#page=2|TBK 1 s. 2]], [[TBK 1 úvod 25.ppt [režim kompatibility].pdf#page=4|TBK 1 s. 4]], [[TBK 1 úvod 25.ppt [režim kompatibility].pdf#page=7|TBK 1 s. 7]], [[TBK 6 systémy 20.pdf#page=3|TBK 6 s. 3]].

## Typy rádiových spojů

Podle směru přenosu se rozlišuje:

- **simplex**: přenos jen jedním směrem,
- **poloduplex**: obousměrný přenos, ale ne současně; typicky TDD, tedy časové přepínání vysílání a příjmu,
- **plný duplex**: současný přenos oběma směry; typicky FDD, tedy oddělené vysílací a přijímací frekvence.

Podle geometrie služby se používá:

- **bod-bod**: pevná rádiová trasa mezi dvěma směrovými anténami,
- **bod-mnohobod**: základnová stanice obsluhuje více koncových stanic,
- **bod-plocha**: vysílání do oblasti, například rozhlas,
- **mobilní spoj**: alespoň jedna stanice se pohybuje, takže je významné vícecestné šíření, fading a Dopplerův posuv.

U TDD se TX a RX obvykle slučují do jedné antény přepínačem. U FDD se používají diplexery, tedy slučovací filtry, protože vysílací a přijímací frekvence jsou oddělené.

**Zdroj:** [[TBK 6 systémy 20.pdf#page=3|TBK 6 s. 3]], [[TBK 6 systémy 20.pdf#page=4|TBK 6 s. 4]], [[TBK 6 systémy 20.pdf#page=5|TBK 6 s. 5]], [[TBK 6 systémy 20.pdf#page=51|TBK 6 s. 51]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=14|Antény a šíření s. 14]].

## Základy digitálních modulací

Digitální komunikace přenáší informaci jako posloupnost symbolů z konečné množiny stavů. Symbol moduluje nosnou vlnu změnou amplitudy, fáze, frekvence nebo jejich kombinace.

Základní rodiny:

- **BPSK**: dva fázové stavy, jeden bit na symbol,
- **QPSK / 4-QAM**: čtyři stavy v IQ rovině, dva bity na symbol,
- **M-PSK**: více fázových stavů při přibližně konstantní obálce,
- **M-QAM**: změna amplitudy i fáze, vysoká spektrální účinnost, ale vyšší nároky na SNR a linearitu,
- **OFDM**: datový tok se rozdělí do mnoha ortogonálních úzkopásmových subkanálů, každý se moduluje např. QAM.

IQ modulace vytváří signál jako součet složek v kvadratuře:

$$
s(t)=I(t)\cos\omega_0t-Q(t)\sin\omega_0t.
$$

Hodnoty $I$ a $Q$ určují bod konstelačního diagramu. Vyšší řády QAM přenášejí více bitů na symbol, ale body v konstelačním diagramu jsou blíže u sebe, takže roste požadovaný odstup signálu od šumu a citlivost na nelinearitu.

Pro porovnání modulací se používá parametr

$$
\frac{E_b}{N_0}=T_bB\cdot\mathrm{SNR},
$$

kde $E_b$ je energie na bit, $N_0$ spektrální hustota šumu, $T_b$ doba bitu a $B$ šířka pásma. Požadovaná hodnota $E_b/N_0$ závisí na modulaci, kódování a požadovaném BER.

```tikz
\begin{document}
  \begin{tikzpicture}[scale=0.85]
    \draw[->] (-2.5,0) -- (2.7,0) node[right] {$I$};
    \draw[->] (0,-2.5) -- (0,2.7) node[above] {$Q$};
    \foreach \x in {-1.5,-0.5,0.5,1.5}
      \foreach \y in {-1.5,-0.5,0.5,1.5}
        \fill (\x,\y) circle (1.8pt);
    \draw[dashed] (-2,-2) rectangle (2,2);
    \node[anchor=west] at (2.2,1.7) {16-QAM};
    \node[anchor=west] at (2.2,1.25) {4 bits/symbol};
  \end{tikzpicture}
\end{document}
```

**Zdroj:** [[TBK 5 signály 25 .pdf#page=4|TBK 5 s. 4]], [[TBK 5 signály 25 .pdf#page=9|TBK 5 s. 9]], [[TBK 5 signály 25 .pdf#page=14|TBK 5 s. 14]], [[TBK 5 signály 25 .pdf#page=20|TBK 5 s. 20]], [[TBK 5 signály 25 .pdf#page=24|TBK 5 s. 24]], [[TBK 5 signály 25 .pdf#page=26|TBK 5 s. 26]].

## Napěťové vlny

Ve VF a mikrovlnné technice často selhává nízkofrekvenční představa soustředěných napětí a proudů. Rozměry obvodů jsou srovnatelné s vlnovou délkou a je nutné popisovat šíření po vedení. Místo jednoho napětí se zavádí dopředná a odražená napěťová vlna:

$$
V(z)=V^+(z)+V^-(z),
$$

$$
I(z)=\frac{V^+(z)-V^-(z)}{Z_0}.
$$

Charakteristická impedance vedení je

$$
\hat Z_0=\sqrt{\frac{R+j\omega L}{G+j\omega C}},
$$

pro bezeztrátové vedení

$$
Z_0=\sqrt{\frac{L}{C}}.
$$

Koeficient odrazu je poměr odražené a dopadající napěťové vlny:

$$
\Gamma=\frac{V^-}{V^+}
=\frac{Z_Z-Z_0}{Z_Z+Z_0},
$$

kde $Z_Z$ je impedance zátěže. Při $Z_Z=Z_0$ je $\Gamma=0$, vedení je přizpůsobené a nevzniká stojaté vlnění.

Útlum odrazů, tedy Return Loss, se zapisuje

$$
RL=-20\log|\Gamma|.
$$

Poměr stojatých vln je

$$
PSV=\frac{1+|\Gamma|}{1-|\Gamma|}.
$$

**Zdroj:** [[TBK 2 teoretické základy 25.pdf#page=12|TBK 2 s. 12]], [[TBK 2 teoretické základy 25.pdf#page=15|TBK 2 s. 15]], [[TBK 2 teoretické základy 25.pdf#page=17|TBK 2 s. 17]], [[TBK 2 teoretické základy 25.pdf#page=40|TBK 2 s. 40]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=5|Antény a šíření s. 5]].

## Smithův diagram

Smithův diagram je grafické zobrazení komplexního koeficientu odrazu $\Gamma$ a zároveň normalizované impedance

$$
z=\frac{Z}{Z_0}.
$$

Umožňuje číst impedanci, admitanci, koeficient odrazu, PSV a transformaci impedance podél bezeztrátového vedení. V praxi se používá hlavně pro návrh impedančního přizpůsobení, například pomocí sériové nebo paralelní reaktance, pahýlu nebo transformačního vedení.

```tikz
\begin{document}
  \begin{tikzpicture}[scale=2.35]
    % Unit circle in the reflection-coefficient plane.
    \draw[thick] (0,0) circle (1);
    \draw[->] (-1.08,0) -- (1.16,0) node[right] {$\Re\{\Gamma\}$};
    \draw[->] (0,-1.08) -- (0,1.14) node[above] {$\Im\{\Gamma\}$};

    % Constant normalized resistance circles, z = r + jx.
    \foreach \r in {0.2,0.5,1,2,5} {
      \pgfmathsetmacro{\cx}{\r/(1+\r)}
      \pgfmathsetmacro{\rad}{1/(1+\r)}
      \draw[thin] (\cx,0) circle (\rad);
    }

    % Constant normalized reactance arcs.
    \begin{scope}
      \clip (0,0) circle (1);
      \foreach \x in {0.2,0.5,1,2,5} {
        \pgfmathsetmacro{\cy}{1/\x}
        \pgfmathsetmacro{\rad}{1/\x}
        \draw[thin] (1,\cy) circle (\rad);
        \draw[thin] (1,-\cy) circle (\rad);
      }
    \end{scope}

    % Labels for selected resistance circles.
    \node[below] at (-1,0) {$0$};
    \node[below] at (0,0) {$1$};
    \node[below] at (0.5,0) {$2$};
    \node[below] at (0.82,0) {$5$};
    \node[below right] at (1,0) {$\infty$};

    % Labels for selected reactance arcs.
    \node[right] at (0.64,0.76) {$+j1$};
    \node[right] at (0.64,-0.76) {$-j1$};
    \node[right] at (0.28,0.96) {$+j2$};
    \node[right] at (0.28,-0.96) {$-j2$};

    % Example impedance point and its reflection coefficient.
    \fill (0.38,0.42) circle (0.018) node[above right] {$z=1+j1$};
    \draw[->,thick] (0,0) -- (0.38,0.42) node[midway,above left] {$\Gamma$};
    \fill (0,0) circle (0.014) node[above left] {$Z_0$};
  \end{tikzpicture}
\end{document}
```

**Zdroj:** [[TBK 2 teoretické základy 25.pdf#page=31|TBK 2 s. 31]], [[TBK 2 teoretické základy 25.pdf#page=38|TBK 2 s. 38]], [[TBK 2 teoretické základy 25.pdf#page=57|TBK 2 s. 57]].

## Používané VF lineární parametry

Ve VF a mikrovlnné oblasti se obvody popisují hlavně pomocí S-parametrů, protože měření napětí a proudů na portech je obtížné a přirozenější je měřit dopadající a odražené vlny.

Pro dvojbran:

- $s_{11}$: vstupní koeficient odrazu při výstupu zakončeném $Z_0$,
- $s_{21}$: dopředný přenos, tedy zisk nebo útlum z portu 1 na port 2,
- $s_{12}$: zpětný přenos,
- $s_{22}$: výstupní koeficient odrazu při vstupu zakončeném $Z_0$.

Důležité lineární parametry jsou zisk $G$, vložný útlum $IL$, odrazový útlum $RL$, izolace, šířka pásma a skupinové zpoždění. Většina VF komponent musí mít vstupy a výstupy blízké standardní impedanci, typicky $50\,\Omega$.

**Zdroj:** [[TBK 3 parametry 25.pdf#page=6|TBK 3 s. 6]], [[TBK 3 parametry 25.pdf#page=8|TBK 3 s. 8]], [[TBK 3 parametry 25.pdf#page=15|TBK 3 s. 15]], [[TBK 4 komponenty 25.pdf#page=5|TBK 4 s. 5]].

## Používané VF šumové parametry

Šum omezuje citlivost přijímače a přímo ovlivňuje BER. Tepelný šum v šířce pásma $B$ je

$$
N=kTB.
$$

Pro referenční teplotu $T_0=290\,\mathrm K$ se šumové číslo dvojbranu definuje přes zhoršení odstupu signál-šum:

$$
F=\frac{SNR_\mathrm{in}}{SNR_\mathrm{out}}.
$$

V decibelech:

$$
F_\mathrm{dB}=10\log F.
$$

Ekvivalentní šumová teplota je

$$
T_e=(F-1)T_0.
$$

Pro kaskádu platí Friisův vztah

$$
F_c=F_1+\frac{F_2-1}{G_1}
+\frac{F_3-1}{G_1G_2}+\cdots.
$$

Z toho plyne praktické pravidlo: první prvek přijímače je kritický. Proto se na vstup RX dává nízkošumový zesilovač LNA a vstupní ztráty před LNA jsou velmi drahé, protože přímo zhoršují celkové šumové číslo.

**Zdroj:** [[TBK 3 parametry 25.pdf#page=18|TBK 3 s. 18]], [[TBK 3 parametry 25.pdf#page=20|TBK 3 s. 20]], [[TBK 3 parametry 25.pdf#page=21|TBK 3 s. 21]], [[TBK 3 parametry 25.pdf#page=22|TBK 3 s. 22]], [[TBK 3 parametry 25.pdf#page=23|TBK 3 s. 23]].

## Používané VF nelineární parametry

Nelinearity vznikají hlavně v aktivních prvcích, směšovačích, násobičích, přepínačích a výkonových zesilovačích. Způsobují kompresi, harmonické a intermodulační produkty.

Polynomiální model:

$$
v_2=k_1v_1+k_2v_1^2+k_3v_1^3+\cdots.
$$

Důležité parametry:

- **$P_{-1\mathrm{dB}}$**: výstupní výkon, kde se reálná charakteristika odchýlí o 1 dB od extrapolované lineární části,
- **IP2**: průsečík extrapolovaných složek 1. a 2. řádu,
- **IP3**: průsečík extrapolovaných složek 1. a 3. řádu,
- **IM2, IM3**: intermodulační produkty, z nichž IM3 typu $2a-b$ a $2b-a$ často padají do sousedního nebo stejného kanálu,
- **ACPR/ACLR**: výkon unikající do sousedních kanálů vlivem rozšiřování spektra.

Pro IM3 se v dBm často používá

$$
P_{IM3}=3P_\mathrm{out}-2IP3,
\qquad
OIM3=2IP3-2P_\mathrm{out}.
$$

Snížení výstupního výkonu o 1 dB sníží IM3 přibližně o 3 dB a zlepší odstup IM3 o 2 dB.

**Zdroj:** [[TBK 3 parametry 25.pdf#page=29|TBK 3 s. 29]], [[TBK 3 parametry 25.pdf#page=32|TBK 3 s. 32]], [[TBK 3 parametry 25.pdf#page=35|TBK 3 s. 35]], [[TBK 3 parametry 25.pdf#page=39|TBK 3 s. 39]], [[TBK 6 systémy 20.pdf#page=18|TBK 6 s. 18]].

## Komponenty VF a mikrovlnných vysílačů a přijímačů

VF a mikrovlnné systémy se skládají z impedančně přizpůsobených bloků propojených přenosovými vedeními. Základní komponenty:

- **přenosová vedení a vlnovody**: koaxiál, mikropásek, vlnovod,
- **konektory, atenuátory, bezodrazové koncovky**,
- **filtry**: dolní, horní, pásmové propusti a zádrže, SAW/BAW filtry,
- **děliče, slučovače, směrové vazby**,
- **zesilovače**: LNA pro přijímač, PA pro vysílač, VGA pro řízení zisku,
- **směšovače**: up-konverze v TX, down-konverze v RX,
- **oscilátory, VCO, PLL, DDS**,
- **duplexery**: přepínače pro TDD, diplexery pro FDD.

U všech bloků se hlídá zisk nebo útlum, přizpůsobení, šum, linearita, výkonová zatížitelnost, izolace a parazitní produkty.

**Zdroj:** [[TBK 4 komponenty 25.pdf#page=2|TBK 4 s. 2]], [[TBK 4 komponenty 25.pdf#page=23|TBK 4 s. 23]], [[TBK 4 komponenty 25.pdf#page=30|TBK 4 s. 30]], [[TBK 4 komponenty 25.pdf#page=34|TBK 4 s. 34]], [[TBK 4 komponenty 25.pdf#page=40|TBK 4 s. 40]].

## Struktury VF a mikrovlnných vysílačů

Vysílač vytváří modulovanou nosnou, filtruje nežádoucí produkty, zesiluje signál na požadovaný výkon a dodává ho do antény.

Základní struktury:

- **přímá IQ modulace na RF**: jednoduchá, malý počet směšování, ale citlivá na únik LO, DC offset a kvadraturní chyby,
- **modulace na mezifrekvenci a up-konverze**: lepší filtrace a potlačení parazitních produktů, ale složitější struktura,
- **digitální IF / SDR přístup**: větší část modulace probíhá v DSP a DAC,
- **PLL nebo DDS generace nosné**: stabilní a laditelný lokální oscilátor.

Výkonový zesilovač PA určuje výstupní výkon, účinnost a linearitu. U QAM a OFDM je nutná vysoká linearita kvůli proměnné obálce a vysokému PAPR. Řešení jsou back-off, lineárnější PA, predistorze nebo jiné linearizační techniky.

**Zdroj:** [[TBK 6 systémy 20.pdf#page=9|TBK 6 s. 9]], [[TBK 6 systémy 20.pdf#page=13|TBK 6 s. 13]], [[TBK 6 systémy 20.pdf#page=15|TBK 6 s. 15]], [[TBK 6 systémy 20.pdf#page=18|TBK 6 s. 18]], [[TBK 6 systémy 20.pdf#page=23|TBK 6 s. 23]].

## Struktury VF a mikrovlnných přijímačů

Přijímač musí z antény zpracovat velmi slabý signál, potlačit rušivé kanály, zachovat SNR a převést signál na mezifrekvenci nebo do základního pásma.

Základní struktury:

- **přímo laděný přijímač**: RF filtr a zesílení na přijímané frekvenci, jednodušší, ale horší selektivita a rozsah ladění,
- **superhet**: směšování na mezifrekvenci, pevný úzký IF filtr, vysoká selektivita; nutno řešit zrcadlové frekvence,
- **vícenásobný superhet**: více mezifrekvencí pro lepší kompromis mezi potlačením zrcadla a selektivitou,
- **přímá IQ demodulace / zero-IF**: převod rovnou do základního pásma, vhodné pro integrované digitální přijímače, citlivé na DC offset, LO leakage a IQ nevyvážení.

Typický RX řetězec:

$$
\text{anténa}\rightarrow\text{filtr}\rightarrow\text{LNA}\rightarrow\text{směšovač}\rightarrow\text{IF/BB filtr}\rightarrow\text{VGA/ADC/DSP}.
$$

AGC řídí zisk podle okamžité úrovně signálu, aby nedošlo k zahlcení dalších stupňů a zároveň zůstala dobrá citlivost.

**Zdroj:** [[TBK 6 systémy 20.pdf#page=27|TBK 6 s. 27]], [[TBK 6 systémy 20.pdf#page=31|TBK 6 s. 31]], [[TBK 6 systémy 20.pdf#page=33|TBK 6 s. 33]], [[TBK 6 systémy 20.pdf#page=37|TBK 6 s. 37]], [[TBK 6 systémy 20.pdf#page=45|TBK 6 s. 45]], [[TBK 6 systémy 20.pdf#page=54|TBK 6 s. 54]].

## Co umět u zkoušky

- Vysvětlit rozdíl mezi vlnou na vedení a vlnou ve volném prostoru.
- Rozlišit simplex, TDD poloduplex a FDD plný duplex.
- Popsat BPSK, QPSK, M-QAM, OFDM a význam IQ roviny.
- Zapsat dopřednou a odraženou napěťovou vlnu, $\Gamma$, $RL$ a $PSV$.
- Vysvětlit, k čemu slouží Smithův diagram.
- Rozlišit S-parametry, šumové číslo, šumovou teplotu, $P_{-1\mathrm{dB}}$, IP2, IP3 a IM produkty.
- Popsat základní bloky TX/RX a rozdíl mezi přímou IQ strukturou a superhetem.
