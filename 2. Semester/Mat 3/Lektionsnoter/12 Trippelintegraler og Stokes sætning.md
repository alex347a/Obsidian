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

Det kan også skrive som:
$$
\iint_{S} \vec{F} \cdot \vec{n} \, dA = \iint_{R} \vec{F} (r(u,v)) \cdot \vec{N}(u,v) \, du\, dv
$$
Her er det vigtigt at se at store $\vec{N}$ ikke er en enhedsvektor ligesom lille $\vec{n}$
$$
\vec{n} \, dA = \vec{n} |\vec{N}| \, du \, dv = \vec{N} \, du \, dv
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
x &= r \cos(\theta)\\
y &= r \sin(\theta)\\
r^{2} &= x^{2} + y^{2}\\
\tan(\theta) &= \frac{y}{x}\\
&= \iint_{R} (-2 r \cos(\theta) - 2 r \sin(\theta) - 1) \, \underbrace{r}_{1} \, dr \, d \theta\\
&= \int_{0} ^{2\pi} \int_{0}^{1} (-2 r \cos(\theta) - 2 r \sin(\theta) - 1)\, dr \, d \theta\\
&= -\pi
\end{align*}
$$
#### Eksempel
Hvis man har en flade i xy planen, som betragtes som fladen S.
Så har man parameterfremstillingen
$$
\begin{align*}
\vec{r}(s) &= 
\begin{pmatrix}
x\\
y
\end{pmatrix} \\
\text{dermed er } \vec{r}' (s) &=
\begin{pmatrix}
\frac{dx}{ds}\\
\frac{dy}{ds}
\end{pmatrix}\\
\int_{C} 
\begin{pmatrix}
F_{1}\\
F_{2}
\end{pmatrix}
\cdot 
\begin{pmatrix}
\frac{dx}{ds}\\
\frac{dy}{ds}
\end{pmatrix} \, ds &=  \int_{C}\left(F_{1} \frac{dx}{ds} + F_{2} \frac{dy}{ds}\right) \, ds\\
&= \int_{C} F_{1} \, dx + F_{2} \, dy\\
\end{align*}
$$
Hvis man i stedet for beregner linjeintegralet:
$$
\begin{align*}
\iint_{S} \text{curl } (\vec{F}) \cdot \vec{n} \, dA\\
\text{Standardformel:}\\
\text{curl } (\vec{F}) &= 
\begin{vmatrix}
\vec{i}  &  \vec{j}  &  \vec{k}\\
\frac{\partial }{\partial x}  &  \frac{\partial }{\partial y}  &  \frac{\partial }{\partial z}\\
F_{1}  &  F_{2} &   F_{3}
\end{vmatrix}\\
\text{Indsætter:}\\
\begin{vmatrix}
\vec{i}  &  \vec{j}  &  \vec{k}\\
\frac{\partial }{\partial x}  &  \frac{\partial }{\partial y}  &  \frac{\partial }{\partial z}\\
F_{1}  &  F_{2} &  0
\end{vmatrix}\\
\text{Pga. mellemregningerne kommer der andre fortegn}\\
 &= - \frac{\partial F_{2}}{\partial z} \vec{i} + \frac{\partial F_{1}}{\partial z} \vec{j} + \left(\frac{\partial F_{2}}{\partial x} - \frac{\partial F_{1}}{\partial y}\right) \vec{k}\\
\vec{n} &=  \vec{k}\\
\text{curl } \vec{F} \cdot \vec{n} &= \frac{\partial F_{2}}{\partial x} - \frac{\partial F_{1}}{\partial y}
\end{align*}
$$
Greens sætning (s. 433)

#### Eksempel
$$
\begin{align*}
\text{Paraboloide: } z &=  x^{2} + y^{2}\\
\text{Cylinder: } (x-1)^{2} + y^{2} &= 1\\
\end{align*}
$$
Cylinderen svarer til formlen for en cirkel med radius i centrum $(1,0)$
Skæringsfladen mellem cylinderen og paraboloiden betegnes $C$
Derfor skal de to ligninger sættes ligmed hinanden for at finde skæringsfladen:
$$
\begin{align*}\\
z &= x^{2} + (1 - (x-1)^{2})\\
&= x^{2} + 1 - (x^{2} - 2x+1)\\
&= 2x
\end{align*}
$$
$$
\begin{align*}
\text{Kraft } \vec{F} &=  2xy^{3} \sin(z) \vec{i} + 3x^{2} y^{2} \sin(z) \vec{j} + x^{2}y^{3} \cos(z) \vec{k}\\
\text{Opgaven er nu at finde arbejdet:}\\
\text{Man finder en potentiel funktion:}\\
f &=  x^{2} y^{3} \sin(z)\\
\text{Hvis man differentiere mht. x, y og } & \text{z så passer det henholdsvist til } F_{1}, \space F_{2} \text{ og } F_{3}\\
\vec{F} &= \nabla f \Rightarrow \vec{F} \text{ er konservativ}\\
\text{Dvs. Arbejdet er det samme } & \text{uanset hvilken rute der tages}\\
\text{curl } (\vec{F}) &= 
\begin{vmatrix}
\vec{i}  &  \vec{j}  &  \vec{k}\\
\frac{\partial }{\partial x}  &  \frac{\partial }{\partial y}  &  \frac{\partial }{\partial z}\\
F_{1}  &  F_{2} &  F_{3}\\
\end{vmatrix}\\
(\frac{\partial F_{3}}{\partial y} - \frac{\partial}{\partial})
\end{align*}
$$