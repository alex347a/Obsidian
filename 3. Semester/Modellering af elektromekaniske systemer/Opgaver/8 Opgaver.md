![[Pasted image 20251104142145.png]]
En snurre består af en cirkulær skive med radius r og masse m, der sidder på den ene ende af en stang med længden l. Stangens anden ende kan dreje sig frit om et fast punkt, O. Der ses bort fra stangens masse. Snurren udfører en præcessionsbevægelse med vandret akse under påvirkning af tyngdekraften.

a) Hvilken vinkelhastighed, $\omega_{O}$ om snurreaksen skal man give snurren, for at vinkelhastigheden ved præcessionsbevægelsen bliver $\Omega_{O} = \frac{\omega_{O}}{100}$?
$$
\Omega \omega I = \tau
$$
$\tau = l m g$
I dette tilfælde bliver det så:

$$
\Omega_{O} \omega_{O} I = l m g
$$
Ud fra inertitensoren for et svinghjul så er inertimomentet givet ved:
$$
I = \frac{1}{2} m r^{2}
$$
$$
\Omega_{O} \omega_{O} \frac{1}{2} m r^{2}  = l m g
$$
$$
\Omega_{O} = \frac{lmg}{\frac{1}{2} m r^{2}  \omega_{O}}
$$
$$
\Omega_{O}= \frac{2lg}{ r^{2}  \omega_{O}}
$$
$$
\Omega_{O} = \frac{\omega_{O}}{100}
$$
$$
\omega_{O}^{2} = \frac{200lg}{r^{2}}
$$
$$
\omega_{O} = \frac{\sqrt{200 l g}}{r^{2}}
$$
b) Find systemets samlede impulsmoment, $L_{O}$
$$
\Omega_{O} \times L_{O} = \tau
$$
Isolerer $L_{O}$:
$$
\tau \times \Omega_{O} = L_{O}
$$
$\tau = l \times m \boldsymbol{g}$
$$
l \times m \boldsymbol{g} \times \Omega_{O}  = L_{O}
$$
$$
L_{O} = l \times m \boldsymbol{g} \times \frac{\frac{\sqrt{200 l g}}{r^{2}}}{100}
$$

![[Pasted image 20251104145111.png]]
![[Pasted image 20251104140211.png]]
$$
6 \times 3
$$
$$
\begin{align*}
\begin{bmatrix}
J_{P_{1}}  &  J_{P_{2}}  &  J_{P}\\
J_{O_{1}}  &  J_{O_{2}}  &  J_{O_{3}}
\end{bmatrix}
\end{align*}
$$

$$z_{i-1} = \begin{bmatrix} 0  \\  0  \\  1\end{bmatrix}$$
$$
p_{1} = \begin{bmatrix} a_{1}\cos(p_{1})   \\  a_{1} \sin(p_{1}) \\ 0\end{bmatrix}
$$
$$
p_{2} = \begin{bmatrix} a_{1}\cos(p_{1}) + a_{2} \cos(p_{1} + p_{2})   \\  a_{1} \sin(p_{1}) + a_{2} \sin(p_{1} + p_{2}) \\ 0\end{bmatrix}
$$
$$
p_{3} = \begin{bmatrix} a_{1}\cos(p_{1}) + a_{2} \cos(p_{1} + p_{2}) + a_{3} \cos(p_{1} + p_{2} + p_{3})   \\  a_{1} \sin(p_{1}) + a_{2} \sin(p_{1} + p_{2})  + a_{3} \sin(p_{1} + p_{2} + p_{3}) \\ 0\end{bmatrix}
$$
$$
J_{P_{1}} = z_{1}\times \begin{bmatrix} a_{1}\cos(p_{1})   \\  a_{1} \sin(p_{1}) \\ 0\end{bmatrix} - 0
$$
$$
J_{P_{1}} = \begin{bmatrix}0 \\ 0  \\ 1\end{bmatrix} \times \begin{bmatrix}0 \\ 0  \\ 1\end{bmatrix}
$$
$$
J_{O_{1,2,3}} = \begin{bmatrix}0 \\ 0  \\ a_{1,2,3}\end{bmatrix}
$$
$$
\begin{align*}
\begin{bmatrix}
J_{P_{1}}  &  J_{P_{2}}  &  J_{P}\\
J_{O_{1}}  &  J_{O_{2}}  &  J_{O_{3}}
\end{bmatrix}
\end{align*}
$$