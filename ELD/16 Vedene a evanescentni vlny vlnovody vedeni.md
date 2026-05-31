# 16 Vedené a evanescentní vlny, vlnovody a vedení

> Hlavní podklad: [[Elektromagnetická vlna_13_5_2021.pdf]]. Kontrola rozsahu: [[hex_compost.pdf#page=161|HEX s. 161]].

## Vedená a evanescentní vlna

Vedená vlna vzniká tehdy, když geometrie prostředí a okrajové podmínky způsobí, že se elektromagnetická energie šíří převážně podél určitého směru: podél rozhraní, mezi vodivými rovinami, ve vlnovodu nebo na vedení.

ELD ukazuje princip na šikmém dopadu vlny na dobrý vodič. Superpozicí dopadající a odražené vlny vznikne pole, které má:

- ve směru kolmém k rozhraní charakter stojatého vlnění,
- ve směru podél rozhraní charakter postupné vlny.

Evanescentní vlna je vlna, která se šíří podél rozhraní nebo vedené struktury, ale kolmo od rozhraní exponenciálně zaniká. U totálního odrazu má prostupující pole tvar

$$
\hat E_t(x,y,z)
= \hat E_{t0} e^{-jk_2 p x}e^{-k_2 q z}.
$$

Člen $e^{-jk_2 p x}$ popisuje postup podél rozhraní, člen $e^{-k_2 q z}$ zánik amplitudy kolmo do druhého prostředí.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=67|ELD s. 67]], [[Elektromagnetická vlna_13_5_2021.pdf#page=70|ELD s. 70]], [[Elektromagnetická vlna_13_5_2021.pdf#page=87|ELD s. 87]].

## Vlna mezi dvěma vodivými rovinami

Jednoduchý model vedené vlny vznikne přidáním druhé vodivé roviny k poli vedenému nad vodivým rozhraním. Vzdálenost rovin $a$ musí odpovídat celému počtu půlvln stojatého vlnění v příčném směru:

$$
a = m\frac{\lambda_z}{2}.
$$

V příčném směru je stojaté vlnění, v podélném směru postupná vlna. Pro příčnou a podélnou konstantu platí

$$
k_z^2 + k_x^2 = k_1^2.
$$

Pokud je podélná konstanta reálná, vlna se vede. Pokud je imaginární, exponenciálně klesá ve směru vedení a daný mód se nešíří. Kritický kmitočet pro dvě roviny je

$$
f_{\mathrm{krit}(m)}
= \frac{mc}{2a\sqrt{\varepsilon_r}}.
$$

Při kritickém kmitočtu vznikne jen stojaté vlnění; pro vyšší kmitočet vzniká postupná vedená vlna.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=87|ELD s. 87]], [[Elektromagnetická vlna_13_5_2021.pdf#page=88|ELD s. 88]], [[Elektromagnetická vlna_13_5_2021.pdf#page=89|ELD s. 89]].

## Obdélníkový kovový vlnovod a módy

V obdélníkovém kovovém vlnovodu se vlna šíří podélně, zatímco v příčném průřezu vzniká stojaté vlnění. Tvar elektromagnetického pole ve vlnovodu se nazývá mód. Módy se dělí na:

- **TE módy**: transverzálně elektrické, elektrické pole nemá podélnou složku,
- **TM módy**: transverzálně magnetické, magnetické pole nemá podélnou složku,
- **hybridní módy**: kombinace TE a TM, ELD je uvádí stručně u vedení TEM.

Čísla módů $m,n$ udávají počet půlvln stojatého vlnění v příčném směru na hranách vlnovodu. Značení je například $\mathrm{TE}_{10}$ nebo $\mathrm{TM}_{11}$.

Pro příčné konstanty obdélníkového vlnovodu se používá

$$
k_x = \frac{m\pi}{a},
\qquad
k_y = \frac{n\pi}{b}.
$$

Pro konstanty platí

$$
k^2 = k_x^2+k_y^2+k_z^2,
$$

kde $k$ odpovídá vlně ve volném prostoru se stejným prostředím uvnitř vlnovodu. Podélná konstanta $k_z$ má význam fázové konstanty vedené vlny. Pokud je reálná, mód se vede; pokud je imaginární, amplituda v podélném směru klesá a mód se nešíří.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=86|ELD s. 86]], [[Elektromagnetická vlna_13_5_2021.pdf#page=89|ELD s. 89]], [[Elektromagnetická vlna_13_5_2021.pdf#page=90|ELD s. 90]], [[Elektromagnetická vlna_13_5_2021.pdf#page=93|ELD s. 93]], [[Elektromagnetická vlna_13_5_2021.pdf#page=94|ELD s. 94]].

## Podmínka vedení, mezní kmitočet a dominantní mód

Aby se mód ve vlnovodu vedl, musí být pracovní kmitočet větší než kritický kmitočet daného módu. Hranicí je $k_z=0$, kdy nevzniká postupná vlna, ale pouze stojaté vlnění.

Pro obdélníkový vlnovod je kritický kmitočet módu určen rozměry příčného průřezu a čísly $m,n$. ELD formuluje podmínku obecně přes vztah mezi $k$, $k_x$, $k_y$, $k_z$ a uvádí, že pracovní kmitočet musí být větší než kritický.

Podélná vlnová délka, fázová a skupinová rychlost vedené vlny jsou

$$
\lambda_z = \frac{2\pi}{k_z},
\qquad
v_f = \frac{\omega}{k_z},
\qquad
v_s = \frac{d\omega}{dk_z}.
$$

Při kritickém kmitočtu je $k_z=0$, fázová rychlost a podélná vlnová délka formálně rostou k nekonečnu a skupinová rychlost je nulová.

Při obvyklé volbě rozměrů $a>b$ má nejnižší kritický kmitočet mód $\mathrm{TE}_{10}$. Nazývá se dominantní mód. V praxi se vlnovod často provozuje v pásmu, kde existuje jen dominantní mód a vyšší módy ještě nejsou vedeny.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=94|ELD s. 94]], [[Elektromagnetická vlna_13_5_2021.pdf#page=95|ELD s. 95]], [[Elektromagnetická vlna_13_5_2021.pdf#page=96|ELD s. 96]], [[Elektromagnetická vlna_13_5_2021.pdf#page=97|ELD s. 97]].

## Impedance ve vlnovodu a přenos výkonu

Pro vlnovod se zavádí impedance vedeného módu jako vztah mezi příslušnými příčnými složkami elektrického a magnetického pole. ELD odvozuje vztahy zvlášť pro vlny typu TM a TE. Smysl je stejný jako u rovinné vlny: impedance říká, jaký je poměr mezi elektrickou a magnetickou složkou daného módu.

Výkon přenášený vlnovodem se počítá z Poyntingova vektoru přes příčný průřez:

$$
P = \int_S \mathbf S_\mathrm{stř}\cdot d\mathbf S,
\qquad
\mathbf S_\mathrm{stř}
= \frac{1}{2}\operatorname{Re}(\hat{\mathbf E}\times \hat{\mathbf H}^{*}).
$$

U dominantního módu $\mathrm{TE}_{10}$ ELD uvádí samostatnou část pro výkon. Pro zkoušku je důležité vědět, že výkon teče v podélném směru vlnovodu a že rozložení pole v příčném průřezu se musí při integraci respektovat.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=98|ELD s. 98]], [[Elektromagnetická vlna_13_5_2021.pdf#page=102|ELD s. 102]], [[Elektromagnetická vlna_13_5_2021.pdf#page=106|ELD s. 106]].

## Vlna TEM na vedení

Na symetrickém homogenním dvouvodičovém vedení, například na koaxiálním kabelu nebo symetrické dvojlince, může vzniknout vlna TEM. Znamená to:

- elektrické pole je kolmé na směr šíření,
- magnetické pole je kolmé na směr šíření,
- elektromagnetické pole nemá podélnou složku.

Na rozdíl od kovového dutého vlnovodu vede symetrické dvouvodičové vedení mód TEM od nulového kmitočtu. U koaxiálního vedení se od určitého kritického kmitočtu mohou přidat vyšší módy TE a TM.

Homogenní vedení se popisuje parametry na jednotku délky:

- $R$: podélný činný odpor,
- $L$: podélná indukčnost,
- $G$: příčná vodivost,
- $C$: příčná kapacita.

Pro fázory napětí a proudu se používá konstanta šíření $\hat\gamma$ a charakteristická impedance

$$
\hat Z_0
= \sqrt{\frac{R+j\omega L}{G+j\omega C}}.
$$

Pro bezeztrátové vedení $R=0$, $G=0$:

$$
Z_0 = \sqrt{\frac{L}{C}}.
$$

ELD přímo porovnává charakteristickou impedanci vedení s vlnovou impedancí prostředí.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=108|ELD s. 108]], [[Elektromagnetická vlna_13_5_2021.pdf#page=109|ELD s. 109]], [[Elektromagnetická vlna_13_5_2021.pdf#page=114|ELD s. 114]].

## Odraz, stojaté vlnění a transformace impedance na vedení

Na vedení se obecně skládá postupná vlna směrem k zátěži a odražená vlna od zátěže. Pokud je zátěž rovna charakteristické impedanci, vedení je přizpůsobené a činitel odrazu je nulový:

$$
\hat Z_K = \hat Z_0
\quad \Rightarrow \quad
\hat R = 0.
$$

Při nepřizpůsobení vzniká stojaté vlnění. Komplexní činitel odrazu je svázán s impedancí; Smithův diagram je grafický nástroj, který tento vztah a transformaci impedance podél vedení zobrazuje.

Pro vedení zakončené nakrátko se vlna úplně odrazí a na konci vznikne uzel napětí. Pro rozpojené vedení se vlna také úplně odrazí, ale na konci vznikne kmitna napětí a uzel proudu. Vlastnosti bezeztrátového vedení se opakují s polovinou vlnové délky.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=114|ELD s. 114]], [[Elektromagnetická vlna_13_5_2021.pdf#page=119|ELD s. 119]], [[Elektromagnetická vlna_13_5_2021.pdf#page=122|ELD s. 122]], [[Elektromagnetická vlna_13_5_2021.pdf#page=129|ELD s. 129]], [[Elektromagnetická vlna_13_5_2021.pdf#page=130|ELD s. 130]], [[Elektromagnetická vlna_13_5_2021.pdf#page=133|ELD s. 133]].

## Zdroje vln a pole zářičů

> [!todo] DOPLNIT Z JINÉHO PODKLADU ELD  
> Otázka vyžaduje zdroje vln, elementární zářiče a blízké, přechodné a vzdálené pole zářičů. V dodaném souboru [[Elektromagnetická vlna_13_5_2021.pdf]] jsem našel pouze úvodní zmínku harmonicky kmitajícího elektrického dipólu jako intuitivního zdroje vlny, ne samostatný výklad elementárního zářiče ani oblastí pole. `hex_compost.pdf` tuto část očekává kontrolně, ale faktické vztahy nejsou v předmětovém PDF doložené.

**Zdroj:** [[Elektromagnetická vlna_13_5_2021.pdf#page=4|ELD s. 4]], kontrolně [[hex_compost.pdf#page=161|HEX s. 161]].

## Vlna v anizotropním prostředí

> [!todo] DOPLNIT Z JINÉHO PODKLADU ELD  
> V dodaném ELD PDF jsem nenašel samostatnou kapitolu o vlně v anizotropním prostředí. Pro úplnou odpověď bude potřeba doplnit zdroj, který pokrývá tenzorovou permitivitu/permeabilitu a závislost směru $\mathbf D$ na $\mathbf E$.

**Zdroj:** kontrolně [[hex_compost.pdf#page=161|HEX s. 161]].

## Co umět u zkoušky

- Vysvětlit rozdíl mezi postupnou, stojatou, vedenou a evanescentní vlnou.
- Popsat vznik vedené vlny superpozicí dopadající a odražené vlny u vodivého rozhraní.
- Definovat módy TE, TM a TEM.
- Vysvětlit význam módových čísel $m,n$ v obdélníkovém vlnovodu.
- Zapsat podmínku vedení přes reálnost $k_z$ a kritický kmitočet.
- Popsat dominantní mód $\mathrm{TE}_{10}$.
- Vysvětlit fázovou a skupinovou rychlost ve vlnovodu.
- Popsat charakteristickou impedanci vedení, odraz, přizpůsobení a stojaté vlnění.
