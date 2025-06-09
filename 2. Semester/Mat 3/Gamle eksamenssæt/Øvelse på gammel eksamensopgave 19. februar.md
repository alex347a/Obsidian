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
u_{t}(x,0) = \sum_{n=1} ^{\infty} \left[\frac{n \pi}{2} D_{n}\right] \sin\left(\frac{n \pi x}{2}\right) = 0 \Rightarrow D_{n} = 0, \text{ for alle n}
$$
Derfor kan løsningen simplificeres til:
$$
u(x,t) = \sum_{n=1} ^{\infty} \left[B_{n} \sin\left(\frac{n \pi x}{2}\right)\right] \cos\left(\frac{n \pi t}{2}\right)
$$
Fra den anden begyndelsesbetingelse $u(x,0) = f(x)$:
$$
f(x) = \sum_{n=1} ^{\infty} A_{n} \sin\left(\frac{n \pi x}{2}\right)
$$
Jeg beregner $A_{n}$ med formlen:
$$
A_{n} = \frac{2}{L} \int_{0}^{L} f(x) \sin\left(\frac{n \pi x}{2}\right) \, dx = \int_{0}^{2} f(x) \sin\left(\frac{n \pi x}{2}\right) \, dx 
$$

Fra randbetingelsen: $u_{t}(x,0) = 0$:
$$
G_{n}' (0) = \frac{n \pi}{2} D_{n} = 0 \Rightarrow D_{n} = 0
$$
Derfor bliver den fulde løsning:
$$
u(x,t) = \sum_{n=1} ^ {\infty} a_{n} \sin\left(\frac{n \pi x}{2}\right) \cos\left(\frac{n \pi x}{2}\right)
$$
hvor $a_{n} = B_{n} C_{n}$ bestemmes fra $u(x,0) = f(x)$