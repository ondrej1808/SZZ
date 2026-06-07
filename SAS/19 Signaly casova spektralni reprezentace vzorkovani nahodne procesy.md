# 19 Signály, reprezentace, vzorkování a náhodné procesy

> [!info] Podklady
> Hlavní zdroj: [[sas_cviceni_v0.96_250225.pdf]]. Text je zpracovaný podle cvičebních poznámek SAS, hlavně kapitol 2, 4, 5 a 11.

## Klasifikace signálů

**Signál ve spojitém čase** je funkce spojité proměnné, typicky $s(t)$. **Signál v diskrétním čase** je posloupnost hodnot, typicky $s[k]$. V SAS se soustavně rozlišuje spojité značení $t,\omega$ a diskrétní značení $k,\Omega$. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=59|SAS s. 59]], [[sas_cviceni_v0.96_250225.pdf#page=65|SAS s. 65]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.9cm,y=0.8cm]
    \draw[->] (-0.3,0) -- (6.6,0) node[right] {$t,k$};
    \draw[->] (0,-1.4) -- (0,1.5) node[above] {$s$};
    \draw[color=blue,thick,domain=0:6,samples=100] plot (\x,{sin(1.2*\x r)}) node[right] {$s(t)$};
    \foreach \x/\y in {0/0,1/0.93,2/0.68,3/-0.44,4/-1.00,5/-0.28,6/0.79}
      {
        \draw[color=red,thick] (\x,0) -- (\x,\y);
        \fill[color=red] (\x,\y) circle (1.6pt);
      }
    \node[color=red] at (5.2,1.15) {$s[k]$};
  \end{tikzpicture}
\end{document}
```

**Deterministický signál** má známý průběh popsatelný funkcí. **Stochastický signál** je náhodný a vyžaduje pravděpodobnostní popis. Tato klasifikace je v `hex_compost.pdf` uvedená jako kontrolní osnova otázky SAS. Zdroj: [[hex_compost.pdf#page=200|HEX s. 200]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.85cm,y=0.75cm]
    \draw[->] (-0.2,0) -- (6.6,0) node[right] {$t$};
    \draw[->] (0,-1.5) -- (0,1.7);
    \draw[color=blue,thick,domain=0:6.2,samples=120] plot (\x,{sin(1.6*\x r)});
    \draw[color=orange,thick] plot coordinates {(0,0.1) (0.6,1.0) (1.2,-0.6) (1.8,0.4) (2.4,-1.1) (3.0,0.2) (3.6,1.2) (4.2,-0.4) (4.8,0.8) (5.4,-0.9) (6.0,0.3)};
    \node[color=blue] at (1.8,1.35) {deterministický};
    \node[color=orange] at (4.8,1.35) {stochastický};
  \end{tikzpicture}
\end{document}
```

**Energetický signál** má konečnou energii. Pro spojitý a diskrétní čas:

$$
E=\int_{-\infty}^{\infty}|s(t)|^2\,dt,\qquad
E=\sum_{k=-\infty}^{\infty}|s[k]|^2.
$$

Finitní signál je energetický, opačně to obecně neplatí; například jednostranná exponenciála má konečnou energii, i když není finitní. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=14|SAS s. 14-16]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=1cm,y=0.9cm]
    \draw[->] (-0.5,0) -- (5.2,0) node[right] {$t$};
    \draw[->] (0,-0.2) -- (0,1.7) node[above] {$s(t)$};
    \draw[color=blue,thick] (0,1.2) -- (2.2,1.2) -- (2.2,0);
    \draw[color=blue,thick] (0,0) -- (0,1.2);
    \draw[color=orange,thick,domain=0:5,samples=100] plot (\x,{1.3*exp(-0.75*\x)});
    \node[color=blue] at (1.1,1.45) {finitní puls};
    \node[color=orange] at (3.5,0.65) {$Ae^{-at}1(t)$};
  \end{tikzpicture}
\end{document}
```

**Výkonový signál** má konečný nenulový střední výkon. Pro spojitý čas:

$$
P=\operatorname{Av}\{|s(t)|^2\}
=\lim_{T\to\infty}\frac{1}{2T}\int_{-T}^{T}|s(t)|^2\,dt.
$$

Periodický signál je výkonový a u periodických signálů se průměr může počítat přes jednu periodu. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=16|SAS s. 16-18]].

```tikz
\begin{document}
  \begin{tikzpicture}[domain=0:6.3,x=0.9cm,y=0.9cm]
    \draw[->] (-0.2,0) -- (6.7,0) node[right] {$t$};
    \draw[->] (0,-1.4) -- (0,1.5) node[above] {$s(t)$};
    \draw[color=blue,thick,samples=120] plot (\x,{sin(2*\x r)});
    \draw[dashed] (3.14,-1.2) -- (3.14,1.2);
    \node at (1.57,-1.25) {$T_0$};
    \node[color=blue] at (4.8,1.15) {periodický výkonový signál};
  \end{tikzpicture}
\end{document}
```

## Speciální signály

**Jednotkový skok** $1(t)$, respektive $1[k]$, je nulový před počátkem a jednotkový od počátku. V PDF se používá například u signálu $s(t)=1(t)$ a $s[k]=Aa^k1[k]$. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=16|SAS s. 16]], [[sas_cviceni_v0.96_250225.pdf#page=16|SAS s. 16]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=1cm,y=0.9cm]
    \draw[->] (-2.2,0) -- (3.2,0) node[right] {$t$};
    \draw[->] (0,-0.2) -- (0,1.6) node[above] {$1(t)$};
    \draw[color=blue,thick] (-2,0) -- (0,0);
    \draw[color=blue,thick] (0,1) -- (3,1);
    \fill[color=blue] (0,1) circle (1.5pt);
    \draw[color=blue,fill=white] (0,0) circle (1.5pt);
  \end{tikzpicture}
\end{document}
```

**Diracův impuls** $\delta(t)$ a **jednotkový impuls** $\delta[k]$ jsou základní buzení pro impulsovou odezvu LTI soustavy. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=107|SAS s. 107]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=1cm,y=0.9cm]
    \draw[->] (-2.2,0) -- (3.2,0) node[right] {$t,k$};
    \draw[->] (0,-0.2) -- (0,1.8);
    \draw[color=blue,very thick,->] (0,0) -- (0,1.4) node[above] {$\delta(t)$};
    \foreach \x in {-2,-1,1,2,3} \fill (\x,0) circle (1pt);
    \fill[color=red] (0,1.0) circle (1.6pt);
    \node[color=red] at (1.1,1.05) {$\delta[k]$};
  \end{tikzpicture}
\end{document}
```

## Autokorelace

**Autokorelační funkce energetického signálu** měří podobnost signálu s posunutou kopií:

$$
R(\tau)=\int_{-\infty}^{\infty}s(t+\tau)s^*(t)\,dt.
$$

U výkonového signálu se místo integrálu přes celý čas používá časový průměr:

$$
R(\tau)=\operatorname{Av}\{s(t+\tau)s^*(t)\}.
$$

Pro periodický výkonový signál se průměr redukuje na jednu periodu. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=19|SAS s. 19]], [[sas_cviceni_v0.96_250225.pdf#page=50|SAS s. 50]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.9cm,y=0.9cm]
    \draw[->] (-3.2,0) -- (3.4,0) node[right] {$\tau$};
    \draw[->] (0,-0.2) -- (0,1.7) node[above] {$R(\tau)$};
    \draw[color=blue,thick] (-2,0) -- (0,1.2) -- (2,0);
    \node[color=blue] at (1.8,1.25) {ACF pulsu};
    \node at (0,-0.25) {$0$};
  \end{tikzpicture}
\end{document}
```

Hodnota $R(0)$ odpovídá energii energetického signálu nebo výkonu výkonového signálu; v příkladech PDF se výkon počítá jako $P=R(0)$. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=51|SAS s. 51]], [[sas_cviceni_v0.96_250225.pdf#page=61|SAS s. 61]].

## Spektrální reprezentace signálů

Čtyři základní Fourierovy reprezentace se volí podle toho, zda je signál spojitý/diskrétní a periodický/neperiodický.

Podrobnější srovnávací mapa je v samostatné poznámce [[19a Srovnani spektralnich reprezentaci signalu]].

| Signál                 | Reprezentace                  | Přímý vztah                                                     | Inverzní vztah                                                              |
| ---------------------- | ----------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------------- |
| spojitý periodický     | Fourierova řada FS            | $c_n=\frac{1}{T_0}\int_{(T_0)}s(t)e^{-jn\omega_0t}\,dt$         | $s(t)=\sum_{n=-\infty}^{\infty}c_ne^{jn\omega_0t}$                          |
| spojitý neperiodický   | Fourierova transformace FT    | $S(\omega)=\int_{-\infty}^{\infty}s(t)e^{-j\omega t}\,dt$       | $s(t)=\frac{1}{2\pi}\int_{-\infty}^{\infty}S(\omega)e^{j\omega t}\,d\omega$ |
| diskrétní periodický   | diskrétní Fourierova řada DFS | $d_n=\frac{1}{N_0}\sum_{k=k_p}^{k_p+N_0-1}s[k]e^{-jn\Omega_0k}$ | $s[k]=\sum_{n=n_p}^{n_p+N_0-1}d_ne^{jn\Omega_0k}$                           |
| diskrétní neperiodický | DtFT                          | $S(\Omega)=\sum_{k=-\infty}^{\infty}s[k]e^{-j\Omega k}$         | $s[k]=\frac{1}{2\pi}\int_{(2\pi)}S(\Omega)e^{j\Omega k}\,d\Omega$           |

Zdroje: [[sas_cviceni_v0.96_250225.pdf#page=50|SAS s. 50]], [[sas_cviceni_v0.96_250225.pdf#page=53|SAS s. 53]], [[sas_cviceni_v0.96_250225.pdf#page=59|SAS s. 59]], [[sas_cviceni_v0.96_250225.pdf#page=65|SAS s. 65]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.75cm,y=0.75cm]
    \draw[->] (-3.2,0) -- (3.4,0) node[right] {$n,\omega,\Omega$};
    \draw[->] (0,-0.2) -- (0,2.0);
    \foreach \x/\h in {-2/0.7,-1/1.2,0/1.7,1/1.2,2/0.7}
      {
        \draw[color=blue,very thick] (\x,0) -- (\x,\h);
        \fill[color=blue] (\x,\h) circle (1.5pt);
      }
    \draw[color=orange,thick,domain=-3:3,samples=100] plot (\x,{1.5*exp(-0.35*\x*\x)});
    \node[color=blue] at (-2.1,1.65) {čárové spektrum};
    \node[color=orange] at (2.0,1.55) {spojité spektrum};
  \end{tikzpicture}
\end{document}
```

**Výkonové spektrum periodického signálu** je dáno kvadráty absolutních hodnot koeficientů Fourierovy řady, například $|c_n|^2$ nebo $|d_n|^2$. Výkon lze získat jako součet výkonového spektra. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=51|SAS s. 51]], [[sas_cviceni_v0.96_250225.pdf#page=60|SAS s. 60]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.8cm,y=0.8cm]
    \draw[->] (-3.2,0) -- (3.4,0) node[right] {$n$};
    \draw[->] (0,-0.2) -- (0,2) node[above] {$|c_n|^2$};
    \foreach \x/\h in {-1/0.7,0/1.6,1/0.7}
      {
        \draw[color=blue,very thick] (\x,0) -- (\x,\h);
        \fill[color=blue] (\x,\h) circle (1.5pt);
      }
  \end{tikzpicture}
\end{document}
```

## Vzorkování

**Vzorkování periodického signálu** převádí $s(t)$ na $s[k]=s(kT_{sa})$, kde $T_0/T_{sa}=N_0$. Spektra souvisejí vztahem

$$
d_n=\sum_{m=-\infty}^{\infty}c_{n-mN_0}.
$$

Je-li spojitý periodický signál spektrálně omezený tak, že $c_n=0$ pro $|n|>N_m$, pak stačí

$$
N_0\ge 2N_m+1,\qquad \omega_{sa}\ge \omega_0(2N_m+1).
$$

Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=78|SAS s. 78]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.75cm,y=0.75cm]
    \draw[->] (-0.3,0) -- (7.2,0) node[right] {$t$};
    \draw[->] (0,-1.4) -- (0,1.6) node[above] {$s$};
    \draw[color=blue,thick,domain=0:6.3,samples=120] plot (\x,{sin(2*\x r)+0.35*cos(4*\x r)});
    \foreach \x/\y in {0/0.35,1/1.20,2/-0.52,3/-0.47,4/1.16,5/0.07,6/-1.29}
      {
        \draw[color=red,thick] (\x,0) -- (\x,\y);
        \fill[color=red] (\x,\y) circle (1.5pt);
      }
    \node[color=red] at (5.7,1.35) {$s[k]$};
  \end{tikzpicture}
\end{document}
```

**Vzorkování neperiodického signálu** vede ke spektru vzorků

$$
S_d(\Omega)=\frac{1}{T_{sa}}\sum_{m=-\infty}^{\infty}
S_s\left(\frac{\Omega}{T_{sa}}-m\omega_{sa}\right).
$$

Je-li $S(\omega)=0$ pro $|\omega|>\omega_m$, pak vzorkovací podmínka je $\omega_{sa}>2\omega_m$; příklady v PDF pak pracují s hraniční volbou $\omega_{sa}=2\omega_m$ jako nejmenší ideální hodnotou. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=82|SAS s. 82]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.85cm,y=0.75cm]
    \draw[->] (-4.2,0) -- (4.4,0) node[right] {$\omega$};
    \draw[->] (0,-0.2) -- (0,1.7) node[above] {$S_s$};
    \draw[color=blue,thick] (-1.2,0) -- (-0.8,1.1) -- (0,1.35) -- (0.8,1.1) -- (1.2,0);
    \draw[color=orange,thick,dashed] (-3.7,0) -- (-3.3,0.8) -- (-2.5,1.0) -- (-1.7,0.8) -- (-1.3,0);
    \draw[color=orange,thick,dashed] (1.3,0) -- (1.7,0.8) -- (2.5,1.0) -- (3.3,0.8) -- (3.7,0);
    \node at (-1.2,-0.25) {$-\omega_m$};
    \node at (1.2,-0.25) {$\omega_m$};
    \node[color=orange] at (2.7,1.45) {repliky};
  \end{tikzpicture}
\end{document}
```

## Náhodné procesy

**Náhodný proces** je v SAS chápán jako náhodný signál; důležitou třídou jsou stacionární procesy, jejichž pravděpodobnostní vlastnosti jsou invariantní vůči časovému posunu. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=163|SAS s. 163]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.85cm,y=0.75cm]
    \draw[->] (-0.2,0) -- (6.6,0) node[right] {$t$};
    \draw[->] (0,-1.6) -- (0,1.7) node[above] {$X(t)$};
    \draw[color=blue,thick] plot coordinates {(0,0.2) (0.7,1.1) (1.4,-0.8) (2.1,0.6) (2.8,-1.2) (3.5,-0.1) (4.2,1.0) (4.9,0.1) (5.6,-0.7) (6.3,0.5)};
    \draw[color=orange,thick,dashed] plot coordinates {(0,-0.4) (0.7,0.5) (1.4,1.2) (2.1,-0.7) (2.8,0.2) (3.5,1.3) (4.2,-0.5) (4.9,-1.1) (5.6,0.6) (6.3,-0.2)};
    \node[color=blue] at (4.8,1.45) {realizace};
  \end{tikzpicture}
\end{document}
```

**SSS stacionarita** vyžaduje invarianci hustot pravděpodobnosti vůči posunu času. Z PDF plyne například

$$
\forall\tau:\operatorname{pdf}_X(\xi;t)=\operatorname{pdf}_X(\xi;t+\tau),
$$

a analogická podmínka pro sdruženou hustotu ve dvou časech. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=163|SAS s. 163]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.9cm,y=0.8cm]
    \draw[->] (-0.2,0) -- (6.2,0) node[right] {$t$};
    \draw[->] (0,-0.2) -- (0,1.7);
    \draw[color=blue,thick] (0.5,0.5) -- (1.0,1.1) -- (1.5,0.4) -- (2.0,1.0) -- (2.5,0.6);
    \draw[color=blue,thick] (3.2,0.5) -- (3.7,1.1) -- (4.2,0.4) -- (4.7,1.0) -- (5.2,0.6);
    \draw[->,gray] (2.2,1.35) -- (3.3,1.35) node[midway,above] {$\tau$};
    \node at (1.5,-0.25) {stejné statistiky};
    \node at (4.2,-0.25) {po posunu};
  \end{tikzpicture}
\end{document}
```

**WSS stacionarita** je slabší podmínka:

$$
\mu_X(t)=\mu_X=\text{konst.},\qquad
R_X(t_1,t_2)=R_X(t_1-t_2).
$$

Bez explicitních požadavků na hustotu pravděpodobnosti. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=163|SAS s. 163]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.85cm,y=0.75cm]
    \draw[->] (-3.2,0) -- (3.4,0) node[right] {$\tau=t_1-t_2$};
    \draw[->] (0,-0.2) -- (0,1.7) node[above] {$R_X(\tau)$};
    \draw[color=blue,thick,domain=-3:3,samples=100] plot (\x,{1.3*exp(-0.45*\x*\x)});
    \draw[dashed] (-3,0.45) -- (3,0.45) node[right] {$\mu_X$ konst.};
  \end{tikzpicture}
\end{document}
```

**Ergodicita vůči střední hodnotě nebo autokorelaci** znamená, že časová střední hodnota $m_X$, respektive časová autokorelace, už nejsou náhodné a rovnají se odpovídajícím pravděpodobnostním charakteristikám. Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=164|SAS s. 164]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.85cm,y=0.75cm]
    \draw[->] (-0.2,0) -- (6.6,0) node[right] {$t$};
    \draw[->] (0,-1.3) -- (0,1.5) node[above] {$X(t)$};
    \draw[color=blue,thick] plot coordinates {(0,0.4) (0.8,1.0) (1.6,-0.9) (2.4,0.7) (3.2,-0.2) (4.0,0.9) (4.8,-0.8) (5.6,0.1) (6.3,0.5)};
    \draw[color=red,thick,dashed] (0,0.2) -- (6.3,0.2) node[right] {$m_X$};
    \node[color=red] at (3.2,-1.05) {časový průměr jedné realizace};
  \end{tikzpicture}
\end{document}
```

**Výkonová spektrální hustota stacionárního procesu** je Fourierova transformace autokorelační funkce:

$$
S_X(\omega)=\mathcal F_{\tau\to\omega}\{R_X(\tau)\},\qquad
S_X(\Omega)=\mathcal F_{m\to\Omega}\{R_X[m]\}.
$$

Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=164|SAS s. 164]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.78cm,y=0.72cm]
    \draw[->] (-3.2,0) -- (3.4,0) node[right] {$\omega$};
    \draw[->] (0,-0.2) -- (0,1.8) node[above] {$S_X(\omega)$};
    \draw[color=blue,thick,domain=-3:3,samples=100] plot (\x,{1.3/(1+\x*\x)});
    \node[color=blue] at (1.9,1.35) {PSD};
  \end{tikzpicture}
\end{document}
```

**Bílý šum** je definovaný konstantním spektrem; pro spojitý a diskrétní případ PDF uvádí:

$$
S_X(\omega)=\frac{\eta}{2}\Rightarrow R_X(\tau)=\frac{\eta}{2}\delta(\tau),
\qquad
S_X(\Omega)=\sigma^2\Rightarrow R_X[m]=\sigma^2\delta[m].
$$

Zdroj: [[sas_cviceni_v0.96_250225.pdf#page=165|SAS s. 165]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.75cm,y=0.75cm]
    \draw[->] (-3.2,0) -- (3.4,0) node[right] {$\omega,\Omega$};
    \draw[->] (0,-0.2) -- (0,1.8) node[above] {$S_X$};
    \draw[color=blue,thick] (-3,1.0) -- (3,1.0);
    \node[color=blue] at (2.1,1.35) {konstanta};
    \begin{scope}[shift={(0,-2.0)}]
      \draw[->] (-3.2,0) -- (3.4,0) node[right] {$\tau,m$};
      \draw[->] (0,-0.2) -- (0,1.6) node[above] {$R_X$};
      \draw[color=red,very thick,->] (0,0) -- (0,1.25);
      \node[color=red] at (1.2,1.0) {$\delta$};
    \end{scope}
  \end{tikzpicture}
\end{document}
```

## Kontrolní shrnutí

- Spojitý čas používá $t,\omega$, diskrétní čas $k,\Omega$.
- Energetický signál má konečné $E$, výkonový signál má konečné nenulové $P$.
- $R(0)$ dává energii nebo výkon podle typu signálu.
- FS a DFS mají čárová spektra; FT a DtFT pracují se spojitým kmitočtem.
- Vzorkování bez ztráty vyžaduje nepřekrytí spektrálních replik.
- WSS proces má konstantní střední hodnotu a autokorelaci závislou jen na časovém rozdílu.
