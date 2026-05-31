# 10a Srovnání transformací Fourier, Laplace a Z

> Přehled k otázce [[10 Fourier Laplace Z transformace]]. Zdroje: [[transformace.pdf#page=7|transformace s. 7-11]], [[transformace.pdf#page=11|transformace s. 11-15]], [[transformace.pdf#page=25|transformace s. 25-27]], [[transformace.pdf#page=36|transformace s. 36-44]], [[transformace.pdf#page=50|transformace s. 50-54]], [[transformace.pdf#page=60|transformace s. 60-63]].

## Rychlé srovnání

| Značka | Transformace | Přímá transformace | Inverzní transformace | Spojitá / diskrétní |
|---|---|---|---|---|
| $\mathcal F$ | Fourierova transformace | $\widehat f(\omega)=\mathcal F[f](\omega)=\int_{-\infty}^{\infty} f(t)e^{-i\omega t}\,dt$ | $f(t)=\mathcal F^{-1}[\widehat f](t)=\frac1{2\pi}\int_{-\infty}^{\infty}\widehat f(\omega)e^{i\omega t}\,d\omega$ | spojitá v čase, spojitá ve frekvenci |
| $\mathcal L$ | Laplaceova transformace | $F(s)=\mathcal L[f](s)=\int_0^\infty f(t)e^{-st}\,dt$ | $f(t)=\mathcal L^{-1}[F](t)$, obecně $\frac{f(t+)+f(t-)}2=\frac1{2\pi i}\int_{x-i\infty}^{x+i\infty}F(s)e^{st}\,ds$ | spojitá v čase, komplexní proměnná $s$ |
| $\mathbb Z$ | Z-transformace | $F(z)=\mathbb Z[a_n](z)=\sum_{n=0}^{\infty}\frac{a_n}{z^n}$ | $a_n=\mathbb Z^{-1}[F]_n=\frac1{2\pi i}\int_C F(z)z^{n-1}\,dz$ | diskrétní čas / posloupnost, komplexní proměnná $z$ |

## Kdy kterou použít

- $\mathcal F$: spektrum spojitého signálu na celé reálné ose; typicky frekvenční analýza a konvoluce.
- $\mathcal L$: počáteční úlohy pro diferenciální rovnice na $[0,\infty)$; počáteční podmínky se objeví přímo v obrazu derivací.
- $\mathbb Z$: diferenční rovnice a diskrétní systémy; posuny posloupnosti se změní na algebraické výrazy v $z$.
