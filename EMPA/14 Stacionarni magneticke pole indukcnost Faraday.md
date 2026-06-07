# 14 Stacionární magnetické pole, indukčnost, Faradayův zákon

> Hlavní podklad: [[empa_complete_edition.pdf]]. Znění okruhu: [[SZZ - Odborné okruhy|odborný okruh 14]].

## Stacionární magnetické pole

Stacionární magnetické pole je magnetické pole, jehož veličiny se v čase nemění. Vzniká kolem vodičů se stejnosměrným proudem, v proudových smyčkách, cívkách a permanentních magnetech.

Zdrojem magnetického pole jsou pohybující se náboje. Na pohybující se náboj působí magnetická síla

$$
\mathbf F=Q(\mathbf v\times\mathbf B).
$$

Na proudový element působí

$$
d\mathbf F=I(d\mathbf l\times\mathbf B),
$$

a celková síla na vodič je

$$
\mathbf F=I\int_l d\mathbf l\times\mathbf B.
$$

Magnetický indukční tok plochou $S$ je

$$
\Phi=\int_S\mathbf B\cdot d\mathbf S.
$$

Protože magnetické indukční čáry jsou uzavřené,

$$
\oint_S\mathbf B\cdot d\mathbf S=0.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=40|EMPA s. 40]], [[empa_complete_edition.pdf#page=41|EMPA s. 41]], [[empa_complete_edition.pdf#page=43|EMPA s. 43]], [[empa_complete_edition.pdf#page=46|EMPA s. 46]].

## Biotův-Savartův zákon

Biotův-Savartův zákon udává příspěvek proudového elementu $I\,d\mathbf l$ k magnetické indukci v pozorovacím bodě:

$$
d\mathbf B
=\frac{\mu_0 I}{4\pi}
\frac{d\mathbf l\times\mathbf r_0}{r^2}.
$$

Pro tenkou proudovou smyčku se integruje přes celou dráhu proudu:

$$
\mathbf B
=\frac{\mu_0 I}{4\pi}
\oint_l\frac{d\mathbf l\times\mathbf r_0}{r^2}.
$$

Používá se hlavně tam, kde nelze snadno využít symetrii pro Ampérův zákon, například pro konečné vodiče a proudové smyčky.

**Zdroj:** [[empa_complete_edition.pdf#page=42|EMPA s. 42]], [[empa_complete_edition.pdf#page=43|EMPA s. 43]].

## Ampérův zákon

Ampérův zákon celkového proudu říká, že cirkulace magnetické indukce po uzavřené křivce je úměrná celkovému proudu procházejícímu plochou ohraničenou touto křivkou:

$$
\oint_l\mathbf B\cdot d\mathbf l
=\mu_0 I_\mathrm{celk}.
$$

Po zavedení intenzity magnetického pole $\mathbf H$ se pro volné proudy používá tvar

$$
\oint_l\mathbf H\cdot d\mathbf l=I_0.
$$

Diferenciální tvar je

$$
\operatorname{rot}\mathbf H=\mathbf J_0.
$$

Materiálový vztah v lineárním izotropním prostředí je

$$
\mathbf B=\mu_0\mu_r\mathbf H=\mu\mathbf H.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=44|EMPA s. 44]], [[empa_complete_edition.pdf#page=45|EMPA s. 45]], [[empa_complete_edition.pdf#page=49|EMPA s. 49]], [[empa_complete_edition.pdf#page=52|EMPA s. 52]].

## Aplikace Ampérova zákona pro výpočet magnetického pole

Ampérův zákon je výpočetně silný u soustav s vysokou symetrií. Zvolí se uzavřená Ampérova křivka tak, aby $\mathbf H$ bylo tečné ke křivce a mělo na ní konstantní velikost.

Pro dlouhý tenký přímý vodič s proudem $I$:

$$
H_\varphi 2\pi r=I,
\qquad
H_\varphi=\frac{I}{2\pi r},
\qquad
B_\varphi=\mu\frac{I}{2\pi r}.
$$

U dlouhého válcového vodiče se postupuje po částech podle toho, jaký proud je uzavřen Ampérovou křivkou. U koaxiálního kabelu je pole soustředěno hlavně v prostoru mezi vodiči; mimo ideální koaxiální dvojici se proudy opačného směru vyruší.

Na rozhraní magnetik z $\operatorname{div}\mathbf B=0$ plyne spojitost normálové složky $\mathbf B$:

$$
B_{1n}=B_{2n}.
$$

Z Ampérova zákona pro $\mathbf H$ plyne při nulovém plošném volném proudu spojitost tečné složky:

$$
H_{1t}=H_{2t}.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=45|EMPA s. 45]], [[empa_complete_edition.pdf#page=46|EMPA s. 46]], [[empa_complete_edition.pdf#page=53|EMPA s. 53]], [[empa_complete_edition.pdf#page=64|EMPA s. 64]], [[empa_complete_edition.pdf#page=65|EMPA s. 65]].

## Energie v magnetickém poli

Energie magnetického pole lineárního induktoru je

$$
W_m=\frac12LI^2=\frac12\Phi I.
$$

Obecně lze energii vyjádřit integrálem

$$
W_m=\int_0^\Phi i\,d\Phi.
$$

U feromagnetik závisí energie na magnetizační charakteristice a při cyklickém přemagnetování vznikají hysterezní ztráty.

**Zdroj:** [[empa_complete_edition.pdf#page=57|EMPA s. 57]], [[empa_complete_edition.pdf#page=58|EMPA s. 58]].

## Objemová hustota energie

Objemová hustota energie magnetického pole v lineárním prostředí je

$$
w_m=\frac12\mathbf B\cdot\mathbf H.
$$

Celková energie v objemu $V$ je

$$
W_m=\int_Vw_m\,dV.
$$

Tento vztah se používá i pro výpočet indukčnosti energetickou metodou: nejdřív se spočítá energie pole z rozložení $\mathbf B$ a $\mathbf H$, potom se použije

$$
L=\frac{2W_m}{I^2}.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=58|EMPA s. 58]], [[empa_complete_edition.pdf#page=59|EMPA s. 59]].

## Faradayův indukční zákon

Faradayův indukční zákon říká, že časová změna magnetického toku procházejícího plochou ohraničenou vodivou smyčkou indukuje elektromotorické napětí:

$$
u_i=-\frac{d\Phi}{dt}.
$$

U cívky s více závity se používá spřažený tok

$$
u_i=-\frac{d\Phi_\mathrm{celk}}{dt}.
$$

Pokud všemi $N$ závity prochází stejný tok $\Phi$,

$$
u_i=-N\frac{d\Phi}{dt}.
$$

Záporné znaménko je Lenzovo pravidlo: indukované napětí a proud působí proti změně toku, která je vyvolala.

**Zdroj:** [[empa_complete_edition.pdf#page=69|EMPA s. 69]], [[empa_complete_edition.pdf#page=70|EMPA s. 70]].

## Indukovaná napětí

Indukované napětí může vzniknout změnou magnetického pole v čase, změnou plochy smyčky, změnou orientace smyčky nebo pohybem vodiče v magnetickém poli.

Pro přímý vodič délky $l$ pohybující se rychlostí $v$ kolmo na homogenní magnetické pole $\mathbf B$ i na směr vodiče platí pro velikost pohybového indukovaného napětí

$$
u_i=Bvl.
$$

Obecně je důležité sledovat orientaci křivky, orientaci plochy a znaménkovou konvenci. Fyzikální směr určuje Lenzovo pravidlo.

**Zdroj:** [[empa_complete_edition.pdf#page=70|EMPA s. 70]], [[empa_complete_edition.pdf#page=71|EMPA s. 71]].

## Vlastní a vzájemná indukčnost

Vlastní indukčnost podle statické definice je podíl spřaženého magnetického toku a proudu:

$$
L_\mathrm{stat}=\frac{\Phi_\mathrm{celk}}{I}.
$$

U cívky s $N$ závity je spřažený tok součet toků jednotlivými závity:

$$
\Phi_\mathrm{celk}=\sum_i\Phi_i.
$$

Pokud všemi závity prochází stejný tok,

$$
\Phi_\mathrm{celk}=N\Phi.
$$

Vzájemná indukčnost dvou cívek je dána tokem vybuzeným proudem v první cívce a spřaženým s druhou cívkou:

$$
M_{12}=\frac{N_2\Phi_{12}}{I_1}.
$$

U nelineárního magnetického obvodu je nutné rozlišovat statickou, dynamickou a energetickou indukčnost:

$$
L_\mathrm{stat}=\frac{\Phi_\mathrm{celk}}{I},
\qquad
L_\mathrm{dyn}=\frac{d\Phi_\mathrm{celk}}{di},
\qquad
L_\mathrm{en}=\frac{2W_m}{I^2}.
$$

V lineárním případě se tyto definice shodují.

**Zdroj:** [[empa_complete_edition.pdf#page=49|EMPA s. 49]], [[empa_complete_edition.pdf#page=50|EMPA s. 50]], [[empa_complete_edition.pdf#page=59|EMPA s. 59]], [[empa_complete_edition.pdf#page=60|EMPA s. 60]].

## Výpočet indukčnosti pro základní geometrické uspořádání proudovodičů

Indukčnost se počítá dvěma rovnocennými cestami:

- **staticky**: spočítat magnetické pole, tok a použít $L=\Phi_\mathrm{celk}/I$,
- **energeticky**: spočítat energii pole a použít $L=2W_m/I^2$.

Pro dlouhou cívku délky $l$, průřezu $S$, $N$ závitů a lineární permeabilitu $\mu$ platí přibližně

$$
L=\mu\frac{N^2S}{l}.
$$

Pro magnetický obvod s reluktancí

$$
R_m=\sum_i\frac{l_i}{\mu_iS_i}
$$

platí Hopkinsonův zákon

$$
\Phi=\frac{NI}{R_m},
$$

a indukčnost cívky na lineárním magnetickém obvodu

$$
L=\frac{N^2}{R_m}.
$$

Vnější indukčnost koaxiálního kabelu na jednotku délky, pro proudy opačného směru a prostor pole mezi poloměry $a$ a $b$, je standardně

$$
L'=\frac{\mu}{2\pi}\ln\frac{b}{a}.
$$

EMPA u podrobných vztahů pro dvouvodičové vedení, koaxiální kabel, vnitřní indukčnost válcového vodiče a vzájemnou indukčnost vodiče se smyčkou odkazuje na řešené příklady MG/35, MG/37, MG/50 a MG/51; v hlavním PDF nejsou tyto odvozené vztahy rozepsané.

**Zdroj:** [[empa_complete_edition.pdf#page=61|EMPA s. 61]], [[empa_complete_edition.pdf#page=62|EMPA s. 62]], [[empa_complete_edition.pdf#page=67|EMPA s. 67]], [[empa_complete_edition.pdf#page=68|EMPA s. 68]], [[empa_complete_edition.pdf#page=69|EMPA s. 69]].

## Co umět u zkoušky

- Popsat zdroje a vlastnosti stacionárního magnetického pole.
- Zapsat Biotův-Savartův zákon a vědět, kdy ho použít.
- Zapsat Ampérův zákon v integrálním i diferenciálním tvaru.
- Vypočítat pole dlouhého přímého vodiče a vysvětlit postup pro válec nebo koaxiál.
- Zapsat energii a objemovou hustotu energie magnetického pole.
- Vysvětlit Faradayův zákon, Lenzovo pravidlo a indukované napětí $u_i=Bvl$.
- Definovat vlastní, vzájemnou, statickou, dynamickou a energetickou indukčnost.
- Popsat statickou a energetickou metodu výpočtu indukčnosti základních proudovodičů.
