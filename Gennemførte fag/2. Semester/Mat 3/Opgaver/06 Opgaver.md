### 12.6.5 (benyt cm som enhed)
Find the temperature $u(x,t)$ in a bar of silver of length 10 cm and constant cross section of area $1 \space cm^{2}$ (density $10.6 \frac{g}{cm^{3}}$), thermal conductivity $1.04 \space \frac{cal}{cm \space sec \space \degree C}$, specific heat $0.056 \space \frac{cal}{g \space \degree C}$ that is perfectly insulated laterally, with ends kept at temperature $0 \degree C$ and initial temperature $f(x) \degree C$, where
$f(x) = \sin(0.1\pi x)$ 

Jeg starter med at indsætte formlen for en varmeligning:
$$
\begin{align*}
\frac{\delta u}{\delta t} &=  c \frac{\delta ^{2} u}{\delta x^{2}}\\
\text{Hvor c er thermal diffusivity}\\
c &=  \frac{K}{p \sigma}
\end{align*}
$$
Jeg har fået dette givet i opgaven:
$$
\begin{align*}
L &=  10 \space cm\\
K &= 1.04 \space \frac{cal}{cm \space sec \space \degree C}\\
p &=  10.6 \frac{g}{cm^{3}}\\
\sigma &=  0.056 \space \frac{cal}{g \space \degree C}
\end{align*}
$$
Jeg regner først c:
$$
c = \frac{1.04 \space \frac{cal}{cm \space sec \space \degree C}}{10.6 \frac{g}{cm^{3}} \cdot 0.056 \space \frac{cal}{g \space \degree C}}= 1.752 \frac{cm^{2}}{sec}
$$
Startbetingelserne:
$$
\begin{align*}
u(0,t) &=  0, \quad u(10, t) = 0\\
u(x,0) &=  f(x) = \sin(0.1 \pi x)
\end{align*}
$$
Separation af variable:
$$
\begin{align*}
u(x,t) &=  X(x)T(t)\\
\text{Substituer ind i varmeligningen}\\
XT' &= c X''T\\
\text{Dividerer med XT:}\\
\frac{T'}{cT} = \frac{X''}{X} &= - \lambda\\
\end{align*}
$$
Løser først for $X(x)$:
$$
\begin{align*}
X''+ \lambda X = 0, \quad X(0)= 0, \quad X(10) &= 0\\
\text{Generelle løsning:}\\
X(x) &= A \cos(\sqrt{\lambda} x) + B \sin(\sqrt{\lambda} x)\\
\text{Indsætter } X(0)&= 0\\
A \cos(0) + B \sin(0) = A &= 0\\
\text{Siden } B &\neq 0\\
X(x) &= B \sin(\sqrt{\lambda} x)\\
\text{Egenfunktionen bliver:}\\
X_{n}(x) &=  \sin(0.1 n \pi x)\\
\text{Med egenværdier}\\
\lambda_{n} &= (0.1 n \pi)^{2}
\end{align*}
$$
Løser nu for $T_{n}(T)$:
$$
\begin{align*}
T_{n}' + c \lambda_{n}T_{n} &=  0\\
T_{n}(t) &= C_{n}e^{-c \lambda_{n} t}
\end{align*}
$$
Siden $f(x) = \sin(0.1 \pi x)$ og egenfunktionen var:
$$
\begin{align*}
f(x) &= \sin(0.1 \pi x)\\
\text{Dette svarer til } n&= 1:\\
f(x) &= \sin(1\cdot 0.1 \pi x)\\
f(x) &= A_{1} \sin(0.1 \pi x)\\
A_{1}&= 1\\
u(x,t) &= \sin(0.1 \pi x) e^{-c \left(\frac{\pi}{10}\right)^{2} t}\\
\text{indsætter c = 1.752}\\
u(x,t) &= \sin(0.1 \pi x) e^{-1.752 \left(\frac{\pi}{10}\right)^{2} t}\\
\text{Da } \left(\frac{\pi}{10}\right)^{2} &= \frac{\pi^{2}}{100}\\
u(x,t) &= \sin(0.1 \pi x) e^{\frac{-1.752 \pi^{2} t}{100}}
\end{align*}
$$
### 12.6.10
**Change of end temperatures.** Assume that the ends of the bar in Probs. 5–7 have been kept at $100 \degree C$ for a long time. Then at some instant, call it $t=0$, the temperature at $x=L$ is suddenly changed to $0 \degree C$ and kept at $0 \degree C$, whereas the temperature at $x = 0$ is kept at $100 \degree C$. 
Find the temperature in the middle of the bar at $t = 1,2,3,10,50 \space sec$. First guess, then calculate.

Jeg gætter på at stangen i midten er omkring 50 grader ved start og falder langsomt ned til 35 grader over 50 sekunder.
Jeg indsætter længden $L=5$ på x's plads i den forrige beregnet funktion:
$$
u(x,t) = \sin(0.1 \pi x) e^{\frac{-1.752 \pi^{2} t}{100}}
$$
$$
\sin(0.1 \pi \cdot 0.5) = \sin(0.5 \pi) = \sin\left(\frac{\pi}{2}\right) = 1
$$
Derfor når jeg skal beregne temperaturen til tiden $t$ så skal jeg blot indsætte det i funktionen:
$$
u(L,t) = u(5,t) = e^{\frac{-1.752 \pi^{2} t}{100}}
$$
![[MatLab 12.6.10.png]]
$t=1$:
$$
u(5,1) = e^{\frac{-1.752 \pi^{2} 1}{100}} = 0.8412
$$
$t=2$:
$$
u(5,2) = e^{\frac{-1.752 \pi^{2} 2}{100}} = 0.7076
$$
$t=3$:
$$
u(5,3) = e^{\frac{-1.752 \pi^{2} 3}{100}} = 0.5953
$$
$t=10$:
$$
u(5,10) = e^{\frac{-1.752 \pi^{2} 10}{100}} = 0.1774
$$
$t=50$:
$$
u(5,50) = e^{\frac{-1.752 \pi^{2} 50}{100}} = 1.7587\cdot 10^{-4}
$$

### 12.6.13
Find the temperature in problem 11 with  $L=\pi$, $c=1$ and $f(x)=1$
Problem 11:
$$
u(x,t) = A_{0} + \sum_{n\space =\space 1} ^{\infty} A_{n}\cos\left(\frac{n \pi x}{L}\right)e ^{-\left(\frac{cn \pi}{L}\right)^{2} t}
$$

Bruger startbetingelser
$$
\begin{align*}
u(x,0) = f(x) &= 1\\
\text{Så temperaturen er konstant ligmed 1}\\
u(x,0) &= A_{0} + \sum_{n\space =\space 1} ^{\infty} A_{n}\cos\left(\frac{n \pi x}{L}\right)\\
\text{Substituerer } L&= \pi\\
u(x,0) &= A_{0} + \sum_{n\space =\space 1} ^{\infty} A_{n}\cos(nx)\\
\text{Da } u(x,0) &= 1\\
1&= A_{0} + \sum_{n\space =\space 1} ^{\infty} A_{n}\cos(nx)\\
\end{align*}
$$
Nu skal jeg finde Fourier koefficienterne $A_{0}$ og $A_{n}$ 
Jeg bruger formlen:
$$
A_{0}= \frac{1}{L} \int_{0}^{L }f(x) \, dx
$$
Siden $f(x) = 1$ og $L = \pi$:
$$
A_{0}= \frac{1}{\pi} \int_{0}^{\pi} 1 \, dx = \frac{1}{\pi} \cdot \pi = 1
$$
Nu regner jeg $A_{n}$:
$$
A_{n} = \frac{2}{L} \int_{0}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx
$$
Siden igen at $f(x) = 1$ og $L = \pi$:
$$
\begin{align*}
A_{n} &=  \frac{2}{\pi} \int_{0}^{\pi} \cos\left(\frac{n \cancel{\pi}x}{\cancel{\pi}}\right) \, dx\\
A_{n} &=  \frac{2}{\pi} \int_{0}^{\pi} \cos(n x) \, dx\\
&= \frac{2}{\pi} \left[\frac{\sin(nx)}{n}\right]_{0}^{\pi}\\
\text{Da både} \sin(\pi) = 0 \text{ og } \sin(0) &= 0\\
&= 0
\end{align*}
$$
Dvs. uanset hvilket naturligt heltal n er så er $A_{0} = 1$ og $A_{n}= 0$
Derfor bliver:
$$u(x,t) = 1$$
Dette betyder at baren konstant er 1 grad ved alle positioner uanset tidspunktet.
### 12.6.21
Heat flow in a plate. The faces of the thin square plate in Fig. 297 with side $a=24$ are perfectly insulated. The upper side is kept at $25 \degree C$ and the other sides are kept at $0 \degree C$. Find the steady-state temperature $u(x,t)$ in the plate.
Figure 297:
![[Fig 297.png]]
Til dette to-dimensionelle problem skal jeg bruge Laplace ligningen (steady-state heat equation):
$$
\frac{\delta ^{2} u}{\delta x^{2}} + \frac{\delta ^{2} u}{\delta y ^{2}} = 0
$$
Som har følgende startbetingelser:
$$
\begin{align*}
u(x,0) = 0,u(x,24) &=  25 \degree C \text{ temperatur ved bunden og toppen}\\
u(0,y) = 0,u(0,24) &=  0 \degree C \text{ temperatur ved venstre og højre kant}
\end{align*}
$$
"steady-state temperature" betyder at løsningen ikke skal afhænge af tiden $t$

Separation af variable:
$$
\begin{align*}
u(x,y) &= X(x)Y(y)\\
\text{Bruger Laplaces ligning:}\\
X''(x)Y(y) + X(x) Y''(y) &= 0\\
\text{Dividerer med X(x) og Y(y):}\\
X''\frac{x}{X(x)} = - Y''\frac{y}{Y(y)} &= \lambda\\
\text{Dermed fås to differentialligninger:}\\
X''(x) + \lambda X(x) &=  0\\
Y''(y) - \lambda Y(y) &=  0\\
\end{align*}
$$
Starter med at løse for $X(x)$:
$$
\begin{align*}
X(x) = 0, \quad \text{ og } X(24) &= 0\\
\text{Den generelle løsning er:}\\
X(x) = A \sin(\sqrt{\lambda} x) + B \sin(\sqrt{\lambda} x)\\
X(0) &= 0 \\
X(0) = A \cos(0) + B \sin(0) &=  A\\
\text{Siden } X(0)&= 0\\
A &= 0\\
\text{Derfor bliver løsningen:}\\
X(x) &= B \sin(\sqrt{\lambda} x)\\
X(24) = B \sin(\sqrt{\lambda} \cdot 24) &= 0\\
\text{Men da } B &\neq 0\\
\sin(\sqrt{\lambda} \cdot 24) &= 0\\
\sqrt{\lambda} \cdot 24 &=  k \pi, \quad k = 1,2,3 \dots\\
\lambda &= \left(\frac{k \pi}{24}\right)^{2}\\
\text{Siden sinus funktionen er ulige: } k = 1,3,5 \dots\\
k&= 2n-1\\
\lambda = \left(\frac{(2n -1) \pi}{24}\right)^{2}\\
\sqrt{\lambda} = \frac{(2n-1) \pi}{24}\\
\sin\left(\sqrt{\lambda} = \frac{(2n-1) \pi x}{24}\right)&= 0, x= 0 \land x=24\\
X_{n}(x)&= \sin\left(\frac{(2n-1) \pi x}{24}\right) 
\end{align*}
$$
Løser for $Y(y)$:
$$
\begin{align*}
Y''(t)- \lambda Y(y) &= 0\\
\text{Den generelle løsning er:}\\
Y(y) &= C \cosh(\sqrt{\lambda} y) + D \sinh (\sqrt{\lambda} y)\\
Y(y) &= 0\\
C &= 0\\
Y(y) &= D \sinh(\sqrt{\lambda} y)\\
Y(24) = D \sinh(\sqrt{\lambda} \cdot 24) &= 25\\
\lambda &= \left(\frac{(2n -1) \pi }{24}\right)^{2}\\
D \sinh \left(\frac{(2n -1) \pi 24 }{24}\right) &=  25\\
D \sinh((2n -1) \pi) &=  25\\
Y_{n}(y)&= \sinh\left(\frac{(2n-1) \pi y}{24}\right) \\
\end{align*}
$$

Derfor bliver løsningen:
$$
\begin{align*}
u(x,y) &=  \sum_{n\,=\, 1} ^{\infty} A_{n}\sin\left(\frac{(2n-1) \pi x}{24}\right) \sinh \left(\frac{(2n -1) \pi y}{24}\right)\\
u(x,24) &= \sum_{n\,=\, 1} ^{\infty} A_{n}\sin\left(\frac{(2n-1) \pi x}{24}\right) \sinh ((2n-1) \pi)
\end{align*}
$$
Nu skal jeg løse for $A_{n}$ og $B_{n}$
...

To move from our derived result to the book’s final result, we need to determine the coefficients $A_n$. 


Siden $u(x,24) = 25$:
$$
\sum_{n=1}^{\infty} A_n \sin\left(\frac{(2n-1)\pi x}{24}\right) \sinh((2n-1)\pi) = 25.
$$
Dette er en sinus serie. Fourier serien over $0 \leq x \leq 24$ er:
$$
f(x) = \sum_{n=1}^{\infty} B_n \sin\left(\frac{(2n-1)\pi x}{24}\right),
$$
Hvor $B_{n}$:
$$
B_n = \frac{2}{24} \int_0^{24} 25 \sin\left(\frac{(2n-1)\pi x}{24}\right) dx.
$$
Standardintegralet er:

$$
\int_0^{L} \sin\left(\frac{(2n-1)\pi x}{L}\right) dx = \frac{L}{(2n-1)\pi} \cdot 2.
$$
$L = 24$:
$$
B_n = \frac{2}{24} \cdot 25 \cdot \frac{24}{(2n-1)\pi} \cdot 2 = \frac{100}{(2n-1)\pi}.
$$
$A_{n}$:
$$
A_n \sinh((2n-1)\pi) = B_n = \frac{100}{(2n-1)\pi}.
$$
$$
A_n = \frac{100}{(2n-1)\pi \sinh((2n-1)\pi)}.
$$
Substituerer tilbage i Fourierrækken:
$$
u(x,y) = \sum_{n=1}^{\infty} \frac{100}{(2n-1)\pi \sinh((2n-1)\pi)} \sin\left(\frac{(2n-1)\pi x}{24}\right) \sinh\left(\frac{(2n-1)\pi y}{24}\right).
$$

Som svarer til bogens svar:
$$u = \frac{100}{\pi} \sum_{n\,=\,1}^ {\infty} \frac{1}{(2n-1) \sinh (2n-1) \pi} \sin\left(\frac{(2n-1)\pi x}{24}\right) \sinh \left(\frac{(2n-1)\pi y}{24}\right)$$