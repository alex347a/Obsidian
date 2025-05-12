Hvis man tager et legeme T med en overflade S.

### Gauss' divergenssætning.
Hvis man laver et trippelintegrale over T så er divergensen et vektorfoelt af volumen. Man kan i stedet for integrere over fladen, altså ligesom at integrere over randen
$$
\iiint_{T} \text{div } \vec{F} \, dV = \iint_{S} \vec{F} \cdot \vec{n} \,  dA
$$
$$
\begin{align*}
\vec{F} &=  (F_{1}, F_{2}, F_{3})\\
\text{div } \vec{F} &= \frac{\partial F_{1}}{\partial x} + \frac{\partial F_{2}}{\partial y} + \frac{\partial F_{3}}{\partial z}
\end{align*}
$$
#### Eksempel

$$
\begin{align*}
\iint_{S} (7 x \vec{i} - z \vec{k}) \cdot \vec{n} \, dA\\
\text{Hvor S er kuglefladen:} \quad x^{2} + y^{2} + z^{2} &= 4\\
\text{div } \vec{F} = 7 - 1 &=  6
\end{align*}
$$
Trippelintegrale:
$$
\begin{align*}
\iiint_{T} 6 \, dv = 6 \iiint_{T} \, dv
\end{align*}
$$