### 10.3.5
Describe the region of integration and evaluate.
$$
\int_{0}^{1} \int_{x^{2}}^{x} (1-2xy) \, dy \, dx
$$
I det ydre integrale går x fra 0 til 1, og i det indre integrale går for hver x fra 0 til 1, så går y fra $x^{2}$ til x

For hver x mellem 0 og 1, er y begrænset under parablen $y = x^{2}$ og over linjen $y = x$ 
For at finde skæringspunktet skal jeg se hvornår $x^{2} = x$.
Da $x^{2} = x$ så må det betyde at $x^{2} - x = 0$
Dermed er løsningerne 0 og 1.
Dermed er linjen $y=x$ ovenover parablen $y=x^{2}$ over hele intervallet.

$$
\begin{align*}
\int_{0}^{1} \int_{x^{2}}^{x} (1-2xy) \, dy \, dx &= \int_{0}^{1} dx
\left(\int_{x^{2}}^{x} 1 \, dy - \int_{x^{2}} ^{x} 2xy \, dy\right) \\
\text{Udregner det højre integrale:}\\
\int_{x^{2}} ^{x} 2xy \, dy = [x y^{2}]_{x^{2}}^{x} &= x\cdot x^{2} - (x \cdot x^{4})\\
&= x^{3} - x^{5}\\
\text{udregner det venstre integrale:}\\
\int_{0}^{1} 1  \, dx = [x]_{x^{2}} ^{x} &=  x - x^{2}\\
\text{Sætter de to resultater ind:}\\
x - x^{2} - (x^{3} - x^{5}) &= x-x^{2} - x^{3} + x^{5}\\
\text{Indsætter i det ydre integrale}\\
\int_{0}^{1} x - x^{2} - x^{3} + x^{5} \, dx &= \left[\frac{1}{2} x^{2} - \frac{1}{3} x^{3} - \frac{1}{4} x^{4} + \frac{1}{6} x^{6}\right]_{0}^{1}\\
&= \frac{1}{2} - \frac{1}{3} - \frac{1}{4} + \frac{1}{6}\\
&= \frac{6}{12} - \frac{4}{12} - \frac{3}{12} + \frac{2}{12}\\
&= \underline{\underline{\frac{1}{12}}}
\end{align*}
$$
### 10.3.9
Find the volume of the given region in space
The region beneath $z = 4x^{2} + 9y^{2}$ and above the rectangle with vertices $(0, 0)$, $(3, 0)$, $(3, 2)$, $(0, 2)$ in the xy-plane.

Ud fra rektanglet så går x fra 0 til 3 og y går fra 0 til 2. Det er regionen under den 3D ellipse (elliptiske paraboloide) $z = 4x^{2} + 9y^{2}$
Volumen under en flade $z = f(x,y)$ og over regionen $R$ i xy-planet er givet ved:
$$
V = \iint_{R} f(x,y) \, dA
$$
I dette tilfælde er $f(x,y) = 4x^{2} + 9y^{2}$
R er rektanglet, hvor $0 \leq x \leq 3$ og $0 \leq y \leq 2$

Dermed bliver dobbeltintegralet:
$$
\begin{align*}
V &= \int_{x=0} ^{3}  \,dx \int_{y=0} ^{2} (4x^{2} + 9y^{2}) \, dy\\
\text{Regner det indre integrale:}\\
\int_{y=0} ^{2} (4x^{2} + 9y^{2}) \, dy &=  \int_{y=0} ^{2} 4x^{2} \, dy + \int_{y=0} ^{2} 9y^{2} \, dy\\
\text{Starter med det venstre integrale:}\\
\int_{y=0} ^{2} 4x^{2} \, dy = [4x^{2}y]_{y=0}^{2} &=  8x^{2}\\
\int_{y=0} ^{2} 9y^{2} \, dy = \left[\frac{1}{3} y^{3}\right]_{y=0}^{2} = 3 \cdot 2^{3} &= 24\\
\text{Samler de to integraler:}\\
\int_{y=0} ^{2} 4x^{2} \, dy + \int_{y=0} ^{2} 9y^{2} \, dy &= 8x^{2} + 24\\
\text{Indsætter i det ydre integrale:}\\
\int_{x=0} ^{3} 8x^{2} + 24 \, dx = \int_{x=0} ^{3} 8x^{2} \, dx + \int_{x=0} ^{3} 24 \, dx\\
\text{Starter med det venstre integrale:}\\
\int_{x=0} ^{3} 8x^{2} \, dx = \left[\frac{8}{3} x^{3}\right]_{x=0}^{3} = \frac{8}{3} \cdot 27 =  \frac{216}{3} &= 72\\
\int_{x=0} ^{3} 24 \, dx = [24x]_{x=0} ^{3} = [24 \cdot 3] &= 72\\
\text{Sætter de to resultater sammen}\\
\int_{x=0} ^{3} 8x^{2} \, dx + \int_{x=0} ^{3} 24 \, dx &= 72 + 72\\
&= 144
\end{align*}
$$

### 10.3.15
Find the center of gravity $(\overline{x}, \overline{y})$ of a mass of density $f(x,y) = 1$ in the given region R.
![[10.3.15 opgavetegning.png]]
Formlen for en cirkel er $x^{2} + y^{2} = r^{2}$
Formlen for en halvcirkel er derfor: $y = \sqrt{r^{2} - x^{2}}$ når $-r \leq x \leq r$ og $y \geq 0$
Dvs. regionen R er:
$$
R = ((x,y) |- r \leq x \leq r, \quad 0 \leq y \leq \sqrt{r^{2} -x^{2}})
$$
tyngdepunktet ($\overline{x}, \overline{y}$) er givet ved:
$$
\begin{align*}
\overline{x} &=  \frac{1}{A} \iint_{R} x \, dA \\
\overline{y} &=  \frac{1}{A} \iint_{R} y \, dA
\end{align*}
$$
Hvor A er arealet af regionen R.

Arealet for en halvcirkel er givet ved: $A = \frac{1}{2} \pi r^{2}$
Fordi en halvcirkel er symmetrisk omkring y-aksen så bliver integralet over x nødt til at være 0, fordi alle punkterne i den første kvadrant har et tilsvarende punkt for de negative x-værdier, så alle punkterne går ud med hinanden:
$$
\overline{x} = \frac{1}{A} \iint_{R} x \, dA = 0
$$
Siden det kun er en halvcirkel så gælder det samme ikke for $\overline{y}$ og derfor skal jeg beregne det:
$$
\iint_{R} y \, dA = \int_{-r}^{r} \left(\int_{0} ^{\sqrt{r^{2}-x^{2}}}y \, dy\right) \, dx
$$
Starter med det indre integrale:
$$
\begin{align*}
\int_{0} ^{\sqrt{r^{2}-x^{2}}}y \, dy = \left[\frac{1}{2} y^{2}\right]_{0} ^{\sqrt{r^{2}-x^{2}}} = \frac{r^{2} - x^{2}}{2}
\end{align*}
$$
Indsætter i det ydre integrale:
$$
\begin{align*}
\int_{-r}^{r} \frac{r^{2} - x^{2}}{2} \, dx &= \frac{1}{2} \left(\int_{-r}^{r} r^{2} \, dx - \int_{-r}^{r} x^{2} \, dx\right)
\end{align*}
$$
Start

### 10.4.1
Evaluate $\int_{C} F(r) \cdot dr$ counterclockwise around the boundary C of the region R by Green's theorem, where
$$y
F = [y,-x], C \text{ the circle } x^{2} + y^{2} = \frac{1}{4}
$$

### 10.4.3
Evaluate $\int_{C} F(r) \cdot dr$ counterclockwise around the boundary C of the region R by Green's theorem, where
$$
F = [x^{2} e^{y}, y^{2} e^{x}], r \text{ the rectangle with vertices } (0,0), (2,0), (2,3), (0,3)
$$

### 10.4.9
Evaluate $\int_{C} F(r) \cdot dr$ counterclockwise around the boundary C of the region R by Green's theorem, where
$$
F = [e^{\frac{y}{x}}, e^{y} \ln(x) + 2x], R: 1 + x^{4} \leq y \leq 2
$$

### 10.4.13
Using (9), find the value of $\int_{C} \frac{\partial w}{\partial n} \, ds$ taken counterclockwise over the boundary C of the region R.
$$
w = \cosh (x), \quad \text{R the triangle with vertices } (0,0), (4,2), (0,2). 
$$

### 10.4.17
Using (9), find the value of $\int_{C} \frac{\partial w}{\partial n} \, ds$ taken counterclockwise over the boundary C of the region R.
$$
w = x^{3} - y^{3}, \quad 0 \leq y \leq x^{2}, \quad |x| \leq 2
$$

### 10.4.19
Show that $w = e^{x} \sin(y)$ satisfies Laplace's equation $\nabla^{2} w = 0$ and, using (12), integrate $w(\frac{\partial w}{\partial n})$ counterclockwise around the boundary curve C of the rectangle $0 \leq x \leq 2, \quad 0 \leq y \leq 5$ 