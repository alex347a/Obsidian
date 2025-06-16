### Opgave 12.3.14
Nonzero initial velocity. Find the deflection $u(x,t)$ of the string of length $L = \pi$ and $c^{2}= 1$  for zero initial displacement and “triangular” initial velocity $u_{t}(x,0) = 0.01x$ if $0 \leq x \leq \frac{1}{2}\pi, \quad u_{t}(x,0) = 0.01(\pi - x)$ if $\frac{1}{2}\pi \leq x \leq \pi$. (Initial conditions with $u_{t}(x,0) \neq 0$ are hard
to realize experimentally.)

Jeg skal altså løse bølgeligningen for en streng med længden $L = \pi$ med en given starthastighed og med 0 forskydning
$$
\begin{align*}
u_{tt} &= c^{2} u_{xx}\\
u(0,t) &= u (\pi,t) =0, \quad \text{for } t \geq 0\\
u(x,0)  &= 0\\
u_{t}(x,0) &= \cases{0.01x, \quad 0 \leq x \leq \frac{\pi}{2},\\ 0.01(\pi -x), \quad \frac{\pi}{2} \leq x \leq \pi}
\end{align*}
$$
Separation af variable:
$$
\begin{align*}
u(x,t) &= \sum_{n \,= \, 1} ^{\infty} X_{n}(x)T_{n}(t)\\
X_{n}'' + \lambda_{n}X_{n} = 0, \quad X_{n}(0) = X_{n}(\pi) &=  0\\
X_{n}(x) = \sin(nx), \quad \lambda_{n} &=  n^{2}
\end{align*}
$$
$$
\begin{align*}
X(x)T''(t) &=  c^{2}X''(x)T(t)\\
\text{Dividere begge sider med } X(x)T(t):\\
\frac{T''(t)}{c^{2}T(t)} =\frac{ X''(x)}{X(x)}\\
\text{Dette må give en konstant:}\\
\frac{T''(t)}{c^{2}T(t)} = \frac{ X''(x)}{X(x)} &= k\\
\text{Derudaf fås to differentialligniner}\\
X''(x) + kX(x) &=  0\\
X(0) = 0, \quad X(\pi) &= 0\\
T''(t) + c^{2}kT(t) &= 0\\
\text{Opgaven fortæller at} c^{2}=1\\
T''(t) +kT(t) &= 0\\
\end{align*}
$$
Løser differentialligningerne:
$$
\begin{align*}
X''(x) + kX(x) &=  0\\
\text{Her skal både } X_{n}(0)=0 \text{ og } X_{n}(\pi) &= 0\\
\end{align*}
$$

$$
\begin{align*}
u_{tt} &= c^{2} u_{xx}\\
u(0,t) &= u (\pi,t) =0, \quad \text{for } t \geq 0\\
u(x,0)  &= 0\\
u_{t}(x,0) &= \cases{0.01x, \quad 0 \leq x \leq \frac{\pi}{2},\\ 0.01(\pi -x), \quad \frac{\pi}{2} \leq x \leq \pi}
\end{align*}
$$
Den generelle løsning er givet ved en Fourier-sinusserie, fordi der er nulrandbetingelser:
$$
\begin{align*}
u(x,t) &= \sum_{n\,=\,1} ^{\infty} (A_{n} \cos(nt) + B_{n} \sin(nt) \sin(nx))\\
\end{align*}
$$
Opgaven nu er derfor at finde $A_{n}$ og $B_{n}$:
$$
\begin{align*}
\text{Da } u(x,0) &=  0\\
\sum_{n\,=\,1} ^{\infty} A_{n}\sin(nx) &=  0
\end{align*}
$$
Da $A_{n}=0$ for alle x, så er $A_{0} = 0$
$B_{n}$:
$$
\begin{align*}
u_{t}(x,0)&= 0\\
u_{t}(x,t) &= \sum_{n\,=\,1} ^{\infty} (- A_{n}n \sin(nt)+B_{n}n \cos(nt)) \sin(nx)\\
u_{t}(x,0) &= \sum_{n\,=\,1} ^{\infty} (- A_{n}n \sin(n0)+B_{n}n \cos(n0)) \sin(nx)\\
\text{Da } \cos(0) = 1, \quad \sin(0)&= 0\\
u_{t}(x,0) &= \sum_{n\,=\,1} ^{\infty} B_{n}n \sin(nx)\\
B_{n}&=  \frac{2}{\pi} \int_{0}^{\pi} u_{t}(x,0) \sin(nx) \, dx\\
&= \frac{2}{ \pi} \cdot 0.01 \left(\int_{0}^{\frac{\pi}{2}} x \sin(nx) \, dx + \int_\frac{\pi}{2}^{\pi} (\pi - x) \sin(nx) \, dx\right)\\
\end{align*}
$$
Jeg beregner først det første integrale:
$$
\begin{align*}
\int_{0}^{\frac{\pi}{2}}0.01 x \sin(nx) \, dx\\
\text{integration i dele:}\\
u = x, \quad dv &=  \sin(nx) \, dx\\
du = 1, \quad v &= - \frac{1}{n} \cos(nx)\\
\int_{0}^{\frac{\pi}{2}}0.01 x \sin(nx) \, dx &= - \frac{1}{n} x \cos(nx) |_{0}^{\frac{\pi}{2}} + \frac{1}{n} \int_{0} ^{\frac{\pi}{2}} \cos(nx) \, dx\\
&= - \frac{1}{n}\left[\frac{\pi}{2} \cos\left(n \frac{\pi}{2}\right)-0 \right] + \frac{1}{n^{2}} [\sin(nx)]_{0} ^{\frac{\pi}{2}}\\
&= - \frac{\pi}{2n} \cos\left(n \frac{\pi}{2}\right)+ \frac{1}{n^{2}} \sin\left(\frac{n \pi}{2}\right)\\
\end{align*}
$$
Nu det andet integrale:
$$
\begin{align*}
\int_\frac{\pi}{2} ^{\pi} 0.01 (\pi -x) \sin(nx) \, dx\\
\text{integration i dele:}\\
\int u \, dv &=  uv - \int v \, du\\
u = \pi -x, \quad dv &=  \sin(nx) \, dx\\
du = -1, \quad v &=  - \frac{1}{n} \cos(nx)\\
&= \left[- \frac{1}{n} (\pi - x) \cos(nx)\right]_\frac{\pi}{2} ^{\pi} + \frac{1}{n} \int_{\frac{\pi}{2}} ^{\pi} \cos(nx) \, dx\\
&= \left[- \frac{1}{n} \left[(\pi-\pi) \cos(n \pi) - \left(\pi - \frac{\pi}{2}\right)  \cos\left(n \frac{\pi}{2}\right) \right] + \frac{1}{n^{2}} [\sin (nx)]_{\frac{\pi}{2}} ^{\pi} \right]\\
&= \left[- \frac{1}{n} \left[\frac{\pi}{2} \cos\left(n \frac{\pi}{2}\right) \right] + \frac{1}{n^{2}} [\sin (nx)]_{\frac{\pi}{2}} ^{\pi} \right]\\
&= \left[- \frac{1}{n} \left[\frac{\pi}{2} \cos\left(n \frac{\pi}{2}\right) \right] + \frac{1}{n^{2}} \left[\sin (n \pi) - \sin \left(n \frac{\pi}{2}\right)\right] \right]\\
&= \frac{\pi}{2n} \cos\left(\frac{n \pi}{2}\right) - \frac{1}{n^{2}} \sin\left(\frac{n \pi}{2}\right)
\end{align*}
$$
$B_{n}$ bliver derfor:
$$
\frac{2}{\pi}\left(0.01\left(- \frac{\pi}{2n} \cos\left(n \frac{\pi}{2}\right)+ \frac{1}{n^{2}} \sin\left(\frac{n \pi}{2}\right) + \frac{\pi}{2n} \cos\left(\frac{n \pi}{2}\right) - \frac{1}{n^{2}} \sin\left(\frac{n \pi}{2}\right)\right)\right)
$$
$$
\frac{2}{\pi}\left( 0.01 \left(\cancel{- \frac{\pi}{2n} \cos\left(n \frac{\pi}{2}\right)}+ \cancel{\frac{1}{n^{2}} \sin\left(\frac{n \pi}{2}\right) }+ \cancel{\frac{\pi}{2n} \cos\left(\frac{n \pi}{2}\right)} - \cancel{\frac{1}{n^{2}} \sin\left(\frac{n \pi}{2}\right)}\right)\right)
$$
Da $f(x)$ er symmetrisk omkring $x = \frac{\pi}{2}$ og har en slags spejlingssymetri gør det af de to integraler bidrager med de t modsatte fortegn med samme størrelse. Dette gøre at der er en lige trekant over $(0, \pi)$ mens $\sin(nx)$ er ulige. Produktet $f(x) \cdot \sin(nx)$ bliver en funktion der er ulige over midten, og integralet af en ulige funktion over et symmetrisk interval er nul.

Dette betyder at strengen rent faktisk står stille og at der ikke er nogen vibration. Dette burde i præncippet ikke kunne ske fordi starthastigheden $f(x)$ ikke er 0, men gør fordi $f(x)$ er spejlsymmetrisk og $\sin(nx)$ er antisymmetrisk.

Rasmus får $B_{n}$:


$$
- \frac{2}{\pi} \cdot \frac{0.01\pi}{n} \cos(n \pi)
$$

Det burde ikke give 0?????
$$
\begin{align*}
\frac{2}{\pi} \left[0.01\left(- \frac{\pi}{2n} \cos\left(n \frac{\pi}{2}\right) + \frac{\pi}{2n} \cos\left(n \frac{\pi}{2}\right)\right)\right]
\end{align*}
$$
$$
B_{n} = \frac{0.02}{n^{3}\pi} \sin\left(\frac{n \pi}{2}\right)
$$
$$
u(x,t) = \sum_{n\,=\,1} ^ {\infty} \left(\frac{0.02}{n^{3}\pi} \sin\left(\frac{n \pi}{2}\right)\right) \frac{1}{n}\sin(nx) \sin(nt)
$$
$$
u(x,t) = \sum_{n\,=\,1} ^{\infty} \frac{0.02}{n^{4}\pi} \sin\left(\frac{n \pi}{2}\right) \sin(n x) \sin(nt)
$$
### Opgave 12.4.5
Using (13) sketch or graph a figure (similar to Fig. 291 in Sec. 12.3) of the deflection $u(x,t)$ of a vibrating string (length $L=1$, ends fixed, $c=1$) starting with initial velocity 0 and initial deflection (k small, say, k = 0.01).
$f(x) = k \sin(\pi x)$
Jeg starter med at indsætte $k=0.01$
$$
f(x) = 0.01 \sin(\pi x)
$$

Formel (13) ser sådan ud:
$$
u(x,t) = \frac{1}{2} [f(x+ct) + f(x-ct)]
$$
I opgaven er det givet at $c=1$:

$$
u(x,t) = \frac{1}{2} [0.01 \sin(\pi (x+ 1\cdot t)) + 0.01 \sin(\pi (x - 1\cdot t))]
$$

Opgaven går nu ud på at indsætte forskellige t-værdier og tegne dem.
Siden det er en sinus funktion starter funktionen i (0,0) 

$t=0$
$$
u(x,0) = \frac{1}{2} [0.01 \sin(\pi x) + 0.01 \sin(\pi x)] = 0.01 \sin(\pi x)
$$
$t=0.2$
$$
\begin{align*}
u(x,0.2) &=  \frac{1}{2} [0.01 \sin(\pi (x + 1\cdot 0.2)) + 0.01 \sin(\pi (x - 1 \cdot 0.2))]\\
\text{indsætter amplituden } x=0.5:\\
&= \frac{1}{2} [0.01 \sin(0.7\pi ) + 0.01 \sin(0.3 \pi)]\\
&=  \frac{1}{2} \cdot 0.01 \cdot 1.618 = 0.008090
\end{align*}
$$

$t=0.4$
$$
\begin{align*}
u(x,0.4) &=  \frac{1}{2} [0.01 \sin(\pi (x + 1\cdot 0.4)) + 0.01 \sin(\pi (x - 1 \cdot 0.4))]\\
\text{indsætter amplituden } x=0.5:\\
&= \frac{1}{2} [0.01 \sin(0.9\pi ) + 0.01 \sin(0.1 \pi)]\\
&=  \frac{1}{2} 0.01 \cdot 0.6180 = 0.003090
\end{align*}
$$

$t=0.6$
$$
\begin{align*}
u(x,0.6) &=  \frac{1}{2} [0.01 \sin(\pi (x + 1\cdot 0.6)) + 0.01 \sin(\pi (x - 1 \cdot 0.6))]\\
\text{indsætter amplituden } x=0.5:\\
&= \frac{1}{2} [0.01 \sin(1.1\pi ) + 0.01 \sin(-0.1 \pi)]\\
&=  \frac{1}{2}  \cdot 0.01 \cdot  (-0.618) = -0.003090
\end{align*}
$$

$t=0.8$
$$
\begin{align*}
u(x,0.8) &=  \frac{1}{2} [0.01 \sin(\pi (x + 1\cdot 0.8)) + 0.01 \sin(\pi (x - 1 \cdot 0.8))]\\
\text{indsætter amplituden } x=0.5:\\
&= \frac{1}{2} [0.01 \sin(1.3\pi ) + 0.01 \sin(-0.3 \pi)]\\
&=  \frac{1}{2} \cdot 0.01 \cdot  1.618 = 0.008090
\end{align*}
$$

$t=1$
$$
\begin{align*}
u(x,1) &=  \frac{1}{2} [0.01 \sin(\pi (x+1)) + 0.01 \sin(\pi (x-1))]\\
\text{Da } \sin(\pi+ \theta) &=  -\sin(\theta) \text{ og } \sin(\pi - \theta) = - \sin(\pi + \theta):\\
&= \frac{1}{2} [-0.01 \sin(\pi x) - 0.01 \sin(\pi x)]\\
&=  -0.01 \sin(\pi x)
\end{align*}
$$
![[05 opg 12.4.5.pdf]]