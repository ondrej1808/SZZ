# AVT 2 – Slyšení, elektrodynamický a elektrostatický měnič, vzorkování a kódování zvuku

**Oficiální otázka:** Fyziologie a anatomie slyšení. Elektrodynamický a elektrostatický měnič. Vzorkování, kvantování a zdrojové kódování zvuku.

## Fyziologie a anatomie slyšení

### Anatomie

**Vnější ucho.** Boltec směruje zvuk do ucha a pomáhá s lokalizací. **Zvukovod** (~24–27 mm) chrání a působí jako rezonátor v pásmu ~1–4 kHz (oblast lidské řeči). **Bubínek** je membrána provádějící akusticko-mechanický převod tlaku na pohyb.

**Střední ucho.** Soustava kůstek **kladívko–kovadlinka–třmínek** tvoří **impedanční přizpůsobení** (vzduch → kapalina), které zvýší tlak přibližně 19× a předá ho na **oválné okénko**. Svaly středního ucha při velké hlasitosti pomalu napnou (ochrana sluchu), ale nestihnou reagovat na náhlý ráz (výstřel). **Eustachova trubice** vyrovnává tlak za bubínkem.

**Vnitřní ucho.** **Hlemýžď (kochlea)** má ~2,5 závitu a je naplněn kapalinou, kterou rozkmitá oválné okénko. Po jeho délce je **bazilární membrána** a **Cortiho orgán** s vláskovými buňkami. Každé místo membrány rezonuje na jiné frekvenci; rozkmitání excituje vláskové buňky → elektrický signál do mozku.

### Fyziologie vnímání

Slyšení pravděpodobně kombinuje dvě teorie:

1. **Místní (frekvenční) kódování** – poloha maxima rozkmitu na bazilární membráně určuje frekvenci (vysoké tóny).
2. **Časové kódování** – nízké frekvence rozkmitají celou kochleu a mozek frekvenci pozná z časového průběhu.

**Hlasitost** vnímáme **nelineárně** a na každé frekvenci jinak — viz **křivky stejné hlasitosti** (isofony). Nejcitlivější jsme v pásmu řeči; nejspodnější křivka = práh slyšitelnosti. Vnímání hlasitosti je přibližně **logaritmické** (proto dB).

**Maskování** (klíčové pro audio kompresi):

- **Frekvenční** – hlasitější tón zamaskuje slabší tón blízké frekvence (např. 40 dB / 150 Hz zmizí pod 60 dB / 250 Hz).
- **Časové (dopředné a zpětné)** – hlasitý zvuk maskuje slabší těsně před a po sobě na téže frekvenci.

**Lokalizace zdroje** zvuku:

1. **Časový (fázový) rozdíl** mezi ušima (ITD),
2. **Útlum hlavou** závislý na frekvenci (ILD / HRTF),
3. tvarování **boltcem**,
4. **vzdálenost** podle hlasitosti.

## Elektrodynamický a elektrostatický měnič

**Elektroakustické měniče** převádějí elektromagnetické pole na akustické a naopak. Dělení podle principu:

1. **Magnetické pole → elektrodynamický** měnič,
2. **Elektrické pole → elektrostatický** (a piezoelektrický),
3. ostatní.

### Elektrodynamický měnič

Membrána se zvukem rozkmitá, s ní i připojená **cívka** pohybující se v poli pevného **magnetu**.

- **Jako mikrofon:** pohyb cívky v magnetickém poli indukuje napětí podle **Faradayova indukčního zákona**

$$
u = -\frac{\mathrm d\Phi}{\mathrm dt},
$$

kde $\Phi$ je magnetický indukční tok.

- **Jako reproduktor:** proud cívkou v poli magnetu vyvolá **Lorentzovu sílu**, která rozkmitá membránu

$$
\vec F = q\,(\vec v \times \vec B).
$$

Robustní, levný, nevyžaduje napájení.

### Elektrostatický (kondenzátorový) měnič

Místo membrány vibruje vodivá **destička**, která s pevnou protielektrodou tvoří **kondenzátor**. Vyžaduje **polarizační napětí (phantom power)** — destičky musí být nabité (baterie nebo napájení přes konektor).

- **Jako mikrofon:** pohyb mění kapacitu, a tím napětí na nabitém kondenzátoru; náboj

$$
q = uC = u\,\frac{\varepsilon_0 S}{d}.
$$

- **Jako reproduktor:** přiložené napětí vyvolá **elektrostatickou sílu** mezi deskami

$$
F = \frac{\varepsilon_0 S\,u^2}{2 d^2}.
$$

Kvalitnější (lineárnější, širší pásmo), ale dražší a náročnější na napájení — proto převažuje v **měřicích mikrofonech**.

## Vzorkování, kvantování a zdrojové kódování zvuku

### Vzorkování

Převod spojitého (analogového) signálu na diskrétní. Dle **vzorkovací (Nyquistovy) podmínky** musí být vzorkovací kmitočet alespoň **dvojnásobek** nejvyšší frekvence signálu:

$$
f_s \ge 2 f_{\max}.
$$

Člověk slyší do ~20 kHz → teoretické minimum 40 kHz; s rezervou na antialiasingový filtr se používá **44,1 kHz** (CD) a **48 kHz** (produkce). Nesplnění podmínky způsobí **aliasing** (vysoké frekvence se „přehnou" na nízké).

### Kvantování

Spojitá amplituda se zaokrouhlí na konečný počet úrovní. U obrazu stačí 8 bitů (256 úrovní), u zvuku je ucho citlivější → běžně **16 bitů** (CD), pro produkci **24 bitů**. Zaokrouhlení zavádí **kvantizační šum**.

### Zdrojové kódování (komprese)

Cílem je snížit objem dat:

- **Ztrátová** – využívá **psychoakustiku** (maskování, omezení špatně slyšitelných frekvencí): **MP3**, **AAC**.
- **Bezeztrátová** – přesná rekonstrukce: **FLAC**.

## Co umět u zkoušky

- Cesta zvuku uchem, impedanční přizpůsobení kůstek (~19×), kochlea a místní vs. časové kódování frekvence.
- Křivky stejné hlasitosti, logaritmické vnímání, **maskování** (frekvenční i časové) a jeho využití v kompresi.
- Lokalizace (ITD, ILD).
- Elektrodynamický (Faraday / Lorentz) vs. elektrostatický (kapacita, phantom power) měnič — princip mikrofonu i reproduktoru a vzorce.
- Vzorkování (44,1/48 kHz, Nyquist), kvantování (16/24 bit), MP3/AAC/FLAC.

**Zdroje:** AVT skripta (`avt1.pdf`, `avt2.pdf`), HEX-compost.
