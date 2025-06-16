### 9.4.15 Sketch figures similar to Fig. 198. Try to interpret the field of v as a velocity field.
Sketch figures similar to Fig. 198. Try to interpret the field of v as a velocity field.
Fig 198:
![[Fig 198.png]]
$$
v = i + j
$$
Dette betyder at uanset hvor vi er så peger vektorene en hen ad x-aksen og en op ad y-aksen.
![[Pasted Images/2. Semester/Mat 3/08/08 Opgaver.pdf]]
### 9.4.17 Sketch figures similar to Fig. 198. Try to interpret the field of v as a velocity field.
Sketch figures similar to Fig. 198. Try to interpret the field of v as a velocity field.
![[Fig 198.png]]
$$
v = xj
$$
Dette betyder at vektorerne afhænger af x og peger opad, hvis $x=1$ har vektoren længden 1, hvis $x=2$ har vektoren længden 2 osv. Hvis x er negativ peger vektorerne derfor nedad.
![[Pasted Images/2. Semester/Mat 3/08/08 Opgaver.pdf#page=2|08 Opgaver]]
### 9.5.7 What curves are represented by the following? Sketch them.
What curves are represented by the following? Sketch them.
$$
[4 \cos(t), 4 \sin(t), 3t]
$$
Det svarer til en helix, fordi x og y svarer til en cirkel, mens z-værdien stiger med tiden, hvilket derfor danner en helix.
![[Pasted Images/2. Semester/Mat 3/08/08 Opgaver.pdf#page=3|08 Opgaver]]
### 9.5.13 Find a parametric representation:
Find a parametric representation:
Straight line through (2, 1, 3) in the direction of $i + 2j$
Siden det er en linje så må parameterfremstillingen se således ud:
$$
x = x_{0} + at, \quad y = y_{0} + bt, \quad z = z_{0} + ct 
$$
Indsætter de kendte koordinater:
$(x_{0}, y_{0}, z_{0}) = (2,1,3)$
$d = 1i+2j = (1,2,0)$
$$
x = 2 + 1 t, \quad y = 1 + 2t, \quad z = 3 + 0t 
$$
$$
(x,y,z) = (2,1,3) + (1,2,0)t, \quad t \space \in \space \mathbb{R}
$$
### 9.5.27 Given a curve $C: r(t)$, find a tangent vector $r'(t)$, a unit tangent vector $u'(t)$ and the tangent of $C$ at $P$. Sketch the curve and tangent.
Given a curve $C: r(t)$, find a tangent vector $r'(t)$, a unit tangent vector $u'(t)$ and the tangent of $C$ at $P$. Sketch the curve and tangent.
$$
r(t) = \left[t, \frac{1}{t}, 0\right], \quad P: \left(2, \frac{1}{2}, 0\right)
$$
$$
\begin{align*}
r'(t) &=  \left[\frac{\partial}{\partial t}t, \frac{\partial}{\partial t}\left(\frac{1}{t}\right), \frac{\partial}{\partial t}0\right]\\
&= \left[1, -\frac{1}{t^{2}}, 0\right]
\end{align*}
$$
For at finde $r'(t)$ ved punktet $P$ skal jeg beregne til hvilken t-værdi at $r(t) = P$
$$
\begin{align*}
r(t) &=  \left[t, \frac{1}{t}, 0\right] = \left[2, \frac{1}{2}, 0\right]\\
\text{Dette svarer til når } t&= 2\\
r(2) &=  \left[2, \frac{1}{2}, 0 \right] = P\\
\text{Derfor bliver r'(t)}:\\
r'(t) = \left[1, - \frac{1}{2^{2}},0\right]&= \left[1, \frac{-1}{4}, 0\right]
\end{align*}
$$
Nu finder jeg enhedsvektoren:
$$
\begin{align*}
u(t) &=  \frac{r'(t)}{|r'(t)|}\\
\text{Regner først} |r'(t)|:\\
|r'(t)| &= \sqrt{1^{2} + \left(- \frac{1}{t^{2}}\right)^{2} + 0^{2}}\\
&= \sqrt{1 + \frac{1}{t^{4}}}\\
\text{Indsætter } t &= 2\\
&=  \sqrt{1 + \frac{1}{16}}\\
&= \sqrt{\frac{17}{16}} = \frac{\sqrt{17}}{4}\\
\text{Dvs. enhedsvektoren bliver:}\\
u(2) = \frac{r'(2)}{|r'(2)|} &= \left[\frac{1}{\frac{\sqrt{17}}{4}}, \frac{\frac{-1}{4}}{\frac{\sqrt{17}}{4}},0\right]\\
&= \left[\frac{4}{\sqrt{17}}, - \frac{1}{\sqrt{17}}, 0\right]
\end{align*}
$$
Parameterfremstillingen for tangentlinjen:
$$
L(s) = P + s \cdot v
$$
Hvor $P$ er er det givne punkt, $v$ er den givne retningsvektor, hvilket er $r'(2)$. $\lambda$ er den reele parameter
$$
(x,y,z) = \left(2, \frac{1}{2}, 0 \right)+ \lambda \left(1, - \frac{1}{4}, 0\right)
$$
$$
x = 2 + \lambda, \quad y = \frac{1}{2} - \frac{\lambda}{4}, \quad z =0
$$
![[Pasted Images/2. Semester/Mat 3/08/08 Opgaver.pdf#page=4|08 Opgaver]]
Svaret i bogen er: 
$$
q(w) = \left[2+w, \frac{1}{2} - \frac{1}{4} w, 0\right]
$$
Det er det helt samme, men bogen bruger bare $\omega$ 


### 9.8.5 Find $div \space v$ and its value $P$
$$
v = x^{2}y^{2}z^{2} [x,y,z], \quad P: (3,-1,4)
$$
Jeg bruger formlen:
$$
\text{div } \vec{v} = \frac{\partial v_{1}}{\partial x} + \frac{\partial v_{2}}{\partial y} + \frac{\partial v_{3}}{\partial z}\\
$$
$$
\begin{align*}
v_{1} = x^{2}y^{2}z^{2} \cdot x = x^{3}y^{2}z^{2}\\
v_{2} = x^{2}y^{2}z^{2} \cdot y = x^{2}y^{3}z^{2}\\
v_{3} = x^{2}y^{2}z^{2} \cdot z = x^{2}y^{2}z^{3}\\
\end{align*}
$$
$$
\begin{align*}
\frac{\partial v_{1}}{\partial x} = \frac{\partial}{\partial x} (x^{3}y^{2}z^{2}) &= 3x^{2}y^{2}z^{2}\\
\frac{\partial v_{2}}{\partial y} = \frac{\partial}{\partial y} (x^{2}y^{3}z^{2}) &= 3x^{2}y^{2}z^{2}\\
\frac{\partial v_{3}}{\partial z} = \frac{\partial}{\partial z} (x^{2}y^{2}z^{3}) &= 3x^{2}y^{2}z^{2}\\
\end{align*}
$$
Dermed er 
$$
\text{div } v = 3x^{2}y^{2}z^{2}+3x^{2}y^{2}z^{2}+3x^{2}y^{2}z^{2} = 9x^{2}y^{2}z^{2}
$$
Nu kan jeg indsætte punktet $P$:
$$
\begin{align*}
\text{div } v|_{(3,-1,4)} &=  9(3^{2})(-1)^{2}(4^{2})\\
&= 9\cdot 9 \cdot 1\cdot 16\\
&= 81 \cdot 16\\
&= 810 + 81 \cdot 6\\
&= 810 + 486\\
&= 1296  
\end{align*}
$$

Dermed er svaret:
$$
\begin{align*}
\text{div } v &= 9x^{2}y^{2}z^{2}\\
P &= 1296  
\end{align*}

$$

### 9.8.11 Incompressible flow. Show that the flow with velocity $v = yi$ is incompressible. Show that the particles that at time $t = 0$ are in the cube whose faces are portions of the planes $x=0, x=1, y=0, y=1, z=0, z=1$ occupy at $t = 1$ the volume 1.
Incompressible flow. Show that the flow with velocity $v = yi$ is incompressible. Show that the particles that at time $t = 0$ are in the cube whose faces are portions of the planes $x=0, x=1, y=0, y=1, z=0, z=1$ occupy at $t = 1$ the volume 1.
Hvis det er incompressible så må det betyde at:
$$
\text{div } v = \frac{\partial v_{1}}{\partial x} + \frac{\partial v_{2}}{\partial y} + \frac{\partial v_{3}}{\partial z} = 0
$$
Jeg får givet at:
$$
v = yi
$$
Ud fra $i$ antager jeg at y er x-koordinatet, så:
$$
v = (y,0,0)
$$
Divergensen vil i så fald være givet ved:
$$
\begin{align*}
\text{div } \vec{v} &= \frac{\partial v_{1}}{\partial x} + \frac{\partial v_{2}}{\partial y} + \frac{\partial v_{3}}{\partial z}\\
&= \frac{\partial v_{1}}{\partial x}+ \frac{0}{\partial y} + \frac{0}{\partial z}\\
&= 0
\end{align*}
$$
Hver partikel bevæger sig med:
$$
\begin{align*}
\frac{dx}{dt} &= y\\
\frac{dy}{dt} &=  0\\
\frac{dz}{dt} &= 0\\
\text{Så:}\\
y(t) = y(0), \quad z(t) &=  0\\
\text{Ved } t &= 1\\
x = x_{0}+y_{0}, \quad y= y_{0}, \quad z &=  z_{0}\\
\text{Ved } t&= 0\\
0 \leq x_{0} &\leq 1\\
0 \leq y_{0} &\leq 1\\
0 \leq z_{0} &\leq 1\\
\text{Ved } t &= 1\\
x_{0} + y_{0} = [0, 1+1] &= [0,2]\\
y_{0} &= [0,1]\\
z_{0} &= [0,1]\\
\end{align*}
$$
For en given y-værdi så vil x gå fra $x_{0} = 0 \rightarrow x = y$ til $x_{0} = 1 \rightarrow x = 1+y$. Derfor bliver volumeintralet:
$$
\begin{align*}
V &=  \int_{z=0} ^{1} \int_{y=0} ^{1} \int_{x=y} ^{x=1+y} \, dx \, dy \, dz\\
\text{Starter med det inderste integrale}\\
\int_{x=y} ^{x=1+y} \, dx \, dy \, dz &= (1+y) - y\\
&= 1\\
\text{Indsætter svaret i de resterende integraler}\\
\int_{z=0} ^{1} \int_{y=0} ^{1} 1 \, dz \, dy = \int_{y=0} ^{1} (1) \cdot 1 \, dy \\
&= \int_{0}^{1} = 1
\end{align*}
$$
Dermed har partiklerne volumen 1 ved tiden $t=1$

Svaret bør være:
$$
\begin{align*}
[v_{1},v_{2}, v_{3}] = r' = [x',y',z'] = [y,0,0], z' = 0, z = c_{3}, y'=0, y=c_{2}\\
x'=y=c_{2}, x=c_{2}t+c_{1}
\end{align*}
$$
Dermed når t går fra 0 til 1 så transformere "flowet" cuben til en parallelrøret volumen på 1.
### 9.8.17 Calculate $\nabla ^{2} f$ by Eq. (3). Check by direct differentiation.
Indicate when (3) is simpler. Show the details of your work.
Calculate $\nabla ^{2} f$ by Eq. (3). Check by direct differentiation.
Indicate when (3) is simpler. Show the details of your work.
$f = \ln(x^{2} + y^{2})$

For reference, this is equation (3):
$$
\text{div} (\text{grad } f) = \nabla^{2} f
$$

Først bruger jeg formlen ovenover. Derefter prøver jeg direkte at differentiere det.

$$
\begin{align*}
\nabla f = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}\right) &=  \left(\frac{2x}{x^{2} + y^{2}} , \frac{2y}{x^{2} + y^{2}}\right)\\
\nabla ^{2} f&= \frac{\partial}{\partial x} \left(\frac{2x}{x^{2}+y^{2}}\right) + \frac{\partial}{\partial y} \left(\frac{2y}{x^{2}+y^{2}}\right)  
\end{align*}
$$
Jeg regner videre på udtrykkene hver for sig, først x:
$$
\begin{align*}
\frac{\partial}{\partial x} \left(\frac{2x}{x^{2}+y^{2}}\right) &= \frac{2(x^{2}+y^{2}) - 2x(2x)}{(x^{2}+y^{2})^{2}}\\
&= \frac{2(x^{2}+y^{2} - 2x^{2})}{(x^{2}+y^{2})^{2}}\\
&= \frac{2(-x^{2}+y^{2})}{(x^{2}+y^{2})^{2}}
\end{align*}
$$
Nu for y:
$$
\begin{align*}
\frac{\partial}{\partial y} \left(\frac{2y}{x^{2}+y^{2}}\right) &= \frac{2(x^{2}+y^{2}) - 2y(2y)}{(x^{2}+y^{2})^{2}}\\
&= \frac{2(x^{2}+y^{2} - 2y^{2})}{(x^{2}+y^{2})^{2}}\\
&= \frac{2(x^{2}-y^{2})}{(x^{2}+y^{2})^{2}}
\end{align*}
$$
Dermed får jeg:
$$
\nabla f^{2} = \frac{2(-x^{2}+y^{2})}{(x^{2}+y^{2})^{2}} + \frac{2(x^{2}-y^{2})}{(x^{2}+y^{2})^{2}} = 0
$$
Jeg prøver nu med direkte differentiering:
$$
\begin{align*}
\nabla ^{2} f &= \frac{\partial^{2} f}{\partial x^{2}} + \frac{\partial^{2} f}{\partial y ^{2}}\\
\frac{\partial f}{\partial x} = \frac{2x}{x^{2}+y^{2}}, \quad \frac{\partial^{2} f}{\partial x^{2}} &= \frac{2 (x^{2}+y^{2}) - 4x^{2}}{(x^{2}+y^{2})^{2}} = \frac{2(-x^{2} + y^{2})}{(x^{2}+y^{2})^{2}}\\
\frac{\partial f}{\partial y} = \frac{2y}{x^{2}+y^{2}}, \quad \frac{\partial^{2} f}{\partial x^{2}} &= \frac{2 (x^{2}+y^{2}) - 4y^{2}}{(x^{2}+y^{2})^{2}} = \frac{2(x^{2} - y^{2})}{(x^{2}+y^{2})^{2}}\\
\nabla f^{2} = \frac{2(-x^{2}+y^{2})}{(x^{2}+y^{2})^{2}} + \frac{2(x^{2}-y^{2})}{(x^{2}+y^{2})^{2}} &=  0
\end{align*}
$$
Begge metoder giver det samme svar, men at bruge formel 3 kunne jeg forestille mig er simplere når man allerede kender gradienten på forhånd, eller hvis man nu bruger andre typer af koordinater, såsom polære eller sfæriske.

### 9.9.9 Let $v$ be the velocity vector of a steady fluid flow. Is the flow irrotational? Incompressible? Find the streamlines (the paths of the particles).
Let $v$ be the velocity vector of a steady fluid flow. Is the flow irrotational? Incompressible? Find the streamlines (the paths of the particles).
$$
v = [0, 3z^{2}, 0]
$$
For at tjekke for irrotational skal jeg beregne curl:
$$
\begin{align*}
\nabla \times \vec{v} &=  
\begin{vmatrix}
\hat{i} & \hat{j} & \hat{k}\\
\partial_{x} & \partial_{y} & \partial_{z}\\
0 & 3z^{2} & 0\\
\end{vmatrix}\\
&= \hat{i} \left(\frac{\partial}{\partial y}(0) - \frac{\partial}{\partial z}(3z^{2})\right) - \hat{j} \left(\frac{\partial}{\partial x}\left(0\right) - \frac{\partial}{\partial z}(0)\right) + \hat{k} \left(\frac{\partial}{\partial x}\left(3z^{2}\right) - \frac{\partial}{\partial y}(0)\right)\\
&= \hat{i}(0-6z) - \hat{j}(0-0) + \hat{k}(0-0)\\
&=  [-6z,0,0]
\end{align*}
$$
Siden curl ikke er 0, så betyder det at flowet **IKKE** er irrotational. Medmindre $z=0$ selvfølgelig.

Nu tjekker jeg for divergens (incrompessibility)
$$
\nabla \cdot \vec{v} = \frac{\partial v_{x}}{\partial x} + \frac{\partial v_{y}}{\partial y} + \frac{\partial v_{z}}{\partial z}
$$
Siden $\frac{\partial}{\partial y}(6z^{2}) = 0$ fordi det er differentieret mht. til y og resten er 0, så bliver svaret:
$$
\frac{\partial v_{x}}{\partial x} + \frac{\partial v_{y}}{\partial y} + \frac{\partial v_{z}}{\partial z} = 0+0+0=0
$$
Dvs. flowet er incompressible, fordi divergensen er 0.

Til sidst skulle jeg finde streamlines'ne.
Formlen for streamlines:
$$
\frac{dx}{v_{x}}=\frac{dy}{v_{y}}=\frac{dz}{v_{z}}
$$
Dvs. jeg skal integrere for at finde henholdsvis x,y og z, efter at have indsat værdierne for v.
Siden $v=[0,3z^{2}, 0]$:
$$
\begin{align*}
\frac{dx}{0} = \frac{dy}{3z^{2}} &= \frac{dz}{0}\\
dx = 0 \rightarrow x &=  c_{1}\\
dy = 3z^{2} dt = 3c_{3}^{2} \, dt \rightarrow y &= 3c_{3}^{2} + c_{2}\\
dz = 0 \rightarrow z &= c_{3}
\end{align*}
$$


Svaret bliver:
$$
\begin{align*}
\text{curl } v = [-6z,0,0], \text{incompressible, }\\
v=r', = [x',y',z'] = [0,3z^{2},0], x = c_{1}, z= c_{3}, y' = 3z^{2} = 3c_{3}^{2}, y = 3c_{3}^{2} t + c_{2}
\end{align*}
$$
### 9.9.11 Let $v$ be the velocity vector of a steady fluid flow. Is the flow irrotational? Incompressible? Find the streamlines (the paths of the particles).
Let $v$ be the velocity vector of a steady fluid flow. Is the flow irrotational? Incompressible? Find the streamlines (the paths of the particles).
$$
v = [y, -2x, 0]
$$
Ligesom opgaven før, så tjekker jeg for irrotational ved at beregne curl:
$$
\begin{align*}
\nabla \times \vec{v} &=  
\begin{vmatrix}
\hat{i} & \hat{j} & \hat{k}\\
\partial_{x} & \partial_{y} & \partial_{z}\\
y & -2x & 0\\
\end{vmatrix}\\
&= \hat{i} \left(\frac{\partial}{\partial y}(0) - \frac{\partial}{\partial z}(-2x)\right) - \hat{j} \left(\frac{\partial}{\partial x}\left(0\right) - \frac{\partial}{\partial z}(y)\right) + \hat{k} \left(\frac{\partial}{\partial x}\left(-2x\right) - \frac{\partial}{\partial y}(y)\right)\\
&= \hat{i}(0-0) - \hat{j}(0-0) + \hat{k}(-2-1)\\
&=  [0,0,-3]
\end{align*}
$$
Siden curl ikke er 0 så er flowet ikke irrotational.

Nu tjekker jeg for divergens (incrompessibility)
$$
\begin{align*}
\nabla \cdot \vec{v} &=  \frac{\partial v_{x}}{\partial x} + \frac{\partial v_{y}}{\partial y} + \frac{\partial v_{z}}{\partial z}\\
&= \frac{\partial}{\partial x}(y) + \frac{\partial}{\partial y}(-2x) + \frac{\partial}{\partial z}(0)\\
&= 0+0+0\\
&= 0
\end{align*}
$$
Da divergensen er 0 så betyder det at flowet er incompressible.

Til sidst skulle jeg finde streamlines'ne.
Formlen for streamlines:
$$
\frac{dx}{v_{x}}=\frac{dy}{v_{y}}=\frac{dz}{v_{z}}
$$
Dvs. jeg skal integrere for at finde henholdsvis x,y og z, efter at have indsat værdierne for v.
Siden $v = [y, -2x, 0]$:
$$
\begin{align*}
\frac{dx}{y}=\frac{dy}{-2x}&= \frac{dz}{0}\\\\
\frac{dx}{y} &=  \frac{dy}{-2x}\\
y \, dy &= -2x \, dx\\
\text{integrerer begge sider:}\\
\frac{1}{2}y^{2} + c_{1} &= -x^{2} + c_{2}\\
\frac{1}{2}y^{2}+x^{2} &=  C\\\\
dz = 0 \rightarrow z &=  c_{3}
\end{align*}
$$

Svaret bliver:
flowet er ikke irrotational, flowet er incompressible og streamlines'ne er givet ved $\frac{1}{2}y^{2} + x^{2} = C, z = c_{3}$

Svaret i bogen er:
$$
\text{curl } v = [0,0,-3], \text{incompressible, } x'=y, y'=-2x, 2xx' + yy' = 0, x^{2}+ \frac{1}{2}y^{2} = c, z = c_{3}
$$
Det lader til bogen har gættet på en løsning til differentialligningen og beregnet ud fra det, men jeg får det samme svar ved separation af variable.