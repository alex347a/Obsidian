### 10.7.9
Evaluate the surface integral $\iint F \cdot n \, dA$ by the divergence theorem. Show the details.

$F = [x^{2}, 0, z^{2}]$, S the surface of the box $|x| \leq 1, |y| \leq 3, 0 \leq z \leq 2$

$$
\iiint_{T} \text{div } \vec{F} \, dV = \iint_{S} \vec{F} \cdot \vec{n} \,  dA
$$
$$
\begin{align*}
\vec{F} &=  (F_{1}, F_{2}, F_{3})\\
\text{div } \vec{F} &= \frac{\partial F_{1}}{\partial x} + \frac{\partial F_{2}}{\partial y} + \frac{\partial F_{3}}{\partial z}\\
&= \frac{\partial}{\partial x}(x^{2}) + \frac{\partial}{\partial y}(0) + \frac{\partial}{\partial z}(z^{2})\\
&= 2x + 0 + 2z\\
&= 2x + 2z
\end{align*}
$$
Volumen er defineret til at have grænserne:
$$
x \in [-1,1], \quad y \in [-3,3], \quad z \in[0,2]
$$
Derfor bliver integralet:
$$
\iiint_{V} (2x +2z) \, dV = \int_{x=-1}^{1} \, dx \int_{y=-3} ^{3} \, dy \int_{z=0}^{2} (2x + 2z) \, dz
$$
Jeg starter med det inderste integrale:
$$
\begin{align*}
\int_{z=0}^{2} (2x + 2z) \, dz &= [2xz + z^{2}]_{z=0}^{2}\\
&= (4x + 2^{2}) - (0)\\
&= 4x + 4
\end{align*}
$$
Nu indsætter jeg dette i integralet mht. y:
$$
\begin{align*}
\int_{y=-3} ^{3} (4x + 4) \,dy &=  (4x + 4) \int_{y=-3} ^{3} \,dy\\
&=  (4x + 4) \cdot (3 - (-3))\\
&= (4x + 4) \cdot 6\\
&= (24x + 24)
\end{align*}
$$
Nu indsætter jeg dette i integralet mht. x:
$$
\begin{align*}
\int_{x=-1}^{1} (24x + 24) \, dx &= [12x^{2} + 24x]_{x=-1}^{1}\\
&= 12 + 24 - (12 - 24)\\
&= 36 - (-12)\\
&= 48
\end{align*}
$$
Derfor blev:
$$
\begin{align*}
\text{div } F &=  2x + 2z\\
\iint F \cdot n \, dA &= 48
\end{align*}
$$
Svaret i bogen er:
$$
\text{div } F = 2x + 2z, 48
$$
### 10.7.13
Evaluate the surface integral $\iint F \cdot n \, dA$ by the divergence theorem. Show the details.

$F = [\sin(y), \cos(x), \cos(z)]$, S, the surface of $x^{2} + y^{2} \leq 4, \quad |z| \leq 2$ (a cylinder and two disks!)

Svaret i bogen er:
$$
\text{div } F = -\sin(z), 0
$$
### 10.7.20
Given a mass of density 1 in a region T of space, find the moment of intertia about the x-axis
$$
\iint_{T} (y^{2} + z^{2}) \, dx \, dy \, dz
$$
The ball $x^{2} + y^{2} + z^{2} \leq a^{2}$
### 10.7.21
Given a mass of density 1 in a region T of space, find the moment of intertia about the x-axis
$$
I_{x} = \iiint_{T} (y^{2} + z^{2}) \, dx \, dy \, dz
$$
The cylinder $y^{2} + z^{2} \leq a^{2}, \quad 0 \leq x \leq h$

Svaret i bogen er:
$$
\left(\frac{a^{4}}{4}\right)\cdot 2\pi \cdot h = h a^{4} \frac{\pi}{2}
$$
### 10.9.13

### 10.9.15