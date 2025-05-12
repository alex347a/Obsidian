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
\begin{vmatrix}
\vec{i}  &  \vec{j}  &  \vec{k}\\
\frac{\partial }{\partial x}  &  \frac{\partial }{\partial y}  &  \frac{\partial }{\partial z}\\
F_{1}  &  F_{2}  &  F_{3}
\end{vmatrix}
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
\vec{r}(s) &= 
\begin{pmatrix}
\cos(s)\\
\sin(s)\\
0
\end{pmatrix}, \quad 0 \leq s \leq 2\pi\\
r'(s) &= 
\begin{pmatrix}
-\sin(s)\\
\cos(s)\\
0
\end{pmatrix}\\
\text{Så } \vec{F} &= (\underbrace{y}_{\sin(s)},\underbrace{z}_{0},\underbrace{x}_{\cos(s)})\\
\vec{F} \cdot \vec{r}' = 
\begin{pmatrix}
\sin(s)\\
0\\
\cos(s)
\end{pmatrix}
\cdot
\begin{pmatrix}
-\sin(s)\\
\cos(s)\\
0
\end{pmatrix}\\
\int_{0}^{2\pi} - \sin^{2} (s) \, ds  = - \pi\\
\end{align*}
$$
Fladeintegrale:
$$
\begin{align*}
\text{Standardformlen er:}\\
\text{curl } \vec{F} &= 
\begin{vmatrix}
\vec{i}  &  \vec{j}  &  \vec{k}\\
\frac{\partial }{\partial x}  &  \frac{\partial }{\partial y}  &  \frac{\partial }{\partial z}\\
F_{1}  &  F_{2}  &  F_{3}
\end{vmatrix}\\
\text{Med indsatte værdier:}\\
\text{curl } \vec{F} &= 
\begin{vmatrix}
\vec{i}  &  \vec{j}  &  \vec{k}\\
\frac{\partial }{\partial x}  &  \frac{\partial }{\partial y}  &  \frac{\partial }{\partial z}\\
y  &  z  &  x
\end{vmatrix}\\
&= \vec{i}\left(\frac{\partial x}{\partial y} - \frac{\partial z}{\partial z}\right)- \vec{j} \left(\frac{\partial x}{\partial x} - \frac{\partial y}{\partial z}\right) + \vec{k}\left(\frac{\partial z}{\partial x} - \frac{\partial y}{\partial y}\right)\\
= \vec{i} (0 - 1) - \vec{j} (1-0) + \vec{k} (0-1) &= - \vec{i} - \vec{j} - \vec{k}\\
\text{Man kan vælge x og y frit, hvor z afhænger af de to:}\\
z = f(x,y) &=  1-x^{2}-y^{2}, \quad z \geq 0\\
\vec{r}(x, y, 1 - x^{2} - y^{2})\\
\vec{r}_{x} &= (1, 0, -2x)\\
\vec{r}_{y} &= (0, 1, -2y)\\
\vec{N} &=  \vec{r}_{x} \times \vec{r}_{y}\\
\begin{vmatrix}
\vec{i}  &  \vec{j}  &  \vec{k}\\
1  &  0  &  -2x\\
0  &  1  &  -2y
\end{vmatrix}
&= 2x \vec{i} + 2y \vec{j} + \vec{k}\\
\text{curl } \vec{F} \cdot \vec{N} &= 
\begin{pmatrix}
-1\\
-1\\
-1
\end{pmatrix}\\
\iint_{S} \text{curl } \vec{F} \cdot \vec{n} \, dA &= \iint_{R} \text{curl } \vec{F} \cdot \vec{N} \, dx \, dy
\end{align*}
$$
I stedet for at integrere på fladen, så kan man integrere på skyggen, ligesom sidste lektion afsnit 10.6. Her skal man så beregne store $\vec{N}$ ud fra lille $\vec{n}$:
$$
|\vec{N}| = \sqrt{4x^{2} + 4{y}^{2} + 1}
$$
$$
\vec{n} = \frac{\vec{N}}{|\vec{N}|}
$$
Se figur 253 for sammenligning mellem regionen S og regionen R.
![[Fig 253.png]]
$$
\begin{align*}
\iint_{R} (-2x -2y -1) \, dx \, dy\\
&= \iint_{R} (-2 \cos(\theta) - 2 \sin(\theta) - 1) \, \underbrace{r}_{1} \, dr \, d \theta\\
&= \int_{0} ^{2\pi} \int_{0}^{1} (-2 \cos(\theta) - 2 \sin(\theta) - 1) \, r \, dr \, d \theta\\

\end{align*}
$$