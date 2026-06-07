# 23 Konvoluce, DFT, váhování, časově-frekvenční analýza, filtry a kvantování

> Hlavní podklady: [[b2b31czs_pr3_DFT_HANDOUT.pdf]], [[b2b31czs_pr4_spectrum_HANDOUT.pdf]], [[b2b31czs_pr6_filters_II_HANDOUT.pdf]], [[b2b31czs_pr8_FIR_HANDOUT.pdf]], [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf]], [[b2b31czs_pr1_HANDOUT.pdf]]. Znění okruhu: [[SZZ - Odborné okruhy|odborný okruh 23]].

## Lineární konvoluce

Lineární konvoluce diskrétních signálů popisuje výstup LTI systému s impulzní odezvou $h[n]$:

$$
y[n]=h[n]*x[n]=\sum_k h[k]x[n-k].
$$

Pro FIR filtr řádu $M$ má impulzní odezva délku $M+1$ a vstupní úsek $x[n]$ délku $N$. Výsledek lineární konvoluce má délku $N+M$ a skládá se z náběhu, hlavní části a odeznívání. Zdroj: [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=9|CZS 9 s. 9]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.13cm,y=0.55cm]
    \draw[->] (-3,0) -- (62,0) node[right] {$n$};
    \draw[thick,blue] (0,0) -- (0,1) -- (34,1) -- (34,0);
    \draw[thick,orange] (0,0) -- (0,1.7) -- (10,1.7) -- (10,0);
    \draw[thick,green!55!black] (0,0) -- (0,0.45) -- (44,0.45) -- (44,0);
    \draw[dashed] (10,-0.2) -- (10,2.0);
    \draw[dashed] (34,-0.2) -- (34,1.3);
    \draw[dashed] (44,-0.2) -- (44,0.8);
    \node[blue] at (17,1.25) {$x[n]$, délka $N$};
    \node[orange] at (5,1.95) {$h[n]$, délka $M+1$};
    \node[green!55!black] at (26,0.72) {$y[n]$, délka $N+M$};
    \node at (5,-0.45) {náběh};
    \node at (22,-0.45) {hlavní část};
    \node at (39,-0.45) {odeznívání};
  \end{tikzpicture}
\end{document}
```

## Cyklická konvoluce a DFT

Konvoluce v časové oblasti odpovídá násobení spekter:

$$
Y(e^{j\theta})=H(e^{j\theta})X(e^{j\theta}).
$$

Při výpočtu pomocí DFT se ale pracuje s periodicky prodlouženými posloupnostmi. DFT vztah

$$
Y[k]=H[k]X[k]
$$

dává cyklickou konvoluci s periodou $N_{\mathrm{DFT}}$. Pokud se použije $N_{\mathrm{DFT}}=N$, úvodní část výstupu je chybná kvůli periodickému přetočení odezvy. Aby výsledek odpovídal lineární konvoluci, musí platit

$$
N_{\mathrm{DFT}}\ge N+M.
$$

Potom se $x[n]$ i $h[n]$ doplní nulami a cyklická konvoluce dá stejné vzorky jako lineární konvoluce. Zdroj: [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=8|CZS 9 s. 8]], [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=10|CZS 9 s. 10]], [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=12|CZS 9 s. 12]].

```tikz
\begin{document}
  \begin{tikzpicture}[node distance=1.15cm,>=latex]
    \node[draw,minimum width=1.4cm] (x) {$x[n]$};
    \node[draw,below=of x,minimum width=1.4cm] (h) {$h[n]$};
    \node[draw,right=of x] (fftx) {FFT};
    \node[draw,right=of h] (ffth) {FFT};
    \node[draw,right=1.25cm of fftx] (mul) {$\times$};
    \node[draw,right=of mul] (ifft) {IFFT};
    \node[draw,right=of ifft] (y) {$y[n]$};
    \draw[->] (x) -- (fftx);
    \draw[->] (h) -- (ffth);
    \draw[->] (fftx) -- node[above] {$X[k]$} (mul);
    \draw[->] (ffth) -| node[pos=0.25,below] {$H[k]$} (mul);
    \draw[->] (mul) -- node[above] {$Y[k]$} (ifft);
    \draw[->] (ifft) -- (y);
    \node[below=0.25cm of ffth] {$N_{\mathrm{DFT}}\ge N+M$};
  \end{tikzpicture}
\end{document}
```

## Zpracování dlouhých signálů

Pro velmi dlouhé nebo online signály nestačí spočítat jednu velkou FFT. Signál se segmentuje a používá se krátkodobá cyklická konvoluce. U metody OLS se segmenty překrývají o $M$ vzorků a chybná úvodní část každého výstupního segmentu se zahodí. U metody OLA se vstupní segmenty nepřekrývají, doplní se nulami na délku $N+M$ a překrývající se výstupní části se sečtou. Zdroj: [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=19|CZS 9 s. 19]], [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=23|CZS 9 s. 23]], [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=25|CZS 9 s. 25]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.8cm,y=0.8cm]
    \draw[->] (0,0) -- (8.4,0) node[right] {$n$};
    \foreach \x in {0,2,4,6}
      \draw[thick,blue] (\x,0.15) rectangle +(2.4,0.35);
    \node[blue] at (4.2,0.85) {OLS: překryv, zahodit chybný začátek};
    \draw[->] (0,-1.2) -- (8.4,-1.2) node[right] {$n$};
    \foreach \x in {0,2,4,6}
      \draw[thick,orange] (\x,-1.05) rectangle +(2.8,0.35);
    \foreach \x in {2,4,6}
      \node at (\x+0.35,-0.82) {$+$};
    \node[orange] at (4.2,-0.45) {OLA: doplnění nulami, sečíst přesahy};
  \end{tikzpicture}
\end{document}
```

FFT varianta má smysl hlavně pro delší impulzní odezvy. Handout uvádí, že pro krátké impulzní odezvy nemusí být cyklická konvoluce efektivní, zvlášť u reálných signálů kvůli komplexním operacím FFT. Zdroj: [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=13|CZS 9 s. 13]], [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=17|CZS 9 s. 17]].

## DFT a její vlastnosti

N-bodová DFT převádí $N$ vzorků diskrétního časového signálu na $N$ vzorků diskrétního spektra:

$$
S[k]=\sum_{n=0}^{N-1}s[n]e^{-j\frac{2\pi}{N}kn},
\qquad
s[n]=\frac{1}{N}\sum_{k=0}^{N-1}S[k]e^{j\frac{2\pi}{N}kn}.
$$

Spektrum je periodické, diskrétní ve frekvenci a pro reálný signál komplexně symetrické:

$$
X[k]=X^*[(-k)_N].
$$

Frekvenční krok je

$$
\Delta f=\frac{f_s}{N}, \qquad f_k=k\Delta f.
$$

N-tá spektrální čára už není nová hodnota, ale periodické opakování stejnosměrné složky. Zdroj: [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=9|CZS 3 s. 9]], [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=10|CZS 3 s. 10]], [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=11|CZS 3 s. 11]].

Mezi základní vlastnosti DFT patří linearita, dualita, komplexní sdružení, obraz cyklické konvoluce a obraz násobení. Cyklická konvoluce v čase odpovídá násobení DFT spekter, zatímco násobení v čase odpovídá cyklické konvoluci spekter. Zdroj: [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=12|CZS 3 s. 12]].

## FFT

Přímý výpočet DFT má řádově $N^2$ komplexních násobení a sčítání. FFT využívá periodicitu komplexní exponenciály a rozdělení vstupu, například decimaci v čase na sudé a liché vzorky. Pro $N=2^m$ jsou nároky

$$
\frac{N}{2}\log_2N
$$

komplexních násobení a

$$
N\log_2N
$$

komplexních sčítání. Zdroj: [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=71|CZS 3 s. 71]], [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=72|CZS 3 s. 72]], [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=77|CZS 3 s. 77]].

## Váhování a prosakování spektra

DFT se vždy počítá z konečného úseku signálu. Výběr úseku je násobení oknem $w[n]$:

$$
s_w[n]=s[n]w[n].
$$

Ve frekvenční oblasti to odpovídá konvoluci se spektrem okna:

$$
S_w(e^{j\theta})=S(e^{j\theta})*W(e^{j\theta}).
$$

Prosakování vzniká kvůli postranním lalokům frekvenční charakteristiky okna. Zvonová okna tlumí okraje segmentu a zmenšují postranní laloky, ale rozšiřují hlavní lalok, tedy zhoršují schopnost rozlišit blízké frekvence. Zdroj: [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=23|CZS 3 s. 23]].

| Okno | Šířka hlavního laloku | Pokles postranního laloku |
|---|---:|---:|
| obdélníkové | $\Delta f$ | $-13\,\mathrm{dB}$ |
| trojúhelníkové | $2\Delta f$ | $-26\,\mathrm{dB}$ |
| Hannovo | $2\Delta f$ | $-31\,\mathrm{dB}$ |
| Hammingovo | $2\Delta f$ | $-43\,\mathrm{dB}$ |
| Blackmanovo | $3\Delta f$ | $-58\,\mathrm{dB}$ |

Zdroj: [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=27|CZS 3 s. 27]], [[b2b31czs_pr3_DFT_HANDOUT.pdf#page=28|CZS 3 s. 28]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=1cm,y=0.75cm]
    \draw[->] (-3.2,0) -- (3.4,0) node[right] {$f$};
    \draw[->] (0,-0.2) -- (0,2.5) node[above] {$|W(f)|$};
    \draw[blue,thick,domain=-3:3,samples=160] plot (\x,{2.1*abs(sin(2.4*\x r)/(2.4*\x+0.001))});
    \draw[orange,thick,domain=-3:3,samples=160] plot (\x,{2.0*exp(-1.15*\x*\x)});
    \node[blue] at (-2.0,1.7) {obdélníkové};
    \node[orange] at (2.0,1.7) {zvonové};
    \node at (0.9,0.45) {širší hlavní lalok};
  \end{tikzpicture}
\end{document}
```

## Časově-frekvenční analýza

U nestacionárního signálu se spektrum mění v čase, proto se používá spektrogram. Signál se rozdělí na krátkodobé segmenty, segmenty se mohou váhovat a překrývat, pro každý segment se spočítá DFT periodogram a periodogramy se sledují v čase. Zdroj: [[b2b31czs_pr4_spectrum_HANDOUT.pdf#page=32|CZS 4 s. 32]].

Rozlišení je omezené délkou segmentu:

$$
\Delta f=\frac{f_s}{N}, \qquad \Delta t=N.
$$

Delší segment dává lepší frekvenční rozlišení a horší časové rozlišení. Kratší segment dává horší frekvenční rozlišení a lepší časové rozlišení. Krok segmentace $M=N-N_{\mathrm{overlap}}$ určuje hustotu vykreslení, ale časové rozlišení je dáno hlavně délkou segmentu $N$. Zdroj: [[b2b31czs_pr4_spectrum_HANDOUT.pdf#page=35|CZS 4 s. 35]], [[b2b31czs_pr4_spectrum_HANDOUT.pdf#page=38|CZS 4 s. 38]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.95cm,y=0.75cm]
    \draw[->] (0,0) -- (7,0) node[right] {$t$};
    \draw[->] (0,0) -- (0,4.2) node[above] {$f$};
    \foreach \x/\y/\c in {0.6/0.8/blue,1.1/1.2/blue,1.7/1.6/blue,2.4/2.2/orange,3.0/2.7/orange,3.7/3.1/orange,4.5/2.3/green!60!black,5.2/1.6/green!60!black,5.9/1.0/green!60!black}
      \fill[\c] (\x,\y) rectangle +(0.55,0.28);
    \draw[dashed] (2.2,0) -- (2.2,4);
    \draw[dashed] (4.3,0) -- (4.3,4);
    \node at (1.1,-0.35) {segment};
    \node at (3.2,-0.35) {segment};
    \node at (5.3,-0.35) {segment};
  \end{tikzpicture}
\end{document}
```

## Číslicové filtry

FIR filtr řádu $M$ je popsán diferenční rovnicí

$$
y[n]=b_0x[n]+b_1x[n-1]+\cdots+b_Mx[n-M],
$$

impulzní odezvou

$$
h[n]=\sum_{k=0}^{M}b_k\delta[n-k],
$$

a přenosovou funkcí

$$
H(z)=\sum_{k=0}^{M}b_kz^{-k}.
$$

Koeficienty FIR filtru jsou přímo vzorky impulzní odezvy: $b_k=h[k]$. FIR filtry mají póly v nule, jsou vždy stabilní a při symetrické impulzní odezvě mají lineární fázi. Zdroj: [[b2b31czs_pr8_FIR_HANDOUT.pdf#page=3|CZS 8 s. 3]], [[b2b31czs_pr8_FIR_HANDOUT.pdf#page=4|CZS 8 s. 4]], [[b2b31czs_pr8_FIR_HANDOUT.pdf#page=6|CZS 8 s. 6]].

IIR filtry mají zpětnou vazbu. Obecně dosáhnou dané modulové charakteristiky nižším řádem a menším zpožděním než FIR, ale mohou být nestabilní, mají nelineární fázi a jsou citlivější na kvantování koeficientů i mezivýsledků. Zdroj: [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=6|CZS 9 s. 6]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=1cm,y=0.8cm,>=latex]
    \node at (0,1.2) {$x[n]$};
    \draw[->] (0.5,1.2) -- (1.2,1.2);
    \foreach \i in {0,1,2}
      {
        \draw[->] (1.2+\i*1.2,1.2) -- +(0.8,0);
        \node[draw,minimum width=0.7cm] at (2.0+\i*1.2,1.2) {$z^{-1}$};
      }
    \foreach \i/\b in {0/$b_0$,1/$b_1$,2/$b_2$,3/$b_M$}
      {
        \draw[->] (1.0+\i*1.2,1.2) -- +(0,-0.75);
        \node at (1.0+\i*1.2,0.25) {\b};
        \draw[->] (1.0+\i*1.2,0.05) -- (5.3,0.05);
      }
    \node[draw,circle] at (5.6,0.05) {$+$};
    \draw[->] (5.9,0.05) -- (6.7,0.05) node[right] {$y[n]$};
    \node at (3,-0.65) {transverzální FIR struktura};
  \end{tikzpicture}
\end{document}
```

## Kvantování a jeho důsledky

Vzorkování diskretizuje čas: $x(t)\to x[n]$. Kvantování diskretizuje hodnotu vzorku: $x[n]\to x_d[n]$. Číslicová reprezentace proto závisí na počtu bitů na vzorek a na vzorkovací frekvenci. Zdroj: [[b2b31czs_pr1_HANDOUT.pdf#page=12|CZS 1 s. 12]], [[b2b31czs_pr1_HANDOUT.pdf#page=13|CZS 1 s. 13]].

U realizace filtrů je důležité kvantování koeficientů a mezivýsledků. FIR filtry jsou vůči kvantování koeficientů méně citlivé a při kvantování mezivýsledků u nich nevznikají limitní cykly. IIR filtry jsou citlivější, kvantování koeficientů může vést i k nestabilitě a kvantování mezivýsledků může kvůli zpětné vazbě způsobit limitní cykly. Zdroj: [[b2b31czs_pr9_FiltFrek_HANDOUT.pdf#page=6|CZS 9 s. 6]].

## Vazby na další otázky

Okruh navazuje na [[SAS/19 Signaly casova spektralni reprezentace vzorkovani nahodne procesy|SAS 19]] kvůli Fourierovým reprezentacím, vzorkování a náhodným procesům. Na [[24 Filtrace ve frekvencni oblasti prevzorkovani banky filtru odhady analyza predikce]] navazuje přes frekvenční filtraci, OLA s obecným oknem, Welchův odhad PSD, korelační analýzu a převzorkování.
