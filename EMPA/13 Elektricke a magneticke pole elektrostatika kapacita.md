# 13 Elektrické a magnetické pole, elektrostatika, kapacita

> Hlavní podklad: [[empa_complete_edition.pdf]]. Znění okruhu: [[SZZ - Odborné okruhy|odborný okruh 13]].

## Elektrické a magnetické pole a jeho zdroje

Elektrické pole je buzeno elektrickými náboji. Na náboj $Q$ působí silou

$$
\mathbf F=Q\mathbf E.
$$

Pro dva bodové náboje platí Coulombův zákon

$$
\mathbf F_{12}
=\frac{1}{4\pi\varepsilon}
\frac{Q_1Q_2}{r^2}\mathbf r_0.
$$

Intenzita pole bodového náboje je

$$
\mathbf E
=\frac{1}{4\pi\varepsilon}
\frac{Q}{r^2}\mathbf r_0.
$$

Magnetické pole je buzeno pohybujícími se náboji, tedy proudy. Na pohybující se náboj působí magnetická složka Lorentzovy síly

$$
\mathbf F=Q(\mathbf v\times\mathbf B).
$$

Zdrojem magnetického pole v technických úlohách je hlavně kondukční proud; v materiálech se navíc uplatňují vázané proudy související s magnetizací.

**Zdroj:** [[empa_complete_edition.pdf#page=7|EMPA s. 7]], [[empa_complete_edition.pdf#page=10|EMPA s. 10]], [[empa_complete_edition.pdf#page=40|EMPA s. 40]], [[empa_complete_edition.pdf#page=42|EMPA s. 42]].

## Pole vírové a potenciálové

Elektrostatické pole je potenciálové. Intenzita elektrického pole je záporný gradient potenciálu

$$
\mathbf E=-\nabla\varphi,
$$

a práce v uzavřené křivce je nulová. Napětí mezi body $A$ a $B$ je

$$
U_{AB}
=\int_A^B\mathbf E\cdot d\mathbf l
=\varphi_A-\varphi_B.
$$

Magnetické pole je vírové: magnetické indukční čáry netvoří začátky a konce na magnetických nábojích, ale uzavírají se. Tok magnetické indukce uzavřenou plochou je nulový

$$
\oint_S\mathbf B\cdot d\mathbf S=0.
$$

Stacionární magnetické pole má zároveň cirkulaci danou proudy, tedy je přirozeně popisováno Ampérovým zákonem.

**Zdroj:** [[empa_complete_edition.pdf#page=8|EMPA s. 8]], [[empa_complete_edition.pdf#page=19|EMPA s. 19]], [[empa_complete_edition.pdf#page=20|EMPA s. 20]], [[empa_complete_edition.pdf#page=46|EMPA s. 46]].

## Klasifikace prostředí

Pro elektrické pole je základní dělení na vodiče a dielektrika. Ve vodiči jsou volné nosiče náboje a v elektrostatické rovnováze je uvnitř dobrého vodiče elektrické pole nulové. Volný náboj se rozmístí na povrchu.

Dielektrikum nemá dostatek volných nosičů, ale v elektrickém poli se polarizuje. Elektrický dipólový moment je

$$
\mathbf p=q\mathbf d,
$$

a polarizace je objemová hustota dipólového momentu

$$
\mathbf P=\lim_{\Delta V\to0}\frac{\sum_{\Delta V}\mathbf p}{\Delta V}.
$$

Pro magnetické pole se prostředí popisuje permeabilitou a magnetizací. V lineárním izotropním prostředí jsou materiálové vztahy skalární; ve feromagnetiku bývá vztah nelineární a s hysterezí.

**Zdroj:** [[empa_complete_edition.pdf#page=8|EMPA s. 8]], [[empa_complete_edition.pdf#page=15|EMPA s. 15]], [[empa_complete_edition.pdf#page=16|EMPA s. 16]], [[empa_complete_edition.pdf#page=52|EMPA s. 52]], [[empa_complete_edition.pdf#page=55|EMPA s. 55]].

## Základní vektorové veličiny v elektrickém poli

Základní veličiny elektrického pole jsou intenzita $\mathbf E$, elektrická indukce $\mathbf D$, polarizace $\mathbf P$, potenciál $\varphi$ a elektrický indukční tok $\Psi$.

Elektrická indukce zahrnuje vliv volných nábojů i polarizace:

$$
\mathbf D=\varepsilon_0\mathbf E+\mathbf P.
$$

V lineárním izotropním dielektriku

$$
\mathbf P=\varepsilon_0\chi_e\mathbf E,
\qquad
\mathbf D=\varepsilon_0\varepsilon_r\mathbf E=\varepsilon\mathbf E.
$$

Elektrický indukční tok plochou $S$ je

$$
\Psi=\int_S\mathbf D\cdot d\mathbf S.
$$

Okrajové podmínky na rozhraní dielektrik jsou spojitost tečné složky $\mathbf E$ a skok normálové složky $\mathbf D$ podle plošného volného náboje:

$$
E_{1t}=E_{2t},
\qquad
D_{2n}-D_{1n}=\sigma_0.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=16|EMPA s. 16]], [[empa_complete_edition.pdf#page=17|EMPA s. 17]], [[empa_complete_edition.pdf#page=18|EMPA s. 18]], [[empa_complete_edition.pdf#page=27|EMPA s. 27]], [[empa_complete_edition.pdf#page=28|EMPA s. 28]].

## Elektrostatické pole - Gaussova věta elektrostatiky

Gaussova věta elektrostatiky říká, že tok elektrické indukce uzavřenou plochou se rovná volnému náboji uvnitř plochy:

$$
\oint_S\mathbf D\cdot d\mathbf S=Q_0.
$$

Diferenciální tvar je

$$
\operatorname{div}\mathbf D=\rho_0.
$$

V homogenním prostředí lze psát také

$$
\oint_S\mathbf E\cdot d\mathbf S
=\frac{Q_\mathrm{celk}}{\varepsilon},
\qquad
\operatorname{div}\mathbf E=\frac{\rho}{\varepsilon}.
$$

Gaussova věta je nejúčinnější u symetrických úloh, kde lze zvolit Gaussovu plochu tak, aby pole bylo na části plochy konstantní a integrál se zjednodušil.

**Zdroj:** [[empa_complete_edition.pdf#page=12|EMPA s. 12]], [[empa_complete_edition.pdf#page=14|EMPA s. 14]], [[empa_complete_edition.pdf#page=16|EMPA s. 16]], [[empa_complete_edition.pdf#page=17|EMPA s. 17]].

## Aplikace Gaussovy věty pro výpočet

Postup výpočtu je vždy stejný: určit symetrii, zvolit vhodnou uzavřenou Gaussovu plochu, spočítat uzavřený náboj a vyjádřit tok přes plochu.

Pro bodový náboj se volí kulová plocha, protože $\mathbf E$ je radiální a má konstantní velikost na sféře. Pro nekonečně dlouhý přímý náboj se volí válcová plocha. Pro nekonečnou rovinu se volí krabička procházející rovinou.

U koaxiální geometrie s nábojem na jednotku délky $\tau$ je indukce mezi vodiči

$$
D(r)=\frac{\tau}{2\pi r},
$$

a intenzita v homogenním dielektriku

$$
E(r)=\frac{\tau}{2\pi\varepsilon r}.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=12|EMPA s. 12]], [[empa_complete_edition.pdf#page=23|EMPA s. 23]].

## Metoda zrcadlení

Metoda zrcadlení nahrazuje vodivou rovinu fiktivními náboji nebo vodiči tak, aby na původní rovině byly splněny stejné okrajové podmínky. U uzemněné vodivé roviny je potenciál roviny nulový a elektrické pole na ni vstupuje kolmo.

Typický případ je vodič nad uzemněnou rovinou. Rovina se nahradí zrcadlovým vodičem s opačným nábojem. Potom lze úlohu řešit jako pole ve volném prostoru bez explicitního vodiče.

Smysl metody není v jednom zapamatovaném vzorci, ale v tom, že náhradní soustava musí dát stejný potenciál na vodiči a stejný průběh pole v původní oblasti.

**Zdroj:** [[empa_complete_edition.pdf#page=31|EMPA s. 31]], [[empa_complete_edition.pdf#page=32|EMPA s. 32]].

## Energie v elektrickém poli

Energie soustavy nábojů se dá vyjádřit pomocí potenciálů v místech nábojů:

$$
W_e=\frac12\sum_i Q_i\varphi_i.
$$

U lineárního kapacitoru

$$
W_e=\frac12CU^2=\frac12QU=\frac{Q^2}{2C}.
$$

Objemová hustota energie v lineárním elektrickém poli je

$$
w_e=\frac12\mathbf E\cdot\mathbf D.
$$

Celková energie v objemu $V$ je

$$
W_e=\int_V w_e\,dV.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=26|EMPA s. 26]], [[empa_complete_edition.pdf#page=27|EMPA s. 27]].

## Objemová hustota energie

Objemová hustota energie říká, kolik energie elektrického pole připadá na jednotku objemu. V lineárním izotropním prostředí platí

$$
w_e=\frac12\mathbf E\cdot\mathbf D
=\frac12\varepsilon E^2.
$$

Tento vztah je užitečný hlavně při výpočtu energie z rozložení pole, například u kondenzátoru nebo vedení. Z energie lze zpětně určit kapacitu, protože pro lineární kapacitor musí platit $W_e=\frac12CU^2$.

**Zdroj:** [[empa_complete_edition.pdf#page=27|EMPA s. 27]].

## Kapacita

Kapacita je schopnost soustavy elektrod akumulovat náboj při daném napětí:

$$
C=\frac{Q}{U},
\qquad
[C]=\mathrm F.
$$

Je dána geometrií elektrod a permitivitou prostředí. U lineární soustavy nezávisí na velikosti napětí ani náboje.

**Zdroj:** [[empa_complete_edition.pdf#page=22|EMPA s. 22]].

## Výpočet kapacity pro základní geometrické uspořádání elektrod

Deskový kondenzátor s plochou elektrod $S$, vzdáleností $d$ a homogenním dielektrikem má

$$
C=\varepsilon\frac{S}{d}.
$$

Koaxiální vedení délky $l$, vnitřního poloměru $a$ a vnějšího poloměru $b$ má kapacitu

$$
C=\frac{2\pi\varepsilon l}{\ln(b/a)},
$$

a kapacitu na jednotku délky

$$
C'=\frac{C}{l}
=\frac{2\pi\varepsilon}{\ln(b/a)}.
$$

Pro symetrické dvouvodičové vedení se kapacita určí z rozdílu potenciálů vodičů. EMPA pro vodiče s poloměrem $a$ a vzdáleností středů $s$ uvádí

$$
C'=\frac{\pi\varepsilon_0}{\ln\left(\frac{s-a}{a}\right)}
$$

pro geometrii použitou ve skriptu.

Při spojování kondenzátorů platí

$$
C_\parallel=\sum_i C_i,
\qquad
\frac{1}{C_\mathrm{s}}=\sum_i\frac{1}{C_i}.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=22|EMPA s. 22]], [[empa_complete_edition.pdf#page=23|EMPA s. 23]], [[empa_complete_edition.pdf#page=24|EMPA s. 24]], [[empa_complete_edition.pdf#page=25|EMPA s. 25]].

## Základní vektorové veličiny v magnetickém poli

Základní veličiny magnetického pole jsou magnetická indukce $\mathbf B$, intenzita magnetického pole $\mathbf H$, magnetizace $\mathbf M$ a magnetický tok $\Phi$.

Magnetický tok je

$$
\Phi=\int_S\mathbf B\cdot d\mathbf S.
$$

Vztah mezi $\mathbf B$, $\mathbf H$ a $\mathbf M$ je

$$
\mathbf B=\mu_0(\mathbf H+\mathbf M).
$$

V lineárním izotropním prostředí

$$
\mathbf M=\chi_m\mathbf H,
\qquad
\mathbf B=\mu_0\mu_r\mathbf H=\mu\mathbf H.
$$

Na rozhraní magnetik je spojitá normálová složka $\mathbf B$ a bez plošného volného proudu také tečná složka $\mathbf H$:

$$
B_{1n}=B_{2n},
\qquad
H_{1t}=H_{2t}.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=46|EMPA s. 46]], [[empa_complete_edition.pdf#page=52|EMPA s. 52]], [[empa_complete_edition.pdf#page=53|EMPA s. 53]], [[empa_complete_edition.pdf#page=64|EMPA s. 64]], [[empa_complete_edition.pdf#page=65|EMPA s. 65]].

## Co umět u zkoušky

- Vysvětlit zdroje elektrického a magnetického pole.
- Rozlišit potenciálové elektrostatické pole a vírové magnetické pole.
- Popsat vodič, dielektrikum, polarizaci a základní veličiny $\mathbf E$, $\mathbf D$, $\mathbf P$, $\varphi$.
- Použít Gaussovu větu pro jednoduché symetrické výpočty.
- Vysvětlit metodu zrcadlení.
- Zapsat energii a objemovou hustotu energie elektrického pole.
- Spočítat kapacitu deskového, koaxiálního a základního dvouvodičového uspořádání.
- Převést základní magnetické veličiny $\mathbf B$, $\mathbf H$, $\mathbf M$ a $\Phi$.
