## Opgave 1
Givet følgende Euler-Cauchy differentialligning:
$$
x^{2} y '' + 4xy' - 4y = 0
$$
med følgende betingelser: $y(1) = 0$ og $y'(2) = 1$
#### a) Bestem den generelle løsning til differentialligningen.
Jeg har Euler-Cauchy differentialligningen:
$$
x^{2} y'' + 4xy' - 4y = 0
$$

For at løse en Euler-Cauchy differentialligning antager jeg en løsning på formen $y = x^{r}$. Jeg beregner først de afledte:
$$
y' = r x^{r-1}, \quad y'' = r(r-1) x^{r-2}
$$

Indsætter jeg disse i differentialligningen får jeg:
$$
x^{2} \cdot r(r-1) x^{r-2} + 4x \cdot r x^{r-1} - 4 x^{r} = 0
$$

Forenkler udtrykket:
$$
r(r-1) x^{r} + 4r x^{r} - 4 x^{r} = 0
$$

jeg kan dividere med $x^{r}$ (da $x \neq 0$):
$$
r(r-1) + 4r - 4 = 0 \implies r^{2} - r + 4r - 4 = 0 \implies r^{2} + 3r - 4 = 0
$$

Løser den karakteristiske ligning:
$$
r = \frac{-3 \pm \sqrt{9 + 16}}{2} = \frac{-3 \pm 5}{2}
$$

Dermed er rødderne:
$$
r_1 = 1, \quad r_2 = -4
$$

Den generelle løsning til differentialligningen er derfor:
$$
y(x) = C_1 x + \frac{C_2}{x^{4}}
$$

#### b) Bestem den partikulære løsning, der opfylder de givne betingelser.

Jeg har betingelserne $y(1) = 0$ og $y'(2) = 1$. Først bruger jeg $y(1) = 0$:
$$
y(1) = C_1 \cdot 1 + \frac{C_2}{1^{4}} = C_1 + C_2 = 0 \implies C_1 = -C_2
$$

Derefter beregner jeg $y'(x)$:
$$
y'(x) = C_1 - \frac{4 C_2}{x^{5}}
$$

Bruger nu $y'(2) = 1$:
$$
y'(2) = C_1 - \frac{4 C_2}{32} = C_1 - \frac{C_2}{8} = 1
$$

Da $C_1 = -C_2$, indsætter jeg:
$$
-C_2 - \frac{C_2}{8} = 1 \implies -\frac{9 C_2}{8} = 1 \implies C_2 = -\frac{8}{9}
$$

Dermed er $C_1 = \frac{8}{9}$. 

Den partikulære løsning er derfor:
$$
y(x) = \frac{8}{9} x - \frac{8}{9 x^{4}} = \frac{8}{9} \left( x - \frac{1}{x^{4}} \right)
$$
## Opgave 2
Den endimensionale bølgeligning for en given stålwire med længden L er givet ved:
$$
\frac{\partial^{2}u}{\partial t^{2}} = c^{2} \frac{\partial^{2}u}{\partial x^{2}}
$$
hvor $c^{2} = 1$ og $L = 2$

Der gælder følgende randbetingelser: $u(0,t) = 0$ og $u(L,t) = 0$

Desuden gælder følgende begyndelsesbetingelser: $u(x,0) = f(x)$ og $u_{t}(x,0) = 0$

Ved separation af de variable, idet det antages at $u(x,t) = F(x)G(t)$, kan man (som bekendt fra lærerbogen), komme frem til følgende ordinære differentialligninger:
$$
\frac{d^{2} F}{dx^{2}} = kF \quad \text{og} \quad \frac{d^{2}G}{dt^{2}} = kG
$$

#### a) Løs disse to differentialligninger når k er negativ, dvs. $k = -p^{2}$:
Hvis $k<0$:
Jeg sætter $k = -p^{2}$, hvor $p>0$. Derfor bliver differentialligningen:
$$
\frac{d^{2}F}{dx^{2}} + p^{2} F = 0
$$
Den karakteristiske ligninger er:
$$
r^{2} + p^{2} = 0 \Rightarrow r = \pm ip
$$
Her er den generelle løsning:
$$
F(x) = A \cos(px) + B \sin(px)
$$
Med randbetingelserne:
$$
\begin{align*}
F(0) = A \cos(0) + B \sin(0) = A \cdot 1 + B \cdot 0 &= 0\\
F(L) =  A \cos(Lp) + B \sin(Lp) = A \cos(2p) + B \sin(2p)\\
\end{align*}
$$
For at få noget andet end den trivielle løsning $B = 0$ så skal $\sin(p) = 0$, hvilket betyder at:
$$
\sin(2p) = 0 \Rightarrow 2p = n \pi \Rightarrow p = \frac{n \pi}{2}, \quad n = 1,2,3 \dots
$$
De ikke-trivielle løsninger er derfor givet ved:
$$
F_{n}(x) = B_{n} \sin\left(\frac{n \pi x}{2}\right), \quad n = 1,2,3 \dots
$$
For $G(t)$-ligningen:
$$
\frac{d^{2}G}{dt^{2}} + p^{2} G = 0 \Rightarrow \frac{d^{2}G}{dt^{2}} + \left(\frac{n \pi}{2}\right)^{2} G = 0
$$
Den generelle løsning er:
$$
G_{n}(t) = C_{n} \cos\left(\frac{n \pi t}{2}\right) + D_{n} \sin\left(\frac{n \pi t}{2}\right)
$$
#### b) Opskriv løsningen til bølgeligningen $u(x,t) = F(x)G(t)$ med løsningerne fra sp. a indsat. Bestem herefter de løsninger, der opfylder randbetingelserne.
Den generelle løsning ved seperation af variable er:
$$
u(x,t) = \sum_{n=1} ^{\infty} \left[A_{n} \cos\left(\frac{n \pi c t}{2}\right) + B_{n} \sin\left(\frac{n \pi c t}{2}\right)\right] \sin\left(\frac{n \pi x}{2}\right)
$$
Siden $c^{2} = 1 \Rightarrow c = 1$
$$
u(x,t) = \sum_{n=1} ^{\infty} \left[A_{n} \cos\left(\frac{n \pi t}{2}\right) + B_{n} \sin\left(\frac{n \pi t}{2}\right)\right] \sin\left(\frac{n \pi x}{2}\right)
$$

#### c) Herefter anvdendes begyndelsesbetingelsen $u_{t} (x,0) = 0$ Gør rede for at den fuldstændige løsning til bølgeligningen herefter er:
$$
u(x,t) = \sum_{n=1} ^{\infty} B_{n} \sin\left(\frac{n \pi}{2} \cdot x\right) \cdot \cos\left(\frac{n \pi}{2} \cdot t\right)
$$
Fra begyndelsesbetingelsen $u_{t}(x,0) = 0$:
$$
u_{t}(x,t) = \sum_{n=1} ^{\infty} \left[- A_{n}\frac{n \pi}{2} \sin\left(\frac{n \pi t}{2}\right) + B_{n}' \frac{n \pi}{2} \cos\left(\frac{n \pi t}{2}\right) \right] \sin\left(\frac{n \pi x}{2}\right)
$$

Ved $t=0$:
$$
u_{t}(x,0) = \sum_{n=1}^{\infty} B_{n} \frac{n \pi}{2} \sin\left(\frac{n \pi x}{2}\right) = 0
$$
Dette gælder kun hvis $B_{n} = 0$ for alle n. Derfor bliver løsningen:
$$
u(x,t) = \sum_{n=1} ^ {\infty} A_{n}\cos\left(\frac{n \pi t}{2}\right) \sin\left(\frac{n \pi x}{2}\right)
$$

#### d) Bestem den partikulære løsning, der opfylder begyndelsesbetingelsen
$$
u(x,0) = f(x) = 0.1 \cdot \sin\left(\frac{3 \pi}{2} \cdot x\right)
$$
Fourierrækken:
$$
f(x) = \sum A_{n} \sin\left(\frac{n \pi x}{2}\right)
$$
Ud fra begyndelsesbetingelsen ses det at $n=3$. Derfor er:
$$
\begin{align*}
A_{3} &=  0.1\\
A_{n} &= 0, \quad \text{ for } n \neq 3
\end{align*}
$$
Dermed bliver den endelige løsning:
$$
u(x,t) = 0.1 \cdot \cos\left(\frac{3 \pi t}{2}\right) \sin\left(\frac{3 \pi}{2} \cdot x\right)
$$
## Opgave 3
En laplace transformation. Ikke noget vi har haft om i dette kursus.

## Opgave 4
En periodisk funktion er givet ved:
$$
f(x) = \cases{0, \quad \text{for } -0.5 < x < -0.1\\
40, \quad \text{for } -0.1 < x < 0.1\\
0 \quad \text{for } 0.1 < x <0.5}
$$
$f(x+1) = f(x)$

#### a) Skitsér grafen

#### b) Udled fourierrækken for $f(x)$
Fourierrækken for en given funktion $f(x)$ er generelt givet ved formlen
$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{2 \pi n x}{T}\right)+ b_{n} \sin\left(\frac{2 \pi n x}{T}\right)\right]
$$
I dette tilfælde er perioden $p=1$. Da $p = 2L$ Så er $L = 0.5$

Dernæst skal jeg beregne $a_{0}, a_{n} \text{ og } b_{n}$:
$$
\begin{align*}
a_{0} &=  \frac{1}{L} \int_{-L}^{L} f(x) \, dx\\
a_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx\\
b_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx
\end{align*}
$$
Men da jeg kan se at funktionen er lige, dvs. $f(x) = -f(x)$. Så betyder det at $b_{n}$ ud fra teorien har en værdi på 0. Dette skyldes at $\sin(2 \pi n x)$ er enulige funktion, og integralet af en lige funktion ganget med en ulige funktio

Jeg starter med at beregne $a_{0}$:

Nu beregner jeg $a_{n}$: 
$$
a_{n} =  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx
$$

Nu skal jeg trække den nedre grænse fra den øvre grænse:


Nu skal jeg regne hvordan funktionen ser ud for lige og ulige n-værdier:

Derfor bliver $a_{n}$:
$$
a_{n} = \cases{0, \quad \quad \quad \space \text{ hvis n er lige} \\
- \frac{4}{n^{2} \pi^{2}}, \quad \text{ hvis n er ulige}}
$$
Nu beregner jeg $b_{n}$:
$$
b_{n} =  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx\\
$$
Indsætter i formlen for $b_{n}$

Nu skal jeg trække den nedre grænse fra den øvre grænse:

Nu skal jeg regne hvordan funktionen ser ud for lige og ulige n-værdier:

Derfor bliver $b_{n}$:
$$
b_{n} = \cases{-\frac{2}{n \pi}, \quad  \text{ hvis n er lige} \\
0, \quad \quad \space \space  \text{ hvis n er ulige}}
$$
Nu hvor jeg har beregnet $a_{0}, a_{n}$ og $b_{n}$ kan jeg indsætte det i formlen for fourierrækken:
$$
\frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{ \pi n x}{2}\right)+ b_{n} \sin\left(\frac{\pi n x}{2}\right)\right] 
$$