## Opgave 1
$$
\begin{align*}
f(x) &= \cases{0, \quad \text{når } -2 < x < 0,\\
x - 1, \quad \text{når } 0 < x < 2}\\
f(x+4) &= f(x)
\end{align*}
$$
#### a) Skitsér grafen for $f(x)$.
![[Pasted image 20250608133902.png]]

#### b) Udled fourierrækken for $f(x)$
Fourierrækken for en given funktion $f(x)$ er generelt givet ved formlen
$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{ \pi n x}{L}\right)+ b_{n} \sin\left(\frac{ \pi n x}{L}\right)\right]
$$
I dette tilfælde da $f(x+4) = f(x)$ så har funktionen en periode $T$ på 4, og da $2L = p$ så er $L=2$:
$$
f(x) =  \frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{ \pi n x}{2}\right)+ b_{n} \sin\left(\frac{\pi n x}{2}\right)\right]\\
$$
Nu skal jeg beregne $a_{0}, a_{n} \text{ og } b_{n}$:
$$
\begin{align*}
a_{0} &=  \frac{1}{L} \int_{-L}^{L} f(x) \, dx\\
a_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx\\
b_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx
\end{align*}
$$
Jeg starter med at beregne $a_{0}$:
$$
\begin{align*}
a_{0} &= \frac{1}{L} \int_{-L}^{L} f(x) \, dx\\
&= \frac{1}{2} \int_{-2}^{2} f(x) \, dx\\
&= \frac{1}{2} \left(\int_{-2}^{0} 0 \, dx + \int_{0}^{2} (x-1) \, dx\right)\\
&= \frac{1}{2} \left(0 + \left[\frac{x^{2}}{2} - x \right]_{0}^{2}\right)\\
&= \frac{1}{2} \cdot \frac{2^{2}}{2} - 2\\
&= \frac{1}{2} \cdot \frac{4}{2} - 2\\
&= 2-2\\
&= 0
\end{align*}
$$
$a_{0}$ bliver altså 0
Nu beregner jeg $a_{n}$: 
$$
\begin{align*}
a_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx\\
a_{n} &= \frac{1}{2} \int_{-2}^{2} f(x) \cos\left(\frac{n \pi x}{2}\right) \, dx\\
&= \frac{1}{2} \left(\int_{-2}^{0} 0 \cdot \cos\left(\frac{n \pi x}{2}\right) \, dx + \int_{0}^{2} (x-1) \cos\left(\frac{n \pi x}{2}\right) \, dx\right)\\
&= \frac{1}{2}\left(0 + \int_{0}^{2} (x-1) \cdot \cos\left(\frac{n \pi x}{2}\right) \, dx \right)\\
\end{align*}
$$
Nu skal jeg bruge integration i dele:
$$
\begin{align*}
\int u \, dv &= uv - \int v \, du\\
u = x-1 \Rightarrow du &=  dx\\
dv = \cos\left(\frac{n \pi x}{2}\right) \, dx \Rightarrow v &= \int \cos\left(\frac{n \pi x}{2}\right) \, dx\\
\int \cos\left(\frac{n \pi x}{2}\right) \, dx &= \frac{2}{n \pi} \sin\left(\frac{n \pi x}{2}\right)\\
\text{Indsætter i integration i dele formlen:}\\
\int (x-1) \cos\left(\frac{n \pi x}{2}\right) \, dx &= (x-1) \frac{2}{n \pi} \sin\left(\frac{n \pi x}{2}\right) - \int \frac{2}{n \pi} \sin\left(\frac{n \pi x}{2}\right) \, dx\\
\text{Regner integralet}:\\
\int \frac{2}{n \pi} \sin\left(\frac{n \pi x}{2}\right) \, dx &= \frac{2}{n \pi} \int \sin\left(\frac{n \pi x}{2}\right) \, dx\\
&= \frac{2}{n \pi} \cdot \left(- \frac{2}{n \pi} \cos\left(\frac{n \pi x}{2}\right)\right)\\
&= -\frac{4}{n^{2} \pi^{2}} \cos\left(\frac{n \pi x}{2}\right)\\
\text{Indsætter det udregnede integrale i formlen:}\\
\int (x-1) \cos\left(\frac{n \pi x}{2}\right) \, dx &= (x-1) \frac{2}{n \pi} \sin\left(\frac{n \pi x}{2}\right) - \left(-\frac{4}{n^{2} \pi^{2}} \cos\left(\frac{n \pi x}{2}\right)\right)\\
&= (x-1) \frac{2}{n \pi} \sin\left(\frac{n \pi x}{2}\right) + \frac{4}{n^{2} \pi^{2}} \cos\left(\frac{n \pi x}{2}\right) + C\\
\end{align*}
$$
Nu skal jeg evaluerer over intervallet der var fra 0 til 2:
Når $x=2$
$$
\begin{align*}
&= (2-1) \frac{2}{n \pi} \cdot \sin\left(\frac{2n \pi}{2}\right) + \frac{4}{n^{2} \pi^{2}} \cdot \cos\left(\frac{2n \pi }{2}\right)\\
&= \frac{2}{n \pi} \sin(n \pi) + \frac{4}{n^{2} \pi^{2}} \cdot \cos(n \pi)\\
\sin(n \pi) &=  0 \text{ for alle n-værdier}\\
\cos(n \pi) &= (-1)^{n}\\
&= 0 + \frac{4}{n^{2} \pi^{2}} \cdot (-1)^{n}\\
&=  \frac{4 \cdot (-1)^{n}}{n^{2} \pi^{2}}
\end{align*}
$$
Når $x=0$:
$$
\begin{align*}
&= (0-1) \frac{2}{n \pi} \cdot \sin(0) + \frac{4}{n^{2} \pi^{2}} \cdot \cos(0)\\
\sin(0) &= 0\\
\cos(0) &= 1\\
&= 0 + \frac{4}{n^{2} \pi^{2}}\\
&= \frac{4}{n^{2} \pi^{2}}
\end{align*}
$$
Nu skal jeg trække den nedre grænse fra den øvre grænse:
$$
\left(\frac{4 \cdot (-1)^{n}}{n^{2} \pi^{2}}\right) -  \left(\frac{4}{n^{2} \pi^{2}}\right) = \frac{4((-1)^{n}-1)}{n^{2} \pi^{2}}
$$
Derfor da $a_{n}$ var givet ved:
$$
\begin{align*}
\frac{1}{2}\left(0 + \int_{0}^{2} (x-1) \cdot \cos\left(\frac{n \pi x}{2}\right) \, dx \right)\\
\frac{1}{2}\left( \frac{4((-1)^{n}-1)}{n^{2} \pi^{2}}\right)\\
&=  \frac{2((-1)^{n}-1)}{n^{2} \pi^{2}}
\end{align*}
$$
Nu skal jeg regne hvordan funktionen ser ud for lige og ulige n-værdier:
$$
\begin{align*}
\text{Hvis n er lige } (n &= 2k) \Rightarrow (-1)^{n} = 1:\\
a_{n} = \frac{2(1-1)}{n^{2} \pi^{2}} &= 0\\
\text{Hvis n er ulige } (n &= 2k - 1) \Rightarrow (-1)^{n} = -1:\\
a_{n} = \frac{2(-1-1)}{n^{2} \pi^{2}} &= - \frac{4}{n^{2} \pi^{2}}
\end{align*}
$$
Derfor bliver $a_{n}$:
$$
a_{n} = \cases{0, \quad \quad \quad \space \text{ hvis n er lige} \\
- \frac{4}{n^{2} \pi^{2}}, \quad \text{ hvis n er ulige}}
$$
Nu beregner jeg $b_{n}$:
$$
\begin{align*}
b_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx\\
b_{n} &= \frac{1}{2} \int_{-2}^{2} f(x) \sin\left(\frac{n \pi x}{2}\right) \, dx\\
&= \frac{1}{2} \left(\int_{-2}^{0} 0 \cdot \sin\left(\frac{n \pi x}{2}\right) \, dx + \int_{0}^{2} (x-1) \sin\left(\frac{n \pi x}{2}\right) \, dx\right)\\
&= \frac{1}{2}\left(0 + \int_{0}^{2} (x-1) \cdot \sin\left(\frac{n \pi x}{2}\right) \, dx \right)\\
\end{align*}
$$
Nu skal jeg bruge integration i dele:
$$
\begin{align*}
\int u \, dv &= uv - \int v \, du\\
u = x-1 \Rightarrow du &=  dx\\
dv = \sin\left(\frac{n \pi x}{2}\right) \, dx \Rightarrow v &= \int \sin\left(\frac{n \pi x}{2}\right) \, dx\\
\int \sin\left(\frac{n \pi x}{2}\right) \, dx &= -\frac{2}{n \pi} \cos\left(\frac{n \pi x}{2}\right)\\
\text{Indsætter i integration i dele formlen:}\\
\int (x-1) \sin\left(\frac{n \pi x}{2}\right) \, dx &= (x-1) \cdot \left(- \frac{2}{n \pi}\right) \cos\left(\frac{n \pi x}{2}\right) - \int \frac{2}{n \pi} \cos\left(\frac{n \pi x}{2}\right) \, dx\\
\text{Regner integralet}:\\
\int \frac{2}{n \pi} \cos\left(\frac{n \pi x}{2}\right) \, dx &= \frac{2}{n \pi} \int \cos\left(\frac{n \pi x}{2}\right) \, dx\\
&= \frac{2}{n \pi} \cdot \left(\frac{2}{n \pi} \sin\left(\frac{n \pi x}{2}\right)\right)\\
&= \frac{4}{n^{2} \pi^{2}} \sin\left(\frac{n \pi x}{2}\right)\\
\text{Indsætter det udregnede integrale i formlen:}\\
\int (x-1) \sin\left(\frac{n \pi x}{2}\right) \, dx &= (x-1) \cdot \left(-\frac{2}{n \pi}\right) \cos\left(\frac{n \pi x}{2}\right) + \frac{4}{n^{2} \pi^{2}} \sin\left(\frac{n \pi x}{2}\right)\\
&= - \frac{2(x-1)}{n \pi} \cdot \cos\left(\frac{n \pi x}{2}\right) + \frac{4}{n^{2} \pi^{2}} \cdot \sin\left(\frac{n \pi x}{2}\right) + C
\end{align*}
$$
Nu skal jeg evaluerer over intervallet der var fra 0 til 2:
Når $x=2$
$$
\begin{align*}
&= - \frac{2(2-1)}{n \pi} \cdot \cos\left(\frac{2 n \pi}{2}\right) + \frac{4}{n^{2} \pi^{2}} \cdot \sin\left(\frac{2n \pi}{2}\right)\\
&= - \frac{2}{n \pi} \cdot \cos(n \pi) + \frac{4}{n^{2} \pi^{2}} \cdot \sin (n \pi)\\
\sin(n \pi) &=  0 \text{ for alle n-værdier}\\
\cos(n \pi) &= (-1)^{n}\\
&= - \frac{2}{n \pi} \cdot (-1)^{n} + 0\\
&= -\frac{2(-1)^{n}}{n \pi}
\end{align*}
$$
Når $x=0$:
$$
\begin{align*}
&= - \frac{2(0-1)}{n \pi} \cdot \cos(0) + \frac{4}{n^{2} \pi^{2}} \cdot \sin(0)\\
\sin(0) &= 0\\
\cos(0) &= 1\\
&= - \frac{2}{n \pi}
\end{align*}
$$
Nu skal jeg trække den nedre grænse fra den øvre grænse:
$$
-\frac{2(-1)^{n}}{n \pi}-\left(- \frac{2}{n \pi}\right) = - \frac{2 ((-1)^{n} + 1)}{n \pi}
$$
Derfor da $b_{n}$ var givet ved:
$$
\begin{align*}
&= \frac{1}{2}\left(0 + \int_{0}^{2} (x-1) \cdot \sin\left(\frac{n \pi x}{2}\right) \, dx \right)\\
&= \frac{1}{2}\left(- \frac{2 ((-1)^{n} + 1)}{n \pi}\right)\\
&= - \frac{(-1)^{n} + 1}{n \pi}
\end{align*}
$$
Nu skal jeg regne hvordan funktionen ser ud for lige og ulige n-værdier:
$$
\begin{align*}
\text{Hvis n er lige } (n &= 2k) \Rightarrow (-1)^{n} = 1:\\
b_{n} = - \frac{1 + 1}{n \pi} &= -\frac{2}{n \pi}\\
\text{Hvis n er ulige } (n &= 2k - 1) \Rightarrow (-1)^{n} = -1:\\
b_{n} = - \frac{-1 + 1}{n \pi} &= 0
\end{align*}
$$
Derfor bliver $b_{n}$:
$$
b_{n} = \cases{-\frac{2}{n \pi}, \quad  \text{ hvis n er lige} \\
0, \quad \quad \space \space  \text{ hvis n er ulige}}
$$
Nu hvor jeg har beregnet $a_{0}, a_{n}$ og $b_{n}$ kan jeg indsætte det i formlen for fourierrækken:
$$
\begin{align*}
\frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{ \pi n x}{2}\right)+ b_{n} \sin\left(\frac{\pi n x}{2}\right)\right] \\
= 0 + \sum_{n=1}^{\infty} \left[- \frac{4}{n^{2} \pi^{2}} \cos\left(\frac{ \pi n x}{2}\right)\right] + 0 + \sum_{n=2}^{\infty} \left[-\frac{2}{n \pi} \sin\left(\frac{\pi n x}{2}\right)\right]\\
= \frac{4}{\pi^{2}} \sum_{n=1}^{\infty} \left[-  \frac{\cos\left(\frac{ \pi n x}{2}\right)}{n^{2}}\right] + \frac{2}{\pi} \sum_{n=2}^{\infty} \left[ \frac{\sin\left(\frac{\pi n x}{2}\right)}{n}\right]
\end{align*}
$$

## Opgave 2

Den endimensionale varmeledningsligning for en given stang med længden L er givet ved:
$$
\frac{\partial u}{\partial t} - \frac{\partial^{2} u}{\partial x^{2}} = 0, \quad \text{hvor } 0 \leq x \leq L \text{ og } t \geq 0
$$
Der gælder følgende randbetingelser: $u(0,t) = 0$ og $u(L,t) = 0$

Desuden gælder følgende begyndelsesbetingelse:
$$
u(x,0) = \frac{3}{4} \sin\left(\frac{\pi x}{L}\right) - \frac{1}{4} \sin\left(\frac{3 \pi x}{L}\right)
$$
#### a) Benyt separation af de varaible, idet det antages at $u(x,t) = F(x)G(t)$, til at opskrive to ordinære differentialligninger af typen:
$$
\frac{d^{2} F}{d x^{2}} = kF, \quad \text{og } \quad \frac{dG}{dt} = kG
$$
Jeg starter med at indsætte:
$$
u(x,t) = F(x)G(t)
$$
i udtrykket for varmeledningsligningen:
$$
\frac{\partial u}{\partial t} - \frac{\partial^{2} u}{\partial x^{2}} = 0
$$
Først beregner jeg de partielle afledede:
Den tidsafledte:
$$
\frac{\partial u}{\partial t} = F(x) \frac{dG}{dt}
$$
Den rumafledte:
$$
\frac{\partial^{2} u}{\partial x^{2}} = G(t) \frac{d^{2}F}{dx^{2}}
$$
Dette indsætter jeg i varmeledningsligningen:
$$
F(x) \frac{dG}{dt} - G(t) \frac{d^{2}F}{dx^{2}} = 0
$$
Jeg deler begge sider med $F(x)G(t)$, og antager at $F(x)G(t) \neq 0$:
$$
\frac{1}{G(t)} \frac{dG}{dt} = \frac{1}{F(x)} \frac{d^{2}F}{dx^{2}}
$$
Venstre side af ligningen afhænger kun af t, mens højresiden af ligningen kun afhænger af x. Dette betyder at begge sider er lig med den samme konstant $k$. Derfor kan der laves to ordinære differentialligninger:
Først den tidsafledte:
$$
\frac{1}{G(t)} \frac{dG}{dt} = k \quad \Rightarrow \quad \frac{dG}{dt} = k G(t)
$$
Dernæst den rumafledte:
$$
\frac{1}{F(x)} \frac{d^{2}F}{dx^{2}} = k \quad \Rightarrow \quad \frac{d^{2}F}{dx^{2}} = k F(x)
$$
De to ønskede ordinære differentialligninger er altså givet ved:
$$
\frac{dG}{dt} = k G(t), \quad \text{og} \quad \frac{d^{2}F}{dx^{2}} = k F(x)
$$

#### b) Begrund at separationskonstanten k i differentialligningen:
$$
\frac{d^{2}F}{dx^{2}} = kF
$$
skal være negativ (dvs. $k = -p^{2}$) og bestem løsningen.

For at gøre dette skal jeg bruge randbetingelserne, hvilket var givet ved:
$u(0,t) = 0$ og $u(L,t) = 0$
Dette betyder at:
$$
\begin{align*}
F(0) &=  0\\
F(L) &=  0
\end{align*}
$$
Dernæst kigger jeg på de tre forskellige muligheder der er for værdien af k, nemlig $k>0, k=0 \text{ og } k<0$:
Hvis $k>0$:
Jeg sætter $k = p^{2}$, hvor $p > 0$. Derfor bliver differentialligningen:
$$
\frac{d^{2}F}{dx^{2}} =  p^{2} F
$$
Dette er en andenordens lineær differentialligning med konstante koeeficienter.
Den karakteristiske ligning er :
$$
r^{2} - p^{2} = 0 \Rightarrow r = \pm p
$$
Den generelle løsning er givet ved:
$$
F(x) = Ae^{px} + Be^{-px}
$$
Jeg indsætter randbetingelserne:
$$
\begin{align*}
F(0) = Ae^{0} + Be^{0} = A + B &= 0 \ \Rightarrow B = -A\\
F(L) = Ae^{pL} + Be^{-pL} = A e^{pL} - Ae^{-pL} &= 0\\
\text{Faktoriserer A:}\\
A (e^{pL} - e^{-pL}) &= 0
\end{align*}
$$
$e^{pL} - e^{-pL}$ kan omskrives til: $\sinh(pL)$
$$
\sinh(z) = 0, \text{ hvis } z=0
$$
Men da både $p >0$ og $L > 0$ så kan $\sinh(pL) \neq 0$. Derfor bliver både A og B nødt til at være 0, hvilket giver løsningen $F(x) = 0$. Da dette svarer til $u(x,t) = 0$, hvilket ikke er interessant idet begyndelsesbetingelsen ikke er nul overalt.
Hvis $k=0$:
$$
\begin{align*}
\frac{d^{2}F}{dx^{2}} &=  kF\\
\frac{d^{2}F}{dx^{2}} &=  0\\
\frac{dF}{dx} = C_{1}\\
F(x) = C_{1}x + C_{2}
\end{align*}
$$
Dermed hvis $C_{1} = A$ og $C_{2} = B$ bliver løsningen
$$
F(x) = Ax + B
$$
Jeg indsætter randbetingelserne:
$$
\begin{align*}
F(0) = A \cdot 0 + B = B &=  0\\
F(L) = A \cdot L &= 0\\
\text{Da } L>0, \text{ så må } A&= 0
\end{align*}
$$
Derfor bliver både A og B nødt til at være 0, hvilket giver løsningen $F(x) = 0$. Da dette svarer til $u(x,t) = 0$, hvilket ikke er interessant idet begyndelsesbetingelsen ikke er nul overalt.

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
F(0) = A \cos(0) + B \sin(0) = A &= 0\\
F(L) = B \sin(pL) &= 0
\end{align*}
$$
For at få noget andet end den trivielle løsning $B = 0$ så skal $\sin(pL) = 0$, hvilket betyder at:
$$
pL = n \pi \Rightarrow p = \frac{n \pi}{L}, \quad n \in \mathbb{Z}^{+}
$$
De ikke-trivielle løsninger er derfor givet ved:
$$
F_{n}(x) = B_{n} \sin\left(\frac{n \pi x}{L}\right), \quad n = 1,2,3 \dots
$$
Så den eneste ikke-trivielle løsning er når k er negativ, dvs. $k = -p^{2}$, hvor $p = \frac{n \pi}{L}$ for $n \in \mathbb{Z}^{+}$.


#### c) Løs differentialligningen for $G(t)$
Jeg fik i forrige delopgave at:
$$
F_{n}(x) = B_{n} \sin\left(\frac{n \pi x}{L}\right), \quad n = 1,2,3 \dots
$$
For tidsligningen:
$$
\frac{dG}{dt} = kG
$$
Da $k = -p^{2}$ og $p = \frac{n \pi}{L}$, så starter jeg med at beregne $-p^{2}$:
$$
\begin{align*}
-p^{2} = -\left(\frac{n \pi}{L}\right)^2
\end{align*}
$$
Dette indsætter jeg i tidsligningen:
$$
\begin{align*}
\frac{d G}{dt} &= - \left(\frac{n \pi}{L}\right)^{2} G\\
\text{Dette er en separabel ODE.}\\
\text{Jeg integrerer begge sider:}\\
\ln(G) &= - \left(\frac{n \pi}{L}\right)^{2} t + C\\
G_{n}(t) = C_{n} e^{- \left(\frac{n \pi}{L}\right)^{2} t}
\end{align*}
$$
#### d) Gør rede for at den fuldstændige løsning til den partielle differentialligning er:
$$
u(x,t) = \sum_{n=1} ^{\infty} A_{n}\sin\left(\frac{n \pi x}{L}\right) \cdot e^{- \frac{n^{2} \pi^{2}}{L^{2}} t}
$$
Da PDE'en er lineær med Dirichlet-randbetingelser, er den generelle løsning:
$$
u(x,t) = \sum_{n=1} ^{\infty} A_{n}\sin\left(\frac{n \pi x}{L}\right) \cdot e^{- \frac{n^{2} \pi^{2}}{L^{2}} t}
$$
Hvor $A_{n} = B_{n} + C_{n}$

#### e) Bestem den partikulære løsning, der opfylder begyndelsesbtingelsen:
Den generelle løsning til varmeledningsligningen er givet ved:
$$
u(x,t) = \sum_{n=1} ^{\infty} B_{n} \sin\left(\frac{n \pi x}{L}\right) e^{-\left(\frac{n \pi}{L}\right)^{2} t}
$$
Hvor $B_{n}$ er givet ved $C_{n}$ ganget med en konstant der afhænger af begyndelsesbetingelsen.
Der var følgende begyndelsesbetingelse:
$$
u(x,0) = \frac{3}{4} \sin\left(\frac{\pi x}{L}\right) - \frac{1}{4} \sin\left(\frac{3 \pi x}{L}\right)
$$
Hvis jeg sammenligner med den generelle løsning ved $t=0$:
$$
u(x,0) = \sum_{n=1} ^{\infty} B_{n} \sin\left(\frac{n \pi x}{L}\right)
$$
Så ses det at:
$$
\begin{align*}
B_{1} &=  \frac{3}{4},\\
B_{3} &= -\frac{1}{4},\\
B_{n} &=  0 \text{ for alle andre n-værdier}
\end{align*}
$$
Derfor kan den endelige løsning skrives som:
$$
u(x,t) = \frac{3}{4} \sin\left(\frac{\pi x}{L}\right) e^{-(\frac{\pi}{L})^{2} t} - \frac{1}{4} \sin\left(\frac{3 \pi x}{L}\right) e^{-\left(\frac{3 \pi}{L}\right)^{2} t}
$$
## Opgave 3
Givet en skalarfunktion: $f: R^{2} \rightarrow R$
$$
f(x,y) = x \tan(y)
$$
#### a) Bestem gradienten til $f(x,y)$ i punktet $P \left(1, \frac{\pi}{4}\right)$ 
Jeg bruger formlen for gradienten:
$$
\nabla f(x,y) = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}\right)
$$
Derfor skal jeg beregne de partielle afledede mht. x og y. Jeg starter med x:
$$
\begin{align*}
f(x,y) &= x \tan(y)\\
\frac{\partial f}{\partial x} = \tan(y)
\end{align*}
$$
Dernæst den partielle afledede mht. y:
$$
\begin{align*}
f(x,y) &= x \tan(y)\\
\frac{\partial f}{\partial y} &=  x \sec^{2}(y)
\end{align*}
$$
Derfor bliver gradienten:
$$
\nabla f(x,y) = (\tan(y), x \sec^{2}(y))
$$
Jeg indsætter punktet $P\left(1, \frac{\pi}{4}\right)$:
$$
\begin{align*}
\tan\left(\frac{\pi}{4}\right) &=  1\\
1 \cdot \sec\left(\frac{\pi}{4}\right) = \sqrt{2} \Rightarrow \sec^{2}\left(\frac{\pi}{4}\right) &= 2\\
\nabla f\left(1, \frac{\pi}{4}\right) &= (1,2)
\end{align*}
$$

#### b) Bestem den retningsafledede
$$
D_{\overline{v}} f (x,y) \text{ i punktet } P\left(1, \frac{\pi}{4}\right) \text{ i retningen } \overline{v} = (3,4)
$$
Den retningsafledede $D_{\overline{v}} f (x,y)$ er givet ved formlen:
$$
D_{\overline{v}} f (x,y) = \nabla f(x,y) \cdot \frac{\overline{v}}{||\overline{v}||}
$$
Først skal jeg normalisere retningsvektoren $\overline{v} = (3,4)$:
$$
||\overline{v}|| = \sqrt{3^{2} + 4^{2}} = 5 \Rightarrow \frac{\overline{v}}{||\overline{v}||} = \left(\frac{3}{5}, \frac{4}{5}\right)
$$
Gradienten er allerede beregnet i a), så nu indsætter jeg værdierne i formlen for den retningsafledede og beregner:
$$
\begin{align*}
D_{\overline{v}} f (x,y) &=  \nabla f(x,y) \cdot \frac{\overline{v}}{||\overline{v}||}\\
\nabla f(x,y) &= (1,2)\\
\frac{\overline{v}}{||\overline{v}||} &= \left(\frac{3}{5}, \frac{4}{5}\right)\\
(1,2) \cdot \left(\frac{3}{5}, \frac{4}{5}\right) &= 1 \cdot \frac{3}{5} + 2 \cdot \frac{4}{5}\\
&= \frac{3}{5} + \frac{8}{5}\\
&= \frac{11}{5}
\end{align*}
$$
Dermed har jeg beregnet at den retningsafledede $D_{\overline{v}} f (x,y)$ er givet ved:
$$
D_{\overline{v}} f (x,y) = \frac{11}{5}
$$
## Opgave 4
Lad T være området begrænset af paraboloiden:
$$
\begin{align*}
S_{1}: z &=  2x^{2} + 2 y^{2}, \quad 0 \leq z \leq 8\\
\text{og planet: }S_{2}: z &=  8
\end{align*}
$$
Desuden er vektorfunktionen $\overline{F}(x,y,z)$ gives som: $\overline{F}(x,y,z) = (x,y,z)$

#### a) Skitsér området T
![[Pasted image 20250608135141.png]]
#### b) Udregn Tripleintegralet $\iiint_{T} \nabla \cdot \overline{F} \, dv$
Først beregner jeg divergensen af $\overline{F}$:
$$
\nabla \cdot \overline{F} = \frac{\partial F_{x}}{\partial x} + \frac{\partial F_{y}}{\partial y} + \frac{\partial F_{z}}{\partial z} = 1+1+1 = 3
$$

Dermed bliver trippelintegralet:
$$
\iiint_{T} \nabla \cdot \overline{F} \, dv = 3 \iiint_{T} dv
$$

Nu skal jeg finde volumenet af T, som området mellem paraboloiden $z = 2x^{2} + 2y^{2}$ og planet $z = 8$
Grænserne for integrationen er givet ved:
$z$ går fra paraboloiden til planet: $2x^{2} + 2y^{2} \leq z \leq 8$
Projektionen af T på xy-planen er en cirkel, hvor $z=8$ skærer paraboloiden:
$$
2x^{2} + 2y^{2} = 8 \Rightarrow x^{2} + y^{2} = 4
$$

Siden det er en cirkel bruger jeg polære koordinater. Siden $x^{2} + y^{2} = 4$ og formlen for en cirkel er givet ved: $x^{2} + y^{2} = r^{2}$ Så må r være givet ved $r^{2} = 4 \Rightarrow r = 2$ og den øvre grænse bliver så fra $2r^{2}$ til $8$. Intervallet for theta er selvfølgelig $\theta \in [0, 2\pi]$. Derfor bliver integralet med grænserne:
$$
\iiint_{T} dv = \int_{0}^{2\pi} d \theta \int_{0}^{2} r \, dr \int_{2r^{2}} ^{8} r \, dz
$$

Jeg starter med det yderste integrale:
$$
\int_{2r^{2}} ^{8} dz = 8-2r^{2}
$$

Dette indsætter jeg i det midterste integrale:
$$
\begin{align*}
\int_{0}^{2} (8-2r^{2}) r \, dr &= \int_{0}^{2}(8r-2r^{3}) \, dr\\
&= \left[4r^{2} - \frac{2r^{4}}{4}\right]_{0}^{2}\\
&= \left[4r^{2} - \frac{r^{4}}{2}\right]_{0}^{2}\\
&= 4 \cdot 2^{2} - \frac{2^{4}}{2}\\
&= 16 - \frac{16}{2}\\
&= 8
\end{align*}
$$

Dette indsætter jeg i det inderste integrale:
$$
\int_{0}^{2\pi} 8 \, d \theta = 16 \pi
$$

Dette indsætter jeg i det udtryk jeg havde i starten:
$$
\begin{align*}
\iiint_{T} \nabla \cdot \overline{F} \, dv &=  3 \iiint_{T} dv\\
&= 3 \cdot 16 \pi\\
&= 48 \pi
\end{align*}
$$

Dermed har jeg beregnet at:
$$
\iiint_{T} \nabla \cdot \overline{F} \, dv = 48 \pi
$$

#### c) Vis, at en enhedsnormalvektor til den givne overflade bliver $\overline{n} = \left(\frac{4x}{\sqrt{1 + 8z}}, \frac{4y}{\sqrt{1 + 8z}}, \frac{-1}{\sqrt{1 + 8z}}\right)$ (Lidt hjælp: Definer overflade som en niveauflade og bestem normalvektoren vha. gradienten, som står vinkelret på fladen)
Overfladen $S_{1}$ er givet ved $z = 2x^{2} + 2y^{2}$. Dette kan defineres som en niveaufalde:
$$
g(x,y,z) = 2x^{2} + 2y^{2} -z = 0
$$
Normalvektoren er givet ved gradienten af g:
$$
\begin{align*}
\nabla g &=  \left(\frac{\partial g}{\partial x}, \frac{\partial g}{\partial y}, \frac{\partial g}{\partial z}\right)\\
\frac{\partial g}{\partial x} = (2x^{2})' &=  4x\\
\frac{\partial g}{\partial y} = (4y^{2})' &= 4y\\
\frac{\partial g}{\partial z} = (-z)' &= -1
\end{align*}
$$
Dvs. gradienten af g er givet ved:
$$
\nabla g = (4x, 4y, -1)
$$
Jeg beregner nu enhedsnormalvektoren af $\overline{n}$ ved at normalisere $\nabla g$:
$$
\begin{align*}
||\nabla g|| &=  \sqrt{(4x^{2}) + (4y)^{2} + (-1)^{2}}\\
&= \sqrt{16x^{2} + 16y^{2} + 1}\\
&= \sqrt{16 (x^{2} + y^{2}) + 1}
\end{align*}
$$
Da $z = 2x^{2} + 2y^{2}$ så kan jeg udtrykke $x^{2} + y^{2}$ som $\frac{z}{2}$:
$$
\begin{align*}
||\nabla g|| &=  \sqrt{16 \cdot \left(\frac{z}{2}\right) + 1}\\
&= \sqrt{8z + 1}
\end{align*}
$$
Nu skal jeg bare indsætte de beregnede værdier i formlen for enhedsnormalvektoren:
$$
\overline{n} = \frac{\nabla g}{||\nabla g||} = \left(\frac{4x}{\sqrt{8z + 1}}, \frac{4y}{\sqrt{8z + 1}}, \frac{-1}{\sqrt{8z + 1}}\right)
$$

#### d) Eftervis resultatet fra spørgsmål b) ved at udregne fladeintegralet $\iint_{S} \overline{F} \cdot \overline{n} \, dA$ hvor S er overfladen af området begrænset af paraboloiden og planet $z=8$ 
Ifølge formlen:
$$
\iiint_{T} \nabla \cdot \overline{F} \, dv = \iint_{S} \overline{F} \cdot \overline{n} \, dA
$$

Jeg kan bruge den allerede udregnede normalvektor fra c):
$$
\begin{align*}
\overline{F} \cdot \overline{n} &=  (x,y,z) \cdot \left(\frac{4x}{\sqrt{8z + 1}}, \frac{4y}{\sqrt{8z + 1}}, \frac{-1}{\sqrt{8z + 1}}\right)\\
&= \frac{4x^{2} + 4y^{2} -z}{\sqrt{8z + 1}}\\
\text{Da } z&= 2x^{2} + 2y^{2}:\\
&= \frac{4x^{2} + 4y^{2} - 2x^{2} - 2y^{2}}{\sqrt{8z + 1}}\\
&= \frac{2x^{2} + 2y^{2}}{\sqrt{8z + 1}}\\
&= \frac{z}{\sqrt{8z + 1}}
\end{align*}
$$

Dernæst skal jeg beregne overfladeelementet $dA$ på $S_{1}$:
$$
dA = \sqrt{1 + \left(\frac{\partial F_{x}}{\partial x}\right)^{2} + \left(\frac{\partial F_{y}}{\partial y}\right)^{2}} \, dx \, dy
$$

I dette tilfælde er det over paraboloiden $S_{1}: 2x^{2} + 2y^{2}$
$$
\begin{align*}
\frac{\partial F_{x}}{\partial x} = (2x^{2})' &= 4x\\
\frac{\partial F_{y}}{\partial y} = (2y^{2})' &= 4y\\
dA &=  \sqrt{1 + (4x)^{2} + (4y)^{2}} \, dx \, dy\\
&= \sqrt{8z + 1} \, dx \, dy
\end{align*}
$$

Derfor bliver integralet over $S_{1}$:
$$
\begin{align*}
\iint_{S} \overline{F} \cdot \overline{n} \, dA &=  \iint_{x^{2} + y^{2} \leq 4} \frac{z}{\sqrt{8z + 1}} \cdot \sqrt{8z + 1} \, dx \, dy\\
&= \iint_{x^{2} + y^{2} \leq 4} z \, dx \, dy\\
\text{Polære koordinater:}\\
&= \int_{0}^{2\pi} d \theta \int_{0}^{2} 2r^{2} \cdot r \, dr\\
&= \int_{0}^{2\pi} d \theta \int_{0}^{2} 2r^{3} \, dr\\
\end{align*}
$$

Jeg regner først det ydre integrale:
$$
\begin{align*}
\int_{0}^{2} 2r^{3} \, dr &= 2 \int_{0}^{2} 2r^{3} \, dr\\
&= 2\left[\frac{r^{4}}{4}\right]_{0}^{2}\\
&= 2 \cdot \frac{2^{4}}{4}\\
&= 2 \cdot 4\\
&= 8
\end{align*}
$$

Indsætter dette i det indre integrale:
$$
\int_{0}^{2\pi} 8 \, d \theta = 16 \pi
$$

Dernæst skal jeg beregne integralet over planet $S_{2} (z=8)$:
Normalvektoren er $\overline{n} = (0,0,1)$ og $\overline{F} \cdot \overline{n} = z = 8$. Arealet af $S_{2}$ er cirklen med radius 2:
Areal: $r^{2} \cdot \pi = 2^{2} = \pi = 4 \pi$
$$
\iint_{S_{2}} \overline{F} \cdot \overline{n} \, dA = 8 \cdot \text{Areal} = 8 \cdot 4 \pi = 32 \pi
$$

Det samlede fladeintegrale bliver derfor:
$$
\iint_{S} \overline{F} \cdot \overline{n} \, dA = 16 \pi + 32 \pi = 48 \pi
$$

Dermed får jeg det samme som i b) ved brug af divergenssætningen.