# 09 Komplexní funkce, integrál, singularity a rezidua

**Otázka:** Funkce komplexní proměnné a jejich derivace. Křivkový integrál. Singularity. Mocninné řady, Taylorovy a Laurentovy rozvoje. Rezidua, reziduová věta a její aplikace.

## Funkce komplexní proměnné a derivace

Komplexní funkci píšeme jako

$$
f(z)=u(x,y)+iv(x,y), \qquad z=x+iy,
$$

kde $u$ a $v$ jsou reálné funkce dvou reálných proměnných. Derivace v bodě $z$ je definována stejně jako v reálné analýze:

$$
f'(z)=\lim_{h\to 0}\frac{f(z+h)-f(z)}{h}, \qquad h\in\mathbb C.
$$

Rozdíl proti reálné derivaci je v tom, že $h$ se k nule může blížit libovolným směrem v rovině. Existence derivace je proto silná podmínka. Pokud má $f=u+iv$ v bodě $z=x+iy$ derivaci, splňují složky Cauchyho-Riemannovy podmínky

$$
\frac{\partial u}{\partial x}=\frac{\partial v}{\partial y}, \qquad
\frac{\partial u}{\partial y}=-\frac{\partial v}{\partial x},
$$

a při existenci totálního diferenciálu jsou tyto podmínky s existencí komplexní derivace ekvivalentní. Hodnota derivace je

$$
f'(z)=\frac{\partial u}{\partial x}+i\frac{\partial v}{\partial x}.
$$

Funkce je holomorfní na otevřené množině $G\subset\mathbb C$, pokud má derivaci ve všech bodech $G$. Holomorfní funkce je spojitá a její reálná i imaginární část jsou harmonické funkce, pokud mají spojité druhé derivace, tedy splňují Laplaceovu rovnici.

Zdroj: [[testkom.pdf#page=29|testkom, s. 29-34]]

## Elementární komplexní funkce

Komplexní exponenciála je určena požadavky, že rozšiřuje reálnou exponenciálu, převádí součet na součin a je holomorfní. Pro $z=x+iy$ platí

$$
e^z=e^x(\cos y+i\sin y).
$$

Z toho plyne Eulerův vzorec

$$
e^{iy}=\cos y+i\sin y
$$

a periodičnost komplexní exponenciály

$$
e^{z+2k\pi i}=e^z, \qquad k\in\mathbb Z.
$$

Komplexní sinus a kosinus se zavádějí přes exponenciálu:

$$
\sin z=\frac{e^{iz}-e^{-iz}}{2i}, \qquad
\cos z=\frac{e^{iz}+e^{-iz}}{2}.
$$

Komplexní logaritmus je vícehodnotový. Pro $z\ne 0$ je

$$
\operatorname{Ln} z=\{\ln |z|+i\arg z+2k\pi i\mid k\in\mathbb Z\}.
$$

Hlavní větev logaritmu volí hodnotu s $k=0$ a je holomorfní mimo zvolený řez; v podkladu je popsán řez podél záporné reálné osy. Tam platí

$$
(\ln_0 z)'=\frac1z.
$$

Zdroj: [[testkom.pdf#page=34|testkom, s. 34-39]]

## Křivkový integrál komplexní funkce

Je-li $C$ křivka s parametrizací $\varphi:[a,b]\to\mathbb C$, definuje se křivkový integrál komplexní funkce $f$ vztahem

$$
\int_C f(z)\,dz=\int_a^b f(\varphi(t))\varphi'(t)\,dt.
$$

Při změně orientace křivky se změní znaménko:

$$
\int_{-C} f(z)\,dz=-\int_C f(z)\,dz.
$$

Důležitý odhad říká, že pokud $|f(z)|\le M$ na křivce $C$, potom

$$
\left|\int_C f(z)\,dz\right|\le M\cdot \operatorname{délka}(C).
$$

Základní příklad je integrace mocnin po kladně orientované kružnici kolem nuly:

$$
\int_C z^k\,dz=\begin{cases}
2\pi i, & k=-1,\\
0, & k\ne -1.
\end{cases}
$$

Tento výpočet je později důvodem, proč v Laurentově řadě rozhoduje koeficient u $(z-z_0)^{-1}$.

Zdroj: [[testkom.pdf#page=49|testkom, s. 49-51]]

## Cauchyova věta a Cauchyův integrální vzorec

Cauchyova věta říká: je-li $D\subset\mathbb C$ jednoduše souvislá oblast a $f$ je holomorfní na $D$, potom pro každou uzavřenou jednoduchou křivku $C\subset D$ platí

$$
\int_C f(z)\,dz=0.
$$

Důsledkem je existence primitivní funkce za předpokladu nulových integrálů po uzavřených křivkách. Podstatný je také Cauchyův integrální vzorec. Je-li $f$ holomorfní na jednoduše souvislé oblasti $D$, $C\subset D$ je kladně orientovaná jednoduchá uzavřená křivka a $z_0\in\operatorname{Int}C$, potom

$$
\int_C \frac{f(z)}{z-z_0}\,dz=2\pi i f(z_0).
$$

Zobecněná verze dává derivace:

$$
f^{(n)}(z_0)=\frac{n!}{2\pi i}\int_C \frac{f(z)}{(z-z_0)^{n+1}}\,dz.
$$

Z toho plyne důležitá vlastnost: holomorfní funkce má derivace všech řádů. To je silnější než u reálných funkcí jedné proměnné.

Zdroj: [[testkom.pdf#page=52|testkom, s. 52-58]], [[testkom.pdf#page=88|testkom, s. 88-89]]

## Mocninné řady a Taylorův rozvoj

Mocninná řada se středem $z_0$ má tvar

$$
\sum_{n=0}^{\infty} a_n(z-z_0)^n.
$$

Její poloměr konvergence $R$ je určen vztahem

$$
\frac1R=\limsup_{n\to\infty}\sqrt[n]{|a_n|}.
$$

Řada konverguje absolutně uvnitř kruhu $|z-z_0|<R$, diverguje pro $|z-z_0|>R$ a na každém uzavřeném kruhu $|z-z_0|\le r<R$ konverguje stejnoměrně. O hranici $|z-z_0|=R$ obecná věta nerozhoduje.

Funkce daná mocninnou řadou je holomorfní uvnitř kruhu konvergence a lze ji derivovat člen po členu:

$$
\left(\sum_{n=0}^{\infty} a_n(z-z_0)^n\right)'=
\sum_{n=1}^{\infty} n a_n(z-z_0)^{n-1}.
$$

Každá holomorfní funkce je lokálně vyjádřitelná mocninnou řadou. V okolí bodu $z_0$ tedy platí Taylorův rozvoj

$$
f(z)=\sum_{n=0}^{\infty}\frac{f^{(n)}(z_0)}{n!}(z-z_0)^n.
$$

Poloměr konvergence je určen největším kruhem se středem $z_0$, na němž je funkce holomorfní. To souvisí s tématem [[10 Fourier Laplace Z transformace#Laplaceova transformace|Laplaceovy transformace]], kde se inverzní obrazy často hledají pomocí rozvojů v okolí nekonečna.

Zdroj: [[testkom.pdf#page=71|testkom, s. 71-80]], [[testkom.pdf#page=81|testkom, s. 81-88]]

## Laurentovy řady

Laurentova řada se středem $z_0$ má tvar

$$
\sum_{n=-\infty}^{\infty} a_n(z-z_0)^n.
$$

Část s nezápornými mocninami je regulární část, část se zápornými mocninami je hlavní část. Laurentova řada konverguje v mezikruží

$$
P(z_0;r,R)=\{z\in\mathbb C\mid r<|z-z_0|<R\}.
$$

Je-li funkce $f$ holomorfní v takovém mezikruží, má zde jednoznačný Laurentův rozvoj

$$
f(z)=\sum_{n=-\infty}^{\infty} a_n(z-z_0)^n,
$$

kde koeficienty jsou určeny integrálem

$$
a_n=\frac1{2\pi i}\int_C \frac{f(w)}{(w-z_0)^{n+1}}\,dw.
$$

Křivka $C$ je libovolná kladně orientovaná jednoduchá uzavřená křivka ležící v mezikruží a obíhající bod $z_0$. Laurentův rozvoj je hlavní nástroj pro popis izolovaných singularit.

Zdroj: [[testkom.pdf#page=103|testkom, s. 103-110]]

## Izolované singularity

Bod $z_0$ je izolovaná singularita funkce $f$, pokud $f$ není holomorfní v $z_0$, ale je holomorfní v nějakém prstencovém okolí $0<|z-z_0|<R$. Podle tvaru hlavní části Laurentovy řady rozlišujeme tři typy:

1. Odstranitelná singularita: všechny koeficienty hlavní části jsou nulové. Funkce má v bodě vlastní limitu a lze ji dodefinovat holomorfně.
2. Pól řádu $k$: platí $a_{-k}\ne 0$ a $a_n=0$ pro všechna $n<-k$. Funkce se chová jako

$$
f(z)=\frac{g(z)}{(z-z_0)^k}, \qquad g(z_0)\ne 0.
$$

3. Podstatná singularita: hlavní část má nekonečně mnoho nenulových koeficientů.

U pólu se řád určuje také přes převrácenou funkci: $z_0$ je pól řádu $k$ funkce $f$, právě když $z_0$ je kořen řádu $k$ holomorfního rozšíření funkce $1/f$.

Pro singularitu v nekonečnu se používá transformace $g(z)=f(1/z)$ a klasifikace v bodě $0$.

Zdroj: [[testkom.pdf#page=127|testkom, s. 127-133]]

## Reziduum

Reziduum funkce $f$ v izolované singularitě $z_0$ je koeficient $a_{-1}$ Laurentovy řady:

$$
\operatorname{res}_{z_0} f=a_{-1}.
$$

Díky integrálnímu vyjádření koeficientů platí

$$
\int_C f(z)\,dz=2\pi i\operatorname{res}_{z_0}f,
$$

pokud $C$ kladně obíhá jedinou singularitu $z_0$. Pro jednoduchý pól platí praktický vzorec

$$
\operatorname{res}_{z_0} f=\lim_{z\to z_0}(z-z_0)f(z).
$$

Pro pól řádu $k$ platí

$$
\operatorname{res}_{z_0} f=
\frac1{(k-1)!}\lim_{z\to z_0}\frac{d^{k-1}}{dz^{k-1}}
\left((z-z_0)^k f(z)\right).
$$

Je-li $f/g$ podíl holomorfních funkcí a $z_0$ je jednoduchý kořen $g$, potom

$$
\operatorname{res}_{z_0}\frac{f(z)}{g(z)}=\frac{f(z_0)}{g'(z_0)}.
$$

Pro nekonečno je v podkladu definováno

$$
\operatorname{res}_{\infty}f=-a_1,
$$

kde $a_1$ je koeficient Laurentova rozvoje se středem v nekonečnu.

Zdroj: [[testkom.pdf#page=133|testkom, s. 133-139]]

## Reziduová věta

Pro potřeby státnic stačí standardní verze pro kladně orientovanou jednoduchou uzavřenou křivku. Je-li $f$ holomorfní uvnitř a na křivce $C$ až na konečně mnoho izolovaných singularit $z_1,\dots,z_k$ ležících uvnitř $C$, potom

$$
\int_C f(z)\,dz=2\pi i\sum_{j=1}^k \operatorname{res}_{z_j} f.
$$

Do integrálu tedy přispívají právě singularity uvnitř křivky, každá svým reziduem. Singularity vně křivky se do součtu neberou.

Pokud je funkce holomorfní v celé rovině kromě konečně mnoha singularit $z_1,\dots,z_k$, platí součtový vztah

$$
\sum_{j=1}^k \operatorname{res}_{z_j} f+\operatorname{res}_{\infty}f=0.
$$

Zdroj: [[testkom.pdf#page=155|testkom, s. 155-157]]

## Aplikace reziduové věty
Reziduová věta se v podkladu používá hlavně na čtyři typy úloh.

### Integrály racionálních funkcí

Pro racionální funkci $P/Q$, kde $\deg Q\ge \deg P+2$ a $Q$ nemá reálné kořeny, se integrál přes reálnou osu počítá uzavřením kontury horní polokružnicí:

$$
\int_{-\infty}^{\infty}\frac{P(x)}{Q(x)}\,dx=
2\pi i\sum_{\substack{Q(z)=0\\ \operatorname{Im}z>0}}
\operatorname{res}_z\frac{P(z)}{Q(z)}.
$$

Zdroj: [[testkom.pdf#page=157|testkom, s. 157-158]]

### Integrály goniometrických funkcí

Integrály tvaru

$$
\int_0^{2\pi} R(\cos x,\sin x)\,dx
$$

se převádějí substitucí $z=e^{ix}$ na integrál po jednotkové kružnici. Používají se vztahy

$$
\cos x=\frac{z^2+1}{2z}, \qquad
\sin x=\frac{z^2-1}{2iz}, \qquad
 dx=\frac{dz}{iz}.
$$

Zdroj: [[testkom.pdf#page=158|testkom, s. 158-160]]

### Fourierovské integrály s exponenciálou

U integrálů

$$
\int_{-\infty}^{\infty} R(x)e^{ix}\,dx
$$

se opět uzavírá v horní polorovině a pro odhad oblouku se používá Jordanovo lemma. Tato část přímo souvisí s výpočty ve [[10 Fourier Laplace Z transformace#Fourierova transformace|Fourierově transformaci]].

Zdroj: [[testkom.pdf#page=160|testkom, s. 160-164]]

### Součty řad

Pro součty typu $\sum f(n)$ se používá funkce $\pi\cot(\pi z)$, protože má v celých číslech reziduum $1$. Pro alternující součty se používá $\pi/\sin(\pi z)$, která má rezidua $(-1)^n$.

Zdroj: [[testkom.pdf#page=164|testkom, s. 164-168]]
