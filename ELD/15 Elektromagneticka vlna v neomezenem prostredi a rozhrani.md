# 15 Elektromagnetická vlna v neomezeném prostředí a na rozhraní

> Hlavní podklad: [[Elektromagnetická vlna_13_5_2021.pdf]]. Kontrola rozsahu: [[hex_compost.pdf#page=152|HEX s. 152]].

## Maxwellovy rovnice a vlnová rovnice

V nestacionárním elektromagnetickém poli existuje elektrická a magnetická složka současně a nelze je od sebe oddělit. Vztah mezi nimi vyjadřují Maxwellovy rovnice. ELD začíná dvojicí rotačních rovnic:

$$
\operatorname{rot}\mathbf H
= \mathbf J + \frac{\partial \mathbf D}{\partial t},
$$

$$
\operatorname{rot}\mathbf E
= -\frac{\partial \mathbf B}{\partial t}.
$$

V lineárním izotropním prostředí platí materiálové vztahy

$$
\mathbf D = \varepsilon_0\varepsilon_r\mathbf E,
\qquad
\mathbf B = \mu_0\mu_r\mathbf H,
\qquad
\mathbf J = \sigma \mathbf E.
$$

Po dosazení materiálových vztahů a vhodném vyloučení jedné veličiny se získá vlnová rovnice. Pro intenzitu elektrického pole má mimo oblast zdrojů tvar, který lze chápat jako základní matematický popis elektromagnetické vlny:

$$
\nabla^2 \mathbf E
- \mu\sigma \frac{\partial \mathbf E}{\partial t}
- \mu\varepsilon \frac{\partial^2 \mathbf E}{\partial t^2}
= 0.
$$

Pro harmonické časové průběhy se používají fázory. Časové derivace se nahrazují násobením $j\omega$ a vlnová rovnice přechází na Helmholtzovu rovnici.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=5|ELD s. 5]], [[Elektromagnetická vlna_13_5_2021.pdf#page=6|ELD s. 6]], [[Elektromagnetická vlna_13_5_2021.pdf#page=7|ELD s. 7]].

## Rovinná harmonická vlna

Rovinná harmonická elektromagnetická vlna je řešení, ve kterém jsou vlnoplochy roviny a pole závisí jen na jedné prostorové souřadnici ve směru šíření. Pro volbu

$$
\mathbf E = \mathbf x_0 E_x(z)
$$

se u postupné vlny ve směru $+z$ používá fázor

$$
\hat E_x(z) = \hat E_0 e^{-j\hat k z},
$$

kde komplexní konstanta šíření je

$$
\hat k = \beta - j\alpha.
$$

Okamžitá hodnota intenzity elektrického pole je

$$
E_x(z,t)
= E_m e^{-\alpha z}\sin(\omega t-\beta z+\varphi_0).
$$

Význam parametrů:

- $\alpha$ je měrný útlum; určuje exponenciální pokles amplitudy ve směru šíření.
- $\beta$ je fázová konstanta; určuje fázové zpoždění na jednotku délky.
- $\varphi_0$ je referenční fáze na zvolené rovině.

Z Faradayovy rovnice plyne, že v rovinné vlně jsou $\mathbf E$, $\mathbf H$ a směr šíření navzájem kolmé. Vlnová impedance je

$$
\hat Z = \frac{\hat E_x}{\hat H_y}.
$$

Její absolutní hodnota udává poměr amplitud elektrického a magnetického pole; argument udává jejich fázový posun.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=9|ELD s. 9]], [[Elektromagnetická vlna_13_5_2021.pdf#page=10|ELD s. 10]], [[Elektromagnetická vlna_13_5_2021.pdf#page=11|ELD s. 11]], [[Elektromagnetická vlna_13_5_2021.pdf#page=12|ELD s. 12]], [[Elektromagnetická vlna_13_5_2021.pdf#page=13|ELD s. 13]].

## Vlnová délka, fázová a skupinová rychlost

Vlnová délka je nejmenší vzdálenost dvou míst, ve kterých jsou veličiny elektromagnetického pole ve fázi. Platí

$$
\lambda = \frac{2\pi}{\beta}.
$$

Fázová rychlost je rychlost pohybu vlnoplochy konstantní fáze:

$$
v_f = \frac{\omega}{\beta}.
$$

V obecném disperzním prostředí se energie nepřenáší nutně fázovou rychlostí, ale skupinovou rychlostí:

$$
v_s = \frac{d\omega}{d\beta}.
$$

V bezeztrátovém prostředí jsou podle ELD fázová i skupinová rychlost stejné.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=14|ELD s. 14]], [[Elektromagnetická vlna_13_5_2021.pdf#page=15|ELD s. 15]].

## Vliv prostředí, hloubka vniku a výkon

Vlastnosti vlny závisí na parametrech prostředí $\varepsilon$, $\mu$, $\sigma$. ELD rozlišuje elektricky nevodivé a dobře vodivé prostředí podle vztahu vodivostního členu $\sigma$ a posuvného členu $\omega\varepsilon$.

V dobrém vodiči se vlna výrazně tlumí. Hloubka vniku $\delta$ je vzdálenost, na které amplituda poklesne na $1/e$ původní hodnoty:

$$
\delta = \frac{1}{\alpha}.
$$

Přenášený výkon popisuje Poyntingův vektor

$$
\mathbf S = \mathbf E \times \mathbf H.
$$

Pro rovinnou vlnu se výkon šíří ve směru šíření vlny. Střední hodnota Poyntingova vektoru se pro fázory zapisuje

$$
\mathbf S_\mathrm{stř}
= \frac{1}{2}\operatorname{Re}(\hat{\mathbf E}\times \hat{\mathbf H}^{*}).
$$

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=16|ELD s. 16]], [[Elektromagnetická vlna_13_5_2021.pdf#page=17|ELD s. 17]], [[Elektromagnetická vlna_13_5_2021.pdf#page=19|ELD s. 19]], [[Elektromagnetická vlna_13_5_2021.pdf#page=25|ELD s. 25]].

## Rovinná, sférická, válcová vlna a Gaussův svazek

ELD podrobně odvozuje rovinnou harmonickou vlnu. V úvodu zároveň vysvětluje, že vlna od bodového zdroje má v blízkosti zdroje sférické vlnoplochy a v dostatečné vzdálenosti se části těchto vlnoploch podobají rovinám. To je fyzikální důvod, proč se vzdálené pole často aproximuje rovinnou vlnou.

> [!todo] DOPLNIT Z JINÉHO PODKLADU ELD  
> V dodaném ELD PDF jsem nenašel samostatný výklad válcové vlny ani Gaussova svazku. `hex_compost.pdf` tyto pojmy v otázce očekává kontrolně, ale faktické definice zde nejsou ověřitelné proti předmětovému PDF.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=2|ELD s. 2]], [[Elektromagnetická vlna_13_5_2021.pdf#page=3|ELD s. 3]], [[Elektromagnetická vlna_13_5_2021.pdf#page=4|ELD s. 4]], [[Elektromagnetická vlna_13_5_2021.pdf#page=9|ELD s. 9]], kontrolně [[hex_compost.pdf#page=152|HEX s. 152]].

## Polarizace vlny

Polarizace elektromagnetické vlny popisuje orientaci vektorů elektromagnetického pole v prostoru, obvykle podle intenzity elektrického pole. Pokud koncový bod vektoru $\mathbf E$ kmitá po přímce, jde o lineární polarizaci. Pokud vznikne kružnice nebo elipsa, jde o kruhovou nebo eliptickou polarizaci.

Obecnou polarizaci lze chápat jako superpozici dvou lineárně polarizovaných vln, které jsou prostorově natočené o $90^\circ$ a mají určitý vzájemný fázový posun:

- stejné fáze dávají lineární polarizaci,
- stejné amplitudy a fázový posun $90^\circ$ dávají kruhovou polarizaci,
- různé amplitudy a fázový posun $90^\circ$ dávají eliptickou polarizaci.

Při rozhraní se jako referenční rovina bere rovina dopadu. Rozlišuje se:

- **rovnoběžná polarizace**: $\mathbf E$ je rovnoběžná s rovinou dopadu,
- **kolmá polarizace**: $\mathbf E$ je kolmá na rovinu dopadu.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=26|ELD s. 26]], [[Elektromagnetická vlna_13_5_2021.pdf#page=27|ELD s. 27]], [[Elektromagnetická vlna_13_5_2021.pdf#page=38|ELD s. 38]].

## Vlna na rozhraní dvou prostředí

Při dopadu rovinné harmonické vlny na rozhraní dvou prostředí vzniká obecně dopadající, odražená a prostupující vlna. Rovina rozhraní odděluje prostředí 1 a 2. Rovina dopadu obsahuje vlnové vektory dopadající, odražené a prostupující vlny.

Na rozhraní musí být splněny okrajové podmínky pro tečné složky polí:

$$
\hat E_{1t} = \hat E_{2t},
\qquad
\hat H_{1t} = \hat H_{2t}.
$$

Z podmínek na rozhraní vyplývají Snellovy zákony. Úhel odrazu se rovná úhlu dopadu:

$$
\vartheta_r = \vartheta_i.
$$

Pro úhel prostupu platí vztah mezi konstantami šíření v obou prostředích; v dielektrikách se dá interpretovat jako lom ke kolmici nebo od kolmice podle poměru permitivit.

Při kolmém dopadu nezáleží na polarizaci. Činitel odrazu a prostupu jsou

$$
\hat R = \frac{\hat Z_2-\hat Z_1}{\hat Z_2+\hat Z_1},
$$

$$
\hat T = \frac{2\hat Z_2}{\hat Z_2+\hat Z_1}.
$$

Absolutní hodnota činitele odrazu udává poměr amplitudy odražené a dopadající vlny, argument udává fázový posun.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=37|ELD s. 37]], [[Elektromagnetická vlna_13_5_2021.pdf#page=38|ELD s. 38]], [[Elektromagnetická vlna_13_5_2021.pdf#page=40|ELD s. 40]], [[Elektromagnetická vlna_13_5_2021.pdf#page=45|ELD s. 45]], [[Elektromagnetická vlna_13_5_2021.pdf#page=46|ELD s. 46]].

## Totální odraz a evanescentní vlna

Při přechodu z elektricky hustšího prostředí do řidšího prostředí se vlna láme od kolmice. Kritický úhel nastane tehdy, když úhel prostupu dosáhne $\pi/2$. V ELD je pro dielektrika uveden vztah

$$
\vartheta_{i,\mathrm{kr}}
= \arcsin\sqrt{\frac{\varepsilon_{r2}}{\varepsilon_{r1}}},
\qquad \varepsilon_{r2}<\varepsilon_{r1}.
$$

Pro větší úhly dopadu nastává totální odraz. Absolutní hodnota činitele odrazu je rovna jedné bez ohledu na polarizaci:

$$
|\hat R_\parallel| = |\hat R_\perp| = 1.
$$

Přesto pod rozhraním vzniká speciální vlna. ELD ji popisuje jako evanescentní vlnu. Její fázor má tvar

$$
\hat E_t(x,y,z)
= \hat E_{t0} e^{-jk_2 p x}e^{-k_2 q z}.
$$

První exponenciální člen popisuje šíření podél rozhraní, druhý exponenciální člen popisuje pokles amplitudy ve směru kolmo od rozhraní. Vlna tedy postupuje podél rozhraní, ale směrem do druhého prostředí zaniká.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=63|ELD s. 63]], [[Elektromagnetická vlna_13_5_2021.pdf#page=64|ELD s. 64]], [[Elektromagnetická vlna_13_5_2021.pdf#page=65|ELD s. 65]], [[Elektromagnetická vlna_13_5_2021.pdf#page=66|ELD s. 66]], [[Elektromagnetická vlna_13_5_2021.pdf#page=67|ELD s. 67]].

## Polarizace odrazem a Brewsterův úhel

Polarizace odrazem nastává tehdy, když pro jednu polarizační složku vymizí odraz. U rozhraní dvou dielektrik ELD ukazuje, že pro rovnoběžně polarizovanou složku existuje polarizační, neboli Brewsterův úhel. Pokud na rozhraní dopadá obecně polarizovaná vlna, lze ji rozložit na kolmou a rovnoběžnou složku. Při Brewsterově úhlu se rovnoběžná složka neodrazí, a odražená vlna je proto polarizovaná.

ELD uvádí pro nemagnetická dielektrika vztah

$$
\vartheta_{i,\mathrm{BR}}
= \arcsin
\frac{1}{\sqrt{1+\frac{\varepsilon_{r1}}{\varepsilon_{r2}}}}.
$$

Prakticky důležitý je závěr: odraz pro rovnoběžnou polarizaci může být nulový, zatímco činitel prostupu je obecně nenulový pro obě polarizační složky.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=76|ELD s. 76]], [[Elektromagnetická vlna_13_5_2021.pdf#page=77|ELD s. 77]].

## Co umět u zkoušky

- Zapsat rotační Maxwellovy rovnice a vysvětlit vazbu časově proměnného elektrického a magnetického pole.
- Popsat rovinnou harmonickou vlnu pomocí $\alpha$, $\beta$, $\lambda$, $v_f$, $v_s$ a vlnové impedance.
- Vysvětlit význam Poyntingova vektoru.
- Rozlišit lineární, kruhovou a eliptickou polarizaci.
- Popsat geometrii dopadu na rozhraní, kolmou a rovnoběžnou polarizaci.
- Zapsat činitel odrazu a prostupu pro kolmý dopad.
- Vysvětlit kritický úhel, totální odraz a evanescentní vlnu.
- Vysvětlit polarizaci odrazem a význam Brewsterova úhlu.
