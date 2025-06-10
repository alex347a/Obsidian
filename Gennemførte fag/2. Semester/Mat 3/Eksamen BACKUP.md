## Opgave 1
Givet funktionen $g(x) = \cases{-4x(x-1), \quad \text{for } 0 \leq x \leq 1\\ 0 \quad \text{ ellers}}$
#### a) Lav en skitse af $g(x)$
$$
-4x(x-1)
$$
Jeg indsætter x-værdier mellem 0 og 1:
$$
\begin{align*}
x= \frac{1}{4} \Rightarrow -1\left(- \frac{3}{4}\right) &=  \frac{3}{4}\\
x= \frac{1}{2} \Rightarrow -2\left(- \frac{1}{2}\right) &=  1\\
x= \frac{3}{4} \Rightarrow -3\left(- \frac{1}{4}\right) &=  \frac{3}{4}
\end{align*}
$$
![[Pasted image 20250610103605.png]]

#### b) Lav en ulige periodisk udvidelse af $g(x)$ og skitsér denne.
For at lave en ulige periodisk udvidelse, så betyder det at $-g(-x)=g(x)$.

Dette betyder at funktionen $$g(x) = \cases{-4x(x-1), \quad \text{for } 0 \leq x \leq 1,\\ 4x(x-1), \quad \text{for } -1 \leq x \leq 0, \\ 0 \quad \text{ ellers}}$$

![[Pasted image 20250610103557.png]]

Funktionen fra spørgsmål b) benævnes $f(x)$
#### c) Undersøg om $f(x)$, $f'(x)$ og $f''(x)$ er kontinuerte når $x=0$

Jeg tror hvis funktionerne er kontinuerte, så må det betyde at jeg kan differentiere dem i punktet.
$$
f(0) = 4 \cdot 0 (0-1) = 0
$$
$$
\begin{align*}
f'(x) = (-4x(x-1))' &=  (-4x^{2} - 4x)'\\
&= -8x - 4\\
f'(0)&= -4
\end{align*}
$$
$$
\begin{align*}
f''(x) &=  (-8x-4)'\\
&= -8\\
f''(0) &= -8\\
\end{align*}
$$

Jeg ville ikke umiddelbart tro at funktionerne er kontinuerte når $x=0$. Men jeg er ikke sikker på den korrekte måde at tjekke det på.
#### d) Udregn fourierrækken for $f(x)$
Jeg er ikke sikker på hvordan jeg får funktionen på en normal funktionsform, måske det har noget at gøre med min ulige periodiske udvidelse at gøre.

Generelt så er fourierrækken for en given funktion $f(x)$  givet ved formlen
$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{\pi n x}{L}\right)+ b_{n} \sin\left(\frac{\pi n x}{L}\right)\right]
$$
I dette tilfælde har jeg ingen ide om hvad perioden er, men hvis jeg havde den så ville funktionens periode være givet ved $p$, dvs. da $p = 2L$ så ville jeg kunne indsætte L i formlen for fourierrækken. Men i dette tilfælde ved jeg ikke hvad $p$ er, da funktionen tilsyneladende er 0 udover fra $-1 \leq x \leq 1$ 

Dernæst ville jeg skulle beregne $a_{0}, a_{n} \text{ og } b_{n}$:
$$
\begin{align*}
a_{0} &=  \frac{1}{L} \int_{-L}^{L} f(x) \, dx\\
a_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx\\
b_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx
\end{align*}
$$
Men da funktionen er en ulige funktion så vil både $a_{0} = 0$ og $a_{n} = 0$. Derfor ville jeg kun skulle beregne $b_{n}$ og efter at have gjort det indsætte den i formlen for fourrierrækken.
$$
\frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos(\pi x)+ b_{n} \sin(\pi x)\right]
$$
Da både $a_{0} = 0$ og $a_{n} = 0$. Så ville fourierrækken være givet ved:
$$
\sum_{n=1}^{\infty} \left[b_{n} \sin(\pi x)\right]
$$
Hvor jeg så ville kunne indsætte den beregnede $b_{n}$-værdi hvis jeg havde den.
## Opgave 2
Givet den endimensionale varmeledningsligning for en stang med længden $L = 0.2 m$
$$
\frac{\partial u}{\partial t} = 4 \frac{\partial^{2} u }{\partial x^{2}}
$$
hvor $u = u(x,t)$ er temperaturen i stangen som funktion af position og tid.

Der foreslås følgende løsning: $𝑢(𝑥,𝑡)=(𝐴𝑐𝑜𝑠(𝑝𝑥)+𝐵𝑠𝑖𝑛(𝑝𝑥))𝑒^{−4𝑝2𝑡}$

#### a) Vis ved substitution, at dette forslag er en løsning til varmeledningsligningen.
$$
4\frac{d^{2} F}{d x^{2}} = kF, \quad \text{og } \quad \frac{dG}{dt} = \frac{1}{4}kG
$$
Jeg starter med at indsætte:
$$
u(x,t) = F(x)G(t)
$$
i udtrykket for varmeledningsligningen:
$$
\frac{\partial u}{\partial t} = 4 \frac{\partial^{2} u }{\partial x^{2}} \Rightarrow \frac{\partial u}{\partial t} - 4\frac{\partial^{2} u}{\partial x^{2}} = 0
$$
$$
\frac{\partial u}{\partial t} - 4\frac{\partial^{2} u}{\partial x^{2}} = 0
$$
Først beregner jeg de partielle afledede:
Den tidsafledte:
$$
\frac{\partial u}{\partial t} = F(x) \frac{dG}{dt}
$$
Den rumafledte:
$$
4\frac{\partial^{2} u}{\partial x^{2}} = 4G(t) \frac{d^{2}F}{dx^{2}}
$$
Dette indsætter jeg i varmeledningsligningen:
$$
F(x) \frac{dG}{dt} - 4G(t) \frac{d^{2}F}{dx^{2}} = 0
$$
Jeg deler begge sider med $F(x)G(t)$, og antager at $F(x)G(t) \neq 0$:
$$
\frac{1}{G(t)} \frac{dG}{dt} = \frac{4}{F(x)} \frac{d^{2}F}{dx^{2}}
$$
Venstre side af ligningen afhænger kun af t, mens højresiden af ligningen kun afhænger af x. Dette betyder at begge sider er lig med den samme konstant $k$. Derfor kan der laves to ordinære differentialligninger:
Først den tidsafledte:
$$
\frac{1}{G(t)} \frac{dG}{dt} = k \quad \Rightarrow \quad \frac{dG}{dt} = k G(t)
$$
Dernæst den rumafledte:
$$
\frac{4}{F(x)} \frac{d^{2}F}{dx^{2}} = k \quad \Rightarrow \quad \frac{d^{2}F}{dx^{2}} = \frac{1}{4}k F(x)
$$
De to ønskede ordinære differentialligninger er altså givet ved:
$$
\frac{dG}{dt} = k G(t), \quad \text{og} \quad \frac{d^{2}F}{dx^{2}} = \frac{1}{4}k F(x)
$$
$$
\frac{d^{2}F}{dx^{2}} = \frac{1}{4} kF
$$
skal være negativ (dvs. $k = -4p^{2}$) i følge forslaget til løsningen.

Hvis $k<0$:
Jeg sætter $k = -p^{2}$, hvor $p>0$. Derfor bliver differentialligningen:
$$
\frac{d^{2}F}{dx^{2}} + 4p^{2} F = 0
$$
Den karakteristiske ligninger er:
$$
r^{2} + p^{2} = 0 \Rightarrow r = \pm ip
$$
Den generelle løsning:
$$
F(x) = A \cos(px) + B \sin(px)
$$
For tidsligningen:
$$
\frac{dG}{dt} = kG(t)
$$
Da $k = -4p^{2}$:
$$
\begin{align*}
\text{Dette er en separabel ODE.}\\
\text{Jeg integrerer begge sider:}\\
\int \frac{dG}{G} &= -4 p^{2} \int dt\\
\ln(G) &= - \left(\frac{(2 n - 1) \pi}{4}\right)^{2} t + C\\
G_{n}(t) = C_{n} e^{ -4 p^{2} t} 
\end{align*}
$$
Dermed hvis jeg indsætter mit svar for $F(x)$ og for $G_{n}(t)$:
$$
u(x,t) = C_{n}(A \cos(px) + B \cos(px)) e^{-4 p^{2} t}
$$
Måske er konstanten i opgaven bare antaget at være 0, så vil løsningen blive ligesom i opgaven:
$$
u(x,t) = (A \cos(px) + B \cos(px)) e^{-4 p^{2} t}
$$
## Opgave 3
Givet hastighedsfeltet $\vec{v} = (x,x,0)$
#### a) Lav en skitse af $\vec{v}$
![[Pasted image 20250610092607.png]]

#### b) Udregn divergensen 𝑑𝑖𝑣𝑣⃗ og forklar resultatet for punktet P(2, 2) vha. en skitse.
$\text{div }\nabla = \nabla \cdot \vec{v}$
$$
\begin{pmatrix}\frac{\delta }{\delta x} \\ \frac{\delta }{\delta y} \\ \frac{\delta }{\delta z}\end{pmatrix} \cdot \begin{pmatrix}v_{1} \\ v_{2} \\ v_{3}\end{pmatrix}
$$

$$
\vec{v} = [x,x,0]
$$
$$
P: (2,2)
$$
Jeg bruger formlen:
$$
\text{div } \vec{v} = \frac{\delta v_{1}}{\delta x}, \frac{\delta v_{2}}{\delta y}, \frac{\delta v_{3}}{\delta z}\\
$$
$$
\begin{align*}
\frac{\delta v_{1}}{\delta x} &= 1 \\
\frac{\delta v_{2}}{\delta y} &= x\\
\frac{\delta v_{3}}{\delta z} &= 0
\end{align*}
$$

Dermed er 
$$
\text{div } \vec{v} = (1, 0, 0)\\
$$
Nu kan jeg indsætte punktet P:

$$
div (\vec{v})|_{(2,2)} = (1,0,0)
$$
![[Pasted image 20250610094646.png]]
#### c) Udregn rotationen 𝑟𝑜𝑡𝑣⃗ og forklar resultatet for punktet P(2, 2) vha. en skitse
Rotationen er det vi kalder for curl:
$$
\begin{align*}
\nabla \times \vec{v} &=  
\begin{vmatrix}
\hat{i} & \hat{j} & \hat{k}\\
\partial_{x} & \partial_{y} & \partial_{z}\\
x & x & 0\\
\end{vmatrix}\\
&= \hat{i} \left(\frac{\partial}{\partial y}(0) - \frac{\partial}{\partial z}(x)\right) - \hat{j} \left(\frac{\partial}{\partial x}\left(0\right) - \frac{\partial}{\partial z}(x)\right) + \hat{k} \left(\frac{\partial}{\partial x}\left(x\right) - \frac{\partial}{\partial y}(x)\right)\\
&= \hat{i}(0-0) - \hat{j}(0-0) + \hat{k}(1-0)\\
&=  [0,0,1]
\end{align*}
$$
![[Pasted image 20250610094530.png]]
## Opgave 4
Givet et vektorfelt $\vec{F} = (xy + y^{2}, x-y)$ og kurven C, der ses på figuren herunder:
![[Pasted image 20250610094729.png]]
#### a) Udregn linjeintegralet
$$
\oint_{C} \vec{F}(\vec{r}) \cdot d \vec{r}
$$
ved hjælp af Greens sætning.

Greens sætning siger:
$$
\int_{C} \vec{F} \cdot d \vec{r} = \iint_{R} \left(\frac{\partial \vec{F}_{2}}{\partial x} - \frac{\partial \vec{F}_{1}}{\partial y}\right) \, dA
$$
$$
\vec{F} = (xy + y^{2}, x-y)
$$
Da C består af de to kurver fra 0 til (1,1):
$$
y = x^{2} \quad \text{ og } \quad x=y^{2}
$$
Så bliver grænserne for integralet:
$$
 x^{2} \leq y \leq 1 \quad \text{ og } \quad y^{2} \leq x \leq 1
$$
$$
\int_{x^{2}}^{1} \, dy \int_{y^{2}}^{1} \left(\frac{\partial \vec{F}_{2}}{\partial x} - \frac{\partial \vec{F}_{1}}{\partial y}\right) \, dx
$$
Nu skal jeg regne det inde i parentesen:
$$
\begin{align*}
F_{1} &= xy+y^{2}\\
F_{2} &=  x-y\\
\frac{\partial F_{2}}{\partial x} = \frac{\partial(x-y)}{\partial x} &= 0\\
\frac{\partial F_{1}}{\partial y} = \frac{\partial(xy+y^{2})}{\partial y} &= x + 2y\\
\end{align*}
$$

Nu kan jeg indsætte i integralet:
$$
\int_{x^{2}}^{1} \, dy \int_{y^{2}}^{1} 0 - x+2y \, dx = \int_{x^{2}}^{1} 2y \ dy \int_{y^{2}}^{1} -x \, dx
$$
Jeg starter med det yderste integrale:
$$
\begin{align*}
\int_{y^{2}}^{1}-x \, dx &=  \left[-\frac{1}{2} x^{2}\right]_{y^{2}}^{1} = -\frac{1}{2} - \left(- \frac{1}{2} y^{4}\right)\\
&= \frac{1}{2}y^{4} - \frac{1}{2}
\end{align*}
$$
Dette indsætter jeg i det inderste integrale:
$$
\begin{align*}
\int_{x^{2}}^{1} 2y + \frac{1}{2}y^{4} - \frac{1}{2} \ dy &= -\frac{1}{2} \int_{x^{2}}^{1} 2y + \frac{1}{2}y^{4} \ dy\\
\left[y^{2} + \frac{y^{5}}{8}\right]_{x^{2}}^{1} = 1 + \frac{1}{8} - \left(x^{4} + \frac{x^{10}}{8}\right)
\end{align*}
$$
Dermed får jeg:
$$
- \frac{1}{2} \cdot \frac{9}{8} - \left(x^{4} + \frac{x^{10}}{8}\right)
$$
Der er gået noget helt galt i mine grænser idet jeg forventer at mit integrale er et tal, og ikke noget der afhænger af x.