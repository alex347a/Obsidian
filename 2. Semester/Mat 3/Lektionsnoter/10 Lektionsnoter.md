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
\iint_{R} \left(\frac{F_{2}}{\partial x} - \frac{F_{1}}{\partial y}\right) \, dx \, dy = \oint_{C}(F_{1} \, dx + F_{2} \, dy)
$$
Eksempel
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
= \int_{0}^{2\pi}(- \sin^{3}(t) + 7\sin^{2}(t) + 2 \cos^{2} \sin(t) + 2 \cos^{2} (t)) \, dt
$$
$$
0 + 7 \pi + 0 + 2\pi
$$