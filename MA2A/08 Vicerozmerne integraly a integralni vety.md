# 08 Dvojný a trojný integrál, křivkové a plošné integrály, integrální věty

## Dvojný integrál a Fubiniho věta

Pro spojitou funkci $f(x,y)$ na obdélníku
$$
T=\langle a_1,a_2\rangle\times\langle b_1,b_2\rangle
$$
se postupnou integrací zavádějí dvojnásobné integrály
$$
\int_{a_1}^{a_2}\int_{b_1}^{b_2} f(x,y)\,dy\,dx,
\qquad
\int_{b_1}^{b_2}\int_{a_1}^{a_2} f(x,y)\,dx\,dy.
$$
Hodnota nezávisí na pořadí integrace. V tomto výkladu je to Fubiniho věta:
$$
\int_{a_1}^{a_2}\int_{b_1}^{b_2} f(x,y)\,dy\,dx
= \int_{b_1}^{b_2}\int_{a_1}^{a_2} f(x,y)\,dx\,dy.
$$
Společná hodnota se označuje
$$
\iint_T f(x,y)\,dx\,dy.
$$
Pro nezápornou funkci má dvojný integrál význam objemu tělesa nad podstavou $T$ a pod grafem $z=f(x,y)$. Zdroj: [[integralni_pocet_vice_prom.pdf#page=18|Integrální počet více proměnných, dvojnásobná integrace a Fubini, s. 19-25]]

## Integrace přes základní oblasti

Obdélník je speciální případ. Často integrujeme přes základní oblast typu
$$
T=\{(x,y)\in\mathbb{R}^2\mid x\in\langle a_1,a_2\rangle,\ s_1(x)\le y\le s_2(x)\}.
$$
Potom
$$
\iint_T f(x,y)\,dx\,dy
= \int_{a_1}^{a_2}\int_{s_1(x)}^{s_2(x)} f(x,y)\,dy\,dx.
$$
Analogicky pro oblast zadanou jako
$$
T=\{(x,y)\in\mathbb{R}^2\mid y\in\langle b_1,b_2\rangle,\ p_1(y)\le x\le p_2(y)\}
$$
platí
$$
\iint_T f(x,y)\,dx\,dy
= \int_{b_1}^{b_2}\int_{p_1(y)}^{p_2(y)} f(x,y)\,dx\,dy.
$$
Na rozdíl od obdélníku nelze pořadí integrace prohodit mechanicky bez změny mezí. Zdroj: [[integralni_pocet_vice_prom.pdf#page=27|Integrální počet více proměnných, integrály přes základní oblasti, s. 27-32]]

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.95cm,y=0.95cm]
    \draw[->] (-0.2,0) -- (5.6,0) node[right] {$x$};
    \draw[->] (0,-0.2) -- (0,3.6) node[above] {$y$};

    \draw[color=blue,thick,domain=0.8:4.8,samples=80] plot (\x,{0.55+0.22*(\x-2.7)*(\x-2.7)});
    \draw[color=blue,thick,domain=0.8:4.8,samples=80] plot (\x,{2.75-0.18*(\x-2.7)*(\x-2.7)});
    \fill[color=blue,opacity=0.12] (0.8,1.34)
      -- plot[domain=0.8:4.8,samples=80] (\x,{2.75-0.18*(\x-2.7)*(\x-2.7)})
      -- (4.8,1.65)
      -- plot[domain=4.8:0.8,samples=80] (\x,{0.55+0.22*(\x-2.7)*(\x-2.7)})
      -- cycle;

    \draw[dashed] (2.4,0) node[below] {$x$} -- (2.4,2.73);
    \draw[<->,color=red,thick] (2.4,0.57) -- (2.4,2.73) node[midway,right] {$s_1(x)\le y\le s_2(x)$};
    \draw[dashed] (0,1.65) node[left] {$y$} -- (4.8,1.65);
    \draw[<->,color=orange,thick] (0.95,1.65) -- (4.8,1.65) node[midway,above] {$p_1(y)\le x\le p_2(y)$};
    \node[color=blue] at (4.4,3.15) {$T$};
  \end{tikzpicture}
\end{document}
```

## Substituce v dvojném integrálu

Změna souřadnic se popisuje zobrazením
$$
\Phi:T\to\mathbb{R}^2, \qquad \Phi(u,v)=(x(u,v),y(u,v)).
$$
Je-li $\Phi$ třídy $C^1$, její Jacobiho matice je
$$
J_\Phi=\begin{pmatrix}
\frac{\partial \Phi_1}{\partial u} & \frac{\partial \Phi_1}{\partial v} \\
\frac{\partial \Phi_2}{\partial u} & \frac{\partial \Phi_2}{\partial v}
\end{pmatrix},
$$
a jakobián je
$$
\Delta_\Phi=|\det J_\Phi|.
$$
Je-li $\Phi$ třídy $C^1$ a prosté na $T$ a $f$ je spojitá na $\Phi(T)$, potom věta o substituci říká
$$
\iint_{\Phi(T)} f(x,y)\,dx\,dy
= \iint_T f(\Phi(u,v))\,\Delta_\Phi(u,v)\,du\,dv.
$$
Pro polární souřadnice
$$
x=\rho\cos\varphi,\qquad y=\rho\sin\varphi
$$
je
$$
\Delta_\Phi=\rho.
$$
Zdroj: [[integralni_pocet_vice_prom.pdf#page=42|Integrální počet více proměnných, substituce v dvojném integrálu, s. 43-56]]

## Trojný integrál a substituce

Trojný integrál se zavádí analogicky jako integrál dvojný. Pro základní těleso
$$
P=\{(x,y,z)\in\mathbb{R}^3\mid (x,y)\in T,\ h_1(x,y)\le z\le h_2(x,y)\}
$$
platí
$$
\iiint_P f(x,y,z)\,dx\,dy\,dz
= \iint_T\int_{h_1(x,y)}^{h_2(x,y)} f(x,y,z)\,dz\,dx\,dy,
$$
s vhodným pořadím integrace podle popisu tělesa. Pro nezápornou hustotu $f$ má trojný integrál význam hmotnosti tělesa s hustotou $f$.

Substituce v trojném integrálu má stejný tvar jako ve dvojném:
$$
\iiint_{\Phi(P)} f\,dV
= \iiint_P f(\Phi)\,\Delta_\Phi\,dV.
$$
Cylindrické souřadnice
$$
x=\rho\cos\varphi,\qquad y=\rho\sin\varphi,\qquad z=z
$$
mají jakobián $\Delta_\Phi=\rho$. Sférické souřadnice
$$
x=\rho\sin\vartheta\cos\varphi,
\quad y=\rho\sin\vartheta\sin\varphi,
\quad z=\rho\cos\vartheta
$$
mají jakobián
$$
\Delta_\Phi=\rho^2\sin\vartheta.
$$
Zdroj: [[integralni_pocet_vice_prom.pdf#page=64|Integrální počet více proměnných, trojný integrál a substituce, s. 65-72]]

## Křivkový integrál funkce

Křivkový integrál funkce, někdy 1. druhu, integruje skalární funkci po křivce. Pro spojitou funkci $f$ na oblouku $C$ se značí
$$
\int_C f\,ds.
$$
Je-li $\varphi:\langle a,b\rangle\to C$ parametrizace oblouku, potom
$$
\int_C f\,ds=\int_a^b f(\varphi(t))\,\|\varphi'(t)\|\,dt.
$$
Fyzikálně lze tento integrál chápat jako hmotnost tenkého drátu tvaru $C$, jestliže $f$ je lineární hustota. Pro rovinnou nezápornou funkci může vyjadřovat i obsah plochy nad křivkou. Zdroj: [[integralni_pocet_vice_prom.pdf#page=88|Integrální počet více proměnných, křivkový integrál funkce, s. 89-96]]

## Křivkový integrál vektorového pole

Orientace křivky je určena jednotkovým tečným polem $\tau$. Křivkový integrál vektorového pole $F$ po orientované křivce $(C)$ je definován jako
$$
\int_{(C)} F\,d\vec{s}=\int_C (F\cdot\tau)\,ds.
$$
Při parametrizaci $\varphi:\langle a,b\rangle\to C$, která souhlasí s orientací, se počítá vzorcem
$$
\int_{(C)} F\,d\vec{s}=\int_a^b F(\varphi(t))\cdot\varphi'(t)\,dt.
$$
Pro $F=(F_1,F_2,F_3)$ se často píše
$$
\int_{(C)} F\,d\vec{s}=\int_C F_1\,dx+F_2\,dy+F_3\,dz.
$$
Význačná interpretace: integrál udává práci pole po dané orientované dráze. Pro rovinnou uzavřenou křivku lze pomocí vhodného pole popsat také průtok přes hranici oblasti. Zdroj: [[integralni_pocet_vice_prom.pdf#page=100|Integrální počet více proměnných, křivkový integrál vektorového pole, s. 101-110]]

## Obsah plochy a plošný integrál funkce

Je-li elementární plocha $M$ grafem funkce $z=g(x,y)$ nad základní oblastí $D$, potom její obsah je
$$
\operatorname{obsah}(M)=\iint_D \sqrt{1+\left(\frac{\partial g}{\partial x}\right)^2+\left(\frac{\partial g}{\partial y}\right)^2}\,dx\,dy.
$$
Obecněji pro parametrizaci plochy
$$
\Phi(s,t)=(\Phi_1(s,t),\Phi_2(s,t),\Phi_3(s,t))
$$
platí
$$
\operatorname{obsah}(M)=\iint_T \left\|\frac{\partial \Phi}{\partial s}\times\frac{\partial \Phi}{\partial t}\right\|\,ds\,dt.
$$
Plošný integrál funkce, někdy 1. druhu, je
$$
\iint_M f\,dS.
$$
Při parametrizaci se počítá
$$
\iint_M f\,dS
= \iint_T f(\Phi(s,t))\left\|\frac{\partial \Phi}{\partial s}\times\frac{\partial \Phi}{\partial t}\right\|\,ds\,dt.
$$
Fyzikálně jde například o hmotnost plochy s plošnou hustotou $f$. Zdroj: [[integralni_pocet_vice_prom.pdf#page=117|Integrální počet více proměnných, obsah plochy, s. 118-126]]; [[integralni_pocet_vice_prom.pdf#page=134|Integrální počet více proměnných, plošný integrál funkce, s. 135-140]]

## Plošný integrál vektorového pole

Orientace plochy je dána jednotkovým normálovým polem $n$. Plošný integrál vektorového pole $F$ přes orientovanou plochu $(M)$ je
$$
\iint_{(M)} F\,d\vec{S}=\iint_M F\cdot n\,dS.
$$
Tento integrál se nazývá tok pole plochou. Pro parametrizaci $\Phi(s,t)$ orientovanou tak, aby
$$
n=\frac{\frac{\partial \Phi}{\partial s}\times\frac{\partial \Phi}{\partial t}}{\left\|\frac{\partial \Phi}{\partial s}\times\frac{\partial \Phi}{\partial t}\right\|},
$$
platí
$$
\iint_{(M)}F\,d\vec{S}
= \iint_T F(\Phi(s,t))\cdot\left(\frac{\partial \Phi}{\partial s}\times\frac{\partial \Phi}{\partial t}\right)\,ds\,dt.
$$
Zdroj: [[integralni_pocet_vice_prom.pdf#page=148|Integrální počet více proměnných, plošný integrál vektorového pole, s. 149-155]]

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.95cm,y=0.95cm]
    \draw[->] (-0.2,0) -- (5.7,0) node[right] {$x$};
    \draw[->] (0,-0.2) -- (1.7,1.2) node[above] {$y$};
    \draw[->] (0,0) -- (0,3.4) node[above] {$z$};

    \fill[color=blue,opacity=0.16] (1.1,0.8) -- (4.4,1.15) -- (5.0,2.25) -- (1.75,1.9) -- cycle;
    \draw[color=blue,thick] (1.1,0.8) -- (4.4,1.15) -- (5.0,2.25) -- (1.75,1.9) -- cycle;
    \node[color=blue] at (4.7,2.65) {$(M)$};

    \draw[->,color=red,very thick] (3.05,1.55) -- (3.05,3.0) node[above] {$n$};
    \foreach \x/\y in {1.1/2.6,2.0/2.85,3.1/2.65,4.2/2.9}
      \draw[->,color=orange,thick] (\x,\y) -- (\x+0.55,\y-0.9);
    \node[color=orange] at (1.35,3.25) {$F$};
    \node at (2.7,0.35) {$F\cdot n$ měří tok přes plochu};
  \end{tikzpicture}
\end{document}
```

## Gaussova věta

Divergence pole $F=(F_1,\dots,F_n)$ je
$$
\operatorname{div}F=\frac{\partial F_1}{\partial x_1}+\cdots+\frac{\partial F_n}{\partial x_n}.
$$
Nechť $P\subset\mathbb{R}^3$ je základní těleso, jehož hranice $\partial P$ je orientována vnějším normálovým polem. Je-li $F$ vektorové pole třídy $C^1$ na $P$, potom Gaussova věta říká
$$
\iiint_P \operatorname{div}F\,dV
= \iint_{(\partial P)} F\,d\vec{S}.
$$
Výklad: objemový integrál divergence se rovná toku pole přes hranici. Divergence má fyzikální význam hustoty zdrojů pole. Zdroj: [[integralni_pocet_vice_prom.pdf#page=160|Integrální počet více proměnných, Gaussova věta, s. 161-167]]

## Greenova věta

Nechť $T\subset\mathbb{R}^2$ je základní oblast a hranice $\partial T$ je kladně orientována vzhledem k $T$; při procházení hranice je oblast vlevo. Je-li $F=(F_1,F_2)$ třídy $C^1$ na $T$, potom
$$
\int_{(\partial T)} F\,d\vec{s}
= \iint_T\left(\frac{\partial F_2}{\partial x}-\frac{\partial F_1}{\partial y}\right)\,dx\,dy.
$$
Ve složkách:
$$
\int_{(\partial T)} F_1\,dx+F_2\,dy
= \iint_T\left(\frac{\partial F_2}{\partial x}-\frac{\partial F_1}{\partial y}\right)\,dx\,dy.
$$
Zdroj: [[integralni_pocet_vice_prom.pdf#page=168|Integrální počet více proměnných, Greenova věta, s. 168-170]]

## Stokesova věta

Rotace pole $F=(F_1,F_2,F_3)$ je
$$
\operatorname{rot}F=
\left(
\frac{\partial F_3}{\partial y}-\frac{\partial F_2}{\partial z},
\frac{\partial F_1}{\partial z}-\frac{\partial F_3}{\partial x},
\frac{\partial F_2}{\partial x}-\frac{\partial F_1}{\partial y}
\right).
$$
Nechť $F$ je třídy $C^1$ na otevřené množině obsahující orientovanou elementární plochu $M$. Nechť kraj plochy $M$ je uzavřená jednoduchá křivka $C=K(M)$ a orientace $C$ souhlasí s orientací plochy $M$. Potom Stokesova věta říká
$$
\int_{(C)}F\,d\vec{s}
= \iint_{(M)}\operatorname{rot}F\,d\vec{S}.
$$
Je to prostorové zobecnění Greenovy věty: křivkový integrál po kraji plochy odpovídá plošnému integrálu rotace přes plochu. Zdroj: [[integralni_pocet_vice_prom.pdf#page=170|Integrální počet více proměnných, Stokesova věta, s. 170-173]]

```tikz
\begin{document}
  \begin{tikzpicture}[x=0.95cm,y=0.95cm]
    \draw[->] (-0.2,0) -- (5.8,0) node[right] {$x$};
    \draw[->] (0,-0.2) -- (1.8,1.2) node[above] {$y$};
    \draw[->] (0,0) -- (0,3.4) node[above] {$z$};

    \fill[color=blue,opacity=0.14] (3,1.5) ellipse (1.65 and 0.65);
    \draw[color=blue,thick] (3,1.5) ellipse (1.65 and 0.65);
    \node[color=blue] at (4.9,1.8) {$M$};

    \draw[->,color=red,very thick] (3,1.5) -- (3,3.0) node[above] {$n$};
    \draw[->,color=orange,thick] (4.55,1.5) arc (0:70:1.65 and 0.65);
    \draw[->,color=orange,thick] (1.45,1.5) arc (180:250:1.65 and 0.65);
    \node[color=orange] at (3,0.45) {$C=K(M)$};
    \node at (3,3.35) {orientace $C$ souhlasí s $n$};
  \end{tikzpicture}
\end{document}
```

## Potenciál vektorového pole

Vektorové pole $F$ na otevřené množině $G\subset\mathbb{R}^n$ je potenciální, jestliže existuje spojitě diferencovatelná funkce $f$ taková, že
$$
F=\operatorname{grad}f.
$$
Funkce $f$ se nazývá potenciál. Potenciál je určen až na konstantu na souvislé oblasti.

Pro potenciální pole platí, že křivkový integrál nezávisí na cestě. Ekvivalentně:

- $F$ je potenciální,
- integrál po libovolných dvou křivkách se stejným počátkem a koncem je stejný,
- integrál po každé uzavřené jednoduché orientované křivce je nulový.

Je-li $f$ potenciál a křivka vede z bodu $u$ do bodu $v$, potom
$$
\int_{(C)}F\,d\vec{s}=f(v)-f(u).
$$
Nutná podmínka potenciálnosti je nevírovost: v rovině
$$
\frac{\partial F_2}{\partial x}-\frac{\partial F_1}{\partial y}=0,
$$
v prostoru
$$
\operatorname{rot}F=0.
$$
Na jednoduše souvislých oblastech je tato podmínka i postačující. Tohle přímo navazuje na [[07 Funkce vice promennych, gradient, extremy#Gradient a diferenciál|gradient a diferenciál]]. Zdroj: [[integralni_pocet_vice_prom.pdf#page=186|Integrální počet více proměnných, potenciál vektorového pole, s. 187-194]]

## Rychlá orientace pro státnice

- Dvojný integrál: obsah nebo objem nad oblastí, Fubini pro změnu pořadí na obdélníku a správné meze na základní oblasti.
- Substituce: vždy násobit absolutní hodnotou determinantu Jacobiho matice.
- Trojný integrál: objem nebo hmotnost v prostoru, cylindrické a sférické souřadnice mají jakobiány $\rho$ a $\rho^2\sin\vartheta$.
- Křivkový integrál funkce: $\int_C f\,ds$, parametrizace přináší faktor $\|\varphi'\|$.
- Křivkový integrál pole: $\int F\cdot\varphi'\,dt$, význam práce.
- Plošný integrál funkce: $\iint f\,dS$, parametrizace přináší faktor $\|\Phi_s\times\Phi_t\|$.
- Plošný integrál pole: $\iint F\cdot n\,dS$, význam tok.
- Gauss: tok přes uzavřenou hranici $=$ integrál divergence v objemu.
- Green: křivkový integrál po hranici rovinné oblasti $=$ dvojný integrál rotační složky.
- Stokes: křivkový integrál po kraji plochy $=$ tok rotace přes plochu.
- Potenciál: $F=\operatorname{grad}f$, práce nezávisí na cestě.

Zdroj: [[integralni_pocet_vice_prom.pdf#page=3|Integrální počet více proměnných, obsah skript, s. 4-5]]; [[integralni_pocet_vice_prom.pdf#page=160|Integrální věty, s. 161-173]]; [[integralni_pocet_vice_prom.pdf#page=186|Potenciál, s. 187-194]]
