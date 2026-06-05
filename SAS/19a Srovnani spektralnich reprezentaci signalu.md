# 19a Srovnání spektrálních reprezentací signálů

> [!info] Zdroj
> Přehled vychází z transformačních vztahů pro FS, FT, DFS a DtFT v [[sas_cviceni_v0.96_250225.pdf#page=50|SAS s. 50]], [[sas_cviceni_v0.96_250225.pdf#page=53|SAS s. 53]], [[sas_cviceni_v0.96_250225.pdf#page=59|SAS s. 59]] a [[sas_cviceni_v0.96_250225.pdf#page=65|SAS s. 65]].

## Z časové oblasti do spektra

| Časový signál                 | Časová proměnná |        Periodicita v čase | Spektrální reprezentace |   Spektrální proměnná | Jak vypadá spektrum                                             | Co se používá                                   |
| ----------------------------- | --------------: | ------------------------: | ----------------------- | --------------------: | --------------------------------------------------------------- | ----------------------------------------------- |
| $s(t)$ spojitý periodický     |     spojitá $t$ | periodický, perioda $T_0$ | koeficienty $c_n$       | diskrétní $n\omega_0$ | diskrétní čárové spektrum, neperiodická posloupnost koeficientů | Fourierova řada, FS                             |
| $s(t)$ spojitý neperiodický   |     spojitá $t$ |              neperiodický | $S(\omega)$             |      spojitá $\omega$ | spojité neperiodické spektrum                                   | Fourierova transformace, FT                     |
| $s[k]$ diskrétní periodický   |   diskrétní $k$ | periodický, perioda $N_0$ | koeficienty $d_n$       | diskrétní $n\Omega_0$ | diskrétní periodické spektrum s periodou $N_0$                  | diskrétní Fourierova řada, DFS                  |
| $s[k]$ diskrétní neperiodický |   diskrétní $k$ |              neperiodický | $S(\Omega)$             |      spojitá $\Omega$ | spojité periodické spektrum s periodou $2\pi$                   | Fourierova transformace v diskrétním čase, DtFT |

## Opačný směr: ze spektra do časového signálu

| Spektrum | Spektrální proměnná | Periodicita spektra | Časový signál po inverzi | Časová proměnná | Periodicita v čase | Inverzní použití |
|---|---:|---:|---|---:|---|---|
| $c_n$ | diskrétní $n$ | neperiodické koeficienty | $s(t)$ | spojitá $t$ | periodický | inverzní Fourierova řada |
| $S(\omega)$ | spojitá $\omega$ | neperiodické spektrum | $s(t)$ | spojitá $t$ | neperiodický | inverzní FT |
| $d_n$ | diskrétní $n$ | periodické koeficienty | $s[k]$ | diskrétní $k$ | periodický | inverzní DFS |
| $S(\Omega)$ | spojitá $\Omega$ | periodické spektrum, perioda $2\pi$ | $s[k]$ | diskrétní $k$ | neperiodický | inverzní DtFT |

## Vzorce

### Spojitý periodický signál: FS

$$
c_n=\frac{1}{T_0}\int_{(T_0)}s(t)e^{-jn\omega_0t}\,dt,
\qquad
s(t)=\sum_{n=-\infty}^{\infty}c_ne^{jn\omega_0t}.
$$

### Spojitý neperiodický signál: FT

$$
S(\omega)=\int_{-\infty}^{\infty}s(t)e^{-j\omega t}\,dt,
\qquad
s(t)=\frac{1}{2\pi}\int_{-\infty}^{\infty}S(\omega)e^{j\omega t}\,d\omega.
$$

### Diskrétní periodický signál: DFS

$$
d_n=\frac{1}{N_0}\sum_{k=k_p}^{k_p+N_0-1}s[k]e^{-jn\Omega_0k},
\qquad
s[k]=\sum_{n=n_p}^{n_p+N_0-1}d_ne^{jn\Omega_0k}.
$$

### Diskrétní neperiodický signál: DtFT

$$
S(\Omega)=\sum_{k=-\infty}^{\infty}s[k]e^{-j\Omega k},
\qquad
s[k]=\frac{1}{2\pi}\int_{(2\pi)}S(\Omega)e^{j\Omega k}\,d\Omega.
$$

## Rychlé pravidlo

- Periodicita v čase způsobí diskrétní spektrum.
- Diskrétnost v čase způsobí periodické spektrum.
- Spojitý neperiodický signál má spojité neperiodické spektrum.
- Diskrétní periodický signál má diskrétní periodické spektrum.

```tikz
\begin{document}
  \begin{tikzpicture}[x=1cm,y=0.9cm]
    \node[draw,rounded corners=2pt,align=center,minimum width=3.2cm,minimum height=0.8cm] (ctper) at (0,2.2) {spojitý\\periodický};
    \node[draw,rounded corners=2pt,align=center,minimum width=3.2cm,minimum height=0.8cm] (ctaper) at (0,0.7) {spojitý\\neperiodický};
    \node[draw,rounded corners=2pt,align=center,minimum width=3.2cm,minimum height=0.8cm] (dtper) at (0,-0.8) {diskrétní\\periodický};
    \node[draw,rounded corners=2pt,align=center,minimum width=3.2cm,minimum height=0.8cm] (dtaper) at (0,-2.3) {diskrétní\\neperiodický};

    \node[draw,rounded corners=2pt,align=center,minimum width=3.6cm,minimum height=0.8cm] (fs) at (5,2.2) {diskrétní\\neperiodické spektrum\\FS};
    \node[draw,rounded corners=2pt,align=center,minimum width=3.6cm,minimum height=0.8cm] (ft) at (5,0.7) {spojité\\neperiodické spektrum\\FT};
    \node[draw,rounded corners=2pt,align=center,minimum width=3.6cm,minimum height=0.8cm] (dfs) at (5,-0.8) {diskrétní\\periodické spektrum\\DFS};
    \node[draw,rounded corners=2pt,align=center,minimum width=3.6cm,minimum height=0.8cm] (dtft) at (5,-2.3) {spojité\\periodické spektrum\\DtFT};

    \draw[->,thick] (ctper) -- (fs);
    \draw[->,thick] (ctaper) -- (ft);
    \draw[->,thick] (dtper) -- (dfs);
    \draw[->,thick] (dtaper) -- (dtft);
  \end{tikzpicture}
\end{document}
```
