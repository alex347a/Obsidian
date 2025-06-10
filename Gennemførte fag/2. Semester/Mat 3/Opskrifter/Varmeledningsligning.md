## Eksempel
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
Der må være en fejl i opgaven, fordi hele udtrykket i eksponentialfunktionen burde ikke være i anden. Ellers er det den samme løsning som jeg får ved at indsætte mine udregnede funktioner.

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


## Et andet eksempel
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