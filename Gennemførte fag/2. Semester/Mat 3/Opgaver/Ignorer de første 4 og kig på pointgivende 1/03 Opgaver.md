### 11.7.7 Represent $f(x)$ as a fourier cosine integral
Represent $f(x)$ as a fourier cosine integral
$$
f(x) = \cases{1 \text{ if } & 0 < x < 1\\ 0 \text{ if } & x>1}
$$
Jeg bruger formlerne:
$$
\begin{align*}
f(x) = \int_{0}^{\infty}A(w) \, \cos(wx) \, dw\\
A(w) =  \frac{2}{\pi}\int_{0}^{\infty}f(v) \, \cos(wv) \, dv
\end{align*}
$$
Jeg skal altså starte med at finde $A(w)$ så jeg derefter kan indsætte det i funktionen for $f(x)$. Jeg starter med at indsætte de givede grænser i integralet brugt til at udregne $A(w)$:
$$
\begin{align*}
A(w) &=  \frac{2}{\pi} \int_{0}^{1} f(v) \cos(wv) \, dv\\
\int \cos(wv) \, dv &= \frac{\sin(wv)}{w}\\
\frac{2}{\pi}\left[\frac{\sin(wv)}{w}\right]_{0}^{1} &= \frac{2}{\pi} \frac{\sin(w)}{w}-\frac{\sin(0)}{w}\\
&= \frac{2}{\pi} \frac{\sin(w)}{w}\\
\text{Substituerer i f(x):}\\
f(x)&= \int_{0}^{\infty} \frac{2}{\pi} \frac{\sin(w)}{w} \cos(wx) \, dw\\
f(x)&= \frac{2}{\pi} \int_{0}^{\infty} \frac{\sin(w)}{w} \cos(wx)\\
f(x) &= \cases{\frac{2}{\pi} \int_{0}^{\infty} \frac{\sin(w)}{w} \cos(wx), \quad &0<x<1,\\ 0, \quad &x>1}
\end{align*}
$$
Dette er så svaret, da jeg skulle vise $f(x)$ som et fourierintegrale.
### 11.7.17 Represent $f(x)$ as a fourier sine integral
Represent $f(x)$ as a fourier sine integral
$$
f(x) = \cases{1 \text{ if } & 0 < x < 1\\ 0 \text{ if } & x>1}
$$
Jeg bruger formlerne:
$$
\begin{align*}
f(x) = \int_{0}^{\infty}B(w) \, \sin(wx) \, dw\\
B(w) =  \frac{2}{\pi}\int_{0}^{\infty}f(v) \, \sin(wv) \, dv
\end{align*}
$$

Jeg skal altså starte med at finde $B(w)$ så jeg derefter kan indsætte det i funktionen for $f(x)$. Jeg starter med at indsætte de givede grænser i integralet brugt til at udregne $B(w)$:
$$
\begin{align*}
B(w) &=   \frac{2}{\pi}\int_{0}^{1}f(v) \, \sin(wv) \, dv\\
\int \sin(wv) \, dv &= \frac{-\cos(wv)}{w}\\
\frac{2}{\pi} \left[\frac{-\cos(wv)}{w}\right]_{0}^{1} &= \frac{2}{\pi}- \frac{\cos(1)}{w} + \frac{\cos(0)}{w}\\
\text{Da } \cos(0)&= 1:\\
&= \frac{2}{\pi}\frac{-\cos(w)}{w} + \frac{1}{w}\\
&= \frac{2}{\pi} \frac{1-\cos(w)}{w}\\
f(x)&= \int_{0}^{\infty} \frac{2}{\pi} \frac{1-\cos(w)}{w} \sin(wv) \, dw\\
f(x)&= \frac{2}{\pi} \int_{0}^{\infty} \frac{1-\cos(w)}{w} \sin(wv) \, dw\\
f(x) &= \cases{\frac{2}{\pi} \int_{0}^{\infty} \frac{1-\cos(w)}{w} \sin(wv) \, dw, \quad &0<x<1,\\ 0, \quad &x>1}
\end{align*}
$$
Dette er så svaret, da jeg skulle vise $f(x)$ som et fourierintegrale.

### 11.9.3 **Fourier transforms by integration**. Find the Fourier transform of $f(x)$ (without using table III in Sec. 11.10) Show the details.
**Fourier transforms by integration**.
Find the Fourier transform of $f(x)$ (without using table III in Sec. 11.10) Show the details.
$$
f(x)=\cases{1 \text{ if } a<x<b \\ 0 \text{ otherwise}}
$$
Jeg bruger formlen:
$$
\begin{align*}
\int_{-\infty}^{\infty}f(x) e^{-iwx} \, dx\\
\mathcal{F} (w) &=  \int_{a}^{b} e^{-iwx} \, dx\\
\int e ^{-iwx}\, dx &= \frac{e^{-iwx}}{-iw}\\
&= \left[\frac{e^{-iwx}}{-iw}\right]_{a}^{b}\\
&= \frac{e^{-iwb} - e^{-iwa}}{-iw}\\
\text{Da bogen bruger faktoren } \frac{1}{\sqrt{2 \pi}}:\\
&= \frac{e^{-iwb} - e^{-iwa}}{-iw \sqrt{2 \pi}}\\
\end{align*}
$$
Bogen har skrevet det på en lidt anderledes måde hvor den bruger at:
$$
\begin{align*}
e^{-iwb} - e^{-iwa}=-(e^{-iwa} + e^{-iwb})\\
&= \frac{(e^{-iwa} + e^{-iwb})}{-iw}\\
\text{Siden } i=\sqrt{-1}\\
\frac{1}{i}=-i\\
\frac{-1}{i}=i\\
&= \frac{i(e^{-iwa} - e^{-iwb})}{w}\\
\text{Og så med faktoren } \frac{1}{2\pi}:\\
&= \frac{i(e^{iwb} - e^{iwa})}{w \sqrt{2\pi}}\\
\end{align*}
$$
### 11.9.5 Find the Fourier transform of $f(x)$ (without using table III in Sec. 11.10) Show the details.
Find the Fourier transform of $f(x)$ (without using table III in Sec. 11.10) Show the details.
$$
f(x) = \cases{e^{x}, \quad \text{ if } -a <x < a, \\ 
0, \quad \text{ otherwise}}
$$
Jeg bruger formlen:
$$
\begin{align*}
\int_{-\infty}^{\infty}f(x) e^{-iwx} \, dx\\
\mathcal{F} (w) &= \int_{a}^{b} e^{x} e^{-iwx} \, dx\\
I assume I now have to use integration by parts?
\int e ^{-iwx}\, dx &= \frac{e^{-iwx}}{-iw}\\
&= \left[\frac{e^{-iwx}}{-iw}\right]_{a}^{b}\\
&= \frac{e^{-iwb} - e^{-iwa}}{-iw}\\
\text{Fjerner minus i nævneren}:\\
e^{-iwb} - e^{-iwa}=-(e^{-iwa} - e^{-iwb})\\
&= \frac{(e^{-iwa} - e^{-iwb})}{-iw}\\
\text{Siden } i=\sqrt{-1}\\
\frac{1}{i}=-i\\
\frac{-1}{i}=i\\
&= \frac{i(e^{-iwa} - e^{-iwb})}{w}\\
\text{Da } e^{-i\theta}&= \frac{1}{e^{i\theta}}:\\
&= \frac{i(e^{iwb} - e^{iwa})}{w}\\
\text{Da bogen bruger faktoren } \frac{1}{\sqrt{2 \pi}}:\\
&= \frac{i(e^{iwb} - e^{iwa})}{w \sqrt{2\pi}}
\end{align*}
$$

Svaret burde være:
$$
[e ^{(1-iw)a} - e ^{(-1-iw)a}] / (\sqrt{2\pi}(1-iw))
$$