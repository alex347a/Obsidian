### 10.5.3
Familiarize yourself with parametric representations of important surfaces by deriving a representation (1), by finding the parameter curves (curves $u = const$ and $v = const$) of the surface and a normal vector $N = r_{u} \times r_{v}$ of the surface. Show the details in your work. 

For reference (1) is the equation:
$z = f(x,y) \quad \text{ or } \quad g(x,y,z) = 0$.

Cone $r(u,v) = [u \cos(v), u \sin(v), cu]$

Jeg skal altså
1. Derive a representation of the surface in the form $z=f(x,y)$ or $g(x,y,z)=0$.
2. Find the parameter curves where $u=constant$ and $v=constant$.
3. Compute the normal vector $\vec{N} = \vec{r}_{u} \times \vec{r}_{v}$ to the surface.

Først udleder jeg representationen af fladen:
$$
\begin{align*}
g(x,y,z) &= 0\\
x &= u \cos(v)\\
y &= u \sin(v)\\
z&= cu\\
\text{Formlen for en kegle er:}\\
x^{2} + y^{2} &= a^{2} z^{2}\\
\text{Indsætter mine værdier:}\\
x^{2} + y^{2} = u^{2} \cos^{2}(v) + u^{2} \sin^{2}(v) = u^{2}(\cos^{2}(v) + \sin^{2}(v)) &= u^{2}\\
\text{Siden } z&= cu:\\
u &= \frac{z}{c}\\
\text{Substituerer ind i den forrige formel:}\\
x^{2}+y^{2} &= \left(\frac{z}{c}\right)^{2}\\
x^{2}+y^{2}- \frac{z^{2}}{c^{2}} &= 0\\
x^{2}+y^{2}- \frac{z^{2}}{c^{2}} = 0 \Rightarrow z = c \sqrt{x^{2} + y^{2}}
\end{align*}
$$
Nu skal jeg finde parameterkurverne:
$$
\begin{align*}
\text{For } u &=  u_{0}\\
x &= u_{0} \cos(v)\\
y &= u_{0} \sin(v)\\
z &= cu_{0}\\
z &= cu_{0} \text{ beskriver en cirkel i planen med radius } u_{0}\\
\text{Som er centreret på z-aksen}\\
\text{For } v &= v_{0}\\
x &= u \cos(v_{0})\\
y &= u \sin(v_{0})\\
z &= cu\\
u &= \frac{x}{\cos(v_{0})} = \frac{y}{\sin(v_{0})} = \frac{z}{c}\\
\text{Dette er en lige linje igennem origo idet når } u &= 0, x = y = z = 0\\
\end{align*}
$$
Nu skal jeg beregne normalvektoren:
$$
\begin{align*}
\vec{N} &=  \vec{r}_{u} \times \vec{r}_{v}\\
r (u,v) &= (u \cos(v), u \sin(v), cu)\\
\vec{r}_{u} = \left(\frac{\partial x}{\partial u}, \frac{\partial y}{\partial u}, \frac{\partial z}{\partial u}\right) &=  (\cos(v), \sin(v), c)\\
\vec{r}_{v} = \left(\frac{\partial x}{\partial v}, \frac{\partial y}{\partial v}, \frac{\partial z}{\partial v}\right) &=  (-u \sin(v), u \cos(v), 0)\\
\text{Siden jeg ikke skal finde unit vectoren}\\
\text{er der ingen grund til at gøre brug af}\\
\vec{n} = \frac{\text{grad g}}{\text{|grad g|}} &=  \frac{\nabla g}{|\nabla g|}\\
\text{Jeg skal bare beregne normalvektoren } \vec{N}:\\
\vec{N} &=  \vec{r}_{u} \times \vec{r}_{v}\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
\cos(v)  & \sin(v) & c\\
- u \sin(v) & u \cos(v) & 0
\end{vmatrix}\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
a_{1}  & a_{2}  & a_{3}\\
b_{1}  & b_{2} &  b_{3}\\
\end{vmatrix} &= \vec{i}(a_{2}b_{3} - a_{3}b_{2}) - \vec{j}(a_{1}b_{3} - a_{3}b_{1}) + \vec{k}(a_{1}b_{2} - a_{2}b_{1})\\
\vec{N} &= \vec{i} (\sin(v) \cdot 0 - c \cdot u \cos(v)) - \vec{j}(\cos(v) \cdot 0 - c \cdot(-u \sin(v))) + \vec{k} (\cos(v) \cdot u \cos(v) - \sin(v) \cdot(- u \sin(v))\\
&= \vec{i}(-cu \cos(v)) - \vec{j}(cu \sin(v)) + \vec{k}(u \cos^{2}(v) + \sin^{2}(v))\\
&= [-cu \cos(v), -cu \sin(v), u]\\
\vec{N} &=  \underline{\underline{[-cu \cos(v), -cu \sin(v), u]}}\\
\text{Kan også skrives:}\\
\vec{N} &= u[-c \cos(v), -c \sin(v), 1]
\end{align*}
$$
Svaret i bogen er:
$$
z = c \sqrt{x^{2} + y^{2}}, \quad \text{ circles, straight lines}, \quad [-cu \cos(v), - cu \sin(v), u]
$$
### 10.5.4
Familiarize yourself with parametric representations of important surfaces by deriving a representation (1), by finding the parameter curves (curves $u = const$ and $v = const$) of the surface and a normal vector $N = r_{u} \times r_{v}$ of the surface. Show the details in your work. 

For reference (1) is the equation:
$z = f(x,y) \quad \text{ or } \quad g(x,y,z) = 0$.

Elliptic cylinder $r(u,v) = [a \cos(v), b \sin(v), u]$.

Jeg skal altså
1. Derive a representation of the surface in the form $z=f(x,y)$ or $g(x,y,z)=0$.
2. Find the parameter curves where $u=constant$ and $v=constant$.
3. Compute the normal vector $\vec{N} = \vec{r}_{u} \times \vec{r}_{v}$ to the surface.

Først udleder jeg representationen af fladen:
$$
\begin{align*}
g(x,y,z) &= 0\\
x &= a \cos(v)\\
y &= b \sin(v)\\
z&= u\\
\text{Formlen for en elliptisk cylinder er:}\\
\frac{x^{2}}{a^{2}} + \frac{y^{2}}{b^{2}} &= 1\\
\text{Indsætter mine værdier:}\\
\frac{(a \cos(v))^{2}}{a^{2}} + \frac{(b \sin(v))^{2}}{b^{2}} = \cos^{2}(v) + \sin^{2}(v) &= 1\\
\text{Dvs. } z &= u \text{ er en cylinder der udstrækker sig uendeligt langs z-aksen}
\end{align*}
$$
Nu skal jeg finde parameterkurverne:
$$
\begin{align*}
\text{For } u &=  u_{0}\\
x &= a \cos(v)\\
y &= b \sin(v)\\
z &= u_{0}\\
z &= u_{0} \text{ en ellipse centreret på z-aksen} \\
\text{med halvakserne a (langs x) og b (langs y) }\\
\text{For } v &= v_{0}\\
x &= a \cos(v_{0})\\
y &= b \sin(v_{0})\\
z &= u\\
\text{Dette er en lige linje parallel med z-aksen}\\
\end{align*}
$$
Nu skal jeg beregne normalvektoren:
$$
\begin{align*}
\vec{N} &=  \vec{r}_{u} \times \vec{r}_{v}\\
\vec{r}_{u} = \left(\frac{\partial x}{\partial u}, \frac{\partial y}{\partial u}, \frac{\partial z}{\partial u}\right) &= (0, 0, 1)\\
\vec{r}_{v} = \left(\frac{\partial x}{\partial v}, \frac{\partial y}{\partial v}, \frac{\partial z}{\partial v}\right) &= (-a \sin(v), b \cos(v), 0)\\
\text{Siden jeg ikke skal finde unit vectoren}\\
\text{er der ingen grund til at gøre brug af}\\
\vec{n} = \frac{\text{grad g}}{\text{|grad g|}} &=  \frac{\nabla g}{|\nabla g|}\\
\text{Jeg skal bare beregne normalvektoren } \vec{N}:\\
\vec{N} &=  \vec{r}_{u} \times \vec{r}_{v}\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
0  &  0  &  1\\
-a \sin(v)  &  b \cos(v)  &  0\\
\end{vmatrix}\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
a_{1}  & a_{2}  & a_{3}\\
b_{1}  & b_{2} &  b_{3}\\
\end{vmatrix} &= \vec{i}(a_{2}b_{3} - a_{3}b_{2}) - \vec{j}(a_{1}b_{3} - a_{3}b_{1}) + \vec{k}(a_{1}b_{2} - a_{2}b_{1})\\
\vec{N} &= \vec{i}(0 \cdot 0 - 1 \cdot b \cos(v)) - \vec{j}(0 \cdot 0 - 1 \cdot (- a \sin(v))) + \vec{k}(0 \cdot b \cos(v) - 0 \cdot (-a \sin(v))\\
&= \vec{i}(-b \cos(v)) - \vec{j}(-(- a \sin(v))) + 0\\
&= (-b \cos(v), - a \sin(v), 0)
\end{align*}
$$
### 10.5.19
Find a normal vector. The answer gives one representation; there are many. Sketch the surface and parameter curves.

Hyperbolic cylinder $x^{2} - y^{2} = 1$

$$
\begin{align*}
x^{2} - y^{2} &= 1\\
\text{Jeg kan parameteriser funktionen til:}\\
\cosh^{2}(v) - \sinh^{2}(v) &= 1\\
\vec{r} (u,v) &= (\cosh(v), \sinh(v), u)\\
\vec{N} &= \vec{r}_{u} \times \vec{r}_{v}\\
\vec{r}_{u} = \left(\frac{\partial x}{\partial u}, \frac{\partial y}{\partial u}, \frac{\partial z}{\partial u}\right) &= (0, 0, 1)\\
\vec{r}_{v} = \left(\frac{\partial x}{\partial v}, \frac{\partial y}{\partial v}, \frac{\partial z}{\partial v}\right) &= (\sinh(v), \cosh(v), 0)\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
a_{1}  & a_{2}  & a_{3}\\
b_{1}  & b_{2} &  b_{3}\\
\end{vmatrix} &= \vec{i}(a_{2}b_{3} - a_{3}b_{2}) - \vec{j}(a_{1}b_{3} - a_{3}b_{1}) + \vec{k}(a_{1}b_{2} - a_{2}b_{1})\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
0  &  0  &  1\\
\sinh(v)  &  \cosh(v)  &  0\\
\end{vmatrix} \\
&= \vec{i}(0 \cdot 0 - 1 \cdot \cosh(v)) - \vec{j}(0 \cdot 0 - 1 \cdot \sinh(v)) + \vec{k}(0 \cdot \cosh(v) - 0 \cdot \sinh(v))\\
&= \vec{i}(\cosh(v)) - \vec{j}(-\sinh(v)) + 0\\
&= (-\cosh(v), \sinh(v), 0)
\end{align*}
$$
Mangler at tegne den.

Svaret i bogen er:
$$
[\cosh u, \sinh u, v], \quad [\cosh u, - \sinh u, 0]
$$
### 10.6.7
Evaluate the integral for the given data. Describe the kind of surface. Show the details of your work.

$$
F = [0, \sin(y), \cos(z)], \quad \text{ S the cylinder } x = y^{2}, \quad \text{ where } 0 \leq y \leq \frac{\pi}{4} \quad \text{ and } \quad 0 \leq z \leq y
$$

Først parameteriserer jeg fladen:
$$
\begin{align*}
u = y, \quad \text{ og } \quad v &=  z\\
r (u,v) = [u^{2}, u, v], \quad 0 \leq u &\leq \frac{\pi}{4}, \quad 0 \leq v \leq u\\
\vec{r}_{u} = \frac{\partial r}{\partial u} = [2u,1,0], \quad \vec{r}_{u} = \frac{\partial r}{\partial v} &= [0,0,1]\\\\
\text{Nu skal jeg beregne krydsproduktet:}\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
a_{1}  & a_{2}  & a_{3}\\
b_{1}  & b_{2} &  b_{3}\\
\end{vmatrix} &= \vec{i}(a_{2}b_{3} - a_{3}b_{2}) - \vec{j}(a_{1}b_{3} - a_{3}b_{1}) + \vec{k}(a_{1}b_{2} - a_{2}b_{1})\\
\vec{r}_{u} \times \vec{r}_{v} &= 
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
2u  & 1  & 0\\
0  & 0  & 1\\
\end{vmatrix}\\
&= \vec{i}(1 \cdot 1 - 0 \cdot 0) - \vec{j} (2u \cdot 1 - 0 \cdot 0) + \vec{k} (2u \cdot 0 - 1 \cdot 0)\\
&= \vec{i}(1) - \vec{j}(2u) + 0\\
&= [1,-2u,0]\\
\text{Substituerer } y &=  u \quad \text{ og } \quad z =  v\\
F &=  [0, \sin(u), \cos(v)]\\
\text{Nu skal jeg beregne fluxintegralet:}\\
\iint_{S} F  \cdot (\vec{r}_{u} \times \vec{r}_{v}) \, dA &=  \int_{0} ^ {\frac{\pi}{4}} \int_{0}^{u} F \cdot [1,-2,0] \, dv \, du\\
\text{Beregner prikproduktet:}\\
F \cdot (\vec{r}_{u} \times \vec{r}_{v}) &= 0 \cdot 1 + \sin(u) \cdot (-2u) + \cos(v) \cdot 0 \\
&= -2 \sin(u)\\
\text{Integralet bliver derfor:}\\
\int_{0}^{\frac{\pi}{4}} \int_{0} ^{u} - 2u \sin(u) \, dv \, du \\
\text{Beregner det indre integrale:}\\
\int_{0} ^{u} - 2u \sin(u) \, dv &= [-2u \sin(u) \cdot v]_{0}^{u}\\
&= -2u^{2} \sin(u)\\
\text{Indsætter i det ydre integrale:}\\
\int_{0}^{\frac{\pi}{4}} -2u^{2} \sin(u) \, du \\
\text{Bruger integration i dele:}\\
t = u^{2}, dt &=  2u \, du, \\
dv = \sin(u) \, du, v &=  - \cos(u)\\
\int u^{2} \sin(u) \, du &= - u^{2} \cos(u) + 2 \int u \cos(u) \, du\\
\text{Integration i dele igen:}\\
\text{For }\int u \cos(u) \, du,\\
t = u, dt = du, dv &=  \cos(u) \, du, v = \sin(u)\\
\int u \cos(u) \, du = u \sin(u) - \int \sin(u) \, du &= u \sin(u) + \cos(u)\\
\text{Kombinerer resultaterne:}\\
\int u \cos(u) \, du &=  -u^{2} \cos(u) + 2 u \sin(u) + 2 \cos(u) + C\\
\text{Jeg husker at gange med -2, da jeg havde:}\\
-2u^{2} \sin(u) \text{ og ikke bare } u^{2}\\
\int u \cos(u) \, du &=  2u^{2} \cos(u) - 4 u \sin(u) - 4 \cos(u) + C\\
\text{Nu kan jeg evaluere over intervallet af det orignale integrale:}\\
\left[- \left(\frac{\pi}{4}\right)^{2} \cos\left(\frac{\pi}{4}\right) + 2 \cdot \frac{\pi}{4} \sin\left(\frac{\pi}{4}\right) + 2 \cos\left(\frac{\pi}{4}\right)\right] - [0 + 0 + 2 \cos(0)]\\
\text{Da } \cos\left(\frac{\pi}{4}\right) = \sin\left(\frac{\pi}{4}\right) &= \frac{\sqrt{2}}{2}:\\
&= 2 \frac{\pi^{2}}{16} \cdot \frac{\sqrt{2}}{2} + \frac{\pi}{2} \cdot \frac{\sqrt{2}}{2} + \sqrt{2} - 2
\end{align*}
$$
### 10.6.15
Evaluate these integrals for the following data. Indicate the kind of surface. Show the details.

$$
G = (1 + 9xz)^{\frac{3}{2}}, \quad S: r = [u,v,u^{3}], \quad 0 \leq u \leq 1, \quad -2 \leq v \leq 2
$$