Hvis man tager et legeme T med en overflade S.

### Gauss' divergenssætning.
Hvis man laver et trippelintegrale over T så er divergensen et vektorfoelt af volumen. Man kan i stedet for integrere over fladen, altså ligesom at integrere over randen
$$
\iiint_{T} \text{div } \vec{F} \, dV = \iint_{S} \vec{F} \cdot \vec{n} \,  dA
$$
$$
\begin{align*}
\vec{F} &=  (F_{1}, F_{2}, F_{3})\\
\text{div } \vec{F} &= \frac{\partial F_{1}}{\partial x} + \frac{\partial F_{2}}{\partial y} + \frac{\partial F_{3}}{\partial z}
\end{align*}
$$
#### Eksempel

$$
\begin{align*}
\iint_{S} (7 x \vec{i} - z \vec{k}) \cdot \vec{n} \, dA\\
\text{Hvor S er kuglefladen:} \quad x^{2} + y^{2} + z^{2} &= 4\\
\text{div } \vec{F} = 7 - 1 &=  6
\end{align*}
$$
Trippelintegrale:
$$
\begin{align*}
\iiint_{T} 6 \, dv &=  6 \iiint_{T} \, dv \\
= 6 \cdot \frac{4}{3} \pi \cdot 2^{3} &= 64 \pi
\end{align*}
$$
Parameterfremstilling af fladen:
$$
\begin{align*}
S: \vec{r} &=  (\underbrace{2 \cos(v) \cos(u)}_{x}, 2 \cos(v) \sin(u), \underbrace{2 \sin(u)}_{z})\\
\vec{r}_{u} &= (-2 \cos(v) \sin(u), 2 \cos(v) \cos(u), 2 \cos(u))\\
\vec{r}_{v} &= (-2 \sin(v) \cos(u), -2 \sin(v) \sin(u), 0)\\
\text{Normalvektoren findes ved at krydse:}\\
\vec{N} &= \vec{r}_{u} \times \vec{r}_{v}\\
\vec{N} &= (4 \cos^{2}(v) \cos(u), 4 \cos^{2}(v) \sin(u), 4 \cos(v) \sin(v))\\
\text{På S:} 
\begin{pmatrix}
7 \cdot 2 \cos(v) \cos(u) \\ 
2 \sin(u) \\  
0
\end{pmatrix}
\cdot 
\begin{pmatrix}
4 \cos^{2}(v) \cos(u)  \\ 
4 \cos^{2}(v) \\ 
 4 \cos(v) \sin(v)\\
\end{pmatrix}
\\
= \iint_{S} (56 \cos^{3}(v) \cos^{2}(u) - 8 \cos(v) \sin^{2}(v)) \, dA &= 64 \pi
\end{align*}
$$
$$

$$
### Stokes sætning
Transformation af fladeintegraler til linjeintegraler.

Hvis man har en flade S og en rand C så har man ds der er en lille strækning

$$
\begin{align*}
\iint_{S} \text{curl} \vec{F} \cdot \vec{n} \, dA &= \oint_{C} \vec{F} \cdot \vec{r}' \, ds\\
\text{Læg mærke til det er vektor r differentieret}\\
\text{curl } \vec{F} = \text{rot } \vec{F} = \nabla \times \vec{F} = 
\begin{pmatrix}
\vec{i}  &  \vec{j}  &  \vec{k}\\
\frac{\partial }{\partial x}  &  \frac{\partial }{\partial y}  &  \frac{\partial }{\partial z}\\
F_{1}  &  F_{2}  &  F_{3}
\end{pmatrix}
\end{align*}
$$
#### Eksempel
$$
\begin{align*}
F &=  (y, z, x)\\
S &=  \text{paraboloide}\\
z &=  f(x,y) = 1 - x^{2} - y^{2}, \quad z \geq 0\\
\end{align*}
$$
C er det der omgrænser xy-planet, mens S er selve overfladen.
Linjeintegrale:
$$
\begin{align*}
\begin{pmatrix}
\cos(s)\\
\sin(s)\\
0
\end{pmatrix}, \quad 0 \leq s le
\end{align*}
$$