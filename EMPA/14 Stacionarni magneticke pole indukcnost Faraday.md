# 14 Stacionární magnetické pole, indukčnost, Faradayův zákon

> Hlavní podklad: [[empa_complete_edition.pdf]]. Kontrola rozsahu: [[hex_compost.pdf#page=148|HEX s. 148]].

## Stacionární magnetické pole a jeho zdroje

Magnetické pole je buzeno pohybem částic s nábojem. V technických úlohách je hlavním zdrojem kondukční proud, tedy pohyb volných nosičů náboje ve vodiči. V magnetických materiálech se navíc uplatňují vázané proudy, které lze modelovat jako soubor elementárních proudových smyček v materiálu.

Stacionární magnetické pole je pole, jehož magnetická indukce a magnetický tok se v čase nemění. Typicky vzniká v okolí vodičů se stejnosměrným proudem nebo u permanentních magnetů. Magnetická síla působí jen na pohybující se náboje:

$$
\mathbf F = Q(\mathbf v \times \mathbf B).
$$

Magnetická indukce $\mathbf B$ má jednotku tesla. Pro element vodiče protékaný proudem $I$ v magnetickém poli platí

$$
d\mathbf F = I(d\mathbf l \times \mathbf B).
$$

Celková síla na vodič nebo smyčku se získá integrací po proudové dráze:

$$
\mathbf F = I \int_l d\mathbf l \times \mathbf B.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=40|EMPA s. 40]], [[empa_complete_edition.pdf#page=41|EMPA s. 41]], [[empa_complete_edition.pdf#page=43|EMPA s. 43]].

## Magnetické pole proudového elementu a Biotův-Savartův zákon

Pohybující se bodový náboj budí magnetickou indukci, jejíž směr je dán vektorovým součinem rychlosti náboje a směru k pozorovacímu bodu:

$$
\mathbf B
= \frac{\mu_0 Q}{4\pi r^2}
(\mathbf v \times \mathbf r_0).
$$

Pro proudový element $I\,d\mathbf l$ přejde vztah na diferenciální tvar Biotova-Savartova zákona:

$$
d\mathbf B
= \frac{\mu_0 I}{4\pi}
\frac{d\mathbf l \times \mathbf r_0}{r^2}.
$$

Výsledné pole tenké proudové smyčky je integrál přes celou smyčku:

$$
\mathbf B
= \frac{\mu_0 I}{4\pi}
\oint_l \frac{d\mathbf l \times \mathbf r_0}{r^2}.
$$

Tento vztah se používá hlavně tehdy, když není k dispozici jednoduchá symetrie pro Ampérův zákon.

**Zdroj:** [[empa_complete_edition.pdf#page=42|EMPA s. 42]], [[empa_complete_edition.pdf#page=43|EMPA s. 43]].

## Ampérův zákon

Ampérův zákon celkového proudu říká, že cirkulace magnetické indukce po uzavřené křivce je úměrná celkovému proudu procházejícímu plochou ohraničenou touto křivkou:

$$
\oint_l \mathbf B \cdot d\mathbf l
= \mu_0 I_\mathrm{celk}
= \mu_0 \int_S \mathbf J_\mathrm{celk}\cdot d\mathbf S.
$$

Pomocí Stokesovy věty dostaneme diferenciální tvar

$$
\operatorname{rot}\mathbf B
= \mu_0 \mathbf J_\mathrm{celk}
= \mu_0(\mathbf J_0 + \mathbf J_v),
$$

kde $\mathbf J_0$ je hustota kondukčního proudu a $\mathbf J_v$ hustota vázaného proudu.

Po zavedení intenzity magnetického pole $\mathbf H$ se v lineárním prostředí používá vztah

$$
\mathbf B = \mu_0\mu_r \mathbf H = \mu \mathbf H.
$$

Ampérův zákon pro volné proudy má tvar

$$
\oint_l \mathbf H \cdot d\mathbf l = I_0,
\qquad
\operatorname{rot}\mathbf H = \mathbf J_0.
$$

Pro dlouhý přímý vodič s proudem $I$ a kruhovou Ampérovou křivkou poloměru $r$:

$$
H_\varphi 2\pi r = I,
\qquad
H_\varphi = \frac{I}{2\pi r},
\qquad
B_\varphi = \mu\frac{I}{2\pi r}.
$$

U válcového vodiče a koaxiálního kabelu se stejný postup aplikuje po částech podle toho, jaký proud je uzavřen zvolenou Ampérovou křivkou. EMPA v této části uvádí princip a obrázky, detailní vztahy pro některé geometrie odkazuje na příklady.

**Zdroj:** [[empa_complete_edition.pdf#page=44|EMPA s. 44]], [[empa_complete_edition.pdf#page=45|EMPA s. 45]], [[empa_complete_edition.pdf#page=49|EMPA s. 49]], [[empa_complete_edition.pdf#page=52|EMPA s. 52]], [[empa_complete_edition.pdf#page=53|EMPA s. 53]].

## Magnetický tok, vírový charakter pole a rozhraní

Magnetický indukční tok přes plochu $S$ je

$$
\Phi = \int_S \mathbf B \cdot d\mathbf S.
$$

Protože magnetické indukční čáry netečou ze zdrojů ani do zániků, ale uzavírají se, je tok uzavřenou plochou nulový:

$$
\oint_S \mathbf B \cdot d\mathbf S = 0.
$$

Na rozhraní magnetik z toho plyne spojitost normálové složky magnetické indukce:

$$
B_{1n}=B_{2n}.
$$

Z Ampérova zákona pro $\mathbf H$ plyne pro rozhraní bez plošného volného proudu spojitost tečné složky intenzity magnetického pole:

$$
H_{1t}=H_{2t}.
$$

Pokud je na rozhraní plošný proud, rozdíl tečných složek $\mathbf H$ odpovídá tomuto plošnému proudu.

**Zdroj:** [[empa_complete_edition.pdf#page=46|EMPA s. 46]], [[empa_complete_edition.pdf#page=64|EMPA s. 64]], [[empa_complete_edition.pdf#page=65|EMPA s. 65]].

## Magnetizace a materiály

Magnetizace $\mathbf M$ je objemová hustota magnetického dipólového momentu. V materiálu umožňuje popsat vázané proudy a reakci prostředí na magnetické pole.

Obecný vztah mezi magnetickou indukcí, intenzitou magnetického pole a magnetizací je

$$
\mathbf B = \mu_0(\mathbf H + \mathbf M).
$$

V lineárním izotropním prostředí:

$$
\mathbf M = \chi_m \mathbf H,
\qquad
\mathbf B = \mu_0(1+\chi_m)\mathbf H
= \mu_0\mu_r\mathbf H.
$$

U feromagnetik není vztah mezi $\mathbf B$ a $\mathbf H$ obecně lineární. Popisuje ho magnetizační charakteristika a hysterezní smyčka. Relativní permeabilita pak není konstanta nezávislá na pracovním bodě.

**Zdroj:** [[empa_complete_edition.pdf#page=52|EMPA s. 52]], [[empa_complete_edition.pdf#page=53|EMPA s. 53]], [[empa_complete_edition.pdf#page=54|EMPA s. 54]], [[empa_complete_edition.pdf#page=55|EMPA s. 55]], [[empa_complete_edition.pdf#page=56|EMPA s. 56]].

## Energie v magnetickém poli

U obecně nelineárního induktoru je energie dána plochou pod vhodnou částí magnetizační charakteristiky:

$$
W_m = \int_0^\Phi i\,d\Phi.
$$

Pro lineární induktor s konstantní indukčností $L$:

$$
\Phi = L I,
\qquad
W_m
= \int_0^\Phi i\,d\Phi
= \frac{1}{2}LI^2
= \frac{1}{2}\Phi I.
$$

Objemová hustota energie magnetického pole v lineárním prostředí je

$$
w_m = \frac{1}{2}\mathbf B \cdot \mathbf H.
$$

Celková energie v objemu je

$$
W_m = \int_V w_m\,dV.
$$

U feromagnetik souvisí hysterézní ztráty s plochou hysterezní smyčky: energie dodaná při jednom cyklu přemagnetování se nevrátí celá zpět, rozdíl se ztrácí v materiálu.

**Zdroj:** [[empa_complete_edition.pdf#page=57|EMPA s. 57]], [[empa_complete_edition.pdf#page=58|EMPA s. 58]], [[empa_complete_edition.pdf#page=59|EMPA s. 59]].

## Vlastní a vzájemná indukčnost

Vlastní indukčnost podle statické definice je podíl spřaženého magnetického toku a proudu:

$$
L_\mathrm{stat} = \frac{\Phi_\mathrm{celk}}{I}.
$$

U cívky s $N$ závity je spřažený tok součet toků jednotlivými závity:

$$
\Phi_\mathrm{celk} = \sum_i \Phi_i.
$$

Pokud všemi závity prochází stejný tok $\Phi$, pak $\Phi_\mathrm{celk}=N\Phi$.

Vzájemná indukčnost dvou cívek je dána tokem vybuzeným proudem v první cívce a spřaženým s druhou cívkou:

$$
M_{12} = \frac{N_2\Phi_{12}}{I_1}.
$$

Pro nelineární magnetický obvod je nutné rozlišovat tři definice:

$$
L_\mathrm{stat} = \frac{\Phi_\mathrm{celk}}{I},
\qquad
L_\mathrm{dyn} = \frac{d\Phi_\mathrm{celk}}{di},
\qquad
L_\mathrm{en} = \frac{2W_m}{I^2}.
$$

V lineárním případě se tyto definice shodují. V nelineárním feromagnetickém obvodu mohou dávat různé hodnoty pro stejný pracovní bod.

**Zdroj:** [[empa_complete_edition.pdf#page=49|EMPA s. 49]], [[empa_complete_edition.pdf#page=50|EMPA s. 50]], [[empa_complete_edition.pdf#page=59|EMPA s. 59]], [[empa_complete_edition.pdf#page=60|EMPA s. 60]].

## Indukčnost základních uspořádání

Pro výpočet indukčnosti se používají dvě rovnocenné cesty:

1. **Statická definice:** spočítat magnetické pole, z něj tok $\Phi_\mathrm{celk}$ a použít $L=\Phi_\mathrm{celk}/I$.
2. **Energetická definice:** spočítat energii pole $W_m$ a použít $L=2W_m/I^2$.

EMPA výslovně uvádí jako očekávané geometrie vnější indukčnost symetrického dvouvodičového vedení, vnější indukčnost koaxiálního kabelu, vnitřní indukčnost dlouhého válcového vodiče a vzájemnou indukčnost vodiče se smyčkou, ale v textu u těchto vztahů odkazuje na příklady.

Pro orientaci:

- vnitřní indukčnost plného dlouhého válcového vodiče při rovnoměrném rozložení proudu se určuje z energie pole uvnitř vodiče,
- vnější indukčnost koaxiálního kabelu se určuje z pole v dielektriku mezi vodiči,
- u dvouvodičového vedení se integruje tok vytvořený proudem jednoho vodiče přes plochu mezi vodiči.

> [!todo] DOPLNIT Z PŘÍKLADŮ EMPA  
> Do poznámky přidat konkrétní vztahy pro indukčnost na jednotku délky dvouvodičového vedení a koaxiálního kabelu, pokud budou dostupné příklady MG/35 nebo odpovídající cvičení.

**Zdroj:** [[empa_complete_edition.pdf#page=61|EMPA s. 61]], [[empa_complete_edition.pdf#page=62|EMPA s. 62]].

## Magnetické obvody

Magnetomotorické napětí cívky je

$$
U_m = NI.
$$

Reluktance magnetického obvodu vyjadřuje odpor proti průchodu magnetického toku:

$$
R_m = \sum_i R_{mi},
\qquad
R_{mi} = \frac{l_i}{\mu_i S_i}.
$$

Hopkinsonův zákon je magnetická analogie Ohmova zákona:

$$
\Phi = \frac{U_m}{R_m}.
$$

Pro cívku na magnetickém obvodu pak při lineárním chování:

$$
L = \frac{N\Phi}{I}
= \frac{N^2}{R_m}.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=67|EMPA s. 67]], [[empa_complete_edition.pdf#page=68|EMPA s. 68]], [[empa_complete_edition.pdf#page=69|EMPA s. 69]].

## Faradayův indukční zákon a Lenzovo pravidlo

Faradayův indukční zákon říká, že časová změna magnetického toku procházejícího plochou ohraničenou vodivou smyčkou indukuje elektromotorické napětí:

$$
u_i = -\frac{d\Phi}{dt}.
$$

U cívky s více závity se používá spřažený tok:

$$
u_i = -\frac{d\Phi_\mathrm{celk}}{dt}.
$$

Pokud všemi závity prochází stejný tok $\Phi$, pak

$$
u_i = -N\frac{d\Phi}{dt}.
$$

Záporné znaménko vyjadřuje Lenzovo pravidlo: indukované napětí a proud mají takový směr, že svými účinky působí proti změně magnetického toku, která je vyvolala.

U pohybujícího se vodiče délky $l$ v homogenním magnetickém poli, při rychlosti $v$ kolmé na vodič i na $\mathbf B$, platí pro velikost indukovaného napětí:

$$
u_i = Bvl.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=69|EMPA s. 69]], [[empa_complete_edition.pdf#page=70|EMPA s. 70]], [[empa_complete_edition.pdf#page=71|EMPA s. 71]].

## Co umět u zkoušky

- Vysvětlit, že zdrojem magnetického pole jsou pohybující se náboje: kondukční a vázané proudy.
- Zapsat Lorentzovu magnetickou sílu a sílu na proudový element.
- Použít Biotův-Savartův zákon pro proudový element nebo smyčku.
- Použít Ampérův zákon pro symetrické vodiče a umět přejít mezi integrálním a diferenciálním tvarem.
- Rozlišit $\mathbf B$, $\mathbf H$, $\mathbf M$, $\mu$, $\mu_r$.
- Zapsat energii magnetického pole a hustotu energie.
- Definovat vlastní, vzájemnou, statickou, dynamickou a energetickou indukčnost.
- Vysvětlit Faradayův zákon, Lenzovo pravidlo a indukované napětí v pohybujícím se vodiči.
