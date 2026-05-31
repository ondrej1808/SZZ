# 13 Elektrické a magnetické pole, elektrostatika, kapacita

> Hlavní podklad: [[empa_complete_edition.pdf]]. Kontrola rozsahu: [[hex_compost.pdf#page=146|HEX s. 146]].

## Klasifikace polí

Elektromagnetické pole popisuje silové působení mezi částicemi s nábojem. Pro přehled se často rozlišují jednodušší případy:

- **elektrostatické pole**: elektrické pole buzené nepohyblivými volnými náboji,
- **stacionární proudové pole**: pole ustáleně se pohybujících nábojů,
- **stacionární magnetické pole**: magnetické pole buzené časově stálými proudy,
- **nestacionární elektromagnetické pole**: časově proměnné elektrické a magnetické pole, kde se obě složky navzájem vážou.

Elektrické pole má v elektrostatice potenciálový charakter. Jeho intenzita je dána záporným gradientem potenciálu:

$$
\mathbf E = -\nabla \varphi .
$$

Magnetické pole je naopak vírové; magnetické indukční čáry se neukončují na magnetických nábojích, ale tvoří uzavřené víry kolem proudů. Souvisí s tím nulový tok magnetické indukce uzavřenou plochou:

$$
\oint_S \mathbf B \cdot d\mathbf S = 0.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=6|EMPA s. 6]], [[empa_complete_edition.pdf#page=8|EMPA s. 8]], [[empa_complete_edition.pdf#page=46|EMPA s. 46]], kontrolně [[hex_compost.pdf#page=146|HEX s. 146]].

## Náboj, elektrická síla a intenzita pole

Elektrický náboj je vlastnost částice, která určuje její elektrické silové působení. Může být kladný nebo záporný, náboje stejného znaménka se odpuzují a opačného znaménka se přitahují. Náboj se zachovává: nevzniká ani nezaniká, pouze se přemisťuje nebo přeskupuje. Elementární náboj má velikost přibližně $e = 1{,}6 \cdot 10^{-19}\,\mathrm C$.

Silové působení elektrického pole na náboj $Q$ se zapisuje

$$
\mathbf F = Q \mathbf E.
$$

Pro dva bodové náboje platí Coulombův zákon. Ve vakuu:

$$
\mathbf F_{12}
= \frac{1}{4\pi \varepsilon_0}
\frac{Q_1 Q_2}{r^2}\,\mathbf r_0,
$$

kde $\mathbf r_0$ je jednotkový vektor ve směru od jednoho náboje k druhému. Intenzita pole bodového náboje $Q$ je tedy

$$
\mathbf E
= \frac{1}{4\pi \varepsilon}
\frac{Q}{r^2}\,\mathbf r_0.
$$

U více nábojů se používá princip superpozice: výsledné pole je vektorovým součtem příspěvků jednotlivých nábojů.

**Zdroj:** [[empa_complete_edition.pdf#page=7|EMPA s. 7]], [[empa_complete_edition.pdf#page=10|EMPA s. 10]], [[empa_complete_edition.pdf#page=11|EMPA s. 11]], kontrolně [[hex_compost.pdf#page=146|HEX s. 146]].

## Vodiče, dielektrika a základní vektorové veličiny

Ve vodiči jsou volné nosiče náboje, typicky valenční elektrony, které se mohou v materiálu přesouvat. V elektrostatické rovnováze je uvnitř dobrého vodiče elektrické pole nulové a volný náboj se rozmístí na povrchu vodiče.

Dielektrikum neobsahuje volné nosiče v takové míře jako vodič. V elektrickém poli se polarizuje: kladné a záporné vázané náboje se nepatrně posunou proti sobě a vznikají elektrické dipóly. Elektrický dipólový moment je

$$
\mathbf p = q \mathbf d,
$$

kde $\mathbf d$ směřuje od záporného ke kladnému náboji. Polarizace $\mathbf P$ je objemová hustota dipólového momentu:

$$
\mathbf P = \lim_{\Delta V \to 0}\frac{\sum_{\Delta V}\mathbf p}{\Delta V}.
$$

Elektrická indukce $\mathbf D$ zahrnuje vliv volných nábojů a polarizace:

$$
\mathbf D = \varepsilon_0 \mathbf E + \mathbf P.
$$

V lineárním izotropním dielektriku:

$$
\mathbf P = \varepsilon_0 \chi_e \mathbf E,
\qquad
\mathbf D = \varepsilon_0 \varepsilon_r \mathbf E
= \varepsilon \mathbf E.
$$

Elektrický indukční tok přes plochu $S$ je

$$
\Psi = \int_S \mathbf D \cdot d\mathbf S.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=8|EMPA s. 8]], [[empa_complete_edition.pdf#page=15|EMPA s. 15]], [[empa_complete_edition.pdf#page=16|EMPA s. 16]], [[empa_complete_edition.pdf#page=17|EMPA s. 17]], [[empa_complete_edition.pdf#page=18|EMPA s. 18]].

## Gaussova věta elektrostatiky

Gaussova věta elektrostatiky říká, že tok elektrické intenzity uzavřenou plochou je úměrný celkovému náboji uvnitř této plochy:

$$
\oint_S \mathbf E \cdot d\mathbf S
= \frac{Q_\mathrm{celk}}{\varepsilon}.
$$

V prostředí s dielektriky je praktičtější zápis pomocí elektrické indukce, protože $\mathbf D$ je vázána na volné náboje:

$$
\oint_S \mathbf D \cdot d\mathbf S = Q_0.
$$

Diferenciální tvar je

$$
\operatorname{div}\mathbf D = \rho_0.
$$

Pro intenzitu elektrického pole lze v homogenním prostředí psát

$$
\operatorname{div}\mathbf E = \frac{\rho}{\varepsilon}.
$$

Gaussova věta je výpočetně silná u symetrických úloh: koule, nekonečná rovina, dlouhý válec, koaxiální uspořádání. Volí se taková Gaussova plocha, na níž je velikost pole konstantní a směr pole je buď normálový, nebo tečný tak, aby se integrál zjednodušil.

**Zdroj:** [[empa_complete_edition.pdf#page=12|EMPA s. 12]], [[empa_complete_edition.pdf#page=14|EMPA s. 14]], [[empa_complete_edition.pdf#page=16|EMPA s. 16]], [[empa_complete_edition.pdf#page=17|EMPA s. 17]].

## Potenciál, napětí a okrajové podmínky

Napětí mezi body $A$ a $B$ je křivkový integrál intenzity elektrického pole:

$$
U_{AB}
= \int_A^B \mathbf E \cdot d\mathbf l
= \varphi_A - \varphi_B.
$$

Potenciál $\varphi$ je potenciální energie jednotkového náboje. Ekvipotenciály jsou plochy se stejným potenciálem a jsou kolmé na siločáry elektrického pole. V elektrostatice platí

$$
\mathbf E \cdot d\mathbf l = -d\varphi,
\qquad
\mathbf E = -\nabla \varphi.
$$

Po dosazení do Gaussovy věty vzniká Poissonova rovnice pro potenciál:

$$
\Delta \varphi = -\frac{\rho}{\varepsilon}.
$$

V oblasti bez volného náboje přechází na Laplaceovu rovnici:

$$
\Delta \varphi = 0.
$$

Na rozhraní dvou dielektrik platí pro elektrostatické pole spojitost tečné složky intenzity:

$$
E_{1t} = E_{2t}.
$$

Normálové složky elektrické indukce se liší o plošnou hustotu volného náboje na rozhraní:

$$
D_{2n} - D_{1n} = \sigma_0.
$$

Pokud na rozhraní volný náboj není, je $D_{1n}=D_{2n}$. Na rozhraní s dobrým vodičem je uvnitř vodiče elektrostatické pole nulové, tečná složka vně vodiče je nulová a pole vstupuje na povrch kolmo.

**Zdroj:** [[empa_complete_edition.pdf#page=19|EMPA s. 19]], [[empa_complete_edition.pdf#page=20|EMPA s. 20]], [[empa_complete_edition.pdf#page=21|EMPA s. 21]], [[empa_complete_edition.pdf#page=27|EMPA s. 27]], [[empa_complete_edition.pdf#page=28|EMPA s. 28]], [[empa_complete_edition.pdf#page=29|EMPA s. 29]].

## Kapacita

Kapacita vyjadřuje schopnost soustavy elektrod akumulovat elektrický náboj při daném napětí:

$$
C = \frac{Q}{U},
\qquad [C] = \mathrm F.
$$

Pro deskový kondenzátor s plochou elektrod $S$, vzdáleností $d$ a permitivitou $\varepsilon$:

$$
C = \varepsilon \frac{S}{d}.
$$

Pro koaxiální vedení délky $l$, vnitřního poloměru $a$ a vnějšího poloměru $b$ je kapacita na jednotku délky

$$
C' = \frac{C}{l}
= \frac{2\pi\varepsilon}{\ln(b/a)}.
$$

U dvouvodičového vedení se kapacita určí z potenciálů vodičů: nejprve se spočte rozdíl potenciálů $U$ pro známý náboj na jednotku délky $\tau$, potom se použije $C'=\tau/U$. Pro běžné symetrické dvouvodičové vedení vychází vztah s logaritmem geometrického poměru vzdálenosti vodičů a jejich poloměru; přesný tvar závisí na definici geometrie v úloze.

Pro spojování kondenzátorů platí

$$
C_\parallel = \sum_i C_i,
\qquad
\frac{1}{C_\mathrm{s}} = \sum_i \frac{1}{C_i}.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=22|EMPA s. 22]], [[empa_complete_edition.pdf#page=23|EMPA s. 23]], [[empa_complete_edition.pdf#page=24|EMPA s. 24]], [[empa_complete_edition.pdf#page=25|EMPA s. 25]].

## Energie v elektrickém poli

Energie soustavy bodových nábojů se dá vyjádřit pomocí potenciálů v místech nábojů:

$$
W_e = \frac{1}{2}\sum_i Q_i \varphi_i.
$$

U lineárního kapacitoru:

$$
W_e = \int_0^Q u\,dq
= \int_0^U C u\,du
= \frac{1}{2} C U^2
= \frac{1}{2} Q U
= \frac{Q^2}{2C}.
$$

Objemová hustota energie v lineárním elektrickém poli je

$$
w_e = \frac{1}{2}\mathbf E \cdot \mathbf D.
$$

Celková energie v objemu $V$ je

$$
W_e = \int_V w_e\,dV.
$$

**Zdroj:** [[empa_complete_edition.pdf#page=26|EMPA s. 26]], [[empa_complete_edition.pdf#page=27|EMPA s. 27]].

## Metoda zrcadlení

Metoda zrcadlení nahrazuje vodivou rovinu fiktivními zrcadlovými náboji nebo elektrodami tak, aby na původní poloze vodivé roviny vyšel konstantní potenciál a elektrické pole bylo k rovině kolmé. Potom lze úlohu řešit jako pole ve volném prostoru bez explicitního vodiče.

Typický případ je vodič nad uzemněnou vodivou rovinou. Rovina se nahradí symetricky umístěným fiktivním vodičem s opačným nábojem. Pro dlouhý vodič poloměru $a$ ve výšce $h$ nad rovinou EMPA uvádí kapacitu na jednotku délky

$$
C'
= \frac{2\pi\varepsilon_0}
{\ln\left(\frac{2h-a}{a}\right)}.
$$

Smysl metody není v mechanickém zapamatování jednoho vzorce, ale v tom, že náhradní soustava musí splnit stejné okrajové podmínky na vodiči jako původní úloha.

**Zdroj:** [[empa_complete_edition.pdf#page=31|EMPA s. 31]], [[empa_complete_edition.pdf#page=32|EMPA s. 32]], kontrolně [[hex_compost.pdf#page=146|HEX s. 146]].

## Co umět u zkoušky

- Rozlišit elektrostatické, stacionární a nestacionární elektromagnetické pole.
- Vysvětlit rozdíl mezi vodičem, dielektrikem, volným a vázaným nábojem.
- Zapsat a použít Coulombův zákon, superpozici a Gaussovu větu.
- Převádět mezi $\mathbf E$, $\mathbf D$, $\mathbf P$, $\varphi$ v lineárním dielektriku.
- Spočítat kapacitu deskového a koaxiálního kondenzátoru.
- Vysvětlit energii v kapacitoru a hustotu energie pole.
- Popsat princip metody zrcadlení a její okrajové podmínky.
