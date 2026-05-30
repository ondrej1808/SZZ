# 07 Funkce více proměnných, gradient, derivace složené funkce a extrémy

## Funkce více proměnných

Funkce $n$ proměnných je zobrazení
$$
f: M \to \mathbb{R}, \qquad M \subset \mathbb{R}^n.
$$
Množina $M$ je definiční obor $D(f)$. Pro bod $x=(x_1,\dots,x_n)$ píšeme hodnotu krátce $f(x)=f(x_1,\dots,x_n)$.%% idk %% Obor hodnot na množině $M$ je
$$
f(M)=\{f(x)\mid x\in M\}.
$$
Pro funkce více proměnných se často používají konstantní hladiny
$$
H_c=\{x\in D(f)\mid f(x)=c\},
$$
například vrstevnice, izotermy nebo ekvipotenciální hladiny. Graf funkce dvou proměnných je plocha
$$
\operatorname{Graf}(f)=\{(x,y,z)\in\mathbb{R}^3\mid z=f(x,y),\ (x,y)\in D(f)\}.
$$
Zdroj: [[dipocet.pdf#page=16|Diferenciální počet, funkce více proměnných, s. 17-21]]

> [!todo] DOPLNIT OBRÁZEK: graf funkce $z=f(x,y)$ a její vrstevnice v rovině $xy$.

## Směrová a parciální derivace

Nechť $f:G\to\mathbb{R}$ je definována na otevřené množině $G\subset\mathbb{R}^n$, $x_0\in G$ a $h\in\mathbb{R}^n$. Směrová derivace ve směru $h$ je limita
$$
\frac{\partial f}{\partial h}(x_0)=\lim_{t\to 0}\frac{f(x_0+th)-f(x_0)}{t},
$$
pokud existuje. Pro směr $h=0$ je směrová derivace nulová. Výpočet lze převést na derivaci funkce jedné proměnné
$$
\varphi(t)=f(x_0+th), \qquad \varphi'(0)=\frac{\partial f}{\partial h}(x_0).
$$
Parciální derivace podle $x_i$ je směrová derivace ve směru bázového vektoru $e_i$:
$$
\frac{\partial f}{\partial x_i}(x)=\frac{\partial f}{\partial e_i}(x).
$$
Zdroj: [[dipocet.pdf#page=54|Diferenciální počet, směrové a parciální derivace, s. 55-59]]

## Gradient a diferenciál

Gradient funkce $f$ v bodě $x$ je vektor parciálních derivací
$$
\operatorname{grad} f(x)=\left(\frac{\partial f}{\partial x_1}(x),\dots,\frac{\partial f}{\partial x_n}(x)\right).
$$
Silnější pojem než existence směrových derivací je totální diferenciál. Lineární zobrazení $df(x_0):\mathbb{R}^n\to\mathbb{R}$ je diferenciál funkce $f$ v bodě $x_0$, jestliže
$$
\lim_{h\to 0}\frac{f(x_0+h)-f(x_0)-df(x_0)[h]}{\|h\|}=0.
$$
Je-li $f$ diferencovatelná v bodě $x$, pak pro každý směr $h$ platí
$$
df(x)[h]=\frac{\partial f}{\partial h}(x)=h\cdot \operatorname{grad} f(x).
$$
Z toho plyne praktický zápis
$$
df=\frac{\partial f}{\partial x_1}dx_1+\cdots+\frac{\partial f}{\partial x_n}dx_n.
$$
Důležité rozlišení: existence všech parciálních derivací sama o sobě nemusí zaručit spojitost ani diferencovatelnost. Postačující kritérium je: má-li $f$ všechny parciální derivace spojité v bodě $x$, pak má v bodě $x$ diferenciál. Zdroj: [[dipocet.pdf#page=60|Diferenciální počet, diferenciál funkce, s. 61-67]]

## Geometrický význam gradientu

Je-li $\|h\|=1$, potom
$$
\frac{\partial f}{\partial h}(x)=h\cdot \operatorname{grad}f(x)=\|\operatorname{grad}f(x)\|\cos\alpha.
$$
Směr největšího růstu je tedy směr gradientu
$$
h_{\max}=\frac{\operatorname{grad}f(x)}{\|\operatorname{grad}f(x)\|},
$$
a směr největšího poklesu je opačný směr. Směr kolmý na gradient dává nulovou směrovou derivaci, proto je gradient kolmý na konstantní hladiny funkce.

Pro graf $z=f(x,y)$ lze psát $F(x,y,z)=f(x,y)-z$. Normála ke grafu je
$$
n=\operatorname{grad}F=\left(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y},-1\right).
$$
Tečná rovina v bodě $(x_0,y_0,z_0)$, kde $z_0=f(x_0,y_0)$, splňuje
$$
(x-x_0,y-y_0,z-z_0)\cdot\left(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y},-1\right)=0.
$$
Zdroj: [[dipocet.pdf#page=68|Diferenciální počet, geometrický význam diferenciálu, s. 68-71]]

> [!todo] DOPLNIT OBRÁZEK: vrstevnice funkce, gradient kolmý na vrstevnici a směr největšího růstu.

## Derivace složené funkce

Nechť
$$
F(s_1,\dots,s_k)=f(\varphi_1(s_1,\dots,s_k),\dots,\varphi_n(s_1,\dots,s_k)).
$$
Jestliže funkce $\varphi_i$ mají totální diferenciál v bodě $s$ a $f$ má totální diferenciál v odpovídajícím bodě $x_0=(\varphi_1(s),\dots,\varphi_n(s))$, potom má $F$ v bodě $s$ totální diferenciál a platí řetězové pravidlo
$$
\frac{\partial F}{\partial s_i}=\frac{\partial f}{\partial x_1}\frac{\partial \varphi_1}{\partial s_i}+\frac{\partial f}{\partial x_2}\frac{\partial \varphi_2}{\partial s_i}+\cdots+\frac{\partial f}{\partial x_n}\frac{\partial \varphi_n}{\partial s_i}.
$$
Ve zkrácené notaci, kdy $x_j=x_j(s_1,\dots,s_k)$:
$$
\frac{\partial F}{\partial s_i}=\sum_{j=1}^n \frac{\partial f}{\partial x_j}\frac{\partial x_j}{\partial s_i}.
$$
Pro křivku $\varphi(t)=(\varphi_1(t),\dots,\varphi_n(t))$ dostaneme
$$
\frac{d}{dt}f(\varphi_1(t),\dots,\varphi_n(t))=\operatorname{grad} f(\varphi(t))\cdot \varphi'(t).
$$
Zdroj: [[dipocet.pdf#page=80|Diferenciální počet, derivace složeného zobrazení, s. 81-87]]

## Lokální extrémy a stacionární body

Funkce $f$ má v bodě $x$ lokální minimum, jestliže existuje okolí $U$ bodu $x$ takové, že
$$
f(x)\le f(y) \quad \text{pro všechna } y\in U.
$$
Analogicky má lokální maximum, jestliže $f(x)\ge f(y)$ v nějakém okolí. Ostrý lokální extrém znamená ostrou nerovnost pro $y\ne x$.

Je-li $f$ třídy $C^1$ na otevřené množině $G\subset\mathbb{R}^n$ a má v bodě $x\in G$ lokální extrém, potom
$$
\frac{\partial f}{\partial h}(x)=0 \quad \text{pro každý směr } h,
$$
a tedy
$$
\operatorname{grad} f(x)=0.
$$
Bod splňující $\operatorname{grad}f(x)=0$ se nazývá stacionární bod. Je to pouze kandidát na extrém, ne záruka extrému. Zdroj: [[dipocet.pdf#page=106|Diferenciální počet, lokální extrémy a stacionární body, s. 107-109]]

## Test druhým diferenciálem

Pro funkci třídy $C^2$ se ve stacionárním bodě $x$ rozhoduje podle kvadratické formy druhého diferenciálu
$$
d^2f(x)[h,h].
$$
Je-li tato kvadratická forma:

- pozitivně definitní, pak má $f$ v $x$ ostré lokální minimum,
- negativně definitní, pak má $f$ v $x$ ostré lokální maximum,
- indefinitní, pak v $x$ lokální extrém není; jde o sedlový bod.

V maticovém zápisu je druhý diferenciál určen Hessovou maticí. Pro rozhodování definitnosti lze použít Sylvestrovo kritérium: pozitivní definitnost odpovídá kladným hlavním subdeterminantům, negativní definitnost střídání znamének od záporného prvního subdeterminantu. Zdroj: [[dipocet.pdf#page=110|Diferenciální počet, kvadratické formy a kritérium pro extrémy, s. 110-113]]

## Vázané extrémy a Lagrangeova metoda

Vázaný extrém znamená, že extrém funkce $f$ hledáme jen na množině $M$ dané vazbami
$$
g_1(x)=0,\dots,g_p(x)=0.
$$
Nechť $f,g_1,\dots,g_p$ jsou třídy $C^1$ na otevřené množině $G\subset\mathbb{R}^n$, $n>p$, a
$$
M=\bigcap_{i=1}^p\{x\in\mathbb{R}^n\mid g_i(x)=0\}\subset G.
$$
Předpokládá se, že vektory
$$
\operatorname{grad}g_1(x),\dots,\operatorname{grad}g_p(x)
$$
jsou lineárně nezávislé ve všech bodech $M$. Je-li $x_0\in M$ bodem lokálního extrému $f$ vzhledem k $M$, potom existují $\lambda_1,\dots,\lambda_p\in\mathbb{R}$ tak, že $x_0$ je stacionární bod Lagrangeovy funkce
$$
L(x)=f(x)-\sum_{i=1}^p \lambda_i g_i(x).
$$
Tedy řešíme soustavu
$$
\operatorname{grad}L(x)=0, \qquad g_1(x)=0,\dots,g_p(x)=0.
$$
Geometricky pro jednu vazbu v rovině: v bodě vázaného extrému je $\operatorname{grad} f$ násobkem normály k vazbě, tedy
$$
\operatorname{grad}f=\lambda\operatorname{grad}g.
$$
Zdroj: [[dipocet.pdf#page=114|Diferenciální počet, vázané extrémy, s. 114-118]]

> [!todo] DOPLNIT OBRÁZEK: vázaný extrém na křivce $g(x,y)=0$, kde je $\operatorname{grad}f$ rovnoběžný s $\operatorname{grad}g$.

## Jak postupovat u příkladu

1. Bez vazby: najít stacionární body z rovnic $\operatorname{grad}f=0$.
2. V každém stacionárním bodě sestavit Hessovu matici a rozhodnout definitnost $d^2f$.
3. S vazbou: sestavit $L=f-\sum \lambda_i g_i$, řešit $\operatorname{grad}L=0$ spolu s vazbami.
4. Pokud se hledá nejmenší nebo největší hodnota na uzavřené omezené množině, zkontrolovat vnitřní stacionární body i hranici; na hranici typicky použít Lagrangeovu metodu.

Tahle otázka souvisí s [[08 Vicerozmerne integraly a integralni vety#Potenciál vektorového pole|potenciálem vektorového pole]], protože potenciální pole je gradient nějaké funkce. Zdroj: [[dipocet.pdf#page=120|Diferenciální počet, vázané extrémy a nejmenší/největší hodnota, s. 120-122]]
