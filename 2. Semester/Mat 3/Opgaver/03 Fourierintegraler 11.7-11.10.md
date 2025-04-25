### Table over Fourier transforms
![[Table over Fourier transforms 1.png]]
![[Table over Fourier transforms 2.png]]
![[Table over Fourier transforms 3.png]]
$$
f_{L}(x) = a_{0} + \sum_{n \, = \, 1}^{\infty}(a_{n}\cos(w_{n}x) + b_{n}\sin(w_{n}x))
$$
$$w_{n}=\frac{n\pi}{L}$$ $$
\begin{align*}
A(w) &=  \frac{1}{\pi}\int_{-\infty}^{\infty}f(v) \, \cos(wv) \, dv\\
B(w) &=  \frac{1}{\pi}\int_{-\infty}^{\infty}f(v) \, \sin(wv) \, dv\\
f(x)&= \int_{0}^{\infty} [A(w) \, \cos(wx) + B(w) \, \sin(wx)] \, dw
\end{align*}
$$
### Dirichlet's discontinuous factor
$$
\begin{align*}
\int_{0}^{\infty} \frac{\sin(w)}{w}\, dw &=  \frac{\pi}{2}
\end{align*}
$$
Sine integraler:
Definition:
$$
Si(u) = \int_{0}^{u}\frac{\sin(w)}{w} \, dw, \quad \text{hvis } u\rightarrow \infty
$$
Fås:
$$
\int_{0}^{\infty}\frac{\sin(w)}{w}\, dw, \quad \text{ hvis } x=0
$$
$$
\begin{align*}
\int_{0}^{\infty}\frac{\sin(w) \cos(w)x}{w}\, dw = \cases{\frac{\pi}{2} \text{ hvis }0\leq x <1 \\\\
\frac{\pi}{4} \text{ hvis } x=1\\\\
0 \text{ hvis } x>1}
\end{align*}
$$
### Fourier integral trick
If a fourier integral representation is $even$, then $B(w) = 0$ in the formula:
$$
B(w) =  \frac{1}{\pi}\int_{-\infty}^{\infty}f(v) \, \sin(wv) \, dv\\
$$
Because the integrand of $B(w)$ is odd.
So then the formula:
$$
f(x)= \int_{0}^{\infty} [A(w) \, \cos(wx) + B(w) \, \sin(wx)] \, dw
$$
would be reduced to a Fourier cosine integral:
$$
A(w) =  \frac{2}{\pi}\int_{0}^{\infty}f(v) \, \cos(wv) \, dv
$$
Note that the change in $A(w)$ for even $f$ the integrand is even, hence the integral goes from $-\infty$ to $\infty$ equals twice the integral from 0 to $\infty$.

If $f$ has a Fourier integral representation and is $odd$ then $A(w)=0$, because the integrand of $A(w)$ is odd
So then the formula:
$$
f(x)= \int_{0}^{\infty} [A(w) \, \cos(wx) + B(w) \, \sin(wx)] \, dw
$$
would be reduced to a Fourier sine integral:
$$
B(w) =  \frac{2}{\pi}\int_{0}^{\infty}f(v) \, \sin(wv) \, dv
$$
Note the change of $B(w)$ to an integral from 0 to $\infty$ because $B(w)$ is even (odd times odd is even)

### Fourier cosine transform
even functions $f(x)$
$$
\begin{align*}
\hat{f_{c}} (w) &= \sqrt{\frac{2}{\pi}} \int_{0}^{\infty}f(x) \, \cos(wx) \, dx\\
f(x)&= \sqrt{\frac{2}{\pi}} \int_{0}^{\infty}\hat{f_{c}}(x) \, \cos(wx) \, dx\\
\end{align*}
$$
### Fourier sine transform
odd functions $f(x)$
$$
\begin{align*}
\hat{f_{s}} (w) &= \sqrt{\frac{2}{\pi}} \int_{0}^{\infty}f(x) \, \sin(wx) \, dx\\
f(x)&= \sqrt{\frac{2}{\pi}} \int_{0}^{\infty}\hat{f_{s}}(x) \, \sin(wx) \, dx
\end{align*}
$$
### Other notation for cosine and sine Fourier transforms
The notation can also be:
$$
\mathcal{F}_{c}(f) = \hat{f_{c}}, \quad \mathcal{F}_{s}(s) = \hat{f_{s}}
$$

### Cosine and sine Fourier transforms are linear operations
If $f$ and $g$ have Fourier transforms, so does $af+bg$ for any constants $a$ and $b$:
$$
\begin{align*}
\mathcal{F}_{c}(af+bg) &= a \mathcal{F}_{c}(f) + b \mathcal{F}_{c}(g)\\
\mathcal{F}_{s}(af+bg) &= a \mathcal{F}_{s}(f) + b \mathcal{F}_{s}(g)
\end{align*}
$$
### Cosine and sine transforms of derivatives
If you let $f(x)$ be continuous and absolutely integrable on the x-axis, let $f'(x)$ be piecewise continuous on every finite interval, and let $f(x) \rightarrow 0$ as $x \rightarrow \infty$ Then: 
$$
\begin{align*}
\mathcal{F}_{c}(f'(x)) &= w \mathcal{F}_{s}(f(x)) - \sqrt{\frac{2}{\pi}} f(0),\\
\mathcal{F}_{s}(f'(x)) &= -w \mathcal{F}_{c}(f(x)),\\
\mathcal{F}_{c}(f''(x)) &= -w^{2} \mathcal{F}_{c}(f(x)) - \sqrt{\frac{2}{\pi}} \, f'(0),\\
\mathcal{F}_{s}(f'(x)) &= -w^{2} \mathcal{F}_{s}(f(x))+ \sqrt{\frac{2}{\pi}} \, wf(0)\\
\end{align*}
$$
### Eulers formel
$$
e^{ix}=\cos(x)+i \sin(x)
$$
### Complex Fourier integral
$$
f(x) = \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty} \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} f(v)e^{iw (x-v)} \, dv \, dx, \quad (i=\sqrt{-1})
$$
Kan også skrives som:
$$
f(x) = \frac{1}{2\pi}\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(v)e^{iw (x-v)} \, dv \, dx, \quad (i=\sqrt{-1})
$$
$$
\mathcal{F} = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} e^{-iwx} f(v) \, dv
$$
(Minder lidt om Laplace transformation:
$$
\mathcal{L} = \int_{0}^{\infty}e^{-st} f(t) \, dt
$$
)

#### Example 1:
I bogen står der 
$$
\begin{align*}
\mathcal{F}(f(x))&= \frac{1}{\sqrt{2\pi}} \int_{-1}^{1}1 \cdot e^{iwx} \, dx\\
&= \frac{1}{-iw \sqrt{2 \pi}} [e^{-iwx}]_{-1}^{1}\\
&= \frac{1}{-iw \sqrt{2 \pi}} (e^{-iw} - e^{iw})\\
&= \frac{1}{-iw \sqrt{2 \pi}} (\cos(-w) + i \sin(-w) - (\cos(w) + i \sin(w)))\\
&= \frac{1}{-iw \sqrt{2 \pi}} (\cos(w) - i \sin(w) - \cos(w) - i \sin(w)) \\
&= \frac{-2i \sin (w)}{ \sqrt{2 \pi}}\\
&=  2 \sin\frac{w}{w \sqrt{2\pi}} = \frac{\sqrt{2}\cancel{\sqrt{2}} \sin(w)}{w \cancel{\sqrt{2}} \sqrt{\pi}}\\
&= \sqrt{\frac{2}{\pi}} \cdot \frac{\sin(w)}{w}\\
\end{align*}
$$
I bogen står der i stedet at svaret er:
$$
\sqrt{\frac{\pi}{2}} \cdot \frac{\sin(w)}{w}\\
$$
Hvilket er forkert.
### Fourier transform and its inverse
$$
\begin{align*}
\hat{f(w)} &=  \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty}f(x)e^{-iwx} \, dx\\
f(x) &= \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} \hat{f}(w)e^{iwx} \, dw
\end{align*}
$$
### Fourier transform of the derivative of f(x) (complex)
$$
\begin{align*}
\mathcal{F}(f'(x)) &=  iw \mathcal{F}(f(x))\\
\mathcal{F}(f''(x)) &= -w^{2} \mathcal{F}(f(x))
\end{align*}
$$
### Convolution
$$
h(x) = (f*g)(x) = \int_{-\infty}^{\infty}f(p)g(x-p)\, dp = \int_{-\infty}^{\infty}f(x-p)g(p) \, dp
$$
The purpose is the same as in the case of Laplace transforms: Taking the
convolution of two functions and then taking the transform of the convolution is the same
as multiplying the transforms of these functions (and multiplying them by $\sqrt{2\pi}$)
$$
\mathcal{F}(f*g)=\sqrt{2\pi} \, \mathcal{F}(f) \, \mathcal{F}(g)
$$
$$
(f*g)(x) = \int_{-\infty}^{\infty}\hat{f}(w) \, \hat{g}(w) \, e^{iwx} \, dw
$$
### Discrete Fourier transform
The frequency spectrum of the signal is given by:
$$
\hat{f}_{n}= Nc_{n}= \sum_{k \, = \, 0} ^{N-1} f_{k}e^{-inx_{k}}, \quad f_{k}=f(x_{k}), \, n=0,\, \dots, \, N-1
$$
## Opgaver
### 11.7.7
Represent $f(x)$ as an integral
$$
\begin{align*}
f(x) = \int_{0}^{\infty}A(w) \, \cos(wx) \, dw\\
A(w) =  \frac{2}{\pi}\int_{0}^{\infty}f(v) \, \cos(wv) \, dv
\end{align*}
$$
$$
f(x) = \cases{1 \text{ if } & 0 < x < 1\\ 0 \text{ if } & x>1}
$$
$$
\begin{align*}
A(w) &=  \frac{2}{\pi} \int_{0}^{1} f(v) \cos(wv) \, dv\\
\int \cos(wv) \, dv &= \frac{\sin(wv)}{w}\\
\frac{2}{\pi}\left[\frac{\sin(wv)}{w}\right]_{0}^{1} &= \frac{2}{\pi} \frac{\sin(w)}{w}-\frac{\sin(0)}{w}\\
&= \frac{2}{\pi} \frac{\sin(w)}{w}\\
\text{Substituerer i f(x):}\\
f(x)&= \int_{0}^{\infty} \frac{2}{\pi} \frac{\sin(w)}{w} \cos(wx) \, dw\\
\int_{0}^{\infty} \frac{2}{\pi} \frac{\sin(w)}{w} \cos(wx) \, dw &= \frac{\pi}{2}, \quad 0>x>1
\end{align*}
$$

### 11.7.17
Represent $f(x)$ as an integral
$$
\begin{align*}
f(x) = \int_{0}^{\infty}B(w) \, \sin(wx) \, dw\\
B(w) =  \frac{2}{\pi}\int_{0}^{\infty}f(v) \, \sin(wv) \, dv
\end{align*}
$$
$$
f(x) = \cases{1 \text{ if } & 0 < x < 1\\ 0 \text{ if } & x>1}
$$

$$
\begin{align*}
B(w) &=   \frac{2}{\pi}\int_{0}^{1}f(v) \, \sin(wv) \, dv\\
\int \sin(wv) \, dv &= \frac{-\cos(wv)}{w}\\
\frac{2}{\pi} \left[\frac{-\cos(wv)}{w}\right]_{0}^{1} &= \frac{2}{\pi}- \frac{\cos(1)}{w} + \frac{\cos(0)}{w}\\
\text{Da } \cos(0)&= 1:\\
&= \frac{2}{\pi}\frac{-\cos(w)}{w} + \frac{1}{w}\\
&= \frac{2}{\pi} \frac{1-\cos(w)}{w}\\
f(x)&= \int_{0}^{\infty} \frac{2}{\pi} \frac{1-\cos(w)}{w} \sin(wv) \, dw, \quad 0<x<1
\end{align*}
$$

### 11.9.3
**Fourier transforms by integration**.
Find the Fourier transform of $f(x)$ (without using table III in Sec. 11.10) Show the details.
$$
f(x)=\cases{1 \text{ if } a<x<b \\ 0 \text{ otherwise}}
$$

$$
\begin{align*}
\int_{-\infty}^{\infty}f(x) e^{-iwx} \, dx\\
\mathcal{F} (w) &=  \int_{a}^{b} e^{-iwx} \, dx\\
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
### 11.9.5
Svaret burde være:
$$
[e ^{(1-iw)a} - e ^{(-1-iw)a}] / (\sqrt{2\pi}(1-iw))
$$