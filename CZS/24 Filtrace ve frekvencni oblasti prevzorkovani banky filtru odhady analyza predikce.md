# 24 Frekvenční filtrace, převzorkování, banky filtrů, odhady, spektrální a korelační analýza, modelování a predikce

> Hlavní podklady: [[b2b31czs_pr10_OLA_general_HANDOUT.pdf]], [[b2b31czs_pr11_multirate_HANDOUT.pdf]], [[b2b31czs_pr12_multirate_apps_recurrent_HANDOUT.pdf]], [[b2b31czs_pr4_spectrum_HANDOUT.pdf]], [[b2b31czs_pr2_correlation_HANDOUT.pdf]]. Znění okruhu: [[SZZ - Odborné okruhy|odborný okruh 24]].

## Filtrace ve frekvenční oblasti

Pokud je impulzní odezva známá, lze FIR filtraci realizovat přes krátkodobou cyklickou konvoluci:

$$
X[k]=\mathrm{FFT}_{N_{\mathrm{FFT}}}\{x[n]\},\qquad
H[k]=\mathrm{FFT}_{N_{\mathrm{FFT}}}\{h[n]\},
$$

$$
Y[k]=H[k]X[k],\qquad
y[n]=\mathrm{IFFT}_{N_{\mathrm{FFT}}}\{Y[k]\}.
$$

Pro krátký blok musí být $N_{\mathrm{FFT}}\ge N+M$, kde $M+1$ je délka impulzní odezvy. Pro dlouhé signály se používá segmentace, OLS nebo OLA. Zdroj: [[b2b31czs_pr10_OLA_general_HANDOUT.pdf#page=3|CZS 10 s. 3]], [[b2b31czs_pr10_OLA_general_HANDOUT.pdf#page=4|CZS 10 s. 4]].

U neznámé impulzní odezvy se pracuje přímo s krátkodobým spektrem. Používá se ručně definovaná frekvenční charakteristika, nulování vybraných komponent, tabulka hodnot masky, spektrální prahování nebo spektrální odečítání. Výhodou je, že každý krátkodobý segment může mít jinou modifikaci podle aktuálního spektra. Zdroj: [[b2b31czs_pr10_OLA_general_HANDOUT.pdf#page=15|CZS 10 s. 15]].

```tikz
\begin{document}
  \begin{tikzpicture}[node distance=1cm,>=latex]
    \node[draw] (seg) {segment};
    \node[draw,right=of seg] (win) {okno};
    \node[draw,right=of win] (fft) {FFT};
    \node[draw,right=of fft] (mask) {$H_i[k]$};
    \node[draw,right=of mask] (ifft) {IFFT};
    \node[draw,right=of ifft] (ola) {OLA};
    \draw[->] (seg) -- (win);
    \draw[->] (win) -- (fft);
    \draw[->] (fft) -- node[above] {$X_i[k]$} (mask);
    \draw[->] (mask) -- node[above] {$Y_i[k]$} (ifft);
    \draw[->] (ifft) -- (ola);
    \node[below=0.45cm of mask] {modifikace krátkodobého spektra};
  \end{tikzpicture}
\end{document}
```

## DFT masky

Pásmové filtry s ideální frekvenční charakteristikou lze realizovat maskou v DFT spektru. Frekvenční charakteristika musí být navzorkovaná pro dané $N_{\mathrm{FFT}}$ a u reálného časového signálu musí zachovat symetrii spektra. Zdroj: [[b2b31czs_pr10_OLA_general_HANDOUT.pdf#page=16|CZS 10 s. 16]].

Pro dolní propust se mezní index volí

$$
k_c=\left\lfloor \frac{f_c}{f_s}N\right\rfloor
$$

a maska má tvar

$$
H[k]=
\begin{cases}
1, & 0\le k\le k_c \;\text{a}\; N-k_c\le k<N,\\
0, & k_c<k<N-k_c.
\end{cases}
$$

Stejnosměrná složka $k=0$ je v DFT jen jednou; složka $k=N$ je už periodické opakování. Pro sudé $N$ je zvláštní i nepárová složka $k=N/2$. Zdroj: [[b2b31czs_pr10_OLA_general_HANDOUT.pdf#page=17|CZS 10 s. 17]].

Pro pásmovou propust se používají dva mezní indexy:

$$
k_{c1}=\left\lceil \frac{f_{c1}}{f_s}N\right\rceil,\qquad
k_{c2}=\left\lfloor \frac{f_{c2}}{f_s}N\right\rfloor.
$$

Jedničky jsou v kladném i zrcadlovém záporném pásmu, aby byla zachována symetrie. Zdroj: [[b2b31czs_pr10_OLA_general_HANDOUT.pdf#page=18|CZS 10 s. 18]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.9cm,y=0.8cm]
    \draw[->] (-0.2,0) -- (7.2,0) node[right] {$k$};
    \draw[->] (0,-0.2) -- (0,1.6) node[above] {$H[k]$};
    \draw[thick,blue] (0,1) -- (1.3,1) -- (1.3,0) -- (5.1,0) -- (5.1,1) -- (6.6,1);
    \draw[dashed] (3.3,-0.15) -- (3.3,1.4);
    \node at (0,-0.3) {$0$};
    \node at (1.3,-0.3) {$k_c$};
    \node at (3.3,-0.3) {$N/2$};
    \node at (5.1,-0.3) {$N-k_c$};
    \node at (6.6,-0.3) {$N$};
    \node[blue] at (3.2,1.25) {maska DP};
  \end{tikzpicture}
\end{document}
```

## Spektrální prahování a odečítání

Spektrální prahování ponechá jen složky nad prahem:

$$
Y[k]=
\begin{cases}
X[k], & |X[k]|\ge \mathrm{thr},\\
0, & |X[k]|<\mathrm{thr}.
\end{cases}
$$

Je vhodné pro potlačení širokopásmového rušení v úzkopásmovém signálu; opačnou podmínkou lze potlačovat úzkopásmové rušení. Zdroj: [[b2b31czs_pr10_OLA_general_HANDOUT.pdf#page=24|CZS 10 s. 24]].

U spektrálního odečítání se předpokládá aditivní šum

$$
x[n]=s[n]+n[n],\qquad X[k]=S[k]+N[k].
$$

Při nekorelovaném šumu se amplitudové spektrum signálu odhaduje odečtením odhadu šumu:

$$
|\hat S[k]|=|X[k]|-|N[k]|.
$$

Záporné hodnoty se odstraňují jednocestným nebo dvoucestným usměrněním a fáze se obvykle bere ze vstupního signálu. Odhad šumu lze získat z pauz, minim nebo jiného pásma a aktualizovat adaptivně. Zdroj: [[b2b31czs_pr10_OLA_general_HANDOUT.pdf#page=25|CZS 10 s. 25]], [[b2b31czs_pr10_OLA_general_HANDOUT.pdf#page=26|CZS 10 s. 26]].

## Převzorkování

Decimace je celočíselné snížení vzorkovací frekvence. Před podvzorkováním musí být splněn vzorkovací teorém pro novou frekvenci, proto se v běžném nízkofrekvenčním případě zařazuje antialiasingová dolní propust:

$$
f_{s,\mathrm{low}}=\frac{f_{s,\mathrm{high}}}{M},
\qquad
f_c=\frac{f_{s,\mathrm{high}}}{2M}.
$$

Blokově: filtr $H(z)$, potom operátor $\downarrow M$. Zdroj: [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=6|CZS 11 s. 6]].

Interpolace je zvýšení vzorkovací frekvence. V DSP se provádí ve dvou krocích: vložení nul a vyhlazení dolní propustí. Pro faktor $M$ platí

$$
f_{s,\mathrm{high}}=M f_{s,\mathrm{low}},
\qquad
f_c=\frac{f_{s,\mathrm{high}}}{2M}.
$$

Po vložení nul je třeba i $M$-násobné zesílení, protože vložení nul snižuje výkon signálu. Zdroj: [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=11|CZS 11 s. 11]].

Obecná změna vzorkovací frekvence s neceločíselným poměrem se provede jako interpolace a decimace:

$$
f_{s,\mathrm{new}}=\frac{L}{M}f_{s,\mathrm{orig}}.
$$

Jeden filtr lze použít s mezní frekvencí

$$
f_c=\min\left(\frac{f_{s,\mathrm{mid}}}{2L},\frac{f_{s,\mathrm{mid}}}{2M}\right).
$$

Zdroj: [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=12|CZS 11 s. 12]], [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=13|CZS 11 s. 13]].

```tikz
\begin{document}
  \begin{tikzpicture}[node distance=1.05cm,>=latex]
    \node (in) {$s_{\mathrm{orig}}[n]$};
    \node[draw,right=of in] (up) {$\uparrow L$};
    \node[draw,right=of up] (h) {$H(z)$};
    \node[draw,right=of h] (down) {$\downarrow M$};
    \node[right=of down] (out) {$s_{\mathrm{new}}[n]$};
    \draw[->] (in) -- (up);
    \draw[->] (up) -- node[above] {$f_{s,\mathrm{mid}}$} (h);
    \draw[->] (h) -- (down);
    \draw[->] (down) -- (out);
    \node[below=0.4cm of h] {$f_{s,\mathrm{new}}=\frac{L}{M}f_{s,\mathrm{orig}}$};
  \end{tikzpicture}
\end{document}
```

U pásmových VF signálů nemusí základní podmínka vypadat jako $f_s>2f_{\max}$. Pokud spektrum neobsahuje stejnosměrnou složku, může se použít pásmové vzorkování s podmínkou

$$
\frac{2f_{\max}}{M+1}\le f_s\le \frac{2f_{\min}}{M},
\qquad
M=\left\lfloor \frac{f_{\min}}{B}\right\rfloor,\quad B=f_{\max}-f_{\min}.
$$

Zdroj: [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=16|CZS 11 s. 16]].

## Banky filtrů

Banka filtrů rozkládá signál do více frekvenčních pásem. Dvoupásmová analyzující banka používá dolní a horní propust, potom decimaci $\downarrow 2$. Syntetizující banka provede interpolaci $\uparrow 2$, filtraci syntetizujícími filtry a součet větví. Zdroj: [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=20|CZS 11 s. 20]], [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=21|CZS 11 s. 21]].

Obecná $M$-pásmová banka s kritickou decimací používá analyzující filtry $H_0(z),\ldots,H_{M-1}(z)$, v každé větvi decimaci $\downarrow M$, při syntéze interpolaci $\uparrow M$, syntetizující filtry $G_0(z),\ldots,G_{M-1}(z)$ a součet. Všechna pásma dohromady pokrývají celé frekvenční pásmo. Zdroj: [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=23|CZS 11 s. 23]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=1cm,y=0.75cm,>=latex]
    \node at (0,0) (s) {$s[n]$};
    \node[draw] (h0) at (1.5,0) {$H_0(z)$};
    \node[draw] (h1) at (1.5,-1) {$H_1(z)$};
    \node[draw] (hM) at (1.5,-2) {$H_{M-1}(z)$};
    \node[draw] (d0) at (3.0,0) {$\downarrow M$};
    \node[draw] (d1) at (3.0,-1) {$\downarrow M$};
    \node[draw] (dM) at (3.0,-2) {$\downarrow M$};
    \node[draw] (u0) at (4.6,0) {$\uparrow M$};
    \node[draw] (u1) at (4.6,-1) {$\uparrow M$};
    \node[draw] (uM) at (4.6,-2) {$\uparrow M$};
    \node[draw] (g0) at (6.1,0) {$G_0(z)$};
    \node[draw] (g1) at (6.1,-1) {$G_1(z)$};
    \node[draw] (gM) at (6.1,-2) {$G_{M-1}(z)$};
    \foreach \h/\d/\u/\g in {h0/d0/u0/g0,h1/d1/u1/g1,hM/dM/uM/gM}
      {
        \draw[->] (s) -- (\h);
        \draw[->] (\h) -- (\d);
        \draw[->] (\d) -- (\u);
        \draw[->] (\u) -- (\g);
      }
    \node[draw,circle] (sum) at (7.7,-1) {$+$};
    \foreach \g in {g0,g1,gM} \draw[->] (\g) -- (sum);
    \draw[->] (sum) -- (9,-1) node[right] {$\tilde s[n]$};
    \node at (1.5,-2.7) {$\vdots$};
    \node at (6.1,-2.7) {$\vdots$};
  \end{tikzpicture}
\end{document}
```

Stromové banky filtrů mohou být symetrické, kdy se dále dělí všechna pásma, nebo asymetrické, kdy se dělí jen vybrané větve. Asymetrická stromová struktura odpovídá implementaci diskrétní vlnkové transformace. Zdroj: [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=24|CZS 11 s. 24]], [[b2b31czs_pr11_multirate_HANDOUT.pdf#page=25|CZS 11 s. 25]].

## Odhady parametrů náhodných signálů

U náhodných signálů mají odhady z konečné realizace náhodnou chybu. Základní blokový odhad střední hodnoty je

$$
\hat\mu_x=\frac{1}{N}\sum_{n=0}^{N-1}x[n].
$$

Okamžitá střední hodnota může být odhadována klouzavým průměrem jako FIR filtr:

$$
\hat\mu_x[n]=\frac{1}{M+1}\sum_{k=0}^{M}x[n-k].
$$

Alternativou je rekurentní odhad exponenciálním zapomínáním:

$$
\hat\mu_x[n]=p\hat\mu_x[n-1]+(1-p)x[n],
$$

kde $p$ je parametr zapomínání. Zdroj: [[b2b31czs_pr12_multirate_apps_recurrent_HANDOUT.pdf#page=9|CZS 12 s. 9]], [[b2b31czs_pr12_multirate_apps_recurrent_HANDOUT.pdf#page=10|CZS 12 s. 10]].

## Spektrální analýza a PSD

DFT periodogram náhodného signálu má také náhodný charakter. Délka segmentu $N$ ovlivňuje frekvenční rozlišení, ale náhodná chyba samotného periodogramu je nezávislá na $N$. Spektrální výkonovou hustotu proto nelze spolehlivě odhadnout z jedné realizace nebo jednoho segmentu. Zdroj: [[b2b31czs_pr4_spectrum_HANDOUT.pdf#page=19|CZS 4 s. 19]].

Welchova metoda:

1. rozdělí signál na krátkodobé segmenty, případně s překryvem,
2. každý segment váhuje oknem,
3. spočítá modifikovaný DFT periodogram každého segmentu,
4. periodogramy zprůměruje:

$$
\hat S_x[k]=E\{G_{x,i}[k]\}.
$$

Průměrování periodogramů vyhlazuje PSD a snižuje náhodnou chybu. Pro $L$ průměrovaných periodogramů handout uvádí chybu odhadu $\varepsilon_r=1/\sqrt{L}$. Zdroj: [[b2b31czs_pr4_spectrum_HANDOUT.pdf#page=20|CZS 4 s. 20]], [[b2b31czs_pr4_spectrum_HANDOUT.pdf#page=21|CZS 4 s. 21]], [[b2b31czs_pr4_spectrum_HANDOUT.pdf#page=24|CZS 4 s. 24]].

```tikz
\begin{document}
  \begin{tikzpicture}[node distance=0.95cm,>=latex]
    \node[draw] (seg) {segmenty};
    \node[draw,right=of seg] (w) {okno};
    \node[draw,right=of w] (fft) {FFT};
    \node[draw,right=of fft] (pow) {$|\cdot|^2$};
    \node[draw,right=of pow] (avg) {průměr};
    \node[right=of avg] (out) {$\hat S_x[k]$};
    \draw[->] (seg) -- (w);
    \draw[->] (w) -- (fft);
    \draw[->] (fft) -- (pow);
    \draw[->] (pow) -- node[above] {$G_{x,i}[k]$} (avg);
    \draw[->] (avg) -- (out);
  \end{tikzpicture}
\end{document}
```

Další možnost je odhad PSD z autokorelační funkce podle Wienerovy-Chinčinovy věty:

$$
S_x(f)=\mathrm{DTFT}\{R_x[k]\}.
$$

V praxi se používá DFT zkrácené a váhované ACF, například Bartlettovým oknem:

$$
\hat S_x(f)=\mathrm{DFT}_{N_{\mathrm{DFT}}}\{\hat R_x[k]w_{\mathrm{triang}}[k]\}.
$$

Zdroj: [[b2b31czs_pr4_spectrum_HANDOUT.pdf#page=28|CZS 4 s. 28]].

## Korelační analýza

Autokorelační funkce popisuje vnitřní závislosti mezi vzorky jednoho signálu. Pro reálný diskrétní signál:

$$
R_x[k]=\mathrm{Av}\{x[n]x[n-k]\}
=\mathrm{Av}\{x[n]x[n+k]\}.
$$

Pro stacionární a ergodické signály platí, že ACF je sudá a maximum je v $k=0$:

$$
\max R_x[k]=R_x[0]=P_x.
$$

Zdroj: [[b2b31czs_pr2_correlation_HANDOUT.pdf#page=10|CZS 2 s. 10]], [[b2b31czs_pr2_correlation_HANDOUT.pdf#page=11|CZS 2 s. 11]].

Nevychýlený odhad ACF z konečného signálu délky $N$ je

$$
\hat R_x[k]=\frac{1}{N-|k|}\sum_{n=0}^{N-1-|k|}x[n]x[n+|k|],
\qquad k=0,\pm1,\ldots,\pm(N-1).
$$

Je asymptoticky nevychýlený, ale pro velká $|k|$ má vysoký rozptyl, protože se průměruje málo součinů. Vychýlená varianta dělí konstantně $N$ a má menší rozptyl pro velká zpoždění. Zdroj: [[b2b31czs_pr2_correlation_HANDOUT.pdf#page=13|CZS 2 s. 13]], [[b2b31czs_pr2_correlation_HANDOUT.pdf#page=14|CZS 2 s. 14]], [[b2b31czs_pr2_correlation_HANDOUT.pdf#page=15|CZS 2 s. 15]].

Vzájemná korelační funkce kvantifikuje podobnost dvou různých signálů:

$$
R_{xy}[k]=\mathrm{Av}\{x[n]y[n-k]\}.
$$

Není obecně symetrická a znaménko v definici určuje směr posuvu. Maximum CCF se používá k detekci a měření zpoždění mezi signály. Zdroj: [[b2b31czs_pr2_correlation_HANDOUT.pdf#page=21|CZS 2 s. 21]], [[b2b31czs_pr2_correlation_HANDOUT.pdf#page=22|CZS 2 s. 22]].

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.9cm,y=0.8cm]
    \draw[->] (-3.3,0) -- (3.5,0) node[right] {$k$};
    \draw[->] (0,-0.2) -- (0,1.8) node[above] {$R$};
    \draw[blue,thick] (-2.5,0.15) -- (-1.2,0.45) -- (0,1.45) -- (1.2,0.45) -- (2.5,0.15);
    \draw[orange,thick] (-2.5,0.05) -- (-0.2,0.25) -- (1.2,1.25) -- (2.8,0.25);
    \node[blue] at (-2.1,1.25) {ACF};
    \node[orange] at (2.2,1.45) {CCF maximum = zpoždění};
  \end{tikzpicture}
\end{document}
```

## Modelování a lineární predikce

V dodaných CZS handoutech je lineární predikce přímo zmíněna jako aplikace autokorelační analýzy: ACF je vstup pro LPC analýzu. Zdroj: [[b2b31czs_pr2_correlation_HANDOUT.pdf#page=20|CZS 2 s. 20]].

Z dostupných podkladů lze bezpečně vyvodit tento rozsah: lineární predikce modeluje aktuální vzorek jako kombinaci předchozích vzorků a parametry modelu se odhadují z korelačních charakteristik signálu. Detailní rovnice LPC, Levinsonova-Durbinova rekurze ani explicitní AR model nejsou v dodaných handoutech k tomuto okruhu samostatně vyloženy, proto je zde nedoplňuji mimo podklady.

## Vazby na další otázky

Tento okruh přímo navazuje na [[23 Konvoluce DFT vahovani casove frekvencni analyza filtry kvantovani]]: DFT, okna, spektrogram, cyklická konvoluce a vlastnosti FIR/IIR filtrů jsou předpokladem pro frekvenční filtraci, Welchovu metodu a převzorkování.
