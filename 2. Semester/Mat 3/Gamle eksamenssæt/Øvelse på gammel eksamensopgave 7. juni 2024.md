## Opgave 1
En periodisk funktion $f(x)$ er givet ved:
$$
f(x) = \cases{x, \quad \text{når } 0 < x < 1,
\\ 0, \quad \text{når } 1 < x <2}
$$
$$
f(x+2) = f(x)
$$
#### a) Skitsér grafen for $f(x)$ i intervallet $-4 < x < 4$
![[Pasted image 20250608175731.png]]
#### b) Udled fourierrækken for $f(x)$
Fourierrækken for en given funktion $f(x)$ er generelt givet ved formlen
$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{\pi n x}{L}\right)+ b_{n} \sin\left(\frac{\pi n x}{L}\right)\right]
$$
I dette tilfælde da $f(x+2) = f(x)$ så har funktionen en periode $p$ på 2, dvs. da $p = 2L$ så er $L = 1$:
$$
\begin{align*}
f(x) &=  \frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{\pi n x}{1}\right)+ b_{n} \sin\left(\frac{\pi n x}{1}\right)\right]\\
&=  \frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\pi n x\right)+ b_{n} \sin(\pi n x)\right]
\end{align*}
$$
Nu skal jeg beregne $a_{0}, a_{n} \text{ og } b_{n}$:
$$
\begin{align*}
a_{0} &=  \frac{1}{L} \int_{-L}^{L} f(x) \, dx\\
a_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx\\
b_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx
\end{align*}
$$
Hvor $2L = p$
Jeg starter med at beregne $a_{0}$:
$$
\begin{align*}
a_{0} &= \frac{1}{L} \int_{-L}^{L} f(x) \, dx\\
&= \frac{1}{1} \int_{-1}^{1} f(x) \, dx\\
&=  \left(\int_{-1}^{0} 0 \, dx + \int_{0}^{1} x \, dx\right)\\
&=  \left(0 + \left[\frac{x^{2}}{2} \right]_{0}^{1}\right)\\
&= \frac{1^{2}}{2}\\
&= \frac{1}{2}
\end{align*}
$$
$a_{0}$ bliver altså 2.
Nu beregner jeg $a_{n}$: 
$$
\begin{align*}
a_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx\\
a_{n} &= \frac{1}{1} \int_{-1}^{1} f(x) \cos\left(\frac{n \pi x}{1}\right) \, dx\\
&= \left(\int_{-1}^{0} 0 \cdot \cos(n \pi x) \, dx + \int_{0}^{1} (x) \cos(n \pi x) \, dx\right)\\
&= \left(0 + \int_{0}^{1} (x) \cdot \cos(n \pi x) \, dx \right)\\
\end{align*}
$$
Nu skal jeg bruge integration i dele:
$$
\begin{align*}
\int u \, dv &= uv - \int v \, du\\
u = x \Rightarrow du &=  dx\\
dv = \cos(n \pi x) \, dx \Rightarrow v &= \int \cos(n \pi x) \, dx\\
\int \cos(n \pi x) \, dx &= \frac{1}{n \pi} \sin(n \pi x) + C\\
\text{Indsætter i integration i dele formlen:}\\
\int (x) \cos(n \pi x) \, dx &= (x) \frac{1}{n \pi} \sin(n \pi x) - \int \frac{1}{n \pi} \sin(n \pi x) \, dx\\
\text{Regner integralet}:\\
\int \frac{1}{n \pi} \sin(n \pi x) \, dx &= \frac{1}{n \pi} \int \sin(n \pi x) \, dx\\
&= \frac{1}{n \pi} \cdot \left[- \frac{1}{n \pi} \cos(n \pi x)\right]\\
&= -\frac{1}{n^{2} \pi^{2}} \cos(n \pi x)\\
\text{Indsætter det udregnede integrale i formlen:}\\
\int (x) \cos(n \pi x) \, dx &= (x) \frac{1}{n \pi} \sin(n \pi x) - \left(-\frac{1}{n^{2} \pi^{2}} \cos(n \pi x)\right)\\
&= (x) \frac{1}{n \pi} \sin(n \pi x) + \frac{1}{n^{2} \pi^{2}} \cos(n \pi x) + C\\
\end{align*}
$$
Nu skal jeg evaluerer over intervallet der var fra 0 til 1:
Når $x=1$
$$
\begin{align*}
&= \frac{1}{n \pi} \sin(n \pi) + \frac{1}{n^{2} \pi^{2}} \cos(n \pi)\\
\sin(n \pi) &=  0 \text{ for alle n-værdier}\\
\cos(n \pi) &= (-1)^{n}\\
&= 0 + \frac{1}{n^{2} \pi^{2}} \cdot (-1)^{n}\\
&= \frac{1 \cdot (-1)^{n}}{n^{2} \pi^{2}}\\
&= \frac{(-1)^{n}}{n^{2} \pi^{2}}
\end{align*}
$$
Når $x=0$:
$$
\begin{align*}
&= \frac{1}{n^{2} \pi^{2}} \cos(0)\\
\cos(0) &= 1\\
&= \frac{1}{n^{2} \pi^{2}}
\end{align*}
$$
Nu skal jeg trække den nedre grænse fra den øvre grænse:
$$
\left(\frac{(-1)^{n}}{n^{2} \pi^{2}}\right) - \left(\frac{1}{n^{2} \pi^{2}}\right) = \frac{(-1)^{n} - 1}{n^{2} \pi^{2}}
$$
Derfor da $a_{n}$ var givet ved:
$$
\begin{align*}
&= \left(0 + \int_{0}^{1} (x) \cdot \cos(n \pi x) \, dx \right)\\
&= \frac{(-1)^{n} - 1}{n^{2} \pi^{2}}
\end{align*}
$$
Nu skal jeg regne hvordan funktionen ser ud for lige og ulige n-værdier:
$$
\begin{align*}
\text{Hvis n er lige } (n = 2k) \Rightarrow (-1)^{n} &=  1:\\
a_{n} &=  \frac{1 - 1}{n^{2} \pi^{2}}\\
a_{n} &= 0\\
\text{Hvis n er ulige } (n = 2k - 1) \Rightarrow (-1)^{n} &=  -1:\\
a_{n} &= \frac{-1 - 1}{n^{2} \pi^{2}}\\
a_{n} &= \frac{-2}{n^{2} \pi^{2}}
\end{align*}
$$
Derfor bliver $a_{n}$:
$$
a_{n} = \cases{0, \quad \quad \quad \space \text{ hvis n er lige} \\
- \frac{2}{n^{2} \pi^{2}}, \quad \text{ hvis n er ulige}}
$$
Nu beregner jeg $b_{n}$:
$$
\begin{align*}
b_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx\\
b_{n} &= \frac{1}{1} \int_{-1}^{1} f(x) \sin\left(\frac{n \pi x}{1}\right) \, dx\\
&= \left(\int_{-1}^{0} 0 \cdot \sin(n \pi x) \, dx + \int_{0}^{1} (x) \sin(n \pi x) \, dx\right)\\
&= \left(0 + \int_{0}^{1} (x) \cdot \sin(n \pi x) \, dx \right)\\
\end{align*}
$$
Nu skal jeg bruge integration i dele:
$$
\begin{align*}
\int u \, dv &= uv - \int v \, du\\
u = x \Rightarrow du &=  dx\\
dv = \sin(n \pi x) \, dx \Rightarrow v &= \int \sin(n \pi x) \, dx\\
\int \sin(n \pi x) \, dx &= -\frac{1}{n \pi} \cos(n \pi x)\\
\text{Indsætter i integration i dele formlen:}\\
\int (x) \sin(n \pi x) \, dx &= (x) \cdot \left(- \frac{1}{n \pi}\right) \cos(n \pi x) - \int \frac{1}{n \pi} \cos(n \pi x) \, dx\\
\text{Regner integralet}:\\
\int \frac{1}{n \pi} \cos(n \pi x) \, dx &= \frac{1}{n \pi} \int \cos(n \pi x) \, dx\\
&= \frac{1}{n \pi} \cdot \left(\frac{1}{n \pi} \sin(n \pi x)\right)\\
&= \frac{1}{n^{2} \pi^{2}} \sin(n \pi x)\\
\text{Indsætter det udregnede integrale i formlen:}\\
\int (x) \sin(n \pi x) \, dx &= (x) \cdot \left(-\frac{1}{n \pi}\right) \cos(n \pi x) + \frac{1}{n^{2} \pi^{2}} \sin(n \pi x)\\
&= - \frac{x}{n \pi} \cdot \cos(n \pi x) + \frac{1}{n^{2} \pi^{2}} \cdot \sin(n \pi x) + C
\end{align*}
$$
Nu skal jeg evaluerer over intervallet der var fra 0 til 1:
Når $x=1$
$$
\begin{align*}
&= - \frac{1}{n \pi} \cdot \cos(n \pi) + \frac{1}{n^{2} \pi^{2}} \cdot \sin(n \pi)\\
\sin(n \pi) &=  0 \text{ for alle n-værdier}\\
\cos(n \pi) &= (-1)^{n}\\
&= - \frac{1}{n \pi} \cdot (-1)^{n} + 0\\
&= -\frac{(-1)^{n}}{n \pi}
\end{align*}
$$
Når $x=0$:
$$
\begin{align*}
&= 0+ \frac{1}{n^{2} \pi^{2}} \cdot \sin(0)\\
\sin(0) &= 0\\
&= 0
\end{align*}
$$
Nu skal jeg trække den nedre grænse fra den øvre grænse:
$$
\left(-\frac{(-1)^{n}}{n \pi}\right) - 0 = -\frac{(-1)^{n}}{n \pi}
$$
Derfor da $b_{n}$ var givet ved:
$$
\begin{align*}
&= \left(0 + \int_{0}^{1} (x) \cdot \sin(n \pi x) \, dx \right)\\
&= -\frac{(-1)^{n}}{n \pi}\\
\end{align*}
$$
Nu skal jeg regne hvordan funktionen ser ud for lige og ulige n-værdier:
$$
\begin{align*}
\text{Hvis n er lige } (n &= 2k) \Rightarrow (-1)^{n} = 1:\\
b_{n} &= -\frac{1}{n \pi}\\
\text{Hvis n er ulige } (n &= 2k - 1) \Rightarrow (-1)^{n} = -1:\\
b_{n} =  -\frac{-1}{n \pi} &= \frac{1}{n \pi}
\end{align*}
$$
Derfor bliver $b_{n}$:
$$
b_{n} = \cases{-\frac{1}{n \pi}, \quad  \text{ hvis n er lige} \\
\frac{1}{n \pi}, \quad \quad \space \space  \text{ hvis n er ulige}}
$$
Nu hvor jeg har beregnet $a_{0}, a_{n}$ og $b_{n}$ kan jeg indsætte det i formlen for fourierrækken: 
$$
\frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos(\pi x)+ b_{n} \sin(\pi x)\right]
$$
Først samler jeg lige alle mine resultater:
$$
\begin{align*}
a_{0} &=  \frac{1}{2}\\
a_{n} &=  \cases{0, \quad \quad \quad \space \text{ hvis n er lige} \\
- \frac{2}{n^{2} \pi^{2}}, \quad \text{ hvis n er ulige}}\\
b_{n} &=  \cases{-\frac{1}{n \pi}, \quad  \text{ hvis n er lige} \\
\frac{1}{n \pi}, \quad \quad \space \space  \text{ hvis n er ulige}}
\end{align*}
$$
Her er det vigtigt at pointere at $a_{n} = 0$ for alle lige n-værdier, derfor forsvinder cos-leddene for alle lige værdier af n:
$$
\begin{align*}
&= \frac{\frac{1}{2}}{2} + \left[- \frac{2}{1\pi^{2}} \cos(1 \pi x) + \frac{1}{1\pi} \sin(1 \pi x)\right] + \left[0 - \frac{1}{2\pi} \sin(2 \pi x)\right] + \left[- \frac{2}{(3 \pi)^{2}} \cos\left(3 \pi x\right) + \frac{1}{3\pi} \sin(3 \pi x)\right] \dots\\
&= \frac{1}{4} + \left[- \frac{2}{\pi^{2}} \cos(\pi x) + \frac{1}{\pi} \sin(\pi x)\right] + \left[-\frac{1}{2\pi} \sin(2 \pi x)\right] + \left[- \frac{2}{9 \pi^{2}} \cos\left(3 \pi x\right) + \frac{1}{3\pi} \sin(3 \pi x)\right] \dots
\end{align*}
$$
## Opgave 2

Den endimensionale varmeledningsligning for en given stang med længden L er givet ved:
$$
4 \frac{\partial u}{\partial t} - \frac{\partial^{2} u}{\partial x^{2}} = 0, \quad \text{hvor } 0 < x < 1 \text{ og } t > 0
$$
Der gælder følgende randbetingelser: $u(0,t) = 0$ og $u_{x}(1,t) = 0$

Desuden gælder følgende begyndelsesbetingelse:
$$
u(x,0) = 2 \sin\left(\frac{\pi x}{2}\right) - \sin\left(\frac{3 \pi x}{2}\right) + 4 \sin\left(\frac{5 \pi x}{2}\right)
$$
#### a) Benyt separation af de varaible, idet det antages at $u(x,t) = F(x)G(t)$, til at opskrive to ordinære differentialligninger af typen:
$$
\frac{d^{2} F}{d x^{2}} = kF, \quad \text{og } \quad \frac{dG}{dt} = \frac{k}{4}G
$$
Jeg starter med at indsætte:
$$
u(x,t) = F(x)G(t)
$$
i udtrykket for varmeledningsligningen:
$$
4 \frac{\partial u}{\partial t} - \frac{\partial^{2} u}{\partial x^{2}} = 0
$$
Først beregner jeg de partielle afledede:
Den tidsafledte:
$$
4 \frac{\partial u}{\partial t} = 4 F(x) \frac{dG}{dt}
$$
Den rumafledte:
$$
\frac{\partial^{2} u}{\partial x^{2}} = G(t) \frac{d^{2}F}{dx^{2}}
$$
Dette indsætter jeg i varmeledningsligningen:
$$
4 F(x) \frac{dG}{dt} - G(t) \frac{d^{2}F}{dx^{2}} = 0
$$
Jeg deler begge sider med $F(x)G(t)$, og antager at $F(x)G(t) \neq 0$:
$$
\frac{4}{G(t)} \frac{dG}{dt} = \frac{1}{F(x)} \frac{d^{2}F}{dx^{2}}
$$
Venstre side af ligningen afhænger kun af t, mens højresiden af ligningen kun afhænger af x. Dette betyder at begge sider er lig med den samme konstant $k$. Derfor kan der laves to ordinære differentialligninger:
Først den tidsafledte:
$$
\frac{4}{G(t)} \frac{dG}{dt} = k \quad \Rightarrow \quad \frac{dG}{dt} = \frac{1}{4}k G(t)
$$
Dernæst den rumafledte:
$$
\frac{1}{F(x)} \frac{d^{2}F}{dx^{2}} = k \quad \Rightarrow \quad \frac{d^{2}F}{dx^{2}} = k F(x)
$$
De to ønskede ordinære differentialligninger er altså givet ved:
$$
\frac{dG}{dt} = \frac{1}{4}k G(t), \quad \text{og} \quad \frac{d^{2}F}{dx^{2}} = k F(x)
$$

#### b) Begrund at separationskonstanten k i differentialligningen:
$$
\frac{d^{2}F}{dx^{2}} = kF
$$
skal være negativ (dvs. $k = -p^{2}$) og bestem løsningen.

For at gøre dette skal jeg bruge randbetingelserne, hvilket var givet ved:
$u(0,t) = 0$ og $u_{x}(1,t) = 0$
Dette betyder at:
$$
\begin{align*}
F(0) &=  0\\
F'(1) &=  0
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
F'(1) = p \cdot 1 \cdot Ae^{p \cdot 1} + (-p \cdot 1 \cdot Be^{-p \cdot 1}) &=  p \cdot A e^{p} - (-p Ae^{-p})\\
&= p \cdot A e^{p} + p \cdot Ae^{-p}\\
\text{Faktoriserer pA:}\\
p A (e^{p} - e^{-p}) &= 0
\end{align*}
$$
$e^{p} - e^{-p}$ kan omskrives til: $\sinh(p)$
$$
\sinh(z) = 0, \text{ hvis } z=0
$$
Men da $p >0$ så kan $\sinh(p) \neq 0$. Derfor bliver både A og B nødt til at være 0, hvilket giver løsningen $F(x) = 0$. Da dette svarer til $u(x,t) = 0$, hvilket ikke er interessant idet begyndelsesbetingelsen ikke er nul overalt.
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
F'(1) = A &= 0
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
F(0) = A \cos(0) + B \sin(0) = A \cdot 1 + B \cdot 0 &= 0\\
F'(1) =  - A p \sin(p) + B p \cos(p) &= 0\\
= p (- A \sin(p) + B \cos(p)) &= 0\\
\text{Da } p>0 \text{ kan jeg dividere med p:}\\
= -A \sin(p) + B \cos(p) &= 0\\
\text{Indsætter at jeg fik } A &= 0\\
B \cos(p) &= 0
\end{align*}
$$
For at få noget andet end den trivielle løsning $B = 0$ så skal $\cos(p) = 0$, hvilket betyder at:
$$
p = \frac{(2 n - 1) \pi}{2}, \quad n = 1,2,3 \dots
$$
De ikke-trivielle løsninger er derfor givet ved:
$$
F_{n}(x) = B_{n} \sin\left(\frac{(2 n - 1)\pi x}{2}\right), \quad n = 1,2,3 \dots
$$
Så den eneste ikke-trivielle løsning er når k er negativ, dvs. $k = -p^{2}$, hvor $p = \frac{(2 n - 1) \pi}{2}, \quad n = 1,2,3 \dots$.

#### c) Løs differentialligningen for $G(t)$
Jeg fik i forrige delopgave at:
$$
F_{n}(x) = B_{n} \sin\left(\frac{(2 n - 1)\pi x}{2}\right), \quad n = 1,2,3 \dots
$$
For tidsligningen:
$$
\frac{dG}{dt} = \frac{1}{4}kG
$$
Da $k = -p^{2}$ og $p = \frac{(2 n - 1) \pi}{2}$, så starter jeg med at beregne $-p^{2}$:
$$
\begin{align*}
-p^{2} = \left(\frac{(2 n - 1) \pi}{2}\right)^{2}
\end{align*}
$$
Dette indsætter jeg i tidsligningen:
$$
\begin{align*}
\frac{d G}{dt} &= - \frac{1}{4} \left(\frac{(2 n - 1) \pi}{2}\right)^{2} G\\
\text{For at gange ind skal regne: } \sqrt{\frac{1}{4}}\\
\sqrt{\frac{1}{4}} &= \frac{1}{2}\\
\frac{d G}{dt} &= - \left(\frac{(2 n - 1) \pi}{4}\right)^{2} G\\
\text{Dette er en separabel ODE.}\\
\text{Jeg integrerer begge sider:}\\
\int \frac{dG}{G} &= - \left(\frac{(2n-1)\pi}{4}\right)^{2} \int dt\\
\ln(G) &= - \left(\frac{(2 n - 1) \pi}{4}\right)^{2} t + C\\
G_{n}(t) = C_{n} e^{- \left(\frac{(2 n - 1) \pi}{4}\right)^{2} t}\\
&= C_{n} e^{- \left(\frac{(2 n - 1)^{2} \pi^{2}}{16}\right) t}
\end{align*}
$$
#### d) Gør rede for at den fuldstændige løsning til den partielle differentialligning er:
$$
u(x,t) = \sum_{n=0} ^{\infty} A_{n} \sin\left(\left(\frac{1}{2} + n\right)\pi x\right) \cdot e ^{-\left(\frac{\left(\frac{1}{2} + n\right)^{2} \pi^{2}}{4}\right)^{2} t}
$$
Jeg indsætter mine beregnede funktioner:
$$
u(x,t) = \sum_{n=1} ^{\infty} A_{n} F(x) G(t) 
$$
$$
u(x,t) = \sum_{n=1} ^{\infty} A_{n} \sin\left(\frac{(2 n - 1)\pi x}{2}\right) e^{- \left(\frac{(2 n - 1)^{2} \pi^{2}}{16}\right) t}
$$
Hvor $A_{n} = B_{n} + C_{n}$
Jeg kan sammenligne med den givne løsning ved at indsætte n-værdierne (1 for min løsning og 0 for den givne løsning)
$$
u(x,t) = \sum_{n=1} ^{\infty} A_{n} \sin\left(\frac{(2 \cdot 1 - 1)\pi x}{2}\right) e^{- \left(\frac{(2 \cdot 1 - 1)^{2} \pi^{2}}{16}\right) t} = \sin\left(\frac{\pi x}{2}\right) \cdot e^{- \left(\frac{\pi^{2}}{16}\right) t}
$$
$$
u(x,t) = \sum_{n=0} ^{\infty} A_{n} \sin\left(\left(\frac{1}{2} + 0\right)\pi x\right) \cdot e ^{-\left(\frac{\left(\frac{1}{2} + 0\right)^{2} \pi^{2}}{4}\right)^{2} t}= \sin\left(\frac{1}{2} \pi x\right) \cdot e ^{- \left(\frac{ \pi^{2}}{16}\right)^{2} t}
$$
Der er en fejl i opgaven, fordi hele udtrykket i eksponentialfunktionen burde ikke være i anden. Ellers er det den samme løsning som jeg får ved at indsætte mine udregnede funktioner.

#### e) Bestem den partikulære løsning, der opfylder begyndelsesbtingelsen:
Den generelle løsning til varmeledningsligningen er givet ved:
$$
u(x,t) = \sum_{n=1} ^{\infty} A_{n} \sin\left(\frac{(2 n - 1)\pi x}{2}\right) e^{- \left(\frac{(2 n - 1)^{2} \pi^{2}}{16}\right) t}
$$
Hvor $A_{n}$ er givet ved $C_{n}$ ganget med en konstant der afhænger af begyndelsesbetingelsen.
Der var følgende begyndelsesbetingelse:
$$
u(x,0) = 2 \sin\left(\frac{\pi x}{2}\right) - \sin\left(\frac{3 \pi x}{2}\right) + 4 \sin\left(\frac{5 \pi x}{2}\right)
$$
Hvis jeg sammenligner med den generelle løsning ved $t=0$:
$$
u(x,0) = \sum_{n=1} ^{\infty} A_{n} \sin\left(\frac{n \pi x}{L}\right)
$$
Så ses det at:
$$
\begin{align*}
A_{1} &=  2,\\
A_{2} &= -1,\\
A_{3} &= 4, \\
A_{n} &=  0 \text{ for alle andre n-værdier}
\end{align*}
$$
Derfor kan den endelige løsning skrives som:
$$
u(x,t) = 2 \cdot \sin\left(\frac{\pi x}{2}\right) e^{- \left(\frac{ 1 \pi^{2}}{16}\right) t} - \sin\left(\frac{3 \pi x}{2}\right) e^{- \left(\frac{ 9 \pi^{2}}{16}\right) t} + 4 \cdot \sin\left(\frac{5 \pi x}{2}\right) e^{- \left(\frac{ 25 \pi^{2}}{16}\right) t}
$$
## Opgave 3
Givet en skalarfunktion: $f: R^{2} \rightarrow R$
$$
f(x,y) = x^{2} \sin(y)
$$
#### a) Bestem gradienten til $f(x,y)$ i punktet $P \left(1, \frac{\pi}{4}\right)$
Jeg bruger formlen for gradienten:
$$
\nabla f(x,y) = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}\right)
$$
Derfor skal jeg beregne de partielle afledede mht. x og y. Jeg starter med x:
$$
\begin{align*}
f(x,y) &=  x^{2} \sin(y)\\
\frac{\partial f}{\partial x} &=  2x \sin(y)
\end{align*}
$$
Dernæst den partielle afledede mht. y:
$$
\begin{align*}
f(x,y) &=  x^{2} \sin(y)\\
\frac{\partial f}{\partial y} &=  x^{2} \cos(y)
\end{align*}
$$
Derfor bliver gradienten:
$$
\nabla f(x,y) = (2x \sin(y), x^{2} \cos(y))
$$
Jeg indsætter punktet $P\left(1, \frac{\pi}{4}\right)$:
$$
\begin{align*}
2 \cdot 1 \sin\left(\frac{\pi}{4}\right) = 2 \cdot \frac{\sqrt{2}}{2} &= \sqrt{2}\\
1^{2} \sin\left(\frac{\pi}{4}\right) &= \frac{\sqrt{2}}{2}\\
\nabla f\left(1, \frac{\pi}{4}\right) &= \left(\sqrt{2}, \frac{\sqrt{2}}{2}\right)
\end{align*}
$$
#### b) Bestem de punkter $(x,y)$, hvor den retningsafledede $D_{\overline{v}} f(x,y)$ i retningen $\overline{v} = \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right)$ er ligmed 0.
Den retningsafledede er givet ved:
$$
D_{\overline{v}} f (x,y) = \nabla f(x,y) \cdot \frac{\overline{v}}{||\overline{v}||}
$$
Derfor beregner jeg først enhedsnormalvektoren:
$$
||\overline{v}|| = \sqrt{\left(\frac{1}{\sqrt{2}}\right)^{2} + \left(\frac{1}{\sqrt{2}}\right)^{2}} = \sqrt{\frac{1}{2} + \frac{1}{2}} = \sqrt{1} = 1
$$
$$
\frac{\overline{v}}{||\overline{v}||} = \left(\frac{\frac{1}{\sqrt{2}}}{1}, \frac{\frac{1}{\sqrt{2}}}{1}\right) = \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right)
$$
Efter jeg har sikret det er en enhedsnormalvektor kan jeg indsætte det i formlen:
$$
\begin{align*}
D_{\overline{v}} f (x,y) &=  \nabla f(x,y) \cdot \frac{\overline{v}}{||\overline{v}||}\\
\nabla f(x,y) &= \left(\sqrt{2}, \frac{\sqrt{2}}{2}\right)\\
\frac{\overline{v}}{||\overline{v}||} &= \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right)\\
\text{indsætter det:}\\
&= (2x \sin(y), x^{2} \cos(y)) \cdot \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right)\\
&= \frac{2x \sin(y) + x^{2} \cos(y)}{\sqrt{2}}
\end{align*}
$$
Jeg skulle finde hvornår den var ligmed 0:
$$
\begin{align*}
\frac{2x \sin(y) + x^{2} \cos(y)}{\sqrt{2}} = 0 &\Rightarrow 2x \sin(y) + x^{2} \cos(y) = 0\\
\text{Faktoriserer:}\\
x(2 \sin(y ) + x \cos(y)) &= 0\\
\text{Hvis } x=0, \text{er det i hvert fald en løsning}\\
\text{Anden løsning er hvis: } 2 \sin(y) + x \cos(y) &=  0\\
x \cos(y) = -2 \sin(y) \Rightarrow x &=  - 2 \tan(y)\\
\text{Så længe } \cos(y) &\neq 0
\end{align*}
$$
For at $\cos(y) \neq 0$ så skal $y \neq \frac{\pi}{2} + k \pi$. Derfor bliver løsningerne:
$$
\cases{(x,y) = (0,y) \quad \text{for alle y, } y \in \mathbb{R},\\
\text{eller}\\
(x,y) = (-2 \tan(y),y) \quad \text{for } y \neq \frac{\pi}{2} + k \pi, k \in \mathbb{Z}}
$$

## Opgave 4
Lad S være overfladen af området beskrevet ved paraboloiden:
$$
S: z = \frac{1}{2} x^{2} + \frac{1}{2} y^{2} \quad \text{og} \quad 0 \leq z \leq 8
$$
med rand C beskrevet ved parameterfremstillingen:
$$
C: \overline{r}(\theta) = (4 \cos(\theta), 4 \sin(\theta), 8), \quad \text{hvor } 0 \leq \theta \leq 2 \pi
$$
Desuden er vektorfunktionen $\overline{F}(x,y,z)$ givet som: $\overline{F}(x,y,z) = (x,x,z)$
#### a) Skitsér området S:
![[Pasted image 20250609104913.png]]

#### b) Udregn linjeintegralet $\oint_{C} \overline{F} \cdot d \overline{r}$
Jeg har allerede parameterfremstillingen:
$$
C: \overline{r}(\theta) = (4 \cos(\theta), 4 \sin(\theta), 8), \quad \text{hvor } 0 \leq \theta \leq 2 \pi
$$
Jeg skal beregne $d \overline{r}$ ved at differentiere $\overline{r}(\theta)$:
$$
d \overline{r} = \frac{d \overline{r}}{d \theta} d \theta = (- 4 \sin(\theta), 4 \cos(\theta), 0) d \theta
$$
Dette indsætter jeg i $\overline{F}(x,y,z)$:
$$
\begin{align*}
\overline{F}(x,y,z) &=  (x,x,z)\\
\overline{F}(\overline{r}(\theta)) &= (4 \cos(\theta), 4 \cos(\theta), 8)
\end{align*}
$$
Beregner prikproduktet $\overline{F} \cdot d\overline{r}$:
$$
\begin{align*}
\overline{F} \cdot d \overline{r} &=  (4 \cos(\theta) \cdot (-4 \sin(\theta)) + (4 \cos(\theta) \cdot 4\cos(\theta)) + (8 \cdot 0))\\
&= -16 \cos(\theta) \sin(\theta) + 16 \cos^{2}(\theta)
\end{align*}
$$
Så kan jeg bruge den trigonometriske identitet $2 \cos(\theta) \sin(\theta) = \sin(2 \theta)$ og $\cos^{2}(\theta) = \frac{1 + \cos(2 \theta)}{2}$
$$
\begin{align*}
- 16 \cos(\theta) \sin(\theta) &=  - 8 \sin (2 \theta)\\
16 \cos^{2}(\theta) &= 8(1 + \cos(2 \theta))
\end{align*}
$$
Dermed får jeg at:
$$
\overline{F} \cdot d \overline{r} = -8 \sin( 2 \theta) + 8(1 + \cos(2 \theta)) = 8 -8 \sin(2 \theta) + 8 \cos(2 \theta)
$$
Nu kan jeg integrere:
$$
\oint_{C} \overline{F} \cdot d\overline{r} = \int_{0}^{2\pi} (8 - 8\sin(2 \theta) + 8 \cos(2 \theta)) \, d \theta
$$
Deler op i tre integraler:
$$
\int_{0}^{2\pi} 8 \, d \theta - \int_{0}^{2\pi} 8\sin(2 \theta) \, d \theta + \int_{0}^{2\pi} 8 \cos(2 \theta) \, d \theta
$$
$$
\int_{0}^{2\pi} 8 \, d \theta  = 16 \pi
$$
$$
\int_{0}^{2\pi} 8\sin(2 \theta) \, d \theta = 0
$$
Dette integrale er 0, fordi $\sin(2 \theta)$ har en fuld periode på $2 \pi$
$$
\int_{0}^{2\pi} 8 \cos(2 \theta) \, d \theta = 0
$$
Dette integrale er 0, fordi $\cos(2 \theta)$ har en fuld periode på $2 \pi$
Dermed bliver linjeintegralet:
$$
\oint_{C} \overline{F} \cdot d\overline{r} = 16 \pi - 0 + 0 = 16 \pi
$$
Man kunne også løse denne ved at bruge Stokes' sætning, men jeg kan se jeg bliver bedt om det senere.

#### c) Vis, at en enhedsnormalvektor til den givne overflade bliver $\overline{n} = \left(\frac{-x}{\sqrt{1 + 2z}}, \frac{-y}{\sqrt{1 + 2z}}, \frac{1}{\sqrt{1 + 2z}} \right)$ (Lidt hjælp: Definer overflade som en niveauflade og bestem normalvektoren vha. gradienten, som står vinkelret på fladen)
Overfladen $S$ er givet ved $S: z = \frac{1}{2} x^{2} + \frac{1}{2} y^{2}$. Dette kan defineres som en niveaufalde:
$$
g(x,y,z) =  \frac{1}{2} x^{2} + \frac{1}{2} y^{2} -z = 0
$$
Normalvektoren er givet ved gradienten af g:
$$
\begin{align*}
\nabla g &=  \left(\frac{\partial g}{\partial x}, \frac{\partial g}{\partial y}, \frac{\partial g}{\partial z}\right)\\
\frac{\partial g}{\partial x} = \left(\frac{1}{2}x^{2}\right)' &=  x\\
\frac{\partial g}{\partial y} = \left(\frac{1}{2}y^{2}\right)' &=  y\\
\frac{\partial g}{\partial z} = (-z)' &= -1
\end{align*}
$$
Dvs. gradienten af g er givet ved:
$$
\nabla g = (x, y, -1)
$$
Jeg beregner nu enhedsnormalvektoren af $\overline{n}$ ved at normalisere $\nabla g$:
$$
\begin{align*}
||\nabla g|| &=  \sqrt{(x)^{2} + (y)^{2} + (-1)^{2}}\\
&= \sqrt{x^{2} + y^{2} + 1}\\
\end{align*}
$$
Da $z = \frac{1}{2} x^{2} + \frac{1}{2} y^{2}$ så kan jeg udtrykke $x^{2} + y^{2}$ som $2z$:
$$
\begin{align*}
||\nabla g|| &=  \sqrt{\left(2z\right) + 1}\\
&= \sqrt{2z + 1}
\end{align*}
$$
Nu skal jeg bare indsætte de beregnede værdier i formlen for enhedsnormalvektoren:
$$
\overline{n} = \frac{\nabla g}{||\nabla g||} = \left(\frac{x}{{\sqrt{2z + 1}}}, \frac{y}{\sqrt{2z + 1}}, \frac{-1}{\sqrt{2z + 1}}\right)
$$
Men her peger normalvektoren i den negative z-retning, så hvis jeg vil have den til at pege i den positive z-retning skal jeg tage den negative gradient:
$$
\overline{n}_{udad} = - \frac{\nabla g}{||\nabla g||} = \left(\frac{-x}{{\sqrt{2z + 1}}}, \frac{-y}{\sqrt{2z + 1}}, \frac{1}{\sqrt{2z + 1}}\right)
$$

#### d) Eftervis resultatet fra spørgsmål b) ved at udregne fladeintegralet
Stokes teori er:
$$
\oint_{C} \overline{F} \cdot dr = \iint_{S} (\nabla \times \overline{F}) \cdot ds
$$
Hvor S er en flade der er begrænset af C med en normal vektor der har et ikke negatigt z-komponent, som der står i opgavens beskrivelse.
Først beregner jeg curl af F
$$
\begin{align*}
\nabla \times F &= 
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
a_{1}  & a_{2}  & a_{3}\\
b_{1}  & b_{2} &  b_{3}\\
\end{vmatrix}\\
&= \vec{i}(a_{2}b_{3} - a_{3}b_{2}) - \vec{j}(a_{1}b_{3} - a_{3}b_{1}) + \vec{k}(a_{1}b_{2} - a_{2}b_{1})\\
\text{Indsætter mine værdier:}\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
\frac{\partial}{\partial x}  & \frac{\partial}{\partial y} & \frac{\partial}{\partial z}\\
x  & x &  z\\
\end{vmatrix}\\
&= \vec{i}(\frac{\partial}{\partial y}(z) - \frac{\partial}{\partial z}(x)) - \vec{j}(\frac{\partial}{\partial x}(z) - \frac{\partial}{\partial z}(x)) + \vec{k}(\frac{\partial}{\partial x}(x) - \frac{\partial}{\partial y}(x))\\
&= \vec{k}(1)
\end{align*}
$$
Dermed er $\nabla \times F = [0,0,1]$

Jeg beregner fladeelementet ved at differentiere den allerede beregnet normalvektor:
$$
d \vec{S} = \vec{n} \, dS = \frac{(-x, -y, 1)}{\sqrt{2z+1}} \sqrt{1 + x^{2} + y^{2}} \, dx \, dy = (-x,-y,1) \, dx \, dy
$$

Nu beregner jeg fladeintegralet:
$$
\begin{align*}
(\nabla \times \overline{F}) \cdot dS = [0,0,1] \cdot [-x,-y,1] \cdot dS = 1 \, dx \, dy\\
\iint_{S} (\nabla \times \overline{F}) \, dS = 1 \iint_{C} dx \, dy\\
\end{align*}
$$
Her er C projektionen af S på xy-planet, som er cirklen med radius:
$$
\begin{align*}
x^{2}+y^{2} &=  16\\
r^{2} &=  x^{2} + y^{2}\\
r^{2}= 16 \Rightarrow r&= 4
\end{align*}
$$
Arealet er dermed givet ved $\pi \cdot 4^{2} = 16 \pi$:
$$
\iint_{C} 1 \, dx \, dy = 16 \pi
$$
Dermed med Stokes teori så er linjeintegralet:
$$
\oint \overline{F} \cdot d \overline{r} = 16 \pi
$$
Hvilket var det samme resultat som jeg fik i b).