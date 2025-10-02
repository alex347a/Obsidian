### Discrete time signal vs. continuous time signal
![[Pasted image 20251002081719.png]]
![[Pasted image 20251002081841.png]]
### Discrete time system vs. continuous time system
![[Pasted image 20251002082059.png]]
### Complex Fourier transform
![[Pasted image 20251002082221.png]]
On the left we have the time domain where the square wave consists of multiple sinusoidal waves. On the right the Laplace transform is in the frequency domain tries to decompose the imaginary parts. The red graphs are Fourier transform. The Laplace transform involves the red part of the equation $e^{- \sigma t}$. If you for example have a sinusoidal wave it will be decomposed and will be turned into a non-periodic function.
![[Pasted image 20251002082650.png]]
### Laplace transform and S domain
![[Pasted image 20251002082914.png]]
When passing through a Laplace transform you include $e^{-st}$, which will be converted from the time domain to the S-domain.
![[Pasted image 20251002083314.png]]
When $|x| < 1$ you will always converge to 0.
![[Pasted image 20251002083724.png]]
The poles are the values where the equation will become infinite, because the denominator becomes 0. This is impossible to draw, because of all the poles. Therefore we need to perform a Z-transform.
### Relation between s-domain and z-domain
![[Pasted image 20251002084151.png]]
In the s-domain there is $\omega_{s}$ gap between each value which in the z-domain would be $2 \pi$ since that is one roundtrip in the circle. When going from the s domain to z domain you go from cartesian space to pole coordinates. In the z-domain when moving $\theta + \pi$ you will be using only one point to represent all of the numbers in the s-domain that are repeated because of the $2 \pi$ space between each value. The relation between the first value and the sampling frequency is $\frac{f_{0}}{f_{s}}= \frac{1}{2}$ which is $\pi$ in the circle.

The domains are used for:
### Filter Design:
- **Analog filter poles** in s-domain (Butterworth, Chebyshev, etc.)
- **Map to z-domain** using various methods:
    - Impulse invariance: direct mapping $z = e^{sT}$
    - Bilinear transform: more complex but avoids aliasing
### Stability Analysis:
- **Continuous**: "Are all poles in the left-half plane?"
- **Discrete**: "Are all poles inside the unit circle?"

![[Pasted image 20251002085258.png]]
![[Pasted image 20251002085314.png]]
remember that $s = \sigma + j \omega$. $T$ is the sampling period. The amplitude is given by $e^{\sigma / f_{s}}$ while the angle will be given by $2 \pi \frac{f}{f_{s}}$. So z is essentially just a polar coordinate. The colours correspond to where the s-domain values will be located in the z-domain. 
![[Pasted image 20251002090054.png]]
![[Pasted image 20251002090143.png]]![[Pasted image 20251002090154.png]]
If the poles are not in the gray area the system will not be stable. So in the s-domain the values have to be negative $\sigma$ values.
![[Pasted image 20251002090320.png]]
![[Pasted image 20251002091224.png]]
![[Pasted image 20251002091800.png]]
![[Pasted image 20251002093213.png]]
ROC is the region of the value that z will converge, if z is 0 here the system will be unstable.
![[Pasted image 20251002093428.png]]
### Z-domain in discrete signal processing
![[Pasted image 20251002093707.png]]
### Z-transformation rules
![[Pasted image 20251002093919.png]]
![[Pasted image 20251002094142.png]]
### Causal sequence
Causal sequence means we only consider $n>0$ so all values of $n<0$ will be 0.

![[Pasted image 20251002094422.png]]
### Common z-transform for signal
![[Pasted image 20251002094538.png]]
![[Pasted image 20251002094904.png]]
### Transfer function in z-domain
![[Pasted image 20251002095134.png]]
![[Pasted image 20251002095157.png]]A recursive algorithm means the previous output is used to calculate the current output.
![[Pasted image 20251002095440.png]]
![[Pasted image 20251002095912.png]]
![[Pasted image 20251002095931.png]]
This shows that the function is recursive.
A slide for z-transfer was forgotten by Cheng.
$$
X(z) = \frac{z}{1-z}
$$
$$
Y = X + 0.5z^{-1} Y
$$
$$
(1 - 0.5 z^{-1}) Y = x
$$
$$
H = \frac{Y}{X} = \frac{1}{1 - 0.5 z^{-1}} = \frac{z}{z - 0.5}
$$
$$
Y = HX = \frac{z}{z-0.5} \cdot \frac{z}{1-z} = \frac{z^{2}}{(z-0.5) (1-z)}
$$
Then inverse z-transform to get $y(n)$, which comes later. [[5 Laplace transform and Z transform#Inverse z-transform]]
### Poles and zeros of a transfer function
![[Pasted image 20251002100710.png]]
![[Pasted image 20251002100736.png]]
### Pole-zero diagram
![[Pasted image 20251002100819.png]]
### Factorization
![[Pasted image 20251002101059.png]]
### Matlab functions
![[Pasted image 20251002101147.png]]
Even if you dont have the value for c (here -4) you should still type 0, because it needs the inputs.
![[Pasted image 20251002101157.png]]
![[Pasted image 20251002101208.png]]
### Inverse z-transform
![[Pasted image 20251002101247.png]]
![[Pasted image 20251002103322.png]]
### Partial fraction
![[Pasted image 20251002103653.png]]
![[Pasted image 20251002104026.png]]
![[Pasted image 20251002104225.png]]
### Matlab 
![[Pasted image 20251002105027.png]]