# 10 Fourierovy, Laplaceovy a Z-transformace

**Otázka:** Fourierovy řady, Fourierova a Laplaceova transformace - význam, gramatika, věty o inverzi. Přímá a zpětná transformace Z. Aplikace transformací na řešení diferenciálních a diferenčních rovnic.

> Přehledové srovnání značení a vztahů je v samostatné poznámce [[10a Srovnani transformaci Fourier Laplace Z]].

## Fourierovy řady

Fourierova řada popisuje periodickou funkci pomocí harmonických složek. Je-li $f$ periodická s periodou $T>0$ a $\omega=2\pi/T$, její komplexní Fourierovy koeficienty jsou

$$
c_n=\frac1T\int_a^{a+T} f(t)e^{-in\omega t}\,dt, \qquad n\in\mathbb Z.
$$

Formální Fourierova řada má tvar

$$
\sum_{n=-\infty}^{\infty} c_n e^{in\omega t}.
$$

Pro reálnou funkci platí $c_{-n}=\overline{c_n}$ a řadu lze psát v reálném tvaru

$$
\frac{a_0}{2}+\sum_{n=1}^{\infty}\left(a_n\cos(n\omega t)+b_n\sin(n\omega t)\right),
$$

kde

$$
a_n=\frac2T\int_a^{a+T}f(t)\cos(n\omega t)\,dt, \qquad
b_n=\frac2T\int_a^{a+T}f(t)\sin(n\omega t)\,dt.
$$

Dirichletova věta v podkladu říká, že je-li reálná periodická funkce po částech spojitá a má po částech spojitou derivaci, pak její Fourierova řada v bodě $t$ konverguje k hodnotě

$$
\frac{f(t+)+f(t-)}2.
$$

V bodech spojitosti tedy řada konverguje k $f(t)$. Fourierovy koeficienty jsou jednoznačné pro spojité funkce: pokud mají dvě spojité funkce stejné koeficienty, jsou stejné.

Zdroj: [[transformace.pdf#page=2|transformace, s. 2-5]]

## Fourierova transformace

Fourierova transformace převádí neperiodický signál z časové oblasti do frekvenční oblasti. Pro integrovatelnou funkci $f\in L^1(\mathbb R)$ je přímá Fourierova transformace

$$
\widehat f(\omega)=\int_{-\infty}^{\infty} f(t)e^{-i\omega t}\,dt.
$$

Inverzní Fourierova transformace je

$$
\check f(t)=\frac1{2\pi}\int_{-\infty}^{\infty} f(\omega)e^{i\omega t}\,d\omega.
$$

Hodnota $\widehat f(\omega)$ určuje, jak silně je v signálu zastoupena frekvence $\omega$. Fourierova transformace je spojena s Fourierovou řadou tak, že Fourierovy koeficienty periodické funkce lze získat vzorkováním Fourierovy transformace jedné periody funkce.

Zdroj: [[transformace.pdf#page=7|transformace, s. 7-11]]

## Věta o inverzní Fourierově transformaci

V podkladu jsou uvedeny dvě základní verze inverzní věty. Nechť $f$ je integrovatelná na $\mathbb R$.

Pokud je $f$ spojitá na $\mathbb R$ a $\widehat f\in L^1(\mathbb R)$, potom

$$
f(t)=\frac1{2\pi}\int_{-\infty}^{\infty}\widehat f(\omega)e^{i\omega t}\,d\omega.
$$

Pokud jsou $f$ a $f'$ po částech spojité, potom platí bodová rekonstrukce ve tvaru

$$
\frac{f(t+)+f(t-)}2=
\frac1{2\pi}\int_{-\infty}^{\infty}\widehat f(\omega)e^{i\omega t}\,d\omega.
$$

Tato věta říká, že Fourierova transformace za vhodných podmínek obsahuje úplnou informaci o původním signálu. Dvě spojité funkce z $L^1(\mathbb R)$ se stejnou Fourierovou transformací jsou stejné.

Zdroj: [[transformace.pdf#page=11|transformace, s. 11-15]]

## Gramatika Fourierovy transformace
Základní pravidla umožňují počítat obrazy složitějších funkcí z jednodušších. Je-li $\widehat f=\mathcal F[f]$, potom:

$$
\mathcal F[f(t-a)](\omega)=e^{-i\omega a}\widehat f(\omega),
$$

$$
\mathcal F[f(at)](\omega)=\frac1{|a|}\widehat f\left(\frac{\omega}{a}\right), \qquad a\ne 0,
$$

$$
\mathcal F[e^{iat}f(t)](\omega)=\widehat f(\omega-a).
$$

Podklad dále uvádí pravidlo konjugované reflexe: pro zobrazení $f(t)\mapsto \overline{f(-t)}$ přechází Fourierův obraz na komplexně sdružený obraz,

$$
\mathcal F[\overline{f(-t)}](\omega)=\overline{\widehat f(\omega)}.
$$

Dále platí Riemannovo-Lebesgueovo lemma: je-li $f\in L^1(\mathbb R)$, potom $\widehat f$ je spojitá a

$$
\lim_{\omega\to\pm\infty}\widehat f(\omega)=0.
$$

Pro derivaci platí za podmínek uvedených v podkladu

$$
\mathcal F[f^{(k)}(t)](\omega)=(i\omega)^k\widehat f(\omega).
$$

Pro násobení proměnnou platí

$$
\mathcal F[t^k f(t)](\omega)=i^k\frac{d^k}{d\omega^k}\widehat f(\omega).
$$

Zdroj: [[transformace.pdf#page=15|transformace, s. 15-20]]

## Konvoluce a aplikace Fourierovy transformace

Konvoluce dvou integrovatelných funkcí je

$$
(f*g)(t)=\int_{-\infty}^{\infty} f(\tau)g(t-\tau)\,d\tau.
$$

Fourierova transformace převádí konvoluci na součin:

$$
\widehat{f*g}(\omega)=\widehat f(\omega)\widehat g(\omega).
$$

Toto pravidlo se používá například při filtraci signálů a při řešení diferenciálních rovnic. V podkladu je ukázán postup: diferenciální rovnice se Fourierově transformuje, derivace se změní na násobení mocninou $i\omega$, algebraicky se vyjádří obraz řešení a poté se provede inverze. Například u rovnice

$$
y''(t)-y(t)=e^{-t^2}
$$

se po transformaci získá algebraická rovnice pro $\widehat y(\omega)$ a řešení se vyjádří přes konvoluci.

Fourierova transformace je také kompatibilní se skalárním součinem v $L^2(\mathbb R)$ ve smyslu vztahu

$$
\langle f,g\rangle=\frac1{2\pi}\langle \widehat f,\widehat g\rangle
$$

pro hladké funkce s omezeným nosičem v rozsahu uvedeném v podkladu.

Zdroj: [[transformace.pdf#page=20|transformace, s. 20-24]]

## Laplaceova transformace

Laplaceova transformace je jednostranná integrální transformace. Pro funkci definovanou na $[0,\infty)$ je

$$
\mathcal L[f(t)](s)=F(s)=\int_0^{\infty} f(t)e^{-st}\,dt.
$$

Definiční obor tvoří ta komplexní čísla $s$, pro která integrál existuje. Díky tlumícímu faktoru $e^{-st}$ zvládá Laplaceova transformace i funkce nejvýše exponenciálního růstu. V podkladu se zavádí třída $L_0$: funkce je po částech spojitá a existují $\alpha,M\ge 0$ tak, že

$$
|f(t)|\le M e^{\alpha t}, \qquad t\ge 0.
$$

Typické základní obrazy jsou

$$
\mathcal L[1](s)=\frac1s, \qquad \operatorname{Re}s>0,
$$

$$
\mathcal L[e^{at}](s)=\frac1{s-a}, \qquad \operatorname{Re}s>\operatorname{Re}a,
$$

$$
\mathcal L[\cos t](s)=\frac{s}{s^2+1}, \qquad
\mathcal L[\sin t](s)=\frac1{s^2+1}.
$$

Zdroj: [[transformace.pdf#page=25|transformace, s. 25-27]]

## Gramatika Laplaceovy transformace

Laplaceova transformace je lineární:

$$
\mathcal L[\alpha f_1+\beta f_2](s)=\alpha\mathcal L[f_1](s)+\beta\mathcal L[f_2](s).
$$

Posun v obrazu přes exponenciálu:

$$
\mathcal L[e^{at}f(t)](s)=F(s-a).
$$

Změna měřítka pro $\alpha>0$:

$$
\mathcal L[f(\alpha t)](s)=\frac1\alpha F\left(\frac{s}{\alpha}\right).
$$

Derivace obrazu dává

$$
F'(s)=-\int_0^{\infty} t f(t)e^{-st}\,dt,
$$

tedy zejména

$$
\mathcal L[t f(t)](s)=-F'(s).
$$

Pro posun v čase platí věta o translaci. Je-li $a>0$, pak

$$
\mathcal L[1(t-a)f(t-a)](s)=e^{-as}F(s).
$$

Pro periodickou funkci s periodou $T$ je

$$
F(s)=\frac{\int_0^T f(t)e^{-st}\,dt}{1-e^{-sT}}.
$$

Zdroj: [[transformace.pdf#page=27|transformace, s. 27-33]]

## Laplaceův obraz derivace a diferenciální rovnice

Klíčové pravidlo pro řešení počátečních úloh je obraz $n$-té derivace:

$$
\mathcal L[f^{(n)}(t)](s)=s^nF(s)-s^{n-1}f(0+)-s^{n-2}f'(0+)-\cdots-f^{(n-1)}(0+).
$$

Postup řešení lineární diferenciální rovnice je:

1. Označit $Y(s)=\mathcal L[y(t)](s)$.
2. Transformovat rovnici a počáteční podmínky dosadit přes vzorec pro derivace.
3. Algebraicky vyjádřit $Y(s)$.
4. Najít inverzní Laplaceovu transformaci.

V podkladu je řešen příklad

$$
y''(t)-2y'(t)+2y(t)=e^t, \qquad y(0+)=y'(0+)=1,
$$

kde transformace vede na

$$
(s^2-2s+2)Y(s)=\frac1{s-1}+s-1
$$

a výsledkem je $Y(s)=1/(s-1)$, tedy $y(t)=e^t$.

Toto téma navazuje na [[05 Linearni diferencialni rovnice a soustavy#Lineární diferenciální rovnice vyššího řádu|lineární diferenciální rovnice]] z DRN.

Zdroj: [[transformace.pdf#page=34|transformace, s. 34-35]]

## Inverzní Laplaceova transformace

Inverzní Laplaceovu transformaci lze u racionálních funkcí počítat rozkladem na parciální zlomky. Obecnější pohled dává věta o rozkladu: je-li $F(s)$ holomorfní v okolí nekonečna a má Laurentův rozvoj

$$
F(s)=\sum_{n=1}^{\infty}\frac{a_n}{s^n},
$$

potom je Laplaceovým obrazem funkce

$$
f(t)=\sum_{n=1}^{\infty}\frac{a_n}{(n-1)!}t^{n-1}.
$$

Integrační inverze je dána Riemannovým-Mellinovým vzorcem. Je-li $F$ Laplaceův obraz vhodné funkce $f\in L_0$ s indexem růstu $a$, potom pro $x>a$ platí

$$
\frac{f(t+)+f(t-)}2=\frac1{2\pi i}\int_{x-i\infty}^{x+i\infty} F(s)e^{st}\,ds.
$$

Inverzní Laplaceovu transformaci lze v některých případech počítat také metodou reziduí:

$$
f(t)=\sum_n \operatorname{res}_{s_n}\left(F(s)e^{st}\right),
$$

kde $s_n$ jsou singularity příslušné funkce. Tato metoda přímo používá aparát z [[09 Komplexni funkce integral singularity rezidua#Reziduum|reziduí]].

Zdroj: [[transformace.pdf#page=36|transformace, s. 36-44]]

## Z-transformace

Z-transformace je diskrétní analogie Laplaceovy transformace a používá se pro posloupnosti a diferenční rovnice. Posloupnosti $(a_n)_{n=0}^{\infty}$ přiřazuje funkci

$$
\mathbb Z[a_n](z)=F(z)=\sum_{n=0}^{\infty}\frac{a_n}{z^n}.
$$

Podklad pracuje s posloupnostmi nejvýše exponenciálního růstu, tedy existují $M\ge 0$ a $c\in\mathbb R$ tak, že

$$
|a_n|\le M e^{cn}.
$$

Tato podmínka je ekvivalentní tomu, že řada pro Z-transformaci konverguje v nějakém okolí nekonečna. Z-transformace je prosté zobrazení množiny takových posloupností na množinu funkcí holomorfních v okolí nekonečna s vlastní limitou v nekonečnu.

Základní příklad:

$$
\mathbb Z[a^n](z)=\frac{z}{z-a}, \qquad |z|>|a|.
$$

Zdroj: [[transformace.pdf#page=50|transformace, s. 50-54]]

## Gramatika Z-transformace

Je-li $\mathbb Z[a_n](z)=F(z)$, potom platí:

$$
\mathbb Z[\alpha a_n+\beta b_n](z)=\alpha \mathbb Z[a_n](z)+\beta \mathbb Z[b_n](z),
$$

$$
\mathbb Z[\alpha^n a_n](z)=F\left(\frac z\alpha\right), \qquad \alpha\ne 0,
$$

$$
\mathbb Z[n a_n](z)=-zF'(z).
$$

Posun vpravo: je-li

$$
b_n=\begin{cases}
a_{n-k}, & n\ge k,\\
0, & n<k,
\end{cases}
$$

potom

$$
\mathbb Z[b_n](z)=\frac1{z^k}F(z).
$$

Posun vlevo:

$$
\mathbb Z[a_{n+k}](z)=z^k\left(F(z)-\sum_{n=0}^{k-1}\frac{a_n}{z^n}\right).
$$

Diference posloupnosti je

$$
\Delta a_n=a_{n+1}-a_n
$$

a její obraz je

$$
\mathbb Z[\Delta a_n](z)=(z-1)F(z)-za_0.
$$

Zdroj: [[transformace.pdf#page=54|transformace, s. 54-57]]

## Konvoluce posloupností

Konvoluce posloupností $(a_n)$ a $(b_n)$ je posloupnost $(c_n)$ daná vztahem

$$
c_n=\sum_{k=0}^n a_k b_{n-k}.
$$

Z-transformace převádí konvoluci na součin:

$$
\mathbb Z[c_n](z)=\mathbb Z[a_n](z)\mathbb Z[b_n](z).
$$

Toto je diskrétní obdoba vztahu pro Fourierovu transformaci. V podkladu je konvoluce interpretována také jako odezva lineárního translačně invariantního diskrétního systému: výstup je konvoluce vstupu s odezvou systému na jednotkový impuls.

Pro částečné součty platí

$$
\mathbb Z\left[\sum_{k=0}^{n} a_k\right](z)=\frac{zF(z)}{z-1}.
$$

Zdroj: [[transformace.pdf#page=57|transformace, s. 57-60]]

## Inverzní Z-transformace

Inverzní Z-transformace hledá posloupnost $(a_n)$ z funkce

$$
F(z)=\sum_{n=0}^{\infty}\frac{a_n}{z^n}.
$$

Podklad uvádí tři metody:

1. Přímý rozvoj v Laurentovu řadu v okolí nekonečna.
2. Integrální vyjádření koeficientů:

$$
a_n=\frac1{2\pi i}\int_C F(z)z^{n-1}\,dz,
$$

kde $C$ je kladně orientovaná kružnice ležící v oblasti holomorfnosti obrazu.

3. Přímé vzorce pro počáteční členy, například

$$
a_0=\lim_{z\to\infty}F(z),
$$

$$
a_n=\lim_{z\to\infty} z^n\left(F(z)-\sum_{k=0}^{n-1}\frac{a_k}{z^k}\right).
$$

Pokud jsou splněny předpoklady reziduové věty, lze koeficienty počítat jako součet reziduí funkce $F(z)z^{n-1}$.

Zdroj: [[transformace.pdf#page=60|transformace, s. 60-63]]

## Diferenční rovnice

Z-transformace řeší diferenční rovnice podobně jako Laplaceova transformace řeší diferenciální rovnice. Typický postup je:

1. Označit $Y(z)=\mathbb Z[y_n](z)$.
2. Použít pravidla pro posun vlevo nebo pro diference.
3. Dosadit počáteční podmínky.
4. Vyjádřit $Y(z)$.
5. Provést inverzní Z-transformaci.

Pro rovnici

$$
y_{n+2}+2y_{n+1}+y_n=0, \qquad y_0=y_1=1,
$$

podklad ukazuje transformaci

$$
z^2Y(z)-z^2-z+2zY(z)-2z+Y(z)=0,
$$

tedy

$$
Y(z)=\frac{z^2+3z}{(z+1)^2}.
$$

Inverzí se získá pro $n\ge 1$

$$
y_n=(-1)^n(1-2n),
$$

přičemž $y_0$ je dáno počáteční podmínkou. Podklad uvádí také Fibonacciho posloupnost, kde rovnice

$$
y_{n+2}=y_{n+1}+y_n, \qquad y_0=y_1=1
$$

vede na

$$
Y(z)=\frac{z^2}{z^2-z-1}
$$

a explicitní členy

$$
y_n=\frac1{\sqrt5}\left[\left(\frac{1+\sqrt5}{2}\right)^{n+1}-
\left(\frac{1-\sqrt5}{2}\right)^{n+1}\right].
$$

Zdroj: [[transformace.pdf#page=63|transformace, s. 63-66]]
