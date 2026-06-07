# 16 Vedené a evanescentní vlny, vlnovody a vedení

> Hlavní podklad: [[Elektromagnetická vlna_13_5_2021.pdf]]. Znění okruhu: [[SZZ - Odborné okruhy|odborný okruh 16]].

## Vedené a evanescentní vlny

Vedená vlna je elektromagnetická vlna, jejíž šíření je určeno rozhraním nebo vodivou strukturou. Energie se šíří převážně podél vedení, vlnovodu nebo rozhraní. Příčný průřez přitom určuje, jaké prostorové rozložení pole je možné.

Evanescentní vlna se šíří podél rozhraní nebo struktury, ale kolmo od ní exponenciálně zaniká. U totálního odrazu ELD uvádí fázor

$$
\hat E_t(x,y,z)=\hat E_{t0}e^{-jk_2px}e^{-k_2qz}.
$$

První exponenciála popisuje šíření podél rozhraní, druhá útlum směrem do druhého prostředí. Podobně se ve vlnovodu pod mezním kmitočtem podélná konstanta stává imaginární a mód se podél vlnovodu nešíří jako postupná vlna, ale zaniká.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=67|ELD s. 67]], [[Elektromagnetická vlna_13_5_2021.pdf#page=87|ELD s. 87]], [[Elektromagnetická vlna_13_5_2021.pdf#page=94|ELD s. 94]].

## Módy

Mód je vlastní prostorové rozložení elektromagnetického pole, které v dané geometrii splňuje Maxwellovy rovnice a okrajové podmínky. Ve vlnovodu se pole rozkládá na příčné a podélné složky.

Základní typy módů:

- **TE mód**: elektrické pole nemá podélnou složku, tedy $E_z=0$.
- **TM mód**: magnetické pole nemá podélnou složku, tedy $H_z=0$.
- **TEM mód**: elektrické i magnetické pole jsou celé příčné, tedy $E_z=H_z=0$; vzniká na dvouvodičových vedeních, například na koaxiálním kabelu.

V obdélníkovém vlnovodu se módy značí například $\mathrm{TE}_{10}$ nebo $\mathrm{TM}_{11}$. Indexy $m,n$ vyjadřují počet půlvln stojatého vlnění v příčných směrech. Pro příčné konstanty platí

$$
k_x=\frac{m\pi}{a},
\qquad
k_y=\frac{n\pi}{b},
$$

a pro vlnové číslo

$$
k^2=k_x^2+k_y^2+k_z^2.
$$

Pokud je $k_z$ reálné, mód se šíří. Pokud je $k_z$ imaginární, mód je pod mezí a podél vlnovodu zaniká.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=86|ELD s. 86]], [[Elektromagnetická vlna_13_5_2021.pdf#page=90|ELD s. 90]], [[Elektromagnetická vlna_13_5_2021.pdf#page=93|ELD s. 93]], [[Elektromagnetická vlna_13_5_2021.pdf#page=94|ELD s. 94]], doplněk podle [[hex_compost.pdf#page=161|HEX s. 161]].

## Impedance

Impedance vedené vlny vyjadřuje poměr příslušných příčných složek elektrického a magnetického pole. U rovinné vlny je to prostě poměr $E/H$, ve vlnovodu se rozlišuje podle typu módu.

Pro TE a TM módy je impedance frekvenčně závislá, protože závisí na mezním kmitočtu daného módu. Smysl je zkouškově důležitější než detailní algebra: impedance určuje vztah mezi elektrickou a magnetickou složkou módu a vstupuje do přenosu výkonu a odrazů.

U homogenního vedení se používá charakteristická impedance

$$
\hat Z_0=\sqrt{\frac{R+j\omega L}{G+j\omega C}},
$$

kde $R$, $L$, $G$, $C$ jsou parametry na jednotku délky. Pro bezeztrátové vedení

$$
Z_0=\sqrt{\frac{L}{C}}.
$$

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=98|ELD s. 98]], [[Elektromagnetická vlna_13_5_2021.pdf#page=108|ELD s. 108]], [[Elektromagnetická vlna_13_5_2021.pdf#page=114|ELD s. 114]], doplněk podle [[hex_compost.pdf#page=165|HEX s. 165]].

## Fázová a skupinová rychlost šíření

Fázová rychlost je rychlost pohybu místa se stejnou fází:

$$
v_f=\frac{\omega}{k_z}.
$$

Skupinová rychlost je rychlost šíření obálky vlnového balíku a prakticky souvisí s přenosem energie:

$$
v_s=\frac{d\omega}{dk_z}.
$$

Ve vlnovodu jsou tyto rychlosti závislé na kmitočtu. Při kritickém kmitočtu je $k_z=0$, takže fázová rychlost formálně roste k nekonečnu, ale skupinová rychlost klesá k nule. Nad kritickým kmitočtem se mód vede. U TE a TM módů platí, že fázová rychlost může být větší než rychlost světla v daném prostředí, ale nepřenáší informaci; přenos energie odpovídá skupinové rychlosti.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=95|ELD s. 95]], [[Elektromagnetická vlna_13_5_2021.pdf#page=96|ELD s. 96]], doplněk podle [[hex_compost.pdf#page=165|HEX s. 165]].

## Přenos výkonu

Přenášený výkon se počítá z časové střední hodnoty Poyntingova vektoru přes průřez vedené struktury:

$$
P=\int_S\mathbf S_\mathrm{stř}\cdot d\mathbf S,
\qquad
\mathbf S_\mathrm{stř}
=\frac12\operatorname{Re}(\hat{\mathbf E}\times\hat{\mathbf H}^{*}).
$$

U vlnovodu výkon teče v podélném směru a rozložení pole v průřezu závisí na módu. U homogenního vedení se výkon popisuje také napětím, proudem a charakteristickou impedancí. Pokud je vedení zakončeno impedancí $Z_K=Z_0$, nevzniká odraz a výkon se předává do zátěže.

Při nepřizpůsobení vzniká činitel odrazu

$$
\hat R=\frac{\hat Z_K-\hat Z_0}{\hat Z_K+\hat Z_0}
$$

a na vedení vzniká stojaté vlnění.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=102|ELD s. 102]], [[Elektromagnetická vlna_13_5_2021.pdf#page=106|ELD s. 106]], [[Elektromagnetická vlna_13_5_2021.pdf#page=119|ELD s. 119]], [[Elektromagnetická vlna_13_5_2021.pdf#page=129|ELD s. 129]].

## Zdroje vln - elementární zářiče

Zdrojem elektromagnetické vlny je časově proměnný proud nebo náboj. ELD v úvodu používá jako intuitivní model harmonicky kmitající elektrický dipól: periodické přeskupování náboje budí časově proměnné elektrické pole a s ním spojené magnetické pole.

Elementární elektrický zářič, často Hertzův dipól, je krátký vodičový element délky $l$ protékaný harmonickým proudem, přičemž $l\ll\lambda$. Slouží jako základní model anténního vyzařování. Ve vzdáleném poli má příčné složky $\mathbf E$ a $\mathbf H$, které jsou navzájem kolmé a kolmé ke směru šíření.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=4|ELD s. 4]], doplněk k zadání; v dodaném ELD PDF není samostatná kapitola o elementárním zářiči.

## Blízké, přechodné a vzdálené pole zářičů

Pole zářiče se podle vzdálenosti od zdroje dělí na oblasti:

- **Blízké pole**: reaktivní oblast u zářiče, kde se významně uplatňuje energie vázaná u zdroje a pole se nechová jako lokálně rovinná vlna.
- **Přechodné pole**: oblast mezi blízkým a vzdáleným polem, kde se ještě mění prostorové rozložení pole a nelze jednoduše použít aproximaci rovinné vlny.
- **Vzdálené pole**: radiační oblast, kde jsou $\mathbf E$, $\mathbf H$ a směr šíření navzájem kolmé, poměr $E/H$ odpovídá vlnové impedanci prostředí a amplituda u bodového zářiče klesá přibližně jako $1/r$.

ELD přímo vysvětluje, že u bodového zdroje jsou vlnoplochy blízko zdroje sférické a ve velké vzdálenosti se jejich malé části dají považovat za rovinné.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=2|ELD s. 2]], [[Elektromagnetická vlna_13_5_2021.pdf#page=3|ELD s. 3]], [[Elektromagnetická vlna_13_5_2021.pdf#page=4|ELD s. 4]], doplněk k zadání.

## Vlna v anizotropním prostředí

V izotropním prostředí jsou $\mathbf D$ a $\mathbf E$ rovnoběžné a souvisí skalárem $\varepsilon$; podobně $\mathbf B$ a $\mathbf H$ souvisí skalárem $\mu$. V anizotropním prostředí závisí materiálová odezva na směru, proto se permitivita a permeabilita popisují tenzory:

$$
\mathbf D=\boldsymbol{\varepsilon}\mathbf E,
\qquad
\mathbf B=\boldsymbol{\mu}\mathbf H.
$$

Důsledkem je, že $\mathbf D$ nemusí být rovnoběžné s $\mathbf E$ a vlastnosti vlny závisí na směru šíření i polarizaci. V jednodušších případech se volí hlavní osy materiálu, ve kterých je tenzor diagonální. Typickým jevem je dvojlom: dvě polarizace se mohou šířit různou fázovou rychlostí.

**Zdroj:** doplněk k zadání podle [[hex_compost.pdf#page=166|HEX s. 166]]. V dodaném ELD PDF není anizotropní prostředí samostatně vyloženo.

## Co umět u zkoušky

- Rozlišit vedenou a evanescentní vlnu.
- Definovat módy TE, TM a TEM a vysvětlit mezní kmitočet.
- Popsat impedanci vedeného módu a charakteristickou impedanci vedení.
- Vysvětlit fázovou a skupinovou rychlost ve vlnovodu.
- Spočítat výkon přes Poyntingův vektor a vysvětlit odraz na nepřizpůsobeném vedení.
- Stručně popsat elementární zářič a oblasti blízkého, přechodného a vzdáleného pole.
- Vysvětlit, proč se v anizotropním prostředí používají tenzory $\boldsymbol{\varepsilon}$ a $\boldsymbol{\mu}$.
