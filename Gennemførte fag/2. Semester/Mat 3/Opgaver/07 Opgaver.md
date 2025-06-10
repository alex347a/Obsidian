### 9.2.17 Find the work done by a force p acting on a body if the body is displaced along the straight segment $\overline{AB}$ from A to B. Sketch $\overline{AB}$ and p. Show the details.
$p = [2,5,0], \quad A:(1,3,3), \quad B:(3,5,5)$
Jeg bruger formlen:
$$
W =  |p||d| \cos(\alpha) = p \cdot d
$$
$$
\begin{align*}
d &=  B-A\\
d&= (3-1,5-3,5-3)\\
&= (2,2,2)\\\\

p \cdot d\\
&= (2,5,0) \cdot (2,2,2)\\
&= 4+10+0\\
&= 14\\
W&= 14\\
\end{align*}
$$
![[Pasted Images/2. Semester/Mat 3/07/07 Opgaver.pdf]]


### 9.3.11 With respect to right-handed Cartesian coordinates, let $a = [2,1,0]$, $b = [-3,2,0]$, $c = [1,4,-2]$ and $d = [5,-1,3]$ Showing details, find:
$$
a \times b, \quad b \times a, \quad a \cdot b
$$
$$
\begin{align*}
a \times b &=   
\begin{vmatrix}  
\mathbf{i} & \mathbf{j} & \mathbf{k} \\  
2 & 1 & 0 \\  
-3 & 2 & 0  
\end{vmatrix}\\
a \times b &=   
\mathbf{i} \begin{vmatrix} 1 & 0 \\ 2 & 0 \end{vmatrix}  
- \mathbf{j} \begin{vmatrix} 2 & 0 \\ -3 & 0 \end{vmatrix}  
+ \mathbf{k} \begin{vmatrix} 2 & 1 \\ -3 & 2 \end{vmatrix}\\
\begin{vmatrix} 1 & 0 \\ 2 & 0 \end{vmatrix} = (1)(0) - (0)(2) &=  0\\
\begin{vmatrix} 2 & 0 \\ -3 & 0 \end{vmatrix} = (2)(0) - (0)(-3) &=  0\\
\begin{vmatrix} 2 & 1 \\ -3 & 2 \end{vmatrix} = (2)(2) - (1)(-3) = 4 + 3 &=  7\\
a \times b = 0\mathbf{i} - 0\mathbf{j} + 7\mathbf{k} &=  (0,0,7)   
\end{align*}
$$
Jeg burger den anti-commutative egenskab for krydsproduktet som siger:  
$$
\begin{align*}
b \times a &=  - (a \times b)\\
b \times a &=  - (0,0,7) = (0,0,-7)  
\end{align*}
$$
Nu til prikproduktet:
$$
\begin{align*}
a \cdot b &=  (2)(-3) + (1)(2) + (0)(0)\\
&=  -6 + 2 + 0 = -4  \\
\end{align*}
$$
Svarene bliver altså:
$$
\begin{align*}
a \times b &=  (0,0,7)\\
b \times a &=  (0,0,-7)\\
a \cdot b &=  -4  
\end{align*}
$$
### 9.7.3 Find grad $f$. Graph some level curves $f = const$. Indicate $\nabla f$ by arrows at some points of these curves.
$$f = \frac{y}{x}$$
Gradienten er givet ved:
$$
\nabla f = \left(\frac{\delta f}{\delta x}, \frac{\delta f}{\delta y}\right)
$$
$$
\begin{align*}
\frac{\delta f}{\delta x} &=  \frac{\delta}{\delta x}\left(\frac{y}{x}\right) \\
&=  - \frac{y}{x^{2}}\\\\
\frac{\delta f}{\delta y} &=  \frac{\delta}{\delta x} \left(\frac{y}{x}\right)\\
&= \frac{1}{x}\\\\
\nabla f = \left(\frac{-y}{x^{2}}, \frac{1}{x}\right)
\end{align*}
$$
Niveaukurverne er givet ved: $f = c$
$$
\frac{y}{x} = c, \quad y = cx
$$
$$
\nabla f(x,y) = \left(\frac{-y}{x^{2}}, \frac{1}{x}\right)=\left(- \frac{cx}{x^{2}}, \frac{1}{x}\right) = \left(- \frac{c}{x}, \frac{1}{x}\right)
$$
![[Pasted Images/2. Semester/Mat 3/07/07 Opgaver.pdf#page=2]]

### 9.7.8 Prove and illustrate by example.
$$
\nabla (fg) = f \nabla g + g \nabla f
$$
$$
\nabla(fg) = \left( \frac{\partial(fg)}{\partial x}, \frac{\partial(fg)}{\partial y}, \frac{\partial(fg)}{\partial z} \right)
$$
$$
\frac{\partial(fg)}{\partial x} = f \frac{\partial g}{\partial x} + g \frac{\partial f}{\partial x}
$$
$$
\frac{\partial(fg)}{\partial y} = f \frac{\partial g}{\partial y} + g \frac{\partial f}{\partial y}
$$
$$
\frac{\partial(fg)}{\partial z} = f \frac{\partial g}{\partial z} + g \frac{\partial f}{\partial z}
$$
$$
\nabla(fg) = \left( f \frac{\partial g}{\partial x} + g \frac{\partial f}{\partial x}, f \frac{\partial g}{\partial y} + g \frac{\partial f}{\partial y}, f \frac{\partial g}{\partial z} + g \frac{\partial f}{\partial z} \right)
$$
Dette kan skrives som:
$$
\nabla(fg) = f \nabla g + g \nabla f
$$
Eksempel:
$f(x,y) = x^2 + y$ og $g(x,y) = x - y^2$

$$
\nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right) = (2x, 1)
$$
$$
\nabla g = \left( \frac{\partial g}{\partial x}, \frac{\partial g}{\partial y} \right) = (1, -2y)
$$
$$
\nabla(fg) = \left( \frac{\partial}{\partial x} \left[ (x^2 + y)(x - y^2) \right], \frac{\partial}{\partial y} \left[ (x^2 + y)(x - y^2) \right] \right)
$$
$$
fg = (x^2 + y)(x - y^2) = x^3 + yx - x^2 y^2 - y^3
$$
$$
\frac{\partial(fg)}{\partial x} = 3x^2 + y - 2xy^2
$$
$$
\frac{\partial(fg)}{\partial y} = x - 2xy - 3y^2
$$
Lad os tjekke:
$$
f \nabla g = (x^2 + y)(1, -2y) = (x^2 + y, -2y(x^2 + y))
$$
$$
g \nabla f = (x - y^2)(2x, 1) = (2x(x - y^2), x - y^2)
$$
$$
f \nabla g + g \nabla f = (x^2 + y + 2x(x - y^2), -2y(x^2 + y) + (x - y^2))
$$
$$
= (3x^2 + y - 2xy^2, x - 2xy - 3y^2)
$$
Det er det samme som før.

### 9.7.11 The force in an electrostatic field given by $f(x,y,z)$ has the direction of the gradient. Find $\nabla f$ and its value at $P$
$$
f=xy, \quad P: (-4,5)
$$
Jeg bruger formlen
$$
\nabla f = \left(\frac{\delta f}{\delta x}, \frac{\delta f}{\delta y}\right)
$$
$$
\begin{align*}
\frac{\delta f}{\delta x} = \frac{\delta }{\delta x} (xy) = y
\end{align*}
$$
$$
\begin{align*}
\frac{\delta f}{\delta y} = \frac{\delta }{\delta y} (xy) = x
\end{align*}
$$
Dermed er $\nabla f$:
$$
\nabla f = (y, x)
$$
Jeg indsætter $P = (-4,5)$
$$
\nabla f = (y, x) = (5,-4)
$$
### 9.7.14 The force in an electrostatic field given by $f(x,y,z)$ has the direction of the gradient. Find $\nabla f$ and its value at $P$
$$
f = (x^{2} + y^{2} + z^{2})^{-1/2}, \quad P: (12,0,16)
$$
Jeg bruger formlen
$$
\nabla f = \left(\frac{\delta f}{\delta x}, \frac{\delta f}{\delta y}, \frac{\delta f}{\delta z}\right)
$$
$$
\begin{align*}
\frac{\delta f}{\delta x} = \frac{\delta }{\delta x} (x^{2} + y^{2} + z^{2})^ {\frac{-1}{2}} = -\frac{1}{2} (x^{2} + y^{2} + z^{2})^ {\frac{-3}{2}} \cdot 2x = \frac{x}{(x^{2} + y^{2} + z^{2})^ {\frac{3}{2}}}
\end{align*}
$$
$$
\begin{align*}
\frac{\delta f}{\delta y} = \frac{\delta }{\delta y} (x^{2} + y^{2} + z^{2})^ {\frac{-1}{2}} = -\frac{1}{2} (x^{2} + y^{2} + z^{2})^ {\frac{-3}{2}} \cdot 2y = \frac{y}{(x^{2} + y^{2} + z^{2})^ {\frac{3}{2}}}
\end{align*}
$$
$$
\begin{align*}
\frac{\delta f}{\delta z} = \frac{\delta }{\delta z} (x^{2} + y^{2} + z^{2})^ {\frac{-1}{2}} = -\frac{1}{2} (x^{2} + y^{2} + z^{2})^ {\frac{-3}{2}} \cdot 2z = \frac{z}{(x^{2} + y^{2} + z^{2})^ {\frac{3}{2}}}
\end{align*}
$$
Dvs. 
$$
\nabla f = \left(\frac{\delta f}{\delta x}, \frac{\delta f}{\delta y}\right) = \left(\frac{x}{\left(x^{2} + y^{2} + z^{2}\right)^ {\frac{3}{2}}}, \frac{y}{\left(x^{2} + y^{2} + z^{2}\right)^ {\frac{3}{2}}},  \frac{z}{(x^{2} + y^{2} + z^{2})^ {\frac{3}{2}}}\right)
$$
Indsætter $P = (12,0,16)$
$$
\begin{align*}
\left(\frac{12}{\left(12^{2} + 0^{2} + 16^{2}\right)^ {\frac{3}{2}}}, \frac{0}{\left(12^{2} + 0^{2} + 16^{2}\right)^ {\frac{3}{2}}},  \frac{16}{(12^{2} + 0^{2} + 16^{2})^ {\frac{3}{2}}}\right)\\
\left(\frac{12}{(144+256)^ {\frac{3}{2}}}, 0,  \frac{16}{(144+256)^ {\frac{3}{2}}}\right)\\
\left(\frac{12}{400^ {\frac{3}{2}}}, 0,  \frac{16}{400^ {\frac{3}{2}}}\right)\\
\left(\frac{12}{8000}, 0,  \frac{16}{8000}\right)\\
(0.0015,0,0.002)\\
\end{align*}
$$
### 9.7.33 ??? De to her eksisterer ikke i bogen lol.

### 9.7.38 ??? De to her eksisterer ikke i bogen lol.

### 12.6.5 (Denne her opgave kom jeg til at lave til sidste lektion før han ændrede lektionsplanen til i stedet at være eksamensopgaver) (benyt cm som enhed)
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