![[Pasted image 20251014222940.png]]
To check if the systems are stable the absolute value of ALL of the poles must be above 1

$$
H_{1}(z) = \frac{z}{z^{2} - 3z + 2}
$$
Here I can factorize:
$$
z^{2} - 3z + 2 = (z - 1) (z - 2)
$$
Therefore the roots are 1 and 2, which means the system is UNSTABLE
$$
H_{2}(z) = \frac{z-2}{z^{2} - 1.344z + 0.9025}
$$
$$
z = \frac{-b \pm \sqrt{b^{2} - 4ac}}{2a}
$$
$$
\begin{align*}
a &=  1\\
b &= -1.344\\
c &= 0.9025 
\end{align*}
$$
$$
z = \frac{1.344 \pm \sqrt{(-1.344)^{2} - 4 \cdot 0.9025}}{2}
$$
$$
z = \frac{1.344 \pm \sqrt{1.808 - 3.61}}{2}
$$
$$
z = \frac{1.344 \pm 1.343 j}{2} = 0.672 \pm 0.6715 j
$$
These are COMPLEX CONJUGATE POLES:
$$
\sqrt{0.672^{2} - 0.6715} \approx 0.95
$$
Since the value is below 1 the system is STABLE.


$$
H_{3}(z) = \frac{z^{2} + 0.04z}{z^{2} - 1.556z + 1.21}
$$
$$
H_{4}(s) = \frac{s}{s^{2} + 1}
$$
Factorization:
$$
s^{2} + 1 = (s - 1) (s-1)
$$
$$
H_{5}(s) = \frac{s + 2}{s^{2} - 1.344s + 0.9025}
$$