# 02 Maticový počet, determinant, inverze, vlastní čísla

Související: [[01 Struktura linearniho prostoru, baze a dimenze]]

## Matice a maticový počet

Matice $A:F^s\to F^r$ reprezentuje lineární zobrazení z $F^s$ do $F^r$. Sloupce matice jsou obrazy kanonických vektorů:

$$
A\vec e_j=\vec a_j.
$$

Pro $\vec x=\sum_{j=1}^s x_j\vec e_j$ platí

$$
A\vec x=\sum_{j=1}^s x_j\vec a_j.
$$

Součet matic a násobení matice skalárem se počítají po položkách. Součin $BA$ je definován pro $A:F^s\to F^p$ a $B:F^p\to F^r$, tedy když má $B$ tolik sloupců, kolik má $A$ řádků. Položka součinu v $i$-tém řádku a $j$-tém sloupci je

$$
(BA)_{ij}=\sum_{k=1}^p b_{ik}a_{kj}.
$$

Násobení matic je asociativní, ale obecně není komutativní. Jednotková matice $E_n$ reprezentuje identitu. Transpozice splňuje

$$
(BA)^T=A^TB^T,\qquad (A^T)^T=A.
$$

**Zdroj:** [[akla_2023_09_15.pdf#page=101|AKLA s. 101]], [[akla_2023_09_15.pdf#page=102|AKLA s. 102]], [[akla_2023_09_15.pdf#page=103|AKLA s. 103]], [[akla_2023_09_15.pdf#page=132|AKLA s. 132]], [[akla_2023_09_15.pdf#page=135|AKLA s. 135]], kontrolně [[hex_compost.pdf#page=10|HEX s. 10]]-[[hex_compost.pdf#page=11|HEX s. 11]].

## ~~Matice lineárního zobrazení vzhledem k bázím~~

~~Pro lineární zobrazení $f:L_1\to L_2$ mezi prostory konečné dimenze závisí matice zobrazení na volbě bází. Je-li $B=(\vec b_1,\ldots,\vec b_s)$ báze $L_1$ a $C$ báze $L_2$, pak matice $A_f$ vzhledem k $B,C$ se sestaví takto:~~

~~$$~~
~~\text{$i$-tý sloupec }A_f=\operatorname{coord}_C(f(\vec b_i)).~~
~~$$~~

~~Matice identity vzhledem k libovolné bázi je $E_n$. Matice složeného zobrazení je součin matic odpovídajících zobrazení.~~

~~**Zdroj:** [[akla_2023_09_15.pdf#page=211|AKLA s. 211]], [[akla_2023_09_15.pdf#page=216|AKLA s. 216]], [[akla_2023_09_15.pdf#page=217|AKLA s. 217]].~~

## Determinant

Pro čtvercovou matici $A=(a_{ij})$ velikosti $n\times n$ je determinant

$$
\det(A)=\sum_{\pi\in S_n}\operatorname{sign}(\pi)
 a_{\pi(1),1}\cdots a_{\pi(n),n}.
$$

Pro $2\times2$ matici:

$$
\begin{vmatrix}
a_{11}&a_{12}\\
a_{21}&a_{22}
\end{vmatrix}
=a_{11}a_{22}-a_{21}a_{12}.
$$

Pro $3\times3$ lze použít Sarrusovo pravidlo. Obecně je praktičtější Gaussova eliminace a sledování, jak řádkové úpravy mění determinant.

Geometricky nad $\mathbb R$ determinant vyjadřuje orientovaný obsah/objem rovnoběžnostěnu určeného sloupci matice.

**Zdroj:** [[akla_2023_09_15.pdf#page=182|AKLA s. 182]], [[akla_2023_09_15.pdf#page=184|AKLA s. 184]], [[akla_2023_09_15.pdf#page=185|AKLA s. 185]], kontrolně [[hex_compost.pdf#page=14|HEX s. 14]].

## Vlastnosti determinantu a výpočet

Základní pravidla:

- $\det(A^T)=\det(A)$,
- prohození dvou řádků nebo sloupců změní znaménko determinantu,
- pokud jsou dva řádky nebo sloupce stejné, determinant je $0$,%% idk %%
- vynásobení jednoho řádku nebo sloupce skalárem $a$ vynásobí determinant skalárem $a$,
- přičtení lineární kombinace ostatních řádků/sloupců k jednomu řádku/sloupci determinant nemění,
- u horní trojúhelníkové matice je determinant součin prvků na hlavní diagonále, %% idk %%
- $\det(BA)=\det(B)\det(A)$.

Pozor při GEM: pokud řádek jen přičítám k jinému řádku, determinant se nemění; pokud řádky prohodím, mění se znaménko; pokud řádek násobím skalárem, musím to započítat.

**Zdroj:** [[akla_2023_09_15.pdf#page=188|AKLA s. 188]], [[akla_2023_09_15.pdf#page=189|AKLA s. 189]], [[akla_2023_09_15.pdf#page=190|AKLA s. 190]], [[akla_2023_09_15.pdf#page=191|AKLA s. 191]], [[akla_2023_09_15.pdf#page=192|AKLA s. 192]], [[akla_2023_09_15.pdf#page=193|AKLA s. 193]], kontrolně [[hex_compost.pdf#page=14|HEX s. 14]].

## Inverzní matice

Čtvercová matice $A$ je invertibilní/regulární právě tehdy, když

$$
\det(A)\neq 0.
$$

Pak existuje $A^{-1}$ a platí $A^{-1}A=E_n=AA^{-1}$.

Praktické způsoby výpočtu:

1. GEM na rozšířené matici $(A\mid E_n)$. Úpravami dostat vlevo $E_n$, vpravo pak vznikne $A^{-1}$.
2. Přes adjungovanou matici:

$$
A^{-1}=\det(A)^{-1}\operatorname{adj}(A).
$$

Adjungovaná matice je transponovaná matice algebraických doplňků. Algebraický doplněk pozice $(i,j)$ je

$$
A_{ij}=(-1)^{i+j}\det(A(i,j)),
$$

kde $A(i,j)$ vznikne vyškrtnutím $i$-tého řádku a $j$-tého sloupce.

Pro $2\times2$:

$$
\begin{pmatrix}
a&b\\c&d
\end{pmatrix}^{-1}
=(ad-bc)^{-1}
\begin{pmatrix}
d&-b\\-c&a
\end{pmatrix},
\quad ad-bc\neq0.
$$

**Zdroj:** [[akla_2023_09_15.pdf#page=200|AKLA s. 200]], [[akla_2023_09_15.pdf#page=201|AKLA s. 201]], [[akla_2023_09_15.pdf#page=202|AKLA s. 202]], [[akla_2023_09_15.pdf#page=203|AKLA s. 203]], kontrolně [[hex_compost.pdf#page=12|HEX s. 12]]-[[hex_compost.pdf#page=13|HEX s. 13]].

## Cramerova věta

Je-li $A\vec x=\vec b$ soustava s regulární čtvercovou maticí $A$, má právě jedno řešení. Složka $x_j$ se spočítá jako

$$
x_j=\frac{\det(\vec a_1,\ldots,\vec a_{j-1},\vec b,\vec a_{j+1},\ldots,\vec a_n)}{\det(A)}.
$$

Tedy v čitateli nahradím $j$-tý sloupec matice $A$ pravou stranou $\vec b$.

Podmínky použití: $A$ je čtvercová a regulární, tj. $\det(A)\neq0$.

**Zdroj:** [[akla_2023_09_15.pdf#page=203|AKLA s. 203]], [[akla_2023_09_15.pdf#page=204|AKLA s. 204]], kontrolně [[hex_compost.pdf#page=7|HEX s. 7]]-[[hex_compost.pdf#page=8|HEX s. 8]].

## Vlastní čísla a vlastní vektory

Nenulový vektor $\vec v$ je vlastní vektor lineárního zobrazení $f:L\to L$, pokud existuje skalár $\lambda$ takový, že

$$
f(\vec v)=\lambda\vec v.
$$

Skalár $\lambda$ je vlastní hodnota. Pro matici $A$ je to rovnice

$$
A\vec x=\lambda\vec x,
$$

kde $\vec x\neq\vec o$.

Vlastní prostor příslušný $\lambda$ je

$$
\operatorname{eigen}(\lambda,A)=\ker(A-\lambda E_n).
$$

Vlastní hodnoty najdeme z charakteristické rovnice

$$
\det(A-\lambda E_n)=0.
$$

Charakteristický polynom je

$$
\operatorname{char}_A(x)=\det(A-xE_n).
$$

Postup: spočítat kořeny charakteristického polynomu, pro každé $\lambda$ řešit homogenní soustavu $(A-\lambda E_n)\vec x=\vec o$; její nenulová řešení jsou vlastní vektory.

**Zdroj:** [[akla_2023_09_15.pdf#page=244|AKLA s. 244]], [[akla_2023_09_15.pdf#page=245|AKLA s. 245]], [[akla_2023_09_15.pdf#page=246|AKLA s. 246]], kontrolně [[hex_compost.pdf#page=14|HEX s. 14]]-[[hex_compost.pdf#page=15|HEX s. 15]].

## Podobnost matic

Čtvercové matice $A,B:F^n\to F^n$ jsou podobné, pokud existuje invertibilní matice $T$ taková, že

$$
B=T^{-1}AT.
$$

Význam: $A$ a $B$ jsou matice téhož lineárního zobrazení v různých bázích. Podobné matice mají stejný determinant a stejný charakteristický polynom, tedy stejné vlastní hodnoty včetně algebraických násobností. Samotný stejný charakteristický polynom ale ještě nezaručuje podobnost.

**Zdroj:** [[akla_2023_09_15.pdf#page=229|AKLA s. 229]], [[akla_2023_09_15.pdf#page=230|AKLA s. 230]], [[akla_2023_09_15.pdf#page=231|AKLA s. 231]], [[akla_2023_09_15.pdf#page=245|AKLA s. 245]].

## Diagonalizace

Matice $A$ je diagonalizovatelná, pokud je podobná diagonální matici:

$$
T^{-1}AT=D.
$$

To nastane právě tehdy, když existuje báze prostoru složená z vlastních vektorů matice $A$. Sloupce matice $T$ jsou právě tyto vlastní vektory a na diagonále $D$ jsou odpovídající vlastní hodnoty.

Užitečná kritéria:

- vlastní vektory k různým vlastním hodnotám jsou lineárně nezávislé,
- pokud má matice velikosti $n\times n$ celkem $n$ různých vlastních hodnot, je diagonalizovatelná,
- obecně musí platit, že charakteristický polynom se rozloží na lineární faktory a pro každou vlastní hodnotu $\lambda$ platí

$$
\dim(\operatorname{eigen}(\lambda,A))=\operatorname{ord}(\lambda,\operatorname{char}_A(x)).
$$

Tedy geometrická násobnost každé vlastní hodnoty musí být rovna její algebraické násobnosti.

**Zdroj:** [[akla_2023_09_15.pdf#page=247|AKLA s. 247]], [[akla_2023_09_15.pdf#page=248|AKLA s. 248]], [[akla_2023_09_15.pdf#page=249|AKLA s. 249]], [[akla_2023_09_15.pdf#page=250|AKLA s. 250]], [[akla_2023_09_15.pdf#page=251|AKLA s. 251]], kontrolně [[hex_compost.pdf#page=15|HEX s. 15]].
