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
\int_{0}^{1} \int_{x^{2}}^{x} (1-2xy) \, dy \, dx &= \int_{0}^{1} 1 \, dx \int_{x^{2}} ^{x} 2xy \, dy \\
\int_{x^{2}} ^{x} 2xy \, dy = [x y^{2}]_{x^{2}}^{x} &= x\cdot x^{2} - (x \cdot x^{4})\\
&= x^{3} - x^{5}\\
\text{indsætter resultatet i det ydre integrale:}\\
\int_{0}^{1} 1 \cdot (x^{3} - x^{5}) \, dy &= 
\end{align*}
$$
### 10.3.9
Find the volume of the given region in space
The region beneath $z = 4x^{2} + 9y^{2}$ and above the rectangle with vertices $(0, 0)$, $(3, 0)$, $(3, 2)$, $(0, 2)$ in the xy-plane.

### 10.3.15
Find the center of gravity $(\overline{x}, \overline{y})$ of a mass of density $f(x,y) = 1$ in the given region R.
![[10.3.15 opgavetegning.png]]

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