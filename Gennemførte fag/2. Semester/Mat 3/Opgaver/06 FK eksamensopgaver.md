![[FK 06 eksamensopgave 02.png]]
02
Den endimensionale bølgeligning for en given stålwire med længen L er givet ved:
$$
\frac{\delta^{2}u}{\delta t^{2}} = c^{2} \frac{\delta ^{2} u}{\delta x^{2}}, \quad \text{ hvor } c^{2}= 1 \text{ og } L =2
$$
Der gælder følgende randbetingelser: $u(0,t)=0$ og $u(L,t) = 0$
Desuden gælder følgende begyndelsesbetingelser: $u(x,0) = f(x)$ og $u_{t}(x,0)=0$
Ved seperation af de variable, idet det antages at $u(x,t) = F(x)G(t)$ kan man (som bekends fra lærerbogen), komme frem til følgende ordinære differentialligninger:
$$
\frac{\delta^{2}F}{\delta x^{2}}=kF, \quad \text{ og } \frac{\delta ^{2}G}{\delta t^{2}} = kG
$$
a) Løs disse to differentialligninger når k er negativ, dvs. $k = -p^{2}$

Jeg indsætter i bølgeligningen:
$$
\frac{G''(t)}{G(t)} = \frac{F''(x)}{F(x)} = k
$$
#### Jeg starter med F(x):
$$
F''(x) = -p^{2} F(x)
$$
Så er den karakteristiske løsning:
$$
r ^{2} + p^{2} = 0
$$
Som har rødderne:
$$
r = \pm ip
$$
De komplekse rødder har den generelle løsning:
$$
F(x) = A \cos(px) + \sin(px)
$$
Indsætter randbetingelsen $F(0)= 0$:
$$
\begin{align*}
&= A \underbrace{\cos(0)}_{1} + \underbrace{B \sin(0)}_{0}\\
= A &=  0\\
\text{Derfor er løsningen:}\\
F(x) &=  B \sin(px)\\
\text{Bruger anden randbetingelse } F(L)&= 0\\
B \sin(pL) &= 0\\
\text{For den ikke trivielle løsning:}\\
\sin(pL) &=  0\\
pL &=  n \pi, \quad n = 1,2,3 \dots\\
\text{egenværdierne er:}\\
p_{n} &= \frac{n \pi}{L}\\
\text{egenfunktionerne er:}\\
F_{n}(x) &= B_{n} \sin\left(\frac{n \pi}{L}x\right)\\
\text{Indsætter } L &= 2\\
F_{n}(x) &= B_{n} \sin\left(\frac{n \pi}{2}x\right)\\
\end{align*}
$$
#### Nu til G(t)
$$
\frac{\delta ^{2}G}{\delta t^{2}} = kG
$$
Jeg har jo lige fundet at $p = \frac{n \pi}{L}$ 
$$
\begin{align*}
G_{n}(t) &=  C_{n} \cos\left(\frac{n \pi}{L}\right) + D_{n} \sin\left(\frac{n \pi}{L}\right)\\
\text{ved } u_{t}(x,0) &= 0 \text{ differentieres } u_{n}(x,t) = F_{n}(x)G_{n}(t)\\
u_{t}(x,0) &= F_{n}(x)G'(0)\\
G_{n}' &=  -C_{n} \frac{n \pi}{L} \sin\left(\frac{n \pi}{L}t\right) + D_{n} \frac{n \pi}{L} \cos\left(\frac{n \pi}{L}t\right)\\
G_{n}'(0)&= D_{n}\frac{n \pi}{L}\\
\text{Indsætter } L &= 2\\
G_{n}'(0)&= D_{n}\frac{n \pi}{2}\\
\text{For at } u_{t}(x,0) = 0, \text{ så skal } D_{n}&=  0\\
G_{n}(t) &= C_{n}\cos\left(\frac{n \pi}{L}t\right)\\
\text{Indsætter } L &= 2:\\
G_{n}(t) &= C_{n}\cos\left(\frac{n \pi}{2}t\right)\\
\end{align*}
$$
b) Opskriv løsningen til bølgeligningen $u(x,t) = F(x)G(t)$ med løsningerne fra sp. a indsat. Bestem herefter de løsninger, der opfylder randbetingelserne.

Jeg indsætter løsningerne for $F_{n}(x)$ og $G_{n} (t)$:
$$
u_{n}(x,t) = B_{n} \sin\left(\frac{n \pi}{2} x\right) C_{n} \cos\left(\frac{n \pi}{2} t\right)
$$
Konstanten $B_{n}$ kommer fra $F(x)$, og når randbetingelsen $F(0) = 0$ og $F(L) = 0$  når $L=2$ så er $p=\frac{n \pi}{2}$ og $F_{n} (x) = B_{n} \sin\left(\frac{n \pi}{2}x\right)$
Konstanten $C_{n}$ kommer fra $G(t)$, hvilket bare kan laves sammen med $B_{n}$ til en ny samlet konstant $B_{n}$

Bølgeligningen er lineær. Det betyder, at hvis $u_{1}(x,t)$ og $u_{2}(x,t)$ er løsninger, så er også summen $u(x,t)=u_{1}(x,t)+u_{2}(x,t)$ en løsning. Derfor kan jeg skrive den generelle løsning som en sum (superposition) af alle de separerede løsninger (også kaldet egenfunktioner):
$$
\begin{align*}
u(x,t) &= \sum_{n \, = \, 1} ^{\infty} F_{n}(x) G_{n}(t)\\
&= \sum_{n \, = \, 1} ^{\infty} B_{n} \sin\left(\frac{n \pi}{2} x\right)\cos\left(\frac{n \pi}{2} t\right)
\end{align*}
$$
Checker randbetingelserne:
$$
\begin{align*}
\text{Indsætter } x&= 0\\
u(0,t) = \sum_{n \, = \, 1} ^{\infty} B_{n} \sin\left(\frac{n \pi}{2} 0\right)\cos\left(\frac{n \pi}{2} t\right) &= 0\\
\text{Indsætter } L &= 2\\
u(2,t) = \sum_{n \, = \, 1} ^{\infty} B_{n} \sin\left(\frac{n \pi}{2} 2\right)\cos\left(\frac{n \pi}{2} t\right)\\
&= \sum_{n \, = \, 1} ^{\infty} B_{n} \sin\left(n \pi\right)\cos\left(\frac{n \pi}{2} t\right)\\
\text{Da } \sin(n \pi) &= 0 \text{ for alle heltal n-værdier } (n \space \epsilon \space \mathbb{N})
\end{align*}
$$
Det checker ud.

c) Herefter anvendes begyndelsesbetingelsen $u_t(x,0)=0$ 
Gør rede for at den fuldstændige løsning til bølgeligningen herefter er:
$$
u(x,t) = \sum_{n \, = \, 1} ^{\infty} B_{n}\sin\left(\frac{n \pi}{2}x\right) \cdot \cos\left(\frac{n \pi}{2}t\right)
$$
Jeg starter med at differentiere mht. t:
$$
\begin{align*}
u_{t}(x,t) = \sum_{n \, = \, 1} ^{\infty} B_{n}\sin\left(\frac{n \pi}{2}x\right) \cdot \left(\cos\left(\frac{n \pi}{2}t\right)\right)'\\
\text{Kæderegel}\\
= \sum_{n \, = \, 1} ^{\infty} B_{n}\sin\left(\frac{n \pi}{2}x\right) \cdot \left(-\frac{n \pi}{2} \sin\left(\frac{n \pi}{2}t\right)\right)\\
u_{t}(x,0) &= \sum_{n \, = \, 1} ^{\infty} B_{n}\sin\left(\frac{n \pi}{2}x\right) \cdot \left(-\frac{n \pi}{2} \sin\left(\frac{n \pi}{2}0\right)\right)\\
&= 0
\end{align*}
$$
Det at $u_{t}(x,0) = 0$ for den generelle løsning, kommer netop af, at i løsningen for $G_{n}(t)$ allerede har sat den del, der involverer $\sin$-leddet, til nul (dvs. $D_{n}=0$):
$$
G_{n}(t) = C_{n}\cos\left(\frac{n \pi}{2}t\right)
$$
Når jeg også bruger $u(x,t) = 0$
$$
\begin{align*}
u(x,0) &=  \sum_{n \, = \, 1} ^{\infty} B_{n} \sin\left(\frac{n \pi}{2} x\right)\cos\left(\frac{n \pi}{2} 0\right)\\
\text{Da } \cos(0)&= 1\\
&= \sum_{n \, = \, 1} ^{\infty} B_{n} \sin\left(\frac{n \pi}{2} x\right)\\
\end{align*}
$$
Derfor er den generelle løsning:
$$
\begin{align*}
u(x,t) &= \sum_{n \, = \, 1} ^{\infty} B_{n} \sin\left(\frac{n \pi}{2} x\right) \cdot \cos\left(\frac{n \pi}{2} t\right)\\
\end{align*}
$$
d) Bestem den partikulære løsning, der opfylder begyndelsesbetingelsen
$$
u(x,0) = f(x) = 0.1 \sin \left(\frac{3 \pi}{2}x\right)
$$
Ud fra begyndelsesbetingelsen kan det ses at frekvensen for sinuskurven er sat til $n=3$ og der er $B_{3} = 0.1$. Dvs. $B_{n} = 0$ for $n \neq 3$
Så da den generelle løsning er:
$$
u(x,t) = \sum_{n \, = \, 1} ^{\infty} B_{n} \sin\left(\frac{n \pi}{2} x\right) \cdot \cos\left(\frac{n \pi}{2} t\right)
$$
Så er den partikulære løsning givet ved:
$$
u(x,t) = 0.1 \sin \left(\frac{3 \pi}{2}x\right) \cdot \cos\left(\frac{3 \pi}{2}t\right)
$$


![[FK 06 eksamensopgave 04.png]]
04
a) Skitsér grafen for $f(x)$ i intervallet $-1,5 \leq x \leq 1,5$:
![[06 Eksamensopgaver_250330_161614.pdf]]

b) Udled fourierrækken for $f(x)$:
Jeg bruger formlen for Fourierrækker der har perioden $L$ 
$$
\begin{align*}
f(x)&= \frac{a_{0}}{2} + \sum^{\infty}_{n \, = \, 1} \left(a_{n} \cos\left(\frac{\pi \, n}{L}x\right) + b_{n}  \sin\left(\frac{\pi \, n}{L}x\right)\right)\\
a_{0}&=  \frac{1}{2L} \int_{-L}^{L}f(x) \, dx\\
a_{n}&= \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{\pi \, n}{L}x\right) \, dx\\
b_{n}&= \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{\pi \, n}{L}x\right) \, dx
\end{align*}
$$
$L$ er i dette tilfælde $L=0.5$ Da perioden er på 1 og perioden er $2L$
Men som også kan ses på tegningen så er denne funktion symmetrisk. Dette betyder at $b_{n} = 0$ 

Jeg starter med at beregne $a_{0}$:
$$
\begin{align*}
a_{0}&=  \frac{1}{2L} \int_{-L}^{L}f(x) \, dx\\
&= \frac{1}{1} \int_{-0.5} ^{0.5} f(x) \, dx\\
\end{align*}
$$
I dette tilfælde er der kun en værdi forskellige fra 0 i intervallet: $[-0.1; 0.1]$ 
$$
\begin{align*}
&= \frac{1}{2} \int_{-0.1} ^{0.1} 40 \, dx\\
&= [40 x]_{-0.1} ^{0.1}\\
&= (4-(-4))\\
&=  8
\end{align*}
$$
$$
a_{0}= 8
$$
Nu til $a_{n}$:
$$
\begin{align*}
a_{n}&= \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{\pi \, n}{L}x\right) \, dx\\
&= \frac{1}{0.5} \int_{-0.5}^{0.5} f(x) \cos\left(\frac{\pi n}{0.5}x\right) \, dx\\
\text{Igen kan jeg bare bruge intervallet[-0.1;0.1]:}\\
&= \frac{1}{0.5} \int_{-0.1}^{0.1} f(x) \cos\left(\frac{\pi n}{0.5}x\right) \, dx\\
&=  2\int_{-0.1}^{0.1} 40 \cdot \cos(2\pi n x) \, dx\\
&= 2\cdot 40\cdot \left[\left(\frac{1}{2\pi n}\right) \cdot \sin(2\pi n x)\right]_{-0.1}^{0.1}\\
&= 80 \cdot \frac{1}{2\pi n} \sin(0.2\pi n) - (-\sin (0.2\pi n ))\\
&= 80 \cdot \frac{1}{2\pi n} 2\sin(0.2\pi n)\\
&= 80 \cdot \frac{\sin(0.2 \pi n)}{\pi n}\\
&= \frac{80}{\pi n} \sin(\pi n)
\end{align*}
$$

Derfor bliver den endelige Fourierrække:
$$
\begin{align*}
f(x)&=  \frac{a_{0}}{2} + \sum^{\infty}_{n \, = \, 1} \left(a_{n} \cos\left(\frac{\pi \, n}{L}x\right) + b_{n}  \sin\left(\frac{\pi \, n}{L}x\right)\right)\\
&= \frac{8}{2} + \sum^{\infty}_{n \, = \, 1} \left(\frac{80}{\pi n} \sin(0.2\pi n) \cdot \cos\left(\frac{\pi n}{0.5} x\right)+0\right)\\
&= 4 + \sum^{\infty}_{n \, = \, 1} \left(\frac{80}{\pi n} \sin(0.2\pi n) \cdot \cos\left(2 \pi n x\right)\right)\\\\
\end{align*}
$$