Find Fourierkoefficienterne og Fourierrækken for firkant-signalet defineret som
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
&= 
\end{align*}
$$


Løsning:
$$
f(x) = \frac{1}{2} + \sum_{n = 1,3,5, \dots} \frac{2}{n \pi} \sin(n \pi x)
$$
