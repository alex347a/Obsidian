s. 557
## En dimensional varmeledningsligning
$$
\frac{\delta u }{\delta t } = c^{2}\frac{\delta^{2} u}{\delta t^{2}}
$$
![[06 Lektionsnoter.pdf]]

### steady-state situation:
![[06 Lektionsnoter.pdf#page=2]]


## Vi ser på løsningen: $u(x,t) = X(x) T(t)$:
$$
\begin{align*}
\frac{\delta u}{\delta x}= X'(x)T(t)\\
\frac{\delta^{2} u}{\delta x^{2}}= X''(x)T(t)\\
\frac{\delta u}{\delta t}= X(x)T'(t)\\
\end{align*}
$$
#### Substitution:
$$
\begin{align*}
XT' &=  c^{2}X''T\\
\frac{X''}{X}&=  \frac{1}{c^{2}}\frac{T'}{T}\\
\text{Da de to funktioner er uafhængige:}\\
\frac{X''}{X}&=  \frac{1}{c^{2}}\frac{T'}{T} = k\\
\frac{X''}{X} = k, \quad \text{ og } \quad \frac{1}{c^{2}} \frac{T'}{T}&= k\\
X''-kX= 0 \quad \text{ og } \quad T'-kc^{2}T &=  0\\
\text{sætter } k &=  -p^{2} \quad \text{ (k er negativ)}\\
X''+p^{2}X = 0, \quad \text{ og } \quad T'+p^{2}c^{2}T&= 0\\
u(x,t) &= (A_{1} \cos(px) + A_{2} \sin(px)) e^{-(pc)^{2}t}
\end{align*}
$$
Løsningen beskriver den relative ændring og ikke den absolutte værdi.

### Starttemperaturprofil 
![[06 Lektionsnoter.pdf#page=4]]
![[06 Lektionsnoter.pdf#page=5]]
#### Randbetingelser
$$
u(0,t) = 0 \celsius = (A_{1} \underbrace{\cos(0)}_{1}\underbrace{ A_{2} \sin(0)}_{0}) e^{-(pc)^{2}t} \rightarrow A_{1}= 0
$$
$$
\begin{align*}
u(x_{1},t) &=  A_{1}\sin (px) e^{-(pc)^{2}t}\\
u(l,t) &= 0, \quad = A \underbrace{\sin(p l)}_{0} e^{-(pc)^{2}t}\\
\sin(pl) = 0, \quad pl = n \pi \rightarrow p &=  \frac{n \pi}{l}\\
u_{n}(x_{1},t) &= A_{n} \sin\left(\frac{n \pi}{l}\right) x \cdot e^{-(pc)^{2}t}\\
u(x_{1},t) &= \sum_{n \, = \, 1} ^{\infty} A_{n} \sin\left(\frac{n \pi}{l}\right) x \cdot e^{-(pc)^{2}t}\\
\text{husk at } p&= \frac{n \pi}{l} \text{ i svaret ovenover}\\
\text{indsætter startbetingelsen:}\\
u(x,0) = \sum_{n \, = \, 1} ^{\infty} A_{n} \sin\left(\frac{n \pi}{l}\right) x = f(x), \text{ hvor } A_{n}&=  \frac{2}{l}\int_{0}^{l} f(x) \sin\left(\frac{n \pi}{l}\right)x \, dx
\end{align*}
$$
Der er et eksempel på s. 562
![[Fig 295 s. 562.png]]

## Kapitel 9 Vektorer
$$
\vec{a} = (a_{1}, a_{2}) = a_{1}\vec{i} + a_{2}\vec{j}
$$
![[06 Lektionsnoter.pdf#page=6]]

#### 3 dimensioner
$\vec{a} = (a_{1}, a_{2}, a_{3})$

#### Regneregler
plus $+$
minus $-$
prikke $\cdot$ 

![[06 Lektionsnoter.pdf#page=7]]

Man kan godt gange vektorer hvis man transponere den ene:
$$
\vec{a} \cdot \vec{b} = \vec{a^{T}} \vec{b}
$$
$$
(a_{1}a_{2} a_{3}) \begin{pmatrix}b_{1} \\ b_{2} \\ b_{3}\end{pmatrix}
$$
#### Krydsprodukt
$$
a \times b = \begin{bmatrix}\vec{i} &  \vec{j}  & \vec{k} \\ a_{1} & a_{2} & a_{3} \\ b_{1} & b_{2} & b_{3}\end{bmatrix} = (a_{2} b_{3} - a_{3}b_{2}) \vec{i} - (a_{1}b_{3}- a_{3}b_{1}) \vec{j} + (a_{1}b_{2} - a_{2}b_{1}) \vec{k}
$$

![[06 Lektionsnoter.pdf#page=8]]
## Vektorfelt
$$
\vec{v} = (-y, x)
$$
![[06 Lektionsnoter.pdf#page=9]]
Se figuren:
![[Fig 197 s. 377.png]]

#### Niveaukurver (højdekurver)
Eks. 
$$
f(x,y) = 100- x^{2} - y^{2} \quad \text{ paraboloide}
$$
![[06 Lektionsnoter.pdf#page=10]]

gradienten:

$$
f = \nabla f = \begin{pmatrix}\frac{\delta f}{\delta x} \\ \frac{\delta f}{\delta y}\end{pmatrix} = \begin{pmatrix}-2x \\ -2y\end{pmatrix} \text{ eller } - \nabla f= \begin{pmatrix}2x \\ 2y\end{pmatrix}
$$
Sætning 2 s. 399: Gradienten står altid vinkelret på niveaukurven/niveaufladen (i så fald vil man få en normalvektor til fladen).
![[06 Lektionsnoter.pdf#page=11]]

Eksempel:
conus (snurretop)
![[06 Lektionsnoter.pdf#page=12]]
$$z^{2} = 4(x^{2}+ y^{2})$$
$$
f(x,y,z) = f(x^{2}+y^{2}) - z^{2} = 0
$$
$$
\nabla f = (8x, 8y, -2z)
$$
#### Kædereglen
Eks s. 394
![[06 Lektionsnoter.pdf#page=13]]

$$
w = x^{2}- y^{2}, \quad x = r \cos(\theta), \quad y = \sin(\theta)
$$
$$
\begin{align*}
\frac{\delta w}{\delta r} &= \frac{\delta w}{\delta x} \frac{\delta x }{\delta r} + \frac{\delta w}{\delta y} \frac{\delta y }{\delta r}\\
&= 2x \cdot \cos(\theta) - 2y \sin(\theta)
\end{align*}
$$
$$
\begin{align*}
\frac{\delta w}{\delta \theta} &= \frac{\delta w}{\delta x} \frac{\delta x }{\delta \theta} + \frac{\delta w}{\delta y} \frac{\delta y }{\delta \theta}\\
= - 2x \cdot r \sin(\theta) - 2y \cdot r \cos(\theta)\\
\end{align*}
$$

Eksempel ud fra hierarki:
$$
\frac{\delta w}{\delta r} = \frac{\delta w}{\delta x} \frac{\delta x }{\delta r}
$$
$$
\frac{\delta w}{\delta \theta} = \frac{\delta w}{\delta x} \frac{\delta x }{\delta \theta}
$$
Eksempel ud fra hierarki:
$$
\frac{\delta w}{\delta t} = \frac{\delta w}{\delta x} \frac{\delta x}{\delta t} + \frac{\delta w}{\delta y} \frac{\delta y}{\delta t}
$$
$$
D_{p,\vec{v}} = \nabla f \cdot \frac{\vec{v}}{|\vec{v}|}
$$
![[06 Lektionsnoter.pdf#page=14]]