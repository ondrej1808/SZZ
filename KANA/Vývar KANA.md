[Linka na YT od Bohaty](https://www.youtube.com/watch?v=PqaPiItJFXg&list=PLQL6z4JeTTQk4zpAmJSPt08eT7l97Umam)
Komplexka je triv.
Tento dokument jsem vytvořil když jsem se učil na zkoušku a snad pomůže budoucím generacím s přípravou. Dostal jsem C a to jsem matematicky kripl a na ústní jsem přišel s kocovinou.
Zkouška se skládá z písemné části a nepovinně povinné ústní druhý den ráno.
Písemná část je celkem EZ, hlavně jsou tam Fourierovy, Laplaceovy a Z-transformace. Doporučuji se tyhle našprtat co nejvíc. Tím že se budeš šprtat tohle se budeš muset naučit i integrály a residua, a najednou už umíš všechno. Krom toho pan docent je super a dá ti na úvodní stránku nejčastěji používané vzorce pro transformace a výpočet residua přes limitu. V tomhle dokumentu jsou tyhle vzorce vypsané jen na začátku a pak jsou tu všechny ostatní který ti nedá. Je to vývar z jeho cvik, přesněji z druhé stránky jeho příkladů, kde má vždy vypsané užitečné vztahy pro dané téma.

Ústní je trochu horší, tam nikdo moc neví co přesně po tobě může chtít, ale to nevadí, pokud nemíříš na A. Nauč se nějaký důkaz z internetu a pak mu řekni že mu ho chceš ukázat a bude moc spoko. Na spodku jsou nějaký hezký důkazy co by se mu mohli líbit a dají se zapamatovat. Pro ty co jedou na stýpko, důkazy jede jenom na přednáškách a máš už je mít zapsaný :).

# Úvodní strana
Doporučuju vytisknout a mít neustále vedle sebe když počítáš, ono se pak nebudeš zbytečně učit vzorečky co dostaneš. Tohle je rok 2025 a možná si to změní, tak si radši zkontroluj co a jak.![[komplexkajetriv.png]]
# Komplexní čísla, úvod

Mějme $z = x + yi$, kde $x, y \in \mathbb{R}$. $x$ je reálná část čísla $z$, $y$ je imaginární část čísla $z$. Píšeme:
$$
  \text{Re } z = x \quad \text{a} \quad \text{Im } z = y
$$
Reálná i imaginární část jsou reálná čísla. Geometricky je $z$ bod v rovině o souřadnicích $(x, y)$.
Velikost komplexního čísla $z = x + yi$ je:
$$
  |z| = \sqrt{x^2 + y^2}
$$
Komplexně sdružené číslo k číslu $z = x + yi$ je číslo:
$$
  \overline{z} = x - yi
$$
Platí:
$$
  z\overline{z} = |z|^2 \geq 0
$$
Goniometrický tvar komplexního čísla $z \neq 0$ je vyjádření:
$$
  z = |z|(\cos \varphi + i \sin \varphi), \quad \varphi \in \mathbb{R}
$$
Píšeme $\varphi \in \text{Arg} \, z$. Označíme-li:
$$
  \cos \varphi + i \sin \varphi = e^{i\varphi},
$$
pak můžeme psát stručněji:
$$
  z = |z|e^{i\varphi}.
$$
Tento tvar nazýváme exponenciálním tvarem komplexního čísla $z \neq 0$. Goniometrický/Exponenciální tvar není jednoznačný (je-li $\varphi \in \text{Arg} \, z$, pak také $\varphi + 2k\pi \in \text{Arg} \, z$ pro každé $k \in \mathbb{Z}$). Je-li navíc $\varphi \in (-\pi, \pi]$, říkáme, že $\varphi$ je hlavní hodnota argumentu čísla $z$, a píšeme $\text{arg} \, z = \varphi$.

Moivreova věta říká, že pro každé $n \in \mathbb{Z}$ a $\varphi \in \mathbb{R}$ platí:
$$
  (\cos \varphi + i \sin \varphi)^n = \cos(n\varphi) + i \sin(n\varphi)
$$
Stručněji: 
$$
  (e^{i\varphi})^n = e^{in\varphi}.
$$
Binomické rovnice jsou rovnice tvaru: 
$$
  z^n = w,
$$
kde $n \in \mathbb{N}$ a $w \in \mathbb{C} \setminus \{0\}$ jsou dána. Binomická rovnice má právě $n$ různých řešení (v komplexním oboru). Geometricky řešení binomické rovnice tvoří vrcholy pravidelného n-úhelníku.

## Funkce komplexní proměnné, Cauchyovy-Riemannovy podmínky, harmonické funkce 
Je-li $z = x + iy$ a $f(z) = u(x, y) + iv(x, y)$, kde $u, v$ jsou reálné funkce, pak $u = \text{Re } f$ (reálná část funkce $f$) a $v = \text{Im } f$ (imaginární část funkce $f$). - Mějme funkci $f(z) = u(x, y) + iv(x, y)$ takovou, že funkce $u(x, y)$ a $v(x, y)$ mají spojité parciální derivace. Potom $f'(z)$ existuje právě tehdy, když jsou splněny Cauchyovy-Riemannovy podmínky: $$ \frac{\partial u}{\partial x}(x, y) = \frac{\partial v}{\partial y}(x, y) $$ a $$ \frac{\partial u}{\partial y}(x, y) = -\frac{\partial v}{\partial x}(x, y). $$ V takovém případě platí: $$ f'(z) = \frac{\partial u}{\partial x}(x, y) + i \frac{\partial v}{\partial x}(x, y). $$ - Funkce $u : \Omega \to \mathbb{R}$ je harmonická, kde $\Omega \subseteq \mathbb{R}^2$ je otevřená množina, jestliže má spojité druhé parciální derivace a platí: $$ \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} \equiv 0 \quad \text{na } \Omega. $$ Podstatné je, že součet $\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2}$ je nulový v každém bodě množiny $\Omega$. Tj. neřešíme, pro jaké body $(x, y) \in \Omega$ je součet nulový, ale zda je nulový vždy nezávisle na $(x, y) \in \Omega$. V našich příkladech bude typicky $\Omega = \mathbb{R}^2$.

# Elementární funkce
Pro $z = x + iy \in \mathbb{C}$ definujeme:
$$
  e^z = e^x (\cos y + i \sin y)
$$
$$
  \sin z = \frac{e^{iz} - e^{-iz}}{2i}
$$
$$
  \cos z = \frac{e^{iz} + e^{-iz}}{2}
$$

Pro $z \in \mathbb{C} \setminus \{0\}$ definujeme hlavní hodnotu logaritmu:
$$
  \ln z = \ln |z| + i \arg z.
$$

Pro každé $z \in \mathbb{C} \setminus \{0\}$ platí:
$$
  e^{\ln z} = z.
$$

Pozor, v opačném pořadí to obecně neplatí. Tj. obecně není pravda, že $\ln e^z = z$.

$e^z = e^w$ právě tehdy, když $z = w + 2k\pi i$ pro nějaké $k \in \mathbb{Z}$.

# Mocninné řady
**Mocninná řada** je řada tvaru:
$$
  \sum_{n=0}^\infty a_n (z - z_0)^n,
$$
kde $\{a_n\}_{n=0}^\infty$ je daná číselná posloupnost (tzv. koeficienty mocninné řady), $z$ je proměnná a $z_0$ je pevné dané číslo (tzv. střed mocninné řady).

Pro každou mocninnou řadu existuje (právě jedno) $R \in [0, \infty]$ takové, že:
  - Řada absolutně konverguje na otevřeném kruhu se středem v $z_0$ a poloměru $R$,
  - Řada diverguje na množině $\{z \in \mathbb{C} : |z - z_0| > R\}$.

Toto $R$ se nazývá **poloměr konvergence** mocninné řady. Otevřený kruh se středem $z_0$ a poloměru $R$ se nazývá **kruh konvergence** mocninné řady.

$R = \infty$ znamená, že kruh konvergence je celá komplexní rovina.
Pokud $R = 0$, tak je tento otevřený kruh vlastně prázdná množina. Případ $R = 0$ může nastat, ale takové mocninné řady jsou pro nás nezajímavé, protože s nimi nejde nic moc dále dělat.

**Mocninná řada neobsahuje záporné mocniny** $(z - z_0)$.

---

Pro určení součtů mocninných řad je třeba znát některé známé součty, zejména:
  - $\sum_{n=0}^\infty z^n = \frac{1}{1 - z}$ pro $|z| < 1$ (geometrická řada),
  - $\sum_{n=0}^\infty \frac{z^n}{n!} = e^z$ pro libovolné $z \in \mathbb{C}$ (rozvoj exponenciály).

---

Mocninnou řadu (s kladným poloměrem konvergence) lze na jejím kruhu konvergence derivovat a integrovat člen po členu. Výsledkem je opět mocninná řada se stejným kruhem konvergence. Na kruhu konvergence platí:
  - Derivace:
    $$
    \left(\sum_{n=0}^\infty a_n (z - z_0)^n\right)' = \sum_{n=1}^\infty a_n n (z - z_0)^{n-1},
    $$
  - Integrace:
    $$
    \int_C \left(\sum_{n=0}^\infty a_n (z - z_0)^n\right) dz = \sum_{n=0}^\infty \frac{a_n}{n + 1} (z - z_0)^{n+1}.
    $$

---

**Jednoduché parciální zlomky** (tj. s lineárním polynomem ve jmenovateli) rozvíjíme pomocí známého součtu geometrické řady.

**Správný střed** si vytvoříme přepsáním $z = (z - z_0) + z_0$.

Parciální zlomky odpovídající vyšší násobnosti kořene převedeme pomocí integrování na jednoduché, které umíme rozvinout. Následně derivujeme, abychom získali požadovaný rozvoj.
# Laurentovy řady
**Laurentova řada** je řada tvaru:
$$
  \sum_{n=-\infty}^\infty a_n (z - z_0)^n,
$$
kde $\{a_n\}_{n=-\infty}^\infty$ je daná číselná posloupnost (tzv. koeficienty Laurentovy řady), $z$ je proměnná a $z_0$ je pevné dané číslo (tzv. střed Laurentovy řady).

Na rozdíl od mocninných řad Laurentova řada obsahuje i záporné mocniny $(z - z_0)$.

**Laurentovy řady konvergují na mezikruzích**:
  - $P(z_0; r; R)$, kde $z_0$ je střed, $r$ je vnitřní poloměr a $R$ je vnější poloměr.
  - Speciálně $P(z_0; 0; R)$ je prstencové okolí bodu $z_0$, tj. otevřený kruh se středem v $z_0$ a poloměru $R$ bez svého středu.

Při rozvoji racionální funkce do Laurentovy řady na prstencovém okolí bodu $z_0 \in \mathbb{C}$ postupujeme stejně jako u mocninných řad.

---

# Klasifikace izolovaných singularit (pomocí Laurentova rozvoje)

## Připomenutí

Nechť $f(z) = \sum_{n=-\infty}^\infty a_n (z - z_0)^n$ je Laurentův rozvoj funkce $f$ na prstencovém okolí izolované singularity $z_0 \in \mathbb{C}$. Rozlišujeme tři typy izolovaných singularit:

1. **Odstranitelná singularita:**
   - Pokud $a_n = 0$ pro každé $n < 0$, pak $z_0$ je odstranitelná singularita.
   - Rozvoj v okolí $z_0$:
     $$
     f(z) = a_0 + a_1 (z - z_0) + a_2 (z - z_0)^2 + \cdots
     $$

2. **Pól řádu $k$:**
   - Pokud $a_{-k} \neq 0$ pro nějaké $k \in \mathbb{N}$ a $a_n = 0$ pro každé $n < -k$, pak $z_0$ je pól řádu $k$.
   - Rozvoj v okolí $z_0$:
     $$
     f(z) = \frac{a_{-k}}{(z - z_0)^k} + \cdots + \frac{a_{-1}}{z - z_0} + a_0 + a_1 (z - z_0) + \cdots,
     $$
     kde $a_{-k} \neq 0$.

3. **Podstatná singularita:**
   - Pokud $a_n \neq 0$ pro nekonečně mnoho $n < 0$, pak $z_0$ je podstatná singularita.

---

## Poznámka
Máme-li k dispozici Laurentův rozvoj (na správném prstencovém okolí!), určíme typ izolované singularity přímo z rozvoje.

## Užitečné pravidlo pro izolované singularity

Uvažujme funkci $f = \frac{g}{h}$, přičemž $g$ má v bodě $z_0 \in \mathbb{C}$ kořen násobnosti $k \in \mathbb{N}_0$ a $h$ má v bodě $z_0$ kořen násobnosti $l \in \mathbb{N}$. Potom $f$ má v $z_0$:
  - **Odstranitelnou singularitu**, pokud $k \geq l$.
  - **Pól řádu $l - k$**, pokud $k < l$.

---

## Kořeny holomorfních funkcí

Funkce $f \not\equiv 0$, která je holomorfní na okolí $z_0 \in \mathbb{C}$, má v $z_0$ kořen násobnosti $k \in \mathbb{N}_0$, pokud:
$$
  f(z_0) = f'(z_0) = \cdots = f^{(k-1)}(z_0) = 0 \quad \text{a} \quad f^{(k)}(z_0) \neq 0.
$$

Polynom $(z - z_0)^k$, $k \in \mathbb{N}$, má v bodě $z_0$ kořen násobnosti $k$.

Má-li funkce $f$ v bodě $z_0 \in \mathbb{C}$ kořen násobnosti $k$ a $g$ kořen násobnosti $l$, potom funkce $f(z)g(z)$ má v bodě $z_0$ kořen násobnosti $k + l$.

---

# Reziduum

1. Nechť $f(z) = \sum_{n=-\infty}^\infty a_n (z - z_0)^n$ je Laurentův rozvoj funkce $f$ na prstencovém okolí izolované singularity $z_0 \in \mathbb{C}$. Koeficient $a_{-1}$ (tj. koeficient u $(z - z_0)^{-1}$) nazýváme **reziduem** funkce $f$ v bodě $z_0$ a značíme:
   $$
   \text{res}_{z_0} f(z) = a_{-1}.
   $$

2. Máme-li k dispozici Laurentův rozvoj (na správném prstencovém okolí!), vyčteme reziduum přímo z rozvoje.

3. Pokud nemáme Laurentův rozvoj, hodí se následující pravidla pro výčet reziduí:
   - Má-li $f(z)$ v bodě $z_0$ pól řádu $k \in \mathbb{N}$, potom:
     $$
     \text{res}_{z_0} f(z) = \frac{1}{(k - 1)!} \lim_{z \to z_0} \left[\frac{d^{k-1}}{dz^{k-1}} \left((z - z_0)^k f(z)\right)\right].
     $$
   - Je-li funkce $f$ tvaru $f = \frac{g}{h}$, kde $g$ je holomorfní na okolí $z_0$ a $h$ má v bodě $z_0$ jednonásobný kořen, potom:
     $$
     \text{res}_{z_0} \frac{g(z)}{h(z)} = \frac{g(z_0)}{h'(z_0)}.
     $$

4. Reziduum v izolované singularitě je vždy dobře definované komplexní číslo. Tvrdit, že **reziduum "neexistuje"** nebo je **"nekonečné"**, nedává žádný smysl.
### Mocninné řady

Mocninná řada je řada tvaru:
$$
  \sum_{n=0}^\infty a_n (z - z_0)^n,
$$
kde $(\{a_n\}_{n=0}^\infty)$ je daná posloupnost (koeficienty mocninné řady), $(z)$ je proměnná a \(z_0$) je střed mocninné řady.

Poloměr konvergence $(R$):
  - $(\sum_{n=0}^\infty a_n (z - z_0)^n$) absolutně konverguje pro $(|z - z_0| < R$).
  - Diverguje pro $(|z - z_0| > R$).
  - $(R = \infty$): celá komplexní rovina, $(R = 0$): prázdná množina.

Známé součty:
  - Geometrická řada: $(\sum_{n=0}^\infty z^n = \frac{1}{1-z},\ |z| < 1$).
  - Exponenciála: $(e^z = \sum_{n=0}^\infty \frac{z^n}{n!},\ z \in \mathbb{C}$).

Mocninné řady lze derivovat a integrovat člen po členu (se stejným kruhem konvergence).

Parciální zlomky:
  - Jednoduché: Rozvoj pomocí geometrické řady.
  - Vyšší násobnosti: Integrování a derivace pro získání rozvoje.

---

### Laurentovy řady

Laurentova řada je řada tvaru:
  $$
  \sum_{n=-\infty}^\infty a_n (z - z_0)^n,
  $$
  kde $(\{a_n\}_{n=-\infty}^\infty$) jsou koeficienty a $(z_0$) střed.

Obsahuje i záporné mocniny $((z - z_0)$).

Konverguje na mezikruží $(P(z_0; r; R)$):
  - $(r$): vnitřní poloměr, $(R$): vnější poloměr.
  - Speciálně $(P(z_0; 0; R)$): prstencové okolí bez středu.

Typ izolované singularity dle Laurentova rozvoje:
  1. Odstranitelná singularita: $(a_n = 0$) pro $(n < 0$).
  2. Pól řádu $(k): (a_{-k}\neq 0)$ a $(a_n = 0)$ pro $n < -k$.
  3. Podstatná singularita: $(a_n \neq 0$) pro nekonečně mnoho $(n < 0$).

---

### Klasifikace izolovaných singularit

Z Laurentova rozvoje v prstencovém okolí bodu $(z_0$):
  - Odstranitelná: $(f(z)$) je analytická.
  - Pól: Konečný počet článků s $((z - z_0)^{-k}$).
  - Podstatná: Nekonečně mnoho článků s $((z - z_0)^{-n}$).

---
![[reziduovaveta.png]]

> [!NOTE] Tríček:
> Pokaždý když vidím nějakou f(x) uvnitř nějaké transformace a je to nechutný např:
> ![[nechytnyFourier.png]]
> ![[nechutnaZtrans.png]]
> je to vždycky konvoluce: 
> $$(f*g)(x) $$

# Fourierova transformace 

$$ \hat{f}(\omega) = \mathcal{F}[f(t)](\omega) = \int_{-\infty}^{\infty} f(t)e^{-i\omega t} \, dt \quad \text{(Fourierova transformace funkce } f(t) : \mathbb{R} \to \mathbb{C}) $$ $$ \check{f}(\omega) = \mathcal{F}^{-1}[f(t)](\omega) = \frac{1}{2\pi} \int_{-\infty}^\infty f(t)e^{i\omega t} \, dt \quad \text{(inverzní Fourierova transformace funkce } f(t) : \mathbb{R} \to \mathbb{C}) $$ $\hat{f}(\omega) = 2\pi\check{f}(-\omega)$ 
Pro hezké funkce platí $\mathcal{F}^{-1}(\mathcal{F}[f(t)]) = f(t)$ (věta o inverzi). 
### Vztah Fourierovy transformace a derivace pro pěkné funkce: 
$\mathcal{F}[f^{(n)}(t)](\omega) = (i\omega)^n \mathcal{F}[f(t)](\omega)$ (obraz derivace).
Konvoluce dvou pěkných funkcí $f, g : \mathbb{R} \to \mathbb{C}$ je funkce $(f \ast g)(t) : \mathbb{R} \to \mathbb{C}$ definovaná jako $$ (f \ast g)(t) = \int_{-\infty}^\infty f(\tau)g(t-\tau) \, d\tau \quad \text{pro } t \in \mathbb{R}. $$
### Fourierova transformace konvoluce: 
$$ \mathcal{F}[(f \ast g)(t)](\omega) = \hat{f}(\omega)\hat{g}(\omega). $$

# Heavysideova funkce
![[Heavyside.png]]
Je to funkce, která slouží k "vykousnutí" kusu jiné funkce. Může se ti stát, že se ti budou násobit, tak bacha, nesmíš to roznásobit! Doporučuju si to nakreslit a pak si udělat "nového" heavysida, v těch bodech kde jsou všichni násobení heavisidi 1. Představ si to jako binární násobení 1 a 0. 
# Laplaceova transformace
**Laplaceova transformace funkce** $f(t) : [0, \infty) \to \mathbb{C}$:

$$
\mathcal{L}[f(t)](s) = F(s) = \int_{0}^{\infty} f(t) e^{-st} \, dt
$$

**Identifikace funkcí:** $f(t) = f(t)Heavyside(t)$, tj. $f(t) = 0$ pro $t < 0$.
### Derivace:
První derivace:  
$$
\mathcal{L}[f'(t)](s) = s\mathcal{L}[f(t)](s) - f(0)
$$  
Druhá derivace:  
$$
\mathcal{L}[f''(t)](s) = s^2\mathcal{L}[f(t)](s) - sf(0) - f'(0)
$$  
Obecně:  
$$
\mathcal{L}[f^{(n)}(t)](s) = s^n\mathcal{L}[f(t)](s) - s^{n-1}f(0) - \dots - f^{(n-1)}(0)
$$  
Víc než třetí derivaci tam nikdy nedostaneš, zkus si jí napsat a jsi good.
### Konvoluce:
Definice:  
$$
(f * g)(t) = \int_{0}^{t} f(\tau) g(t - \tau) \, d\tau
$$  
- Laplaceův obraz konvoluce:  
$$
\mathcal{L}[(f * g)(t)](s) = \mathcal{L}[f(t)](s) \cdot \mathcal{L}[g(t)](s)
$$  

### Inverzní Laplaceova transformace:
Pro racionální funkci $F(s) = \frac{P(s)}{Q(s)}$, kde $\deg P < \deg Q$:
$$
f(t) = \mathcal{L}^{-1}[F(s)](t) = \sum_{k=1}^n \text{Res}_{s = z_k} \left(F(s)e^{st}\right)
$$
kde $z_k$ jsou póly funkce $F(s)$.
### Periodické funkce:
Pro periodickou funkci $f(t)$ s periodou $T$(11 = HEAVYSIDE):
$$
\mathcal{L}[f(t)](s) = \frac{\mathcal{L}[f(t)(11(t) - 11(t - T))](s)}{1 - e^{-sT}}
$$
# Z-transformace
**Z-transformace posloupnosti** $(a_n)_{n=0}^\infty$ je definována jako:
$$
\mathcal{Z}[a_n](z) = F(z) = \sum_{n=0}^\infty \frac{a_n}{z^n}
$$
Koefficienty posloupnosti $(a_n)_{n=0}^\infty$ odpovídají mocninám $z^{-n}$. Například:
  - $a_0$ je absolutní člen,  
  - $a_1$ je koeficient u $z^{-1}$,  
  - $a_2$ je koeficient u $z^{-2}$, atd.

### Základní aritmetika Z-transformace:
**Linearita:**  
$$
\mathcal{Z}[\alpha a_n + \beta b_n](z) = \alpha \mathcal{Z}[a_n](z) + \beta \mathcal{Z}[b_n](z)
$$
**Posun vlevo:**  
$$
\mathcal{Z}[a_{n+k}](z) = z^k \mathcal{Z}[a_n](z) - a_0 z^k - a_1 z^{k-1} - \dots - a_{k-1} z
$$
Speciálně:
- $k = 1$:  
$$
\mathcal{Z}[a_{n+1}](z) = z \mathcal{Z}[a_n](z) - a_0 z
$$
- $k = 2$:  
$$
\mathcal{Z}[a_{n+2}](z) = z^2 \mathcal{Z}[a_n](z) - a_0 z^2 - a_1 z
$$
### Konvoluce posloupností:
Pro posloupnosti $(a_n)$ a $(b_n)$:
$$
(a_n * b_n) = \sum_{k=0}^n a_k b_{n-k}
$$
Laplaceův obraz konvoluce:  
$$
\mathcal{Z}[a_n * b_n](z) = \mathcal{Z}[a_n](z) \cdot \mathcal{Z}[b_n](z)
$$
### Inverzní Z-transformace:
**Pomocí Laurentovy řady:**  
$$
F(z) = \sum_{n=0}^\infty \frac{a_n}{z^n}
$$
**Pomocí reziduí:** Pro racionální funkci $F(z) = \frac{P(z)}{Q(z)}$, kde $\deg Q \geq \deg P$, platí: $$ a_n = \sum_{z_j} \text{Res}_{z=z_j} \left( \frac{P(z)}{Q(z)} z^{n-1} \right) $$ kde $z_j$ jsou póly funkce. - **Limita pro $a_0$:** $$ a_0 = \lim_{z \to \infty} F(z) $$

# Důkazy 
Většina důkazů co po tobě může chtít je v podstatě jen dosazení do definice nějaké transformace a vytvoření vzorečků co máš na úvodní straně testu. Možná spočtítat nějakou transformaci z definice.
Ta základní věta a Liovulillova věta jsou hodně pro Áčkaře, kámoš co měl maximální počet bodu mu je tam musel dělat. CR podmínky jsou taky slušný overkill, ale dají se naučit a překvapí ho. Hlavně mu prosím neodvozujte všichni to samý.
![[komplexdukazy1.png]]
![[komplexdukazy2.png]]
![[komplexdukazy3.png]]
![[dukaz3.jpg]]
Specificky pro K=3 reziduum přes limitu.