## Eksempel
Lad S være overfladen af området beskrevet ved paraboloiden:
$$
S: z = \frac{1}{2} x^{2} + \frac{1}{2} y^{2} \quad \text{og} \quad 0 \leq z \leq 8
$$
med rand C beskrevet ved parameterfremstillingen:
$$
C: \overline{r}(\theta) = (4 \cos(\theta), 4 \sin(\theta), 8), \quad \text{hvor } 0 \leq \theta \leq 2 \pi
$$
Desuden er vektorfunktionen $\overline{F}(x,y,z)$ givet som: $\overline{F}(x,y,z) = (x,x,z)$
#### a) Skitsér området S:
![[Pasted image 20250609104913.png]]

#### b) Udregn linjeintegralet $\oint_{C} \overline{F} \cdot d \overline{r}$
Jeg har allerede parameterfremstillingen:
$$
C: \overline{r}(\theta) = (4 \cos(\theta), 4 \sin(\theta), 8), \quad \text{hvor } 0 \leq \theta \leq 2 \pi
$$
Jeg skal beregne $d \overline{r}$ ved at differentiere $\overline{r}(\theta)$:
$$
d \overline{r} = \frac{d \overline{r}}{d \theta} d \theta = (- 4 \sin(\theta), 4 \cos(\theta), 0) d \theta
$$
Dette indsætter jeg i $\overline{F}(x,y,z)$:
$$
\begin{align*}
\overline{F}(x,y,z) &=  (x,x,z)\\
\overline{F}(\overline{r}(\theta)) &= (4 \cos(\theta), 4 \cos(\theta), 8)
\end{align*}
$$
Beregner prikproduktet $\overline{F} \cdot d\overline{r}$:
$$
\begin{align*}
\overline{F} \cdot d \overline{r} &=  (4 \cos(\theta) \cdot (-4 \sin(\theta)) + (4 \cos(\theta) \cdot 4\cos(\theta)) + (8 \cdot 0))\\
&= -16 \cos(\theta) \sin(\theta) + 16 \cos^{2}(\theta)
\end{align*}
$$
Så kan jeg bruge den trigonometriske identitet $2 \cos(\theta) \sin(\theta) = \sin(2 \theta)$ og $\cos^{2}(\theta) = \frac{1 + \cos(2 \theta)}{2}$
$$
\begin{align*}
- 16 \cos(\theta) \sin(\theta) &=  - 8 \sin (2 \theta)\\
16 \cos^{2}(\theta) &= 8(1 + \cos(2 \theta))
\end{align*}
$$
Dermed får jeg at:
$$
\overline{F} \cdot d \overline{r} = -8 \sin( 2 \theta) + 8(1 + \cos(2 \theta)) = 8 -8 \sin(2 \theta) + 8 \cos(2 \theta)
$$
Nu kan jeg integrere:
$$
\oint_{C} \overline{F} \cdot d\overline{r} = \int_{0}^{2\pi} (8 - 8\sin(2 \theta) + 8 \cos(2 \theta)) \, d \theta
$$
Deler op i tre integraler:
$$
\int_{0}^{2\pi} 8 \, d \theta - \int_{0}^{2\pi} 8\sin(2 \theta) \, d \theta + \int_{0}^{2\pi} 8 \cos(2 \theta) \, d \theta
$$
$$
\int_{0}^{2\pi} 8 \, d \theta  = 16 \pi
$$
$$
\int_{0}^{2\pi} 8\sin(2 \theta) \, d \theta = 0
$$
Dette integrale er 0, fordi $\sin(2 \theta)$ har en fuld periode på $2 \pi$
$$
\int_{0}^{2\pi} 8 \cos(2 \theta) \, d \theta = 0
$$
Dette integrale er 0, fordi $\cos(2 \theta)$ har en fuld periode på $2 \pi$
Dermed bliver linjeintegralet:
$$
\oint_{C} \overline{F} \cdot d\overline{r} = 16 \pi - 0 + 0 = 16 \pi
$$
Man kunne også løse denne ved at bruge Stokes' sætning, men jeg kan se jeg bliver bedt om det senere.

#### c) Vis, at en enhedsnormalvektor til den givne overflade bliver $\overline{n} = \left(\frac{-x}{\sqrt{1 + 2z}}, \frac{-y}{\sqrt{1 + 2z}}, \frac{1}{\sqrt{1 + 2z}} \right)$ (Lidt hjælp: Definer overflade som en niveauflade og bestem normalvektoren vha. gradienten, som står vinkelret på fladen)
Overfladen $S$ er givet ved $S: z = \frac{1}{2} x^{2} + \frac{1}{2} y^{2}$. Dette kan defineres som en niveaufalde:
$$
g(x,y,z) =  \frac{1}{2} x^{2} + \frac{1}{2} y^{2} -z = 0
$$
Normalvektoren er givet ved gradienten af g:
$$
\begin{align*}
\nabla g &=  \left(\frac{\partial g}{\partial x}, \frac{\partial g}{\partial y}, \frac{\partial g}{\partial z}\right)\\
\frac{\partial g}{\partial x} = \left(\frac{1}{2}x^{2}\right)' &=  x\\
\frac{\partial g}{\partial y} = \left(\frac{1}{2}y^{2}\right)' &=  y\\
\frac{\partial g}{\partial z} = (-z)' &= -1
\end{align*}
$$
Dvs. gradienten af g er givet ved:
$$
\nabla g = (x, y, -1)
$$
Jeg beregner nu enhedsnormalvektoren af $\overline{n}$ ved at normalisere $\nabla g$:
$$
\begin{align*}
||\nabla g|| &=  \sqrt{(x)^{2} + (y)^{2} + (-1)^{2}}\\
&= \sqrt{x^{2} + y^{2} + 1}\\
\end{align*}
$$
Da $z = \frac{1}{2} x^{2} + \frac{1}{2} y^{2}$ så kan jeg udtrykke $x^{2} + y^{2}$ som $2z$:
$$
\begin{align*}
||\nabla g|| &=  \sqrt{\left(2z\right) + 1}\\
&= \sqrt{2z + 1}
\end{align*}
$$
Nu skal jeg bare indsætte de beregnede værdier i formlen for enhedsnormalvektoren:
$$
\overline{n} = \frac{\nabla g}{||\nabla g||} = \left(\frac{x}{{\sqrt{2z + 1}}}, \frac{y}{\sqrt{2z + 1}}, \frac{-1}{\sqrt{2z + 1}}\right)
$$
Men her peger normalvektoren i den negative z-retning, så hvis jeg vil have den til at pege i den positive z-retning skal jeg tage den negative gradient:
$$
\overline{n}_{udad} = - \frac{\nabla g}{||\nabla g||} = \left(\frac{-x}{{\sqrt{2z + 1}}}, \frac{-y}{\sqrt{2z + 1}}, \frac{1}{\sqrt{2z + 1}}\right)
$$

#### d) Eftervis resultatet fra spørgsmål b) ved at udregne fladeintegralet
Stokes teori er:
$$
\oint_{C} \overline{F} \cdot dr = \iint_{S} (\nabla \times \overline{F}) \cdot ds
$$
Hvor S er en flade der er begrænset af C med en normal vektor der har et ikke negatigt z-komponent, som der står i opgavens beskrivelse.
Først beregner jeg curl af F
$$
\begin{align*}
\nabla \times F &= 
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
a_{1}  & a_{2}  & a_{3}\\
b_{1}  & b_{2} &  b_{3}\\
\end{vmatrix}\\
&= \vec{i}(a_{2}b_{3} - a_{3}b_{2}) - \vec{j}(a_{1}b_{3} - a_{3}b_{1}) + \vec{k}(a_{1}b_{2} - a_{2}b_{1})\\
\text{Indsætter mine værdier:}\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
\frac{\partial}{\partial x}  & \frac{\partial}{\partial y} & \frac{\partial}{\partial z}\\
x  & x &  z\\
\end{vmatrix}\\
&= \vec{i}(\frac{\partial}{\partial y}(z) - \frac{\partial}{\partial z}(x)) - \vec{j}(\frac{\partial}{\partial x}(z) - \frac{\partial}{\partial z}(x)) + \vec{k}(\frac{\partial}{\partial x}(x) - \frac{\partial}{\partial y}(x))\\
&= \vec{k}(1)
\end{align*}
$$
Dermed er $\nabla \times F = [0,0,1]$

Jeg beregner fladeelementet ved at differentiere den allerede beregnet normalvektor:
$$
d \vec{S} = \vec{n} \, dS = \frac{(-x, -y, 1)}{\sqrt{2z+1}} \sqrt{1 + x^{2} + y^{2}} \, dx \, dy = (-x,-y,1) \, dx \, dy
$$

Nu beregner jeg fladeintegralet:
$$
\begin{align*}
(\nabla \times \overline{F}) \cdot dS = [0,0,1] \cdot [-x,-y,1] \cdot dS = 1 \, dx \, dy\\
\iint_{S} (\nabla \times \overline{F}) \, dS = 1 \iint_{C} dx \, dy\\
\end{align*}
$$
Her er C projektionen af S på xy-planet, som er cirklen med radius:
$$
\begin{align*}
x^{2}+y^{2} &=  16\\
r^{2} &=  x^{2} + y^{2}\\
r^{2}= 16 \Rightarrow r&= 4
\end{align*}
$$
Arealet er dermed givet ved $\pi \cdot 4^{2} = 16 \pi$:
$$
\iint_{C} 1 \, dx \, dy = 16 \pi
$$
Dermed med Stokes teori så er linjeintegralet:
$$
\oint \overline{F} \cdot d \overline{r} = 16 \pi
$$
Hvilket var det samme resultat som jeg fik i b).
## Andet eksempel
Lad S være overfladen af området beskrevet ved paraboloiden:
$$
S: z = \frac{1}{2} x^{2} + \frac{1}{2} y^{2} \quad \text{og} \quad 0 \leq z \leq 8
$$
med rand C beskrevet ved parameterfremstillingen:
$$
C: \overline{r}(\theta) = (4 \cos(\theta), 4 \sin(\theta), 8), \quad \text{hvor } 0 \leq \theta \leq 2 \pi
$$
Desuden er vektorfunktionen $\overline{F}(x,y,z)$ givet som: $\overline{F}(x,y,z) = (x,x,z)$
#### a) Skitsér området S:
![[Pasted image 20250609104913.png]]

#### b) Udregn linjeintegralet $\oint_{C} \overline{F} \cdot d \overline{r}$
Jeg har allerede parameterfremstillingen:
$$
C: \overline{r}(\theta) = (4 \cos(\theta), 4 \sin(\theta), 8), \quad \text{hvor } 0 \leq \theta \leq 2 \pi
$$
Jeg skal beregne $d \overline{r}$ ved at differentiere $\overline{r}(\theta)$:
$$
d \overline{r} = \frac{d \overline{r}}{d \theta} d \theta = (- 4 \sin(\theta), 4 \cos(\theta), 0) d \theta
$$
Dette indsætter jeg i $\overline{F}(x,y,z)$:
$$
\begin{align*}
\overline{F}(x,y,z) &=  (x,x,z)\\
\overline{F}(\overline{r}(\theta)) &= (4 \cos(\theta), 4 \cos(\theta), 8)
\end{align*}
$$
Beregner prikproduktet $\overline{F} \cdot d\overline{r}$:
$$
\begin{align*}
\overline{F} \cdot d \overline{r} &=  (4 \cos(\theta) \cdot (-4 \sin(\theta)) + (4 \cos(\theta) \cdot 4\cos(\theta)) + (8 \cdot 0))\\
&= -16 \cos(\theta) \sin(\theta) + 16 \cos^{2}(\theta)
\end{align*}
$$
Så kan jeg bruge den trigonometriske identitet $2 \cos(\theta) \sin(\theta) = \sin(2 \theta)$ og $\cos^{2}(\theta) = \frac{1 + \cos(2 \theta)}{2}$
$$
\begin{align*}
- 16 \cos(\theta) \sin(\theta) &=  - 8 \sin (2 \theta)\\
16 \cos^{2}(\theta) &= 8(1 + \cos(2 \theta))
\end{align*}
$$
Dermed får jeg at:
$$
\overline{F} \cdot d \overline{r} = -8 \sin( 2 \theta) + 8(1 + \cos(2 \theta)) = 8 -8 \sin(2 \theta) + 8 \cos(2 \theta)
$$
Nu kan jeg integrere:
$$
\oint_{C} \overline{F} \cdot d\overline{r} = \int_{0}^{2\pi} (8 - 8\sin(2 \theta) + 8 \cos(2 \theta)) \, d \theta
$$
Deler op i tre integraler:
$$
\int_{0}^{2\pi} 8 \, d \theta - \int_{0}^{2\pi} 8\sin(2 \theta) \, d \theta + \int_{0}^{2\pi} 8 \cos(2 \theta) \, d \theta
$$
$$
\int_{0}^{2\pi} 8 \, d \theta  = 16 \pi
$$
$$
\int_{0}^{2\pi} 8\sin(2 \theta) \, d \theta = 0
$$
Dette integrale er 0, fordi $\sin(2 \theta)$ har en fuld periode på $2 \pi$
$$
\int_{0}^{2\pi} 8 \cos(2 \theta) \, d \theta = 0
$$
Dette integrale er 0, fordi $\cos(2 \theta)$ har en fuld periode på $2 \pi$
Dermed bliver linjeintegralet:
$$
\oint_{C} \overline{F} \cdot d\overline{r} = 16 \pi - 0 + 0 = 16 \pi
$$
Man kunne også løse denne ved at bruge Stokes' sætning, men jeg kan se jeg bliver bedt om det senere.

#### c) Vis, at en enhedsnormalvektor til den givne overflade bliver $\overline{n} = \left(\frac{-x}{\sqrt{1 + 2z}}, \frac{-y}{\sqrt{1 + 2z}}, \frac{1}{\sqrt{1 + 2z}} \right)$ (Lidt hjælp: Definer overflade som en niveauflade og bestem normalvektoren vha. gradienten, som står vinkelret på fladen)
Overfladen $S$ er givet ved $S: z = \frac{1}{2} x^{2} + \frac{1}{2} y^{2}$. Dette kan defineres som en niveaufalde:
$$
g(x,y,z) =  \frac{1}{2} x^{2} + \frac{1}{2} y^{2} -z = 0
$$
Normalvektoren er givet ved gradienten af g:
$$
\begin{align*}
\nabla g &=  \left(\frac{\partial g}{\partial x}, \frac{\partial g}{\partial y}, \frac{\partial g}{\partial z}\right)\\
\frac{\partial g}{\partial x} = \left(\frac{1}{2}x^{2}\right)' &=  x\\
\frac{\partial g}{\partial y} = \left(\frac{1}{2}y^{2}\right)' &=  y\\
\frac{\partial g}{\partial z} = (-z)' &= -1
\end{align*}
$$
Dvs. gradienten af g er givet ved:
$$
\nabla g = (x, y, -1)
$$
Jeg beregner nu enhedsnormalvektoren af $\overline{n}$ ved at normalisere $\nabla g$:
$$
\begin{align*}
||\nabla g|| &=  \sqrt{(x)^{2} + (y)^{2} + (-1)^{2}}\\
&= \sqrt{x^{2} + y^{2} + 1}\\
\end{align*}
$$
Da $z = \frac{1}{2} x^{2} + \frac{1}{2} y^{2}$ så kan jeg udtrykke $x^{2} + y^{2}$ som $2z$:
$$
\begin{align*}
||\nabla g|| &=  \sqrt{\left(2z\right) + 1}\\
&= \sqrt{2z + 1}
\end{align*}
$$
Nu skal jeg bare indsætte de beregnede værdier i formlen for enhedsnormalvektoren:
$$
\overline{n} = \frac{\nabla g}{||\nabla g||} = \left(\frac{x}{{\sqrt{2z + 1}}}, \frac{y}{\sqrt{2z + 1}}, \frac{-1}{\sqrt{2z + 1}}\right)
$$
Men her peger normalvektoren i den negative z-retning, så hvis jeg vil have den til at pege i den positive z-retning skal jeg tage den negative gradient:
$$
\overline{n}_{udad} = - \frac{\nabla g}{||\nabla g||} = \left(\frac{-x}{{\sqrt{2z + 1}}}, \frac{-y}{\sqrt{2z + 1}}, \frac{1}{\sqrt{2z + 1}}\right)
$$

#### d) Eftervis resultatet fra spørgsmål b) ved at udregne fladeintegralet
Stokes teori er:
$$
\oint_{C} \overline{F} \cdot dr = \iint_{S} (\nabla \times \overline{F}) \cdot ds
$$
Hvor S er en flade der er begrænset af C med en normal vektor der har et ikke negatigt z-komponent, som der står i opgavens beskrivelse.
Først beregner jeg curl af F
$$
\begin{align*}
\nabla \times F &= 
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
a_{1}  & a_{2}  & a_{3}\\
b_{1}  & b_{2} &  b_{3}\\
\end{vmatrix}\\
&= \vec{i}(a_{2}b_{3} - a_{3}b_{2}) - \vec{j}(a_{1}b_{3} - a_{3}b_{1}) + \vec{k}(a_{1}b_{2} - a_{2}b_{1})\\
\text{Indsætter mine værdier:}\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
\frac{\partial}{\partial x}  & \frac{\partial}{\partial y} & \frac{\partial}{\partial z}\\
x  & x &  z\\
\end{vmatrix}\\
&= \vec{i}(\frac{\partial}{\partial y}(z) - \frac{\partial}{\partial z}(x)) - \vec{j}(\frac{\partial}{\partial x}(z) - \frac{\partial}{\partial z}(x)) + \vec{k}(\frac{\partial}{\partial x}(x) - \frac{\partial}{\partial y}(x))\\
&= \vec{k}(1)
\end{align*}
$$
Dermed er $\nabla \times F = [0,0,1]$

Jeg beregner fladeelementet ved at differentiere den allerede beregnet normalvektor:
$$
d \vec{S} = \vec{n} \, dS = \frac{(-x, -y, 1)}{\sqrt{2z+1}} \sqrt{1 + x^{2} + y^{2}} \, dx \, dy = (-x,-y,1) \, dx \, dy
$$

Nu beregner jeg fladeintegralet:
$$
\begin{align*}
(\nabla \times \overline{F}) \cdot dS = [0,0,1] \cdot [-x,-y,1] \cdot dS = 1 \, dx \, dy\\
\iint_{S} (\nabla \times \overline{F}) \, dS = 1 \iint_{C} dx \, dy\\
\end{align*}
$$
Her er C projektionen af S på xy-planet, som er cirklen med radius:
$$
\begin{align*}
x^{2}+y^{2} &=  16\\
r^{2} &=  x^{2} + y^{2}\\
r^{2}= 16 \Rightarrow r&= 4
\end{align*}
$$
Arealet er dermed givet ved $\pi \cdot 4^{2} = 16 \pi$:
$$
\iint_{C} 1 \, dx \, dy = 16 \pi
$$
Dermed med Stokes teori så er linjeintegralet:
$$
\oint \overline{F} \cdot d \overline{r} = 16 \pi
$$
Hvilket var det samme resultat som jeg fik i b).