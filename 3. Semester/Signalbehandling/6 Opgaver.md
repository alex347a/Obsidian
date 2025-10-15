![[Pasted image 20251014222940.png]]
To check if the systems are stable the absolute value of ALL of the poles must be above 1

$$
H_{1}(z) = \frac{z}{z^{2} - 3z + 2}
$$
Here I can factorize:
$$
z^{2} - 3z + 2 = (z - 1) (z - 2) = 0
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
z = \frac{-b \pm \sqrt{b^{2} - 4ac}}{2a}
$$
$$
\begin{align*}
a &=  1\\
b &= -1.556\\
c &= 1.21 
\end{align*}
$$
$$
z = \frac{1.556 \pm \sqrt{(-1.556)^{2} - 4 \cdot 1.21}}{2}
$$
$$
\frac{1.556 \pm \sqrt{-2.418864}}{2}
$$
$$
z = 0.778 \pm 0.7776349 j
$$
These are COMPLEX CONJUGATE POLES:
$$
\sqrt{ 0.778^{2} \pm 0.7776349^{2}} = 1.10
$$
Since the value is above 1 the system is UNSTABLE.
$$
H_{4}(s) = \frac{s}{s^{2} + 1}
$$
Factorization:
$$
s^{2} + 1 = 0
$$
$$s = \pm j$$
Since  $Re(s) = 0$ That means the system is MARGINALLY STABLE.
$$
H_{5}(s) = \frac{s + 2}{s^{2} - 1.344s + 0.9025}
$$
This is the exact same as the second one i did, but just in the s-plane this time:
$$
s = \frac{1.344 \pm 1.343 j}{2} = 0.672 \pm 0.6715 j
$$
These are COMPLEX CONJUGATE POLES:
$$
\sqrt{0.672^{2} - 0.6715} \approx 0.95
$$
Since the value is below 1 the system is STABLE.
![[Pasted image 20251015114143.png]]
1. 
   
   
2. In order to determine whether the system is stable I have to calculate the poles:
I use the quadratic formula:
$$
z = \frac{-b \pm \sqrt{b^{2} - 4ac}}{2a}
$$
$$
\begin{align*}
a &=  1\\
b &= 0.8485\\
c &= 0.36 
\end{align*}
$$
$$
z = \frac{-0.8485 \pm \sqrt{0.8485^{2} - 4 \cdot 0.36}}{2}
$$
$$
z = \frac{-0.8485 \pm \sqrt{0.72 - 1.44}}{2}
$$
$$
z = \frac{-0.8485 \pm \sqrt{-0.72}}{2}
$$
$$
z = \frac{-0.8485 \pm 0.8485 j}{2}
$$
$$
z = -0.42425 \pm 0.42425 j
$$
These are COMPLEX CONJUGATES:
$$
\sqrt{(-0.42425)^{2} \pm 0.42425^{2}} = 0.6
$$
Since the poles magnitude are below 1 that means the system is stable.

3. Plot the impulse response of the system with $n = 0:15$ (try different functions / ways)
![[Pasted image 20251015122700.png]]
![[Pasted image 20251015122712.png]]
![[Pasted image 20251015122721.png]]

![[Pasted image 20251015122747.png]]
1. Determine at which frequencies the gain of H(f) is maximum and minimum.
   The maximum and minimum gain is determined by the 
   
2. Determine the phase (using graphical methods) of H(f) at a frequency of 2 kHz.
   
   
3. Plot a Bode diagram of H(z), and check if the above results are correct.
   
   