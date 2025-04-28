Areal = 
$$
\int_{c}^{d} \int_{p(y)}^{q(y)} dx \, dy
$$
Volumen =
$$
\iint z \, dx \, dy
$$
### Green's sætning
Transformere et fladeintegrale til et linjeintegrale

Greens: R er et lukket område i xy-planet
To kontinuerte funktioner $F_{1}(x,y)$ og $F_{2}(x,y)$
$$
\iint_{R} \left(\frac{\partial F_{2}}{\partial x} - \frac{\partial F_{1}}{\partial y}\right) \, dx \, dy = \oint_{C}(F_{1} \, dx + F_{2} \, dy)
$$
#### Eksempel
$$
F_{1}(x,y) = y²  - 7y, \quad F_{2}(x,y) = 2xy+2x
$$
vs: 
$$
\frac{\partial F_{2}}{\partial x} = 2y + 2 \quad \text{og } \frac{\partial F_{1}}{\partial y} = 2y - 7
$$
$$
\frac{\partial F_{2}}{\partial x} - \frac{\partial F_{1}}{\partial y} = 2y+2- (2y - 7) = 9
$$
$$
\iint_{R} 9 \, dx \, dy = 9\iint_{R} \, dx \, dy = 9 \pi
$$
hs: 
$$
\oint_{C} \left(F_{1} \cdot \frac{dx}{dt} + F_{2} \cdot \frac{dy}{dt}\right) \, dt = \oint_{C} (F_{1} \cdot x' + F_{2} \cdot y') \, dt
$$
Fordi det er en cirkel så er det smart at gøre det i polære koordinater.

$$
\begin{align*}
x &=  r \cdot \cos(t) \rightarrow x' = - r \sin(t)\\
y &=  r \cdot \sin(t) \rightarrow y' = r \cos(t)
\end{align*}
$$
$$
\int_{0}^{2\pi} ((r^{2} \sin^{2} (t) - 7 \cdot r \cdot \sin(t)) (- r \sin(t) ) + 2 \cdot r \cdot \cos(t) \cdot r \sin(t) + 2 \cdot r \cos(t)) \cdot r \cos(t)) \, dt
$$
$$
= \int_{0}^{2\pi}(- \sin^{3}(t) + 7\sin^{2}(t) + 2 \cos^{2}(t) \sin(t) + 2 \cos^{2} (t)) \, dt
$$
$$
0 + 7 \pi + 0 + 2\pi
$$
### Areal
sæt $F_{1} = 0$ og $F_{2} = x$

$$
\begin{align*}
\iint_{R} \left(\frac{\partial F_{2}}{\partial x} - \frac{\partial F_{1}}{\partial y}\right) \, dx \, dy\\
\iint_{R}(1-0) \, dx \, dy = A  &=  \oint_{C} x \, dy \\
\text{sæt } F_{1} = -y \text{ og } F_{2} &=  0\\
\iint_{R} \left(\frac{\partial F_{2}}{\partial x} - \frac{\partial F_{1}}{\partial y}\right) \, dx \, dy\\
\iint_{R} (0+1) \, dx \, dy = A &=  \oint_{C} -y \, dx\\
\oint_{C} x \, du - \oint y \, dx =  A+A &=  2A\\
A &= \frac{1}{2} \oint_{C} (x \, dy - y \, dx) \quad \text{Planimeter}
\end{align*}
$$
### Laplacian
$$
\nabla^{2} = \Delta = \left(\frac{\partial^{2} w}{\partial x^{2}} + \frac{\partial^{2} w}{\partial y^{2}}\right) = 0
$$
$$
\iint_{R} \nabla^{2} w \, dx \, dy = \int \frac{\partial w}{\partial n} \, dn
$$
n er egentlig en normalvektor, se fig 240, men den skrives ikke sådan i formlen.

$$
\nabla w \cdot \overline{n} = 
\begin{pmatrix}
\frac{\partial w}{\partial x} \\ 
\frac{\partial w}{\partial y} \\ 
\end{pmatrix}
\cdot
\begin{pmatrix}
\frac{dy}{ds} \\
- \frac{dx}{ds} 
\end{pmatrix}
=
\frac{\partial w}{\partial n}
$$
Den har den modsatte retning af tværvektoren?????? eller sådan noget

#### Eksempel
Her er det ikke C'erne vi regner på, det er de stykker som vi tager integralerne af. Det er derfor vi slutter med at plusse alle I'erne, som er integrales værdier.
$$
\begin{align*}
w &=  (x + 3y)^{2} + 3x\\
R &= x^{2} + y^{2} \leq 16, \quad x \leq 0, \quad y \geq 0\\
\oint_{C} &=  \frac{\partial w}{\partial n} \, ds\\
\frac{\partial w}{\partial x} &= 2(x+3y) + 3\\
\frac{\partial w}{\partial y} &= 2(x+3y) \cdot 3\\
C_{1}: \int_{0}^{4} 
\begin{pmatrix}
6y+3\\
18y
\end{pmatrix}
\cdot
\begin{pmatrix}
1\\
0
\end{pmatrix}
\, dy 
=
\int_{0} ^{4} (6y + 3) \, dy &=  [3y^{2} + 3y]_{0}^{4} \\
= 48+12 &= 60\\
\text{Starter med } C_{3}:\\
C_{3}: y = 0 \quad \text{ og } ds &= dx\\
\int_{-4}^{0}
\begin{pmatrix}
2x + 3\\
6x
\end{pmatrix}
\cdot
\begin{pmatrix}
0\\
-1
\end{pmatrix}
\, dx = \int_{-4} ^{0} -6x \, dx &= [-3x^{2}]_{-4}^{0}\\
&= 48\\
\text{Nu til } C_{2}\\
\text{Polære koordinater:}\\
\text{Da }r &= 4:\\
x &= 4\cos(t)\\
y &=  4\sin(t)\\
t &\in \left[\frac{\pi}{2} , \pi\right]\\
ds &= 4 \cdot dt\\
\overline{r} &= (4 \cos(t), 4 \sin(t))\\
\overline{r}' &= (-4 \sin(t), 4\cos(t))\\
\overline{n} &= (4 \cos(t), 4 \sin(t))\\
I_{2} &= \int_{\frac{\pi}{2}} ^{\pi}
\begin{pmatrix}
2 (4 (\cos(t) + 3 \cdot 4 \sin(t)) + 3)\\
2 (4 \cos(t)) + 3 \cdot 4 \sin(t) \cdot 3)
\end{pmatrix}
\cdot
\begin{pmatrix}
4 \cos(t)\\
4 \sin(t)
\end{pmatrix}\\
424
&= 4 \int_\frac{\pi}{2} ^{\pi} (8 + 64 \sin^{2}(t) + 48 \sin(t) \cos(t) + 3 \cos(t)) \, dt\\
&= 4 \int_\frac{\pi}{2}^{\pi} 8 + 64 \frac{1}{2} (1 - \cos(2t)) + 48 \sin(t) \cos(t) + 3 \cos(t) \, dt\\
&= 80 \pi - 108\\
I_{1} + I_{2} + I_{3} &= 60 + 48 + 80 \pi - 108\\
&= 80 \pi
\end{align*}
$$
$$
C_{1}: x = 0, \quad ds = dy
$$