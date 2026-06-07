# 22 Antény, šíření vln, návrh rádiových spojů a výkonová bilance

> Hlavní podklad: [[AntenySireni-UcebniTextTBK-v1.0.pdf]]. Doplňkově [[TBK 1 úvod 25.ppt [režim kompatibility].pdf]], [[TBK 6 systémy 20.pdf]], [[TBK 6 B příklady systémů f.pdf]]. Znění okruhu: [[SZZ - Odborné okruhy|odborný okruh 22]].

## Používané antény

Anténa převádí vedenou elektromagnetickou vlnu na vlnu šířící se prostorem a na přijímací straně naopak. Parametry antény jsou reciproké: stejná anténa má v zásadě stejné směrové a impedanční vlastnosti při vysílání i příjmu.

Používané typy:

- **izotropický zářič**: idealizovaná referenční anténa, vyzařuje stejně do všech směrů,
- **elementární dipól a půlvlnný dipól**: základní rezonanční antény,
- **čtvrtvlnný monopól nad vodivou zemí**: běžná nesymetrická anténa,
- **všesměrové antény**: pokrytí oblasti kolem stanice,
- **směrové antény**: yagi, trychtýř, parabolická anténa, panelová a sektorová anténa,
- **aperturové a reflektorové antény**: vysoký zisk a úzký svazek pro mikrovlnné spoje.

Vyšší frekvence zkracuje vlnovou délku, takže pro stejný elektrický rozměr může být anténa fyzicky menší. To je důležité u mobilních a mikrovlnných systémů.

**Zdroj:** [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=4|Antény a šíření s. 4]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=8|Antény a šíření s. 8]], [[TBK 1 úvod 25.ppt [režim kompatibility].pdf#page=10|TBK 1 s. 10]], [[TBK 6 B příklady systémů f.pdf#page=7|TBK 6B s. 7]].

## Parametry antén

Vstupní impedance antény $Z_A$ musí být přizpůsobena vedení s impedancí $Z_0$. Činitel odrazu je

$$
R=\frac{Z_A-Z_0}{Z_A+Z_0}.
$$

Return Loss:

$$
RL=-20\log|R|.
$$

Poměr stojatých vln:

$$
PSV=\frac{1+|R|}{1-|R|}.
$$

Šířka pásma antény je interval frekvencí, kde anténa splňuje požadavek na přizpůsobení, zisk nebo jiný parametr.

Směrová charakteristika $F(\vartheta,\varphi)$ popisuje vyzařování do prostoru. Důležité pojmy jsou hlavní lalok, postranní laloky, HPBW a čelní/zadní poměr.

Směrovost je poměr intenzity vyzařování v daném směru vůči referenčnímu izotropickému zářiči při stejném celkovém vyzářeném výkonu:

$$
D(\vartheta,\varphi)=\frac{U(\vartheta,\varphi)}{U_0}.
$$

Zisk zahrnuje i účinnost antény:

$$
G=\eta D,
\qquad
G_\mathrm{dB}=10\log G.
$$

Efektivní vyzářený výkon:

$$
EIRP=P_VG_V,
$$

v dB:

$$
EIRP_\mathrm{dBm}=P_{V,\mathrm{dBm}}+G_{V,\mathrm{dBi}}.
$$

Polarizace může být lineární, kruhová nebo eliptická. Při natočení lineárních polarizací o úhel $\psi$ vzniká polarizační ztráta

$$
L_\mathrm{pol}=\cos^2\psi.
$$

Efektivní plocha přijímací antény:

$$
P_P=w_\mathrm{dop}A_\mathrm{ef},
\qquad
A_\mathrm{ef}=\frac{\lambda^2}{4\pi}G.
$$

```tikz
\begin{document}
  \begin{tikzpicture}[scale=0.95]
    \draw[->] (-3.2,0) -- (3.4,0) node[right] {$\theta$};
    \draw[->] (0,-0.2) -- (0,2.5) node[above] {$|F_n|$};
    \draw[thick] (-3,0.1) .. controls (-2.45,0.15) and (-2.3,0.55) .. (-2.05,0.45)
      .. controls (-1.65,0.25) and (-1.0,0.75) .. (-0.67,1.05)
      .. controls (-0.35,1.85) and (0.35,1.85) .. (0.67,1.05)
      .. controls (1.0,0.75) and (1.65,0.25) .. (2.05,0.45)
      .. controls (2.3,0.55) and (2.45,0.15) .. (3,0.1);
    \draw[dashed] (-0.67,1.05) -- (0.67,1.05);
    \draw[<->] (-0.67,0.85) -- (0.67,0.85) node[midway,below] {HPBW};
    \node at (0,2.15) {main lobe};
    \node at (2.1,0.75) {side};
    \node at (-2.1,0.75) {side};
  \end{tikzpicture}
\end{document}
```

**Zdroj:** [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=5|Antény a šíření s. 5]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=7|Antény a šíření s. 7]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=8|Antény a šíření s. 8]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=9|Antény a šíření s. 9]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=10|Antény a šíření s. 10]].

## Šíření elektromagnetických vln v různých prostředích

Pro pozemní rádiové spoje se rozlišuje několik mechanismů šíření:

- **povrchová vlna**: šíří se podél rozhraní země-vzduch, významná hlavně na nižších frekvencích,
- **prostorová vlna**: přímá a odražená vlna v troposféře, typická pro VHF, UHF a mikrovlnné spoje,
- **troposférická vlna**: rozptyl nebo odraz v troposféře, umožňuje spojení za horizont,
- **ionosférická vlna**: zakřivení nebo odraz v ionosféře, významné hlavně pro krátké vlny do řádu desítek MHz,
- **vlnovodný kanál / ducting**: anomální refrakce v troposféře, kdy se vlna může šířit velmi daleko.

Ztráty šířením mohou vznikat rozprostřením energie ve volném prostoru, absorpcí atmosférickými plyny, útlumem deštěm, odrazem, difrakcí, rozptylem, stíněním, polarizačním nepřizpůsobením a vícecestným šířením.

Ve městě se uplatňují odrazy od budov, difrakce na hranách střech a průchod překážkami. V makrobuňce bývá základnová anténa nad střechami, v mikrobuňce rozhodují ulice a odrazy od stěn, v pikobuňce nebo interiéru je prostředí velmi členité a časově proměnné.

**Zdroj:** [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=14|Antény a šíření s. 14]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=15|Antény a šíření s. 15]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=16|Antény a šíření s. 16]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=46|Antény a šíření s. 46]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=47|Antény a šíření s. 47]].

## Šíření ve volném prostoru

Pro izotropický zářič je výkonová hustota ve vzdálenosti $d$

$$
w=\frac{P_\mathrm{vyz}}{4\pi d^2}.
$$

Pro směrovou vysílací anténu:

$$
w_V=\frac{P_VG_V}{4\pi d^2}.
$$

Přijatý výkon ve volném prostoru určuje Friisův vztah

$$
\frac{P_P}{P_V}
=G_VG_P\left(\frac{\lambda}{4\pi d}\right)^2.
$$

Ztráty volným prostorem jsou

$$
L_\mathrm{FSL}
=20\log\left(\frac{4\pi d}{\lambda}\right).
$$

V decibelech se výkonová bilance ideálního volnoprostorového spoje píše

$$
P_P=P_V+G_V+G_P-L_\mathrm{FSL}-L,
$$

kde $L$ zahrnuje ostatní ztráty.

**Zdroj:** [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=21|Antény a šíření s. 21]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=22|Antény a šíření s. 22]].

## Odraz, difrakce, Fresnelovy zóny a refrakce

Při dopadu vlny na rozhraní dvou prostředí vzniká odražená a pronikající vlna. Činitel odrazu závisí na polarizaci, úhlu dopadu a elektrických parametrech povrchu. U zemského povrchu se výrazně liší chování horizontální a vertikální polarizace.

Fresnelovy zóny popisují oblasti, ze kterých přicházejí příspěvky s postupně se měnící fází. Pro kvalitní LOS spoj nestačí optická viditelnost, ale je potřeba mít dostatečně volnou první Fresnelovu zónu. Zastínění první Fresnelovy zóny způsobuje difrakční ztráty.

Difrakce na ostré překážce se modeluje jako knife-edge. V praxi se používá pro terénní vrcholy, hrany střech a překážky v profilu spoje.

Refrakce v troposféře vzniká změnou indexu lomu s výškou. Standardní refrakce ohýbá paprsek mírně k Zemi; superrefrakce a ducting mohou prodlužovat dosah, subrefrakce naopak zhoršuje spoj.

```tikz
\begin{document}
  \begin{tikzpicture}[scale=0.95]
    \coordinate (Tx) at (0,1.2);
    \coordinate (Rx) at (7,1.0);
    \draw[thick] (0,0) -- (7,0);
    \fill (Tx) circle (2pt) node[above] {TX};
    \fill (Rx) circle (2pt) node[above] {RX};
    \draw[thick,->] (Tx) -- (Rx) node[midway,above] {direct wave};
    \draw[thick,->] (Tx) -- (3.5,0) -- (Rx) node[midway,below right] {reflected wave};
    \draw[dashed] (3.5,1.1) ellipse (2.4 and 0.55);
    \node at (3.5,1.9) {1st Fresnel zone};
  \end{tikzpicture}
\end{document}
```

**Zdroj:** [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=25|Antény a šíření s. 25]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=27|Antény a šíření s. 27]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=32|Antény a šíření s. 32]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=36|Antény a šíření s. 36]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=42|Antény a šíření s. 42]].

## Systémový návrh rádiových spojů

Návrh spoje začíná požadavkem na službu: datová rychlost, šířka pásma, modulace, požadované BER nebo SNR, dostupnost spoje a regulatorní omezení EIRP a frekvenčního pásma.

Základní postup:

1. Zvolit typ spoje, frekvenci, duplexní režim a šířku pásma.
2. Zvolit antény, jejich zisk, polarizaci, směrování a výšky.
3. Spočítat ztráty šířením: volný prostor, atmosféra, déšť, terén, Fresnelova zóna, městské prostředí.
4. Sestavit výkonovou bilanci v dB.
5. Spočítat šumový práh přijímače a požadované SNR.
6. Ověřit rezervu na únik, rušení, nelinearity a regulační limity.

Minimální přijatý výkon lze vyjádřit přímo jako citlivost přijímače nebo přes SNR:

$$
P_{P,\min}=N_\mathrm{dBm}+SNR_\min.
$$

Šumový výkon pro šířku pásma $B$ a systémovou šumovou teplotu $T_e$:

$$
N=kT_eB.
$$

V dBm se často používá

$$
N_\mathrm{dBm}
\approx -174+10\log B_\mathrm{Hz}+F_\mathrm{dB}.
$$

**Zdroj:** [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=17|Antény a šíření s. 17]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=18|Antény a šíření s. 18]], [[TBK 3 parametry 25.pdf#page=23|TBK 3 s. 23]], [[TBK 5 signály 25 .pdf#page=25|TBK 5 s. 25]].

## Výkonová bilance

Výkonová bilance skládá v logaritmické míře všechny zisky a ztráty od vysílače k přijímači:

$$
P_P=P_V+G_V+G_P-L_c-L_\mathrm{ost}.
$$

Podle učebního textu lze požadavek kvality zapsat buď přes minimální přijatý výkon

$$
P_{P,\min}\le P_P,
$$

nebo přes odstup signál-šum

$$
SNR_\min\le
P_P-10\log(kT_eB).
$$

Celkové ztráty šířením se často rozdělí na stabilní část a fading:

$$
L_c=L_z+L_f.
$$

Rezerva na únik je rozdíl mezi přijatým výkonem bez úniků a minimálním požadovaným výkonem:

$$
A=P_{P0}-P_{P,\min}.
$$

```tikz
\begin{document}
  \begin{tikzpicture}[x=1cm,y=0.75cm]
    \draw[->] (0,0) -- (10.5,0) node[right] {link chain};
    \draw[->] (0,-2.2) -- (0,2.5) node[above] {level [dB]};
    \draw[thick] (0.7,1.8) -- (1.7,1.8) node[midway,above] {$P_V$};
    \draw[thick,->] (1.7,1.8) -- (2.4,2.3) node[midway,above left] {$G_V$};
    \draw[thick,->] (2.4,2.3) -- (6.4,-1.0) node[midway,above] {$L_c$};
    \draw[thick,->] (6.4,-1.0) -- (7.2,-1.4) node[midway,below] {$L_\mathrm{ost}$};
    \draw[thick,->] (7.2,-1.4) -- (8.0,-0.8) node[midway,right] {$G_P$};
    \draw[thick] (8.0,-0.8) -- (9.0,-0.8) node[midway,above] {$P_P$};
    \draw[dashed] (0.5,-1.6) -- (9.3,-1.6) node[right] {$P_{P,\min}$};
    \draw[<->] (9.3,-1.6) -- (9.3,-0.8) node[midway,right] {$A$};
  \end{tikzpicture}
\end{document}
```

Rezerva na únik se volí podle požadované dostupnosti spoje a statistiky fadingu pro dané prostředí. U pevných mikrovlnných spojů může dominovat déšť, atmosférická refrakce a vícecestné šíření; u mobilních spojů dominují rychlé úniky, stínění a rušení.

**Zdroj:** [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=17|Antény a šíření s. 17]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=18|Antény a šíření s. 18]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=21|Antény a šíření s. 21]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=22|Antény a šíření s. 22]].

## Modelování šíření

Pro jednoduché spoje na přímou viditelnost se používá volnoprostorový model s doplněním dalších ztrát. Pro mobilní a městská prostředí se často používají empirické modely:

$$
L(d)=L_1+10n\log\frac{d}{d_1},
$$

kde $n$ je spádový koeficient prostředí. Ve volném prostoru je $n\approx2$, v zástavbě může být výrazně vyšší.

Deterministické modely, například ray tracing, vycházejí z geometrické optiky a skládají příspěvky přímých, odražených, difraktovaných a prostupujících paprsků. Jsou přesnější, ale vyžadují geometrii prostředí a vyšší výpočetní náročnost.

**Zdroj:** [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=47|Antény a šíření s. 47]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=48|Antény a šíření s. 48]], [[AntenySireni-UcebniTextTBK-v1.0.pdf#page=49|Antény a šíření s. 49]].

## Co umět u zkoušky

- Vysvětlit funkci antény jako převodníku mezi vedenou a prostorovou vlnou.
- Popsat impedanci, přizpůsobení, PSV, šířku pásma, směrovou charakteristiku, HPBW, zisk, EIRP, polarizaci a efektivní aperturu.
- Rozlišit izotropický zářič, dipól, monopól, směrovou/parabolickou/sektorovou anténu.
- Popsat povrchovou, prostorovou, troposférickou a ionosférickou vlnu.
- Vysvětlit volnoprostorové šíření, Friisův vztah a ztráty volným prostorem.
- Popsat odraz, difrakci, Fresnelovy zóny, refrakci, ducting a vícecestné šíření.
- Sestavit výkonovou bilanci v dB a určit rezervu na únik.
- Vysvětlit rozdíl mezi empirickým a deterministickým modelem šíření.
