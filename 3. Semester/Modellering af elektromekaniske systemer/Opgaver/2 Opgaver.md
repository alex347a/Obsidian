Betragt et masse-fjeder-dæmper system beskrevet ved
$$
m \ddot{x} = - kx - b \dot{x} + f 
$$
Opskriv en overføringsfunktion $G(s)$ for systemet med input $f$ og output $x$

$$
G(s) = \frac{X(s)}{F(s)}
$$
$$
s^{2} X(s) = - \frac{k}{m} X(s)  - \frac{b}{m}X(s) + \frac{1}{m} F(s)
$$
$$
X(s)(ms^{2} + bs + k ) = F(s)
$$
$$
G(s) = \frac{X(s)}{F(s)} = \frac{1}{ms^{2} + bs + k}
$$

$$
\begin{align*}
\mathcal{L^{-1}}\left(\frac{1}{s^{2} + 0.2 s + 0.01}\right) = 2 \cdot \frac{\omega}{s^{2} + \omega^{2}}\\
\omega = 5\\
&= \frac{10}{s^{2} + 25}
\end{align*}
$$