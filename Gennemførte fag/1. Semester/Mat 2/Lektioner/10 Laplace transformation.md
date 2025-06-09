Man bruger det til at løse lineære ordinære differentialligninger med begyndelsesbetingelser. 
Ordinære differentialligninger (ODE).
Det kaldes for IVP (Initial Value Problems), hvilket kan oversættes til begyndelsesværdiproblemer.
Det er et tidsdomæne.
Man laver en laplace transformation $\mathcal{L}$ fra tidsdomæne til s-domæne og løser et algebraisk problem, hvorefter man laver en transformation tilbage til tidsdomænet $\mathcal{L}^{-1}$. 
## Definition:
$f(t), t \geq 0$ 
$$
F(s)=\mathcal{L}(f)=\int_{0}^{\infty}f(t)\cdot e^{-st}\space dt
$$
$$
f(t)=\mathcal{L}^{-1}(F(s))
$$
F(s) er den laplace transformeret af s,
$\mathcal{L}^{-1}(F(s))$ er den inverse laplace transformeret af s.

eksempel:
$$
\begin{align*}
f(t)&= 1\\
t\geq 0\\
\mathcal{L}(f)&= \int_{0}^{\infty}1\cdot e^{-st}\space dt\\
&= \lim_{T\rightarrow \infty}\int_{0}^{T}e^{-st}\space dt\\
&= \lim_{T\rightarrow \infty}\left[e^{-st}\space \right]_{0}^{T} dt\\
&= \lim_{T\rightarrow \infty}-\frac{1}{s}(e^{-sT}-1)\\
&= \frac{1}{s}
\end{align*}
$$
## Sætning for linearitet
f, g funktioner
a, b konstanter
$$
\mathcal{L}(a\cdot f(t)+b\cdot g(t)) = a\cdot \mathcal{L}(f)+b \cdot \mathcal{L}(g)
$$
Eksempel:
$$
\begin{align*}
\mathcal{L}(2+t)&= 2\mathcal{L}(1)+\mathcal{L}(t)\\
\mathcal{L}(t)&= \int_{0}^{\infty}t\cdot e^{-st}\space dt\\
\\
\int uv'&= uv-\int u'v\space \text{partiel}\\
u&= t,\space u'=1\\
v'&= e^{-st},\space v=-\frac{1}{s}e^{-st}\\
\\
&= \left[-\frac{1}{s}t\cdot e^{-st}\right]_{0}^{\infty}-\int^{\infty}_{0}-\frac{1}{s}e^{-st}\space dt\\
&= -\frac{1}{s}\underbrace{\lim_{t\rightarrow \infty}\frac{t}{e^{st}}}_{\rightarrow 0}+\int^{\infty}_{0}e^{-st}\space dt\\
&= \frac{1}{s^{2}}\\
& \text{Så}\space \mathcal{L}(t)=\frac{1}{s^{2}}\\
& \text{mens}\space 2\mathcal{L}(1)=2\cdot \frac{1}{s}\\
&= 2\cdot \frac{1}{s}+\frac{1}{s^{2}}
\end{align*}
$$
## Sætning:
f(t) har F(s), eksisterer for $s>k$ 
$$
\begin{align*}
\mathcal{L}\left(e^{at} f(t)\right)&= F(s-a), \text{eksisterer for}\space s-a>k\\
\mathcal{L}^{-1}\left(F(s-a)\right)&= e^{at} f(t)\\
\end{align*}
$$
## Sætning om eksistens af laplace transformation "Growth restriction".
$$
\begin{align*}
f(t)\space \text{stykvis kontinuert for}\space  t\geq 0\\
\text{og}\space \left|f(t)\right| \leq Me^{kt},\space \text{hvor M,k er konstanter}\\
\mathcal{L}(f)\space \text{eksisterer for alle}\space  s>k\\
\text{f.eks. hvis man havde en funktion}\space e^{t^{2}}, \\
\text{så ville den vokse for meget, og så ville}\space  \left|f(t)\right|\geq Me^{kt}\\
\text{hvilket man ikke kunne løse}
\end{align*}
$$
$f(t), t\geq 0$
$$
\begin{align*}
\mathcal{L}\left(f'(t)\right)&= s\cdot\mathcal{L}(f)-f(0)\\
\mathcal{L}\left(f''(t)\right)&= s^{2}\cdot \mathcal{L}(f)-sf(0)-f'(0)\\
\mathcal{L}\left(f^{(n)}(t)\right)=s^{n}\cdot \mathcal{L}(f)-s^{n-1}f(0)-s^{n-2}f(0)-...f^{(n-1)}(0)
\end{align*}
$$
## Laplace transformation af integraler
$f(t), t\geq 0$
$F(s)$ for $s>k$
$$
\begin{align*}
\mathcal{L}\left(\int^{t}_{0}f(\tau)\space d\tau \right)&= \frac{1}{s}\cdot F(s)
\end{align*}
$$
## Eksempel med løsning af differentialligning:
$$
\begin{align*}
y'(t)+y(t)&= 9\cdot e^{2t},\space \text{hvor}\space  y(0)=3\\
\mathcal{L}\left(y'+y\right)&= \mathcal{L}\left(9\cdot e^{2t}\right)\\
sY(s)-y(0)+Y(s)&= 9\cdot \frac{1}{s-2}\\
\text{kig lige på tabel}\\
Y(s)(s+1)&= \frac{9}{s-2}+3\\
&= \frac{9+3(s-2)}{s-2}\\
Y(s)&= \frac{9+3s-6}{(s+1)(s-2)}\\
&= \frac{3\cancel{(s+1)}}{\cancel{(s+1)}(s-2)}\\
&= \frac{3}{s-2}\\
y(t)&= \mathcal{L}^{-1}\left(Y(s)\right) = 3\cdot e^{2t}
\end{align*}
$$
## Tabel over Laplace regneregler
![[Laplace tabel regneregler.png]]

| Tabel      |                        |
| ---------- | ---------------------- |
| f          | F                      |
| $$e^{at}$$ | $$\frac{1}{s-a}$$      |
| $$t^{n}$$  | $$\frac{n!}{s^{n+1}}$$ |
| 1          | $$\frac{1}{s}$$        |
| t          | $$\frac{1}{s^{2}}$$    |
Eksempel:
$$
\begin{align*}
y''(t)-y(t)&= -t^{2},\space \text{hvor} \space y(0)=2, \space y'(0)=0\\
\mathcal{L}(y''-y)&= \mathcal{L}(-t^{2})\\
s^{2}Y(s)-\underbrace{sy(0)}_{2}-\cancel{y'(0)}-Y(s)&= \frac{-2}{s^{3}}\\
Y(s)(s^{2}-1)=\frac{-2}{s^{3}}+2s&= \frac{-2+2s^{4} }{s^{3}}\\
Y(s)&= \frac{-2+s^{4}}{(s^{2}-1)s^{3}}\\
&= \frac{2(s^{4}-1)}{(s^{2}-1)s^{3}}\\
&= \frac{2(s^2+1)\cancel{(s^2-1)}}{\cancel{(s^2-1)}s^{3}}\\
&= \frac{2s^{2}}{s^{3}}+\frac{2}{s^{3}}\\
&= \frac{2}{s}+\frac{2}{s^{3}}\\
y(t)=\mathcal{L}^{-1}\left(\frac{2}{s}+\frac{2}{s^{3}}\right)&= 2\cdot 1+t^{2}
\end{align*}
$$
## Unit step
Se tegning 1:
$$
\begin{align*}
\mathcal{L}\left(u(t-a)\right)&= \int^{\infty}_{0}u(t-a)\cdot e^{-st}\space dt\\
&= \int^{\infty}_{0}e^{-st}\space dt\\
&= \left[\frac{-1}{s}\cdot e^{-st}\right]_{a}^\infty \\
&= \frac{1}{s}\left(0-e^{-as}\right)=\frac{e^{-as}}{s}
\end{align*}
$$
Se tegning 2:
## Sætning:
$f(t), \space F(s)$
$$
\mathcal{L}\left(f(t-a)\cdot u(t-a)\right)=e^{-as}\space F(s)
$$
## Eksempel:
$$
\mathcal{L}^{-1}\left(\frac{e^{-3s}}{s^{2}}\right)=(t-3)\cdot u(t-3)\\
$$
## Eksempel med Dirac delta
Her er parenteserne der ligner matricer bare en start tuborgklamme {.
$$
\begin{align*}
f_{k}(t-a)&= \begin{pmatrix}\frac{1}{k},a\leq t \leq a+k \\ 0,\space  \text{ellers}\end{pmatrix}\\
\delta(t-a)&= \lim_{k\rightarrow 0}f_{k}(t-a)\\
\text{Se tegning 3:}\\
A&= \int^{\infty}_{0}f_{k}(t-a)\space dt=1\\
\text{Bemærk:}\space \int^{\infty}_{0}g(t)\space \delta(t-a)\space dt&= g(a)\\
\text{her er g(a) funktionsværdien lige inden grænsen}\space \infty\\
\delta (t-a)&= \begin{pmatrix}\infty,\space t=a\\
0,\space ellers\end{pmatrix}\space \text{og} \int^{\infty}_{0}\delta(t-a)\space dt=1\\
\end{align*}
$$
$$
\begin{align*}\\
\mathcal{L}\left(f_{k}(t-a)\right)&= \int^{a+k}_{a}\frac{1}{k}e^{-st}\space dt\\
&= \frac{1}{k}\left[-\frac{1}{s}e^{-st}\right]^{a+k}_{a}\\
-\frac{1}{sk}\left(e^{-s(a+k)}-e^{-as}\right)&= -\frac{1}{sk}e^{-as}\left(e^{-sk}-1\right)\\
\lim_{k\rightarrow 0}e^{-as}\frac{1-e^{-sk}}{-sk}\rightarrow \frac{0}{0}\\
&= \lim_{k\rightarrow 0} e^{-as}\frac{0-(-s)e^{-sk}}{s}\\
&= \lim_{k\rightarrow 0} e^{-as}\frac{se^{-sk}}{s}\\
&= e^{-as}\\
\mathcal{L}\left(\delta (t-a)\right)&= e^{-as}
\end{align*}
$$



