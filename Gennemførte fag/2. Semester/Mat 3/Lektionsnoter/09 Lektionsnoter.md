![[09 Linjeintegraler.pdf]]

$$
\int_{a}^{b} \vec{F} \cdot d\vec{r}
$$
![[09 Linjeintegraler.pdf#page=2]]

$$
\oint \vec{F} \cdot d \vec{r}
$$
Arbejde:
$$
A = \vec{F} \cdot d \vec{s}
$$
![[09 Linjeintegraler.pdf#page=3]]

$$
A = F \cdot s \cos(\theta)
$$
![[09 Linjeintegraler.pdf#page=4]]

$$
E_{pot} = mgh = \int_{a}^{b} \vec{F} \cdot d \vec{r}
$$
Tyngdefeltet er konservativt. Dvs. arbejdet er det samme uanset hvilken rute der tages.

$$
\vec{r}(t) = (x(t), y(t), z(t)) = x(t) \cdot \vec{i} + y(t) \cdot \vec{j} + z(t) \cdot \vec{k}
$$
$$
d \vec{r}(t) = (dx(t), dy(t), dz(t))
$$
$$
d \vec{r} = \frac{d \vec{r}}{dt} \, dt = r'(t) \, dt
$$
$$
\underline{\underline{\int_{a}^{b} \vec{F} \cdot r'(t) \, dt = \int_{a}^{b} \vec{F} \cdot d \vec{r}}}
$$
Nogle gange er det lettere at regne det på den ene måde end den anden.

$$
\vec{F} = (F_{1}, F_{2}, F_{3})
$$
$$
\int_{a}^{b} \vec{F} \cdot d \vec{r} = \int_{a}^{b} 
\begin{pmatrix}F_{1} \\ F_{2} \\ F_{3}\end{pmatrix}
\cdot 
\begin{pmatrix}x' \\ y' \\ z'\end{pmatrix} \, dt
= \int_{a}^{b}(F_{1}x'+F_{2}y'+F_{3}z') \, dt
$$
Eksempel i 2 dimensioner:
$$
\vec{F} = (-y,-xy)
$$
$$
\vec{r}(t) = (\underbrace{\cos(t)}_{x}, \underbrace{\sin(t)}_{y})
$$
$$
0 \leq t \leq \frac{\pi}{2}
$$
![[09 Linjeintegraler.pdf#page=5]]

$$
\begin{align*}
\int_{0}^{\frac{\pi}{2}} 
\begin{pmatrix}- \sin(t) \\ - \cos(t) \cdot \sin(t)\end{pmatrix}
\cdot
\begin{pmatrix}- \sin(t) \\ \cos(t)\end{pmatrix} \, dt
\\
= \int_{0}^{\frac{\pi}{2}} (\sin^{2}(t) - \cos^{2}(t) \sin(t)) \, dt\\
\end{align*}
$$
Regner lige nogle differentiationer ud:
$$
\begin{align*}
\frac{d \sin(t)}{dt}  &=  \cos(t)\\
\frac{d \cos(t)}{dt} &=  - \sin(t)\\
d \cos(t) &=  - \sin(t) \, dt
\end{align*}
$$
Regner videre:
$$
\begin{align*}
= \int_{0}^{\frac{\pi}{2}}\left(\frac{1}{2} - \frac{1}{2} \cos(2t)\right)\, dt - \int_{0}^{\frac{\pi}{2}} \cos^{2}(t) d \cos(t)\\
= \left[\frac{1}{2}t - \frac{1}{4} \sin^{2}\left(t\right) + \frac{1}{3} \cos^{3}(t)\right]_{0} ^\frac{\pi}{2}\\
= \frac{\pi}{4} - 0 + 0 - \left(0 - 0 + \frac{1}{3}\right)= \underline{\underline{\frac{\pi}{4} - \frac{1}{3}}} = 0.45 \space J
\end{align*}
$$
Eksempel i 3 dimensioner:
$$
\vec{F} = (z,y,x)
$$
$$
\vec{r}(t) = (\underbrace{\cos(t)}_{x}, \underbrace{\sin(t)}_{y}, \underbrace{3t}_{z}) \text{ Helix}
$$
$$
0 \leq t \leq 2 \pi
$$
$$
\int_{0}^{2\pi} \vec{F} \cdot \vec{r}'(t) \, dt = \int_{0}^{2\pi} \begin{pmatrix}3t \\ \cos(t) \\ \sin(t)\end{pmatrix} \cdot \begin{pmatrix}-\sin(t) \\ \cos(t)  \\ 3\end{pmatrix} \, dt = \int_{0}^{2\pi} (-3t \sin(t) + \cos^{2}(t) + 3 \sin(t)) \, dt
$$
Fourierrække:
$$
\int t \sin(t) \, dt
$$
For at løse det skal man bruge regnereglerne:
$$
\int d (f \cdot g) = \int g \, df + \int f \cdot dg
$$
$$
\int f \, dg = fg - \int g \, df
$$
$$
\int t \sin(t) \, dt = - \int t d \cos(t) = - t \cdot \cos(t) + \int \cos(t) \, dt
$$
$$
= - t \cos(t) + \sin(t)
$$
Dette kan findes i calculus bogen på back cover. Der står en masse integraler.

Hvis $\vec{F}$ er konservativ afhænger linjeintegralet kun af start- og slutpunkt

Sætning 1:
Et linjeintegrale er linjeuafhængigt [[hviss]]:
$$
\vec{F} = (F_{1}, F_{2}, F_{3}) = \nabla f
$$
Dette gælder begge veje. Her er f en funktion vi prøver at finde. Se næste eksempel.

Hvilket betyder
$$
F_{1} = \frac{\partial f}{\partial x}, \quad F_{2} = \frac{\partial f}{\partial y}, \quad F_{3} = \frac{\partial f}{\partial z}
$$
hvis $f$ findes kaldes: 
$$
\vec{F} \cdot d \vec{r} = F_{1} dx + F_{2} dy, F_{3} dz = df
$$
Dette kaldes for [[det totale differentiale]]
$$
w = f(x,y), x = x(t), y = y(t)
$$
![[09 Linjeintegraler.pdf#page=6]]
$$
\frac{dw}{dt} = \frac{\partial w}{\partial x} \frac{dx}{dt} + \frac{\partial w}{\partial y} \cdot \frac{dy}{dt}
$$
$$
dw = \frac{\partial w}{\partial x} \, dx + \frac{\partial w}{\partial y} \, dy
$$
$$
= F_{1} \, dx + F_{2} \, dy
$$
[[Tjek for eksakthed]] (hvis dette er sandt, så er den konservativ):
$$
\frac{\partial F_{1}}{\partial y} = \frac{\partial F_{2}}{\partial x} \text{ og } \frac{\partial F_{1}}{\partial z} = \frac{\partial F_{3}}{\partial x} \text{ og } \frac{\partial F_{2}}{\partial z} = \frac{\partial F_{3}}{\partial y}
$$
idet $u_{xy} = u_{yx}$

Eksempel 3:
$$
\int_{C} \vec{F} \cdot d \vec{r} = \underbrace{\int_{C} 2 xyz^{2} \, dx}_{F_{1}}+ \underbrace{(x^{2} z^{2} + z \cos(yz)) \, dy}_{F_{2}} + \underbrace{(2x^{2} y z + y \cos(yz)) \, dz}_{F_{3}}
$$
$$
\frac{\partial F_{1}}{\partial y} = 2xz^{2} = \frac{\partial F_{2}}{\partial x} = 2xz^{2}
$$
$$
\frac{\partial F_{1}}{\partial z} = 4xyz = \frac{\partial F_{3}}{\partial x} = 4xyz
$$
$$
\frac{\partial F_{2}}{\partial z} = 2x^{2}z + 1 \cdot \cos(yz) - zy \sin(yz)
$$
$$
\frac{\partial F_{3}}{\partial y} = 2x^{2}z + 1 \cdot \cos(yz) - yz \sin(yz)
$$
Det må betyde at de er eksakt, da de giver det samme.
$$
F_{1} = 2xyz^{2} = \frac{\partial f}{\partial x } \rightarrow f = x^{2}yz^{2} + g (y,z)
$$
g(y,z) giver jo 0 når vi differentiere, hvis den ikke indeholder x, idet vi partielt differentierer mht. x.
$$
F_{2} = x^{2}z^{2} + z \cos(yz) = \frac{\partial f}{\partial y} \rightarrow x^{2}yz^{2} + \underbrace{\sin(yz) + h(z)}_{g (y,z)} 
$$
$\sin(yz)$ differentieret giver cosinus, og yz differentieret mht. y giver z, så det passer.
$$
F_{3} = 2x^{2}yz + y \cos(yz) = \frac{\partial f}{\partial z} \rightarrow f = x^{2}yz^{2} + \sin(yz) + k
$$
h(z) bliver altså til en konstant, fordi z differentieret 
Dvs. vi får:
$$
\int_{C} \vec{F} \cdot d \vec{r} = \underbrace{\int_{C} 2 xyz^{2} \, dx}_{F_{1}}+ \underbrace{(x^{2} z^{2} + z \cos(yz)) \, dy}_{F_{2}} + \underbrace{(2x^{2} y z + y \cos(yz)) \, dz}_{F_{3}} = \int_{(0,0,1)} ^{(1,\frac{\pi}{4}, 2)} df
$$
$$
\int_{(0,0,1)} ^{(1,\frac{\pi}{4}, 2)} df = [f]_{(0,0,1)} ^{(1,\frac{\pi}{4},2 )} = [x^{2}yz^{2} + \sin(yz)]_{(0,0,1)} ^{(1,\frac{\pi}{4},2 )}
$$
$$
= [x^{2}yz^{2} + \sin(yz)]_{(0,0,1)} ^{(1,\frac{\pi}{4},2 )} = 1^{2} \cdot \frac{\pi}{4} \cdot 2^{2} + \sin\left(\frac{\pi}{4} \cdot 2\right) - 0^{2} \cdot 0 \cdot 1^{2} - \sin(0 \cdot 1)
$$
$$
= \underline{\underline{\pi + 1}}
$$