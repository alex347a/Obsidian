### 1.1 Find Fourierkoefficienterne og Fourierrækken for firkant-signalet defineret som
$$
f(x) = \cases{0 \quad \text{hvis } - 1 \leq x \leq 0 \\ 1 \quad \text{hvis } 0 \leq x \leq 1}
$$
og
$$
f(x+2) = f(x)
$$
Den generelle formel er givet ved:
$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1} ^{\infty} \left[a_{n} \cos\left(\frac{n \pi x}{L}\right) + b_{n} \sin\left(\frac{n \pi x}{L}\right)\right]
$$
Idet jeg får givet at:
$$
f(x+2) = f(x)
$$
Så betyder det at perioden $2L = 2$
Dernæst kan jeg beregne konstantleddende:
$$
\begin{align*}
a_{0} &=  \frac{1}{L} \int_{-L}^{L} f(x) \, dx\\
a_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx\\
b_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx
\end{align*}
$$

$$
\begin{align*}
a_{0} &=  \frac{1}{L} \int_{-L}^{L} f(x) \, dx\\
a_{0} &= \frac{1}{1} \int_{-1} ^{1} f(x) \, dx\\
\text{Da } -1 \text{ er udenfor intervallet 0 til 1}:\\
= \int_{0}^{1} 1 \, dx &=  1
\end{align*}
$$
$$
\begin{align*}
a_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx\\
a_{n} &= \frac{1}{1} \int_{0} ^{1} 1 \cdot \cos\left(\frac{n \pi x }{1}\right) \, dx\\
&=  \int_{0}^{1} \cos(n \pi x)\\
&= \left[\sin \left(\frac{n \pi x}{n \pi}\right)\right]_{0}^{1}\\
= \left[\sin \left(\frac{n \pi x}{n \pi}\right)\right]_{0}^{1} &= 0 \text{ for alle n-værdier}
\end{align*}
$$
$$
\begin{align*}
b_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx\\
b_{n} &= \frac{1}{1} \int_{0} ^{1} 1 \cdot \sin\left(\frac{n \pi x }{1}\right) \, dx\\
&=  \int_{0}^{1} \sin(n \pi x)\\
&= \left[-\cos \left(\frac{n \pi x}{n \pi}\right)\right]_{0}^{1}\\
&= - \frac{\cos(n \pi)}{n \pi} - \frac{\cos(0)}{n \pi}\\
&= \frac{1 - \cos(n \pi)}{n \pi}
\end{align*}
$$
Da:
$$
\cos(n \pi) = (-1) ^{n}
$$
$$
\frac{1 - (-1)^{n}}{n \pi}
$$
For lige n giver det 0.
For ulige n:
$$
b_{n} = \frac{2}{n \pi}
$$
Dermed bliver Fourierrækken givet ved:

$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1} ^{\infty} \left[a_{n} \cos\left(\frac{n \pi x}{L}\right) + b_{n} \sin\left(\frac{n \pi x}{L}\right)\right] = \frac{1}{2} + \sum_{n=1} ^{\infty} b_{n} \sin(n \pi x)
$$
$$
f(x) = \frac{1}{2} + \sum_{n = 1, 3, 5, \dots} ^{\infty} \frac{2}{n \pi} \sin(n \pi x)
$$
Hvilket passer med svaret i bogen.

### 1.2 Fouriertransformation. Enhedstrinfunktionen er defineret som
$$
u(t-a) = \cases{1 \quad \text{ for } t- a > 0 \\ 0 \quad \text{ for } t -a <0} 
$$
Benyttes til at definere en firkantimpuls:
$$
x(t) = u(t-a) - u(t-b)
$$
hvor $a<b$

#### 1. Tegn grafen for firkantimpulsen $x(t)$
#### 2. Udregn den Fouriertransformerede af $x(t)$
Den Fouriertransformerede af en funktion $x(t)$ er defineret som:
$$
X(\omega) = \int_{-\infty} ^{\infty} x (t) e^{-j \omega t} \, dt
$$
Jeg indsætter udtrykket for $x(t)$ i formlen ovenfor:
$$
X(\omega) = \int_{-\infty} ^{\infty} [u(t-a) - u(t-b)] e^{-j \omega t} \, dt
$$
Dette kan deles op i to integraler:
$$
X(\omega) = \int_{-\infty} ^{\infty} u(t-a) \cdot e^{-j \omega t} \, dt - \int_{-\infty} ^{\infty} u(t-b) \cdot e ^{-j \omega t} \, dt
$$
For enhedstrinfunktionen gælder det at:
$$
\int_{-\infty}^{\infty} u(t-c) \cdot e^{-j \omega t} \, dt = \int_{c} ^{\infty} e^{- j \omega t} \, dt
$$

$$

$$

Diracs deltafunktion: $\delta(ω)$ er en distribution med egenskaberne:
$$
\begin{align*}
\delta(\omega) = 0 \text{ for } \omega &\neq 0\\
\int_{-\infty}^{\infty} \delta(\omega) d \omega &= 1\\
\int_{-\infty}^{\infty} f(\omega) \delta(\omega) \, d \omega &= f(0) \quad (\text{udpluksegenskab})
\end{align*}
$$
Fouriertransformationen af $u(t-c)$:
$$
\mathcal{F} [u (t-c)] (\omega) = \frac{e^{-j \omega c}}{{j \omega}} + \pi \delta(\omega)
$$
Givet at $x(t) =  u(t-a) - u(t-b)$
$$
\mathcal{F}  [u(t-a) - u(t-b)] (\omega) = \mathcal{F}(u(t-a)(\omega) - \mathcal{F} (t-b) (\omega)
$$
$$
\begin{align*}
\mathcal{F}(u(t-a)(\omega) - \mathcal{F} (t-b) (\omega) &=  \left[\frac{e^{-j \omega a}}{{j \omega}} + \pi \delta(\omega)\right] - \left[ \frac{e^{-j \omega b}}{{j \omega}} + \pi \delta(\omega)\right]\\
&= \frac{e^{-j \omega a}}{{j \omega}} \cancel{+\pi \delta(\omega)} - \frac{e^{-j \omega b}}{{j \omega}} \cancel{-\pi \delta(\omega)}\\
&= \frac{e^{-j \omega a}}{{j \omega}} - \frac{e^{-j \omega b}}{{j \omega}}\\
&= \frac{e^{-j \omega a} - e^{-j \omega b}}{{j \omega}} 
\end{align*}
$$
Hvilket passer med svaret i bogen.