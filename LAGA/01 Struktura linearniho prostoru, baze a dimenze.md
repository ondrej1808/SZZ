# 01 Struktura lineárního prostoru, báze a dimenze

Související: [[02 Maticovy pocet, determinant, inverze, vlastni cisla]]

## Lineární prostor

Lineární prostor nad tělesem $F$ je trojice $(L,+,\cdot)$, kde prvky $L$ jsou vektory, $+$ je sčítání vektorů a $\cdot$ je násobení vektoru skalárem z $F$.

Axiomy sčítání vektorů:

- existence nulového vektoru: existuje $\vec o$ tak, že $\vec x+\vec o=\vec o+\vec x=\vec x$,
- komutativita: $\vec x+\vec y=\vec y+\vec x$,
- asociativita: $\vec x+(\vec y+\vec z)=(\vec x+\vec y)+\vec z$,
- existence opačného vektoru: ke každému $\vec x$ existuje právě jeden $-\vec x$ tak, že $\vec x+(-\vec x)=\vec o$.

Axiomy násobení skalárem a vazba na sčítání:

- neutralita jedničky: $1\cdot\vec x=\vec x$,
- asociativita skalárního násobení: $a\cdot(b\cdot\vec x)=(a\cdot b)\cdot\vec x$,
- distributivita vůči sčítání vektorů: $a\cdot(\vec x+\vec y)=a\cdot\vec x+a\cdot\vec y$,
- distributivita vůči sčítání skalárů: $(a+b)\cdot\vec x=a\cdot\vec x+b\cdot\vec x$.

Typický příklad je $F^n$, kde se sčítání i násobení skalárem počítá po složkách. Pro zkoušku je důležité umět axiomy vyjmenovat a u příkladu ověřit, že operace opravdu dávají lineární prostor.

**Zdroj:** [[akla_2023_09_15.pdf#page=15|AKLA s. 15]], [[akla_2023_09_15.pdf#page=16|AKLA s. 16]], [[akla_2023_09_15.pdf#page=17|AKLA s. 17]], kontrolně [[hex_compost.pdf#page=4|HEX s. 4]]-[[hex_compost.pdf#page=5|HEX s. 5]].

## Lineární kombinace a lineární obal

Lineární kombinace vektorů je výraz

$$
\sum_{i\in I} a_i\vec v_i,
$$

kde $a_i\in F$ a nenulových koeficientů je jen konečně mnoho. Lineární obal množiny $M$ je množina všech lineárních kombinací vektorů z $M$:

$$
\operatorname{span}(M)=\{\text{všechny lineární kombinace vektorů z }M\}.
$$

Množina $G$ generuje prostor $L$, pokud $\operatorname{span}(G)=L$.

**Zdroj:** [[akla_2023_09_15.pdf#page=34|AKLA s. 34]], [[akla_2023_09_15.pdf#page=35|AKLA s. 35]], [[akla_2023_09_15.pdf#page=74|AKLA s. 74]].

## Lineární nezávislost

Seznam $(\vec v_1,\ldots,\vec v_n)$ je lineárně nezávislý, pokud z rovnosti

$$
a_1\vec v_1+\cdots+a_n\vec v_n=\vec o
$$

plyne $a_1=\cdots=a_n=0$. Jinak je lineárně závislý. Jinými slovy: lineárně závislý seznam má netriviální nulovou lineární kombinaci.

Praktické poznámky:

- seznam obsahující $\vec o$ je lineárně závislý,
- seznam s opakovaným vektorem je lineárně závislý,
- kanonické vektory $\vec e_1,\ldots,\vec e_n$ v $F^n$ jsou lineárně nezávislé.

**Zdroj:** [[akla_2023_09_15.pdf#page=71|AKLA s. 71]], [[akla_2023_09_15.pdf#page=72|AKLA s. 72]], kontrolně [[hex_compost.pdf#page=6|HEX s. 6]].

## Báze, dimenze a souřadnice

Báze prostoru $L$ je lineárně nezávislá množina generátorů. Pokud je báze zapsaná jako seznam, mluvíme o uspořádané bázi.

Každý konečně generovaný lineární prostor má bázi a všechny jeho báze mají stejný počet prvků. Tento počet je dimenze:

$$
\dim(L)=\text{počet prvků libovolné báze }L.
$$

Je-li $B=(\vec b_1,\ldots,\vec b_n)$ uspořádaná báze, každý vektor $\vec x\in L$ má právě jeden zápis

$$
\vec x=x_1\vec b_1+\cdots+x_n\vec b_n.
$$

Souřadnicový vektor vzhledem k bázi $B$ je

$$
\operatorname{coord}_B(\vec x)=
\begin{pmatrix}
x_1\\ \vdots\\ x_n
\end{pmatrix}.
$$

Zobrazení $\operatorname{coord}_B:L\to F^n$ je izomorfismus, takže volba báze dovolí počítat v abstraktním prostoru jako v $F^n$.

**Zdroj:** [[akla_2023_09_15.pdf#page=75|AKLA s. 75]], [[akla_2023_09_15.pdf#page=78|AKLA s. 78]], [[akla_2023_09_15.pdf#page=79|AKLA s. 79]], kontrolně [[hex_compost.pdf#page=6|HEX s. 6]].

## Řešení soustav lineárních rovnic

Soustava $r$ lineárních rovnic o $s$ neznámých se zapisuje

$$
A\vec x=\vec b,
$$

kde $A:F^s\to F^r$ je matice soustavy, $\vec x$ je vektor neznámých a $\vec b$ pravá strana. Rozšířená matice je $(A\mid \vec b)$.

Dva důležité pohledy:

- sloupcový: hledáme koeficienty lineární kombinace sloupců $A$, která dá $\vec b$; řešitelnost znamená $\vec b\in\operatorname{im}(A)$,
- řádkový: hledáme společné řešení rovnic daných řádky matice.

Gaussova eliminace používá tři úpravy, které nemění množinu řešení: přičtení násobku řádku k jinému řádku, prohození řádků a vynásobení řádku nenulovým skalárem. Cílem je horní blokový/trojúhelníkový tvar. Počet nenulových řádků v horním blokovém tvaru je hodnost.

Frobeniova věta:

$$
(A\mid \vec b)\text{ má řešení}\quad\Longleftrightarrow\quad
\operatorname{rank}(A)=\operatorname{rank}(A\mid\vec b).
$$

Pokud řešení existuje, všechna řešení jsou

$$
\vec p+\ker(A),
$$

kde $\vec p$ je jedno partikulární řešení. Báze $\ker(A)$ je fundamentální systém homogenní soustavy.

**Zdroj:** [[akla_2023_09_15.pdf#page=136|AKLA s. 136]], [[akla_2023_09_15.pdf#page=137|AKLA s. 137]], [[akla_2023_09_15.pdf#page=140|AKLA s. 140]], [[akla_2023_09_15.pdf#page=147|AKLA s. 147]], kontrolně [[hex_compost.pdf#page=6|HEX s. 6]]-[[hex_compost.pdf#page=7|HEX s. 7]].

## Lineární zobrazení

Zobrazení $f:L_1\to L_2$ je lineární, pokud zachovává sčítání a násobení skalárem:

$$
f(\vec x+\vec y)=f(\vec x)+f(\vec y),
$$

$$
f(a\vec x)=a f(\vec x).
$$

Ekvivalentně pro lineární kombinaci:

$$
f\left(\sum_{i=1}^n a_i\vec x_i\right)=\sum_{i=1}^n a_i f(\vec x_i).
$$

Je-li $B$ báze konečnědimenzionálního prostoru $L_1$, lineární zobrazení je jednoznačně určeno hodnotami na vektorech báze.

Jádro a obraz:

$$
\ker(f)=\{\vec x\mid f(\vec x)=\vec o\},\qquad
\operatorname{im}(f)=\{\vec y\mid \exists\vec x: f(\vec x)=\vec y\}.
$$

Klasifikace:

- monomorfismus právě tehdy, když $\ker(f)=\{\vec o\}$,
- epimorfismus právě tehdy, když $\operatorname{im}(f)=L_2$,
- izomorfismus je lineární zobrazení, které je prosté i na; má inverzi.

**Zdroj:** [[akla_2023_09_15.pdf#page=51|AKLA s. 51]], [[akla_2023_09_15.pdf#page=52|AKLA s. 52]], [[akla_2023_09_15.pdf#page=62|AKLA s. 62]], [[akla_2023_09_15.pdf#page=63|AKLA s. 63]], [[akla_2023_09_15.pdf#page=87|AKLA s. 87]], kontrolně [[hex_compost.pdf#page=8|HEX s. 8]]-[[hex_compost.pdf#page=9|HEX s. 9]].

## Skalární součin

Skalární součin na reálném lineárním prostoru $L$ je funkce

$$
\langle -\mid -\rangle:L\times L\to\mathbb R
$$

splňující:

- linearitu ve druhé souřadnici: pro pevné $\vec v$ je $\langle \vec v\mid -\rangle$ lineární,
- symetrii: $\langle\vec v\mid\vec w\rangle=\langle\vec w\mid\vec v\rangle$,
- pozitivní definitnost: $\langle\vec v\mid\vec v\rangle\ge 0$ a rovnost nastane právě pro $\vec v=\vec o$.

Standardní skalární součin v $\mathbb R^n$:

$$
\langle \vec v\mid \vec w\rangle=\sum_{i=1}^n v_iw_i=\vec v^T\vec w.
$$

Obecný skalární součin v $\mathbb R^n$ lze zapsat pomocí metrického tensoru $G$:

$$
\langle \vec v\mid\vec w\rangle=\vec v^T G\vec w,
$$

kde $G$ je symetrická pozitivně definitní matice. Standardní skalární součin má $G=E_n$.

Ze skalárního součinu dostaneme normu a úhel:

$$
\lVert\vec v\rVert=\sqrt{\langle\vec v\mid\vec v\rangle},\qquad
\cos\varphi=\frac{\langle\vec v\mid\vec w\rangle}{\lVert\vec v\rVert\lVert\vec w\rVert}.
$$

Vektory jsou ortogonální, pokud $\langle\vec v\mid\vec w\rangle=0$.

**Zdroj:** [[akla_2023_09_15.pdf#page=296|AKLA s. 296]], [[akla_2023_09_15.pdf#page=300|AKLA s. 300]], [[akla_2023_09_15.pdf#page=301|AKLA s. 301]], [[akla_2023_09_15.pdf#page=307|AKLA s. 307]], [[akla_2023_09_15.pdf#page=308|AKLA s. 308]], kontrolně [[hex_compost.pdf#page=9|HEX s. 9]]-[[hex_compost.pdf#page=10|HEX s. 10]].

## Ortogonalizace

Ortogonální báze je báze $(\vec u_1,\ldots,\vec u_n)$, kde

$$
\langle\vec u_i\mid\vec u_j\rangle=0\quad\text{pro }i\ne j.
$$

Pokud má podprostor $W$ ortogonální bázi $(\vec u_1,\ldots,\vec u_k)$, projekce vektoru $\vec v$ na $W$ je

$$
\operatorname{proj}_W(\vec v)=\sum_{i=1}^k
\frac{\langle\vec u_i\mid\vec v\rangle}{\langle\vec u_i\mid\vec u_i\rangle}\vec u_i.
$$

Gramova-Schmidtova ortogonalizace z každé báze $(\vec b_1,\ldots,\vec b_n)$ vytvoří ortogonální bázi $(\vec c_1,\ldots,\vec c_n)$ tak, že průběžně zachovává generované podprostory:

$$
\operatorname{span}(\vec b_1,\ldots,\vec b_k)=\operatorname{span}(\vec c_1,\ldots,\vec c_k).
$$

Pro B úroveň stačí umět princip: postupně bereme nové vektory a odečítáme jejich projekce do už vytvořených ortogonálních směrů.

**Zdroj:** [[akla_2023_09_15.pdf#page=322|AKLA s. 322]], [[akla_2023_09_15.pdf#page=323|AKLA s. 323]], kontrolně [[hex_compost.pdf#page=10|HEX s. 10]].
