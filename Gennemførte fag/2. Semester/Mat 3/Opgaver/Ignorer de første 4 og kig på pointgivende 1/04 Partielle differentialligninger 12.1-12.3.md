## Noter

### Important Second-Order PDEs
![[Important Second-Order PDEs.png]]
### One-dimensional wave equation (and its boundary conditions)
![[One-dimensional wave equation.png]]
![[One-dimensional wave equation boundary conditions.png]]
### Separating variables
![[Separating variables.png]]
### Eigenfunctions (egenfunktioner)
![[eigenfunctions partial differential equations.png]]
### Fourier series for the wave equation
![[Fourier series for the wave equation.png]]
![[Fourier series for the wave equation 2.png]]
![[Fourier series for the wave equation 3.png]]
#### Substituting into the sine series
![[Substituting into the sine series.png]]
$$
B_{n}^{*}= \frac{2}{L} \int_{0}^{L} g(x) \sin\left(\frac{n \pi x }{L}\right)\, dx
$$
$\lambda_{n}$ is the eigenvalue (egenværdien) which depends on the boundary conditions and the form of PDE. It comes from solving the separation of values. 
#### Example with Dirichlet boundaries:
$$
X(0) = 0, \quad X(L) = 0
$$
$$
X_{n}(x) = \sin\left(\frac{n \pi x}{L}\right), \quad n = 1,2,3 \dots
$$
The eigenvalues are:
$$
\lambda_{n}= \left(\frac{n \pi}{L}\right)^{2}
$$
## Opgaver

#### Opgave fra Niels:
Løs: $\frac{\delta u}{\delta x} = 2 \frac{\delta u}{\delta t}+u$ hvor $u(x,0) = 6e^{-3x}$

$$
\begin{align*}
\text{Separerer variable: }\\
u(x,t) &= X(x) T(t)\\
X'(x)T(t) &= 2X(x)T'(t)+X(x)T(t)\\
\text{Dividerer med } X(x)T(t)\\
\frac{X'(x)}{X(x)}-1 &= 2\frac{T'(t)}{T(t)}\\
\text{Sætter de to ligmed en konstant}\\
\frac{X'(x)}{X(x)}-1&= k, \quad 2\frac{T'(t)}{T(t)} = k\\
X'(x) &= (k+1)X(x)\\
T'(t)&= \frac{k}{2}T(t)\\
X(x)&= c_{1}e^{(k+1)x}\\
T(t) &= c_{2}e^{\frac{k}{2}t}\\
\text{Så }\\
c&= c_{1}c_{2}\\
u(x,t) = ce^{(k+1)x}e^{\frac{k}{2}t}&= c e^{(k+1)x + \frac{k}{2}t}\\
\text{Jeg bruger nu startbetingelsen}\\
u(x,0) &=  6e^{-3x}\\
6e^{-3x} &= c e^{(k+1)x}\\
\text{Da } k+1 &=  -3\\
k&= -4\\
u(x,t)&= ce ^{(-4+1)x+ \frac{-4}{2}t}\\
u(x,t)&= ce ^{-3x-2t}\\
c&= 6\\
u(x,t)=6e ^{-3x-2t}\\
\end{align*}
$$

#### 12.1.3 Wave equation (1) with suitable c
$u = \cos(4t) \sin(2x)$
Separerer variable:
$$
\begin{align*}
u(x,t) = \cos(4t) \sin(2x)\\
\frac{\delta u}{\delta t} &= -4 \sin(4t) \sin(2x)\\
\frac{\delta^{2} u}{\delta t^{2}} &= -16 \cos(4t) \sin(2x)\\
\\
\frac{\delta u}{\delta x} &= \cos(4t) 2\cos(2x)\\
\frac{\delta^{2} u}{\delta x^{2}} &= -4\cos(4t)\sin(2x)\\
\text{Substituerer i bølgeligningen (1):}\\
\frac{\delta^{2} u}{\delta t^{2}}&= c^{2}\frac{\delta^{2} u}{\delta x^{2}}\\
-16 \cos(4t) \sin(2x)&= c^{2}(-4\cos(4t)\sin(2x))\\
\text{Så længe } \cos(4t) \sin(2x) &\neq 0\\
-16&= -4c^{2}\\
4&= c^{2}\\
c&= 2\\
\end{align*}
$$

#### 12.3.5
Find $u(x,t)$ for the string of length $L = 1$ and $c^{2}= 1$ when
the initial velocity is zero and the initial deflection with small $k$ (say 0.01) is as follows. Sketch or graph $u(x,t)$ as in Fig. 291 in the text.
$k \sin(3 \pi x)$

#### 12.3.9
![[12.3.9.png]]