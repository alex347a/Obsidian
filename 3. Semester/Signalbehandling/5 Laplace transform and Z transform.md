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
When going from the s domain to z domain you go from cartesian space to pole coordinates.

The domains are used for:
### Filter Design:
- **Analog filter poles** in s-domain (Butterworth, Chebyshev, etc.)
- **Map to z-domain** using various methods:
    - Impulse invariance: direct mapping $z = e^{sT}$
    - Bilinear transform: more complex but avoids aliasing
### Stability Analysis:
- **Continuous**: "Are all poles in the left-half plane?"
- **Discrete**: "Are all poles inside the unit circle?"