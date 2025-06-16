### 10.1.4 Calculate $\int_{C} F(r) \cdot dr$ for the given data. If F is a force, this gives the work done by the force in the displacement along C. Show the details.
$$
F = [xy, x^{2}y^{2}], C \text{ from } (2,0) \text{ straight to } (0,2)
$$
For at regne $\int_{C} F(r) \cdot dr$ regner jeg først $F \cdot \frac{dr}{dt}$ og derefter integrerer det. Start med $\frac{dr}{dt}$:
For en lige linje er den standarde parameterfremstilling:
$$
\begin{align*}
r(t) = (1-t)(2,0) + t(0,2) &=  (2-2t, 2t), \quad t \space \in \space [0,1]\\
x(t) = 2-2t, \quad y(t) &= 2t\\
\frac{dr}{dt} = \left(\frac{dx}{dt}, \frac{dy}{dt}\right) &= (-2,2)
\end{align*}
$$
Nu til $F$:
$$
\begin{align*}
F(x(t), y(t)) &=  [x(t)y(t), x(t)^{2}y(t)^{2}]\\
x(t)y(t) =  (2-2t)(2t) &= 4t-4t^{2}\\
x(t)^{2} y(t)^{2} = (2-2t)^{2} (2t)^{2} \text{bruger 2. kvadratsætning }\\
(a-b)^{2} &= a^{2}+b^{2}-2ab\\
(4-8t + 4t^{2})(4t^{2}) &= 16t^{2} -32t^{3} + 16t^{4}
\end{align*}
$$
Dvs.
$$
F(x(t),y(t)) = [4t-4t^{2}, 16t^{2}-32t^{3}+16t^{4}]
$$
$$
\begin{align*}
F \cdot \frac{dr}{dt} &=  (4t-4t^{2})(-2) + (16t^{2}-32t^{3}+16t^{4})(2)\\
&= -8t+8t^{2}+32t^{2}-64t^{3}+32t^{4}\\
&= -8t+40t^{2}-64t^{3}+32t^{4}
\end{align*}
$$
Nu til integrationen:
$$
\int_{C} F \cdot dr = \int_{0}^{1} (-8t+40t^{2}-64t^{3}+32t^{4}) \, dt
$$
Jeg integrerer hvert led for sig:
$$
\begin{align*}
\int_{0}^{1} -8t \, dt = -4\\
\int_{0}^{1} 40t^{2} \, dt = \frac{40}{3}\\
\int_{0}^{1} -64t^{3} \, dt = -16\\
\int_{0}^{1} 32t^{4} \, dt = \frac{32}{5}
\end{align*}
$$
$$
\begin{align*}
&= -4 + \frac{40}{3} - 16 + \frac{32}{5}\\
&= -20 + \frac{200}{15} + \frac{96}{15}\\
&= \frac{-300}{15} + \frac{296}{15}\\
&= \frac{-4}{15}
\end{align*}
$$
Dermed bliver svaret:
$$
\int_{C} F \cdot dr = - \frac{4}{15}
$$

### 10.1.5 Calculate $\int_{C} F(r) \cdot dr$ for the given data. If F is a force, this gives the work done by the force in the displacement along C. Show the details.
$$
F = [xy, x^{2}y^{2}], C \text{ the quarter-circle from } (2,0) \text{ to } (0,2) \text{ with center} (0,0)
$$
For at regne $\int_{C} F(r) \cdot dr$ regner jeg først $F \cdot \frac{dr}{dt}$ og derefter integrerer det. Start med $\frac{dr}{dt}$:
Denne gang er det derimod en kvartcirkel som har en radius på 2 og er centreret i orgio. Derfor er parameterfremstillingen givet ved:
$$
x(t) = 2 \cos(t), \quad y(t) = 2 \sin(t), t \in \left[0, \frac{\pi}{2}\right]
$$
$$
\frac{dr}{dt} = \left(\frac{dx}{dt}, \frac{dy}{dt}\right) = (-2 \sin(t), 2 \cos(t))
$$
Nu til $F$:
$$
\begin{align*}
F(x(t), y(t)) &=  [x(t)y(t), x(t)^{2}y(t)^{2}]\\
x(t)y(t) = 2 \cos(t) 2 \sin(t) &= 4 \cos(t) \sin(t)\\
x(t)^{2}y(t)^{2} &= (2 \cos(t))^{2} (2 \sin(t))^{2}\\
&= 4 \cos^{2}(t) 4 \sin^{2}(t)\\
&= 16 \cos^{2}(t) \sin^{2}(t)\\
\end{align*}
$$
Dvs:
$$
F(x(t),y(t)) = [4 \cos(t) \sin(t), 16 \cos^{2}(t) \sin^{2}(t)]
$$
$$
\begin{align*}
F \cdot \frac{dr}{dt} &=  (4 \cos(t) \sin(t)) (-2 \sin(t)) +  (16 \cos^{2}(t) \sin^{2}(t)) (2 \cos(t))\\
&= -8 \cos(t) \sin^{2}(t) + 32 \cos^{3}(t) \sin^{2}(t)\\
\end{align*}
$$
Nu til integralet:
$$
\begin{align*}
\int_{C} F \cdot dr &=  \int_{0}^{\frac{\pi}{2}} -8 \cos(t) \sin^{2}(t) + 32 \cos^{3}(t) \sin^{2}(t) \, dt\\
\text{Jeg omskriver for at gøre det lettere at integrere}\\
&= \int_{0}^{\frac{\pi}{2}} \cos(t) \sin^{2}(t) (-8 +32 \cos^{2}(t))\, dt\\
\text{substituer:}\\
u = \sin(t), \quad du &= \cos(t) \, dt\\
\text{grænserne bliver:}\\
t = 0 \rightarrow\sin(0) = 0, \quad t= \frac{\pi}{2} \rightarrow \sin\left(\frac{\pi}{2}\right)&= 1\\
\text{Siden } \cos^{2}+\sin^{2} &=  1\\
\cos^{2} &=  1 - \sin^{2}\\
\text{Siden } \sin^{2} &=  u^{2}\\
\cos^{2} &= 1-u^{2}\\
&= \int_{0}^{1}u^{2}(-8 + 32 (1-u^{2})) \, du\\
&= \int_{0}^{1}u^{2}(-8 + 32-32u^{2})) \, du\\
&= \int_{0}^{1}u^{2}(24-32u^{2})) \, du\\
&= \int_{0}^{1} 24u^{2}-32u^{4} \, du\\
&= 24 \int_{0}^{1}u^{2} \, du - 32 \int_{0}^{1} u^{4} \, du\\
&= 24\cdot \frac{1}{3} - 32 \cdot \frac{1}{5}\\
&= 8 - \frac{32}{5}\\
&= \frac{40}{5} - \frac{32}{5}\\
&= \frac{8}{5}\\
\end{align*}
$$
Dermed er $\int_{C} F \cdot dr$:
$$
\int_{C} F \cdot dr = \frac{8}{5}
$$
Svaret i bogen er:
$$
r = [2 \cos(t), 2 \sin(t)], 0 \leq t \leq \frac{\pi}{2}; \quad \frac{8}{5}
$$

10.1.17 Evaluate them with $F$ or $f$ and $C$ as follows.
$$
F = [x+y, y+z, z+x], C:r = [4 \cos(t), \sin(t), 0], \quad 0 \leq t \leq \pi
$$
Jeg har altså:
$$
r(t) = [x(t), y(t), z(t)] = [4 \cos(t), \sin(t), 0]
$$
$$
\frac{dr}{dt} = [-4 \sin(t), \cos(t), 0]
$$
Nu til $F$:
$$
\begin{align*}
F(x(t), y(t), z(t)) &= [x+y, y+z, z+x] = [4 \cos(t) + \sin(t), \sin(t) + 0, 0 + 4 \cos(t)]\\
&= [4 \cos(t) + \sin(t), \sin(t), 4 \cos(t)]\\
\end{align*}
$$
$$
\begin{align*}
F(t) \cdot \frac{dr}{dt} &=  (4 \cos(t) + \sin(t)) (-4 \sin(t)) + (\sin(t))(\cos(t)) + (4 \cos(t))(0)\\
&= -16 \cos(t) \sin(t) - 4 \sin^{2}(t) + \sin(t) \cos(t)\\
&= (-16 + 1) \cos(t) \sin(t) - 4 \sin^{2}(t)\\
&= -15 \cos(t) \sin(t) - 4 \sin^{2}(t)
\end{align*}
$$
Nu til integrationen:
$$
\begin{align*}
\int_{0} ^{\pi} (-15 \cos(t) \sin(t) - 4 \sin^{2}(t)) \, dt\\
&= -15 \int_{0} ^{\pi} \cos(t) \sin(t) \, dt - 4 \int_{0} ^{\pi} \sin^{2}(t) \, dt\\
\text{Starter med det første integrale:}\\
-15 \int_{0}^{\pi} \cos(t) \sin(t) \, dt\\
\text{integration i dele}:\\
\int u \, dv &= uv - \int v \, du\\
u = \sin(t) \rightarrow du &=  \cos(t) \, dt\\
dv = \cos(t) \, dt \rightarrow v &= \sin(t)\\
\int \sin(t) \cos(t) \, dt &= \sin(t) \cdot \sin(t) - \int \sin(t) \cdot \cos(t) \, dt\\
&= \sin^{2}(t) - \int \sin(t) \cos(t) \, dt\\
\text{Jeg får det samme integrale som før igen}\\
\text{Hvis jeg kalder } I &=  \int \sin(t) \cos(t) \, dt\\
I = \sin^{2}(t) - I \rightarrow 2I &=  \sin^{2}(t)\\
I &= \frac{1}{2} \sin^{2}(t)\\
\text{Så integralet bliver:}\\
I &= \frac{1}{2} \sin^{2}(t) + c\\
\int_{0}^{\pi} \sin(t) \cos(t) \, dt = [\frac{1}{2} \sin^{2}(t)]_{0} ^{\pi}\\
&= \frac{1}{2} \sin^{2}(\pi) - \frac{1}{2} \sin^{2}(0)\\
&= 0 - 0\\
&= 0
\end{align*}
$$
Så det første integrale bliver 0, hvilket også giver god mening symmetrisk idet funktionen er ulige over et symmetrisk interval.
Andet integrale:
$$
\begin{align*}
-4 \int_{0} ^{\pi} \sin^{2}(t) \, dt\\
\text{Fra calculus bogen er denne formel}:\\
\int \sin^{2}(x) \, dx &=  \frac{x}{2} - \frac{1}{4} \sin(2x) + c\\
-4 \int_{0} ^{\pi} \sin^{2}(t) \, dt &= -4 \left[\frac{t}{2} - \frac{1}{4} \sin(2t)\right]_{0}^{\pi}\\
&= -4 \left(\frac{\pi}{2} - \frac{1}{4} \sin\left(2 \pi\right) - \frac{\pi}{2} - \frac{1}{4} \sin(2\cdot 0)\right)\\
&= -4 \left(\frac{\pi}{2} - 0 - \frac{0}{2} - 0\right)\\
&= -4 \left(\frac{\pi}{2}\right)\\
&= -2 \pi
\end{align*}
$$
Dermed bliver svaret:
$$
\int_{C} F \cdot dr = - 2 \pi
$$

Svaret burde være:
$$
[4 \cos(t), + \sin(t), \sin(t), 4 \cos(t)], [2,2,0] 
$$
Det lader til bogen tager fejl, for det giver ingen mening, hvorfor der er et komma for meget.

10.2.3 Show that the form under the integral sign is exact in the plane and evaluate the
integral. Show the details of your work.

$$
\int_{(\frac{\pi}{2}, \pi)} ^{(\pi,0)} \left(\frac{1}{2} \cos\left(\frac{1}{2} x\right) \cos(2y) \, dx - 2 \sin\left(\frac{1}{2} x\right) \sin(2y) \, dy\right)
$$

For at tjekke om formen er eksakt:
$$
\begin{align*}
\frac{\partial F_{1}}{\partial y} = \frac{\partial F_{2}}{\partial x}\\
\frac{\partial F_{1}}{\partial y} = \frac{1}{2} \cos\left(\frac{1}{2} x\right)\cdot (- 2 \sin(2y)) &= - \cos\left( \frac{1}{2} x\right) \sin(2y)\\
\frac{\partial F_{2}}{\partial x} = -2 \cdot \left(\frac{1}{2} \cos\left(\frac{1}{2}x\right)\right) \cdot \sin(2y)&= - \cos\left( \frac{1}{2} x\right) \sin(2y)\\
\end{align*}
$$
For at se om dette er sandt integrerer jeg den ene:
$$
\begin{align*}
f(x,y)=\int \frac{1}{2} \cos\left(\frac{1}{2} x\right) \cos(2y) \, dx &= \cos(2 y) \cdot \int \frac{1}{2} \cos\left(\frac{1}{2} x\right)\, dx\\
&= \sin\left(\frac{1}{2} x\right)+ c\\
f(x,y) &= \cos(2y) \cdot \sin\left(\frac{1}{2} x\right) + C(y)\\
\text{Dette skulle svarer til:}\\
\frac{\partial f}{\partial y} &= - 2 \sin\left(\frac{1}{2} x\right) \sin(2y)\\
\text{Da } C'(y) = 0 \rightarrow C(y) &= \text{ konstant}\\
f(x,y) &= \cos(2y) \cdot \sin\left(\frac{1}{2} x\right)
\end{align*}
$$
Jeg skulle nu bestemme integralet:
Siden formen var eksakt kan jeg bruge formlen:
$$
\begin{align*}
\int_{A}^{B} (F_{1} \, dx + F_{2} \, dy) &= f(B) - f(A)\\
\text{Hvor:}\\
A &= (\frac{\pi}{2}, \pi)\\
B &= (\pi, 0)\\\\
f(\pi,0) = \cos(0) \cdot \sin\left(\frac{1}{2} \pi\right)= 1\cdot 1 &= 1\\
f\left(\frac{\pi}{2}, \pi\right)= \cos(2 \pi) \cdot \sin\left(\frac{1}{2} \frac{\pi}{2}\right)= 1 \cdot \sin\left(\frac{\pi}{4}\right) = \frac{\sqrt{2}}{2}\\
\int_{A}^{B} (F_{1} \, dx + F_{2} \, dy) &= 1 - \frac{\sqrt{2}}{2} 
\end{align*}
$$
Så svaret bliver:
$$
\int_{A}^{B} (F_{1} \, dx + F_{2} \, dy) = 1 - \frac{\sqrt{2}}{2} 
$$

Svaret i bogen er:
$$
\sin\left(\frac{1}{2} x\right) \cos(2y), \quad 1 - \frac{1}{\sqrt{2}}
$$