Fourier transform
$$
X(\omega) = \mathcal{F}(x(t)) = \int_{-\infty}^{\infty} x(t) e^{-j \omega t} \, dt
$$
Inverse Fourier transform
$$
x(t) = \mathcal{F}^{-1} ({X(\omega)}) = \frac{1}{2 \pi} \int_{-\infty} ^{\infty} X(\omega) e^{j \omega t} \, d \omega
$$
$$
\omega = 2 \pi f
$$
$$
X(f) = \mathcal{F}(x(t)) = \int_{- \infty} ^{\infty} x(t) e^{-j 2 \pi f t} \, dt
$$
T is the step.
$f_{s}$ is the sampling frequency and is given by $f_{s}\frac{1}{T}$ 
$N$ is the length of the signal, so how many data points there are.
$F$ is the frequency resolution and is given by $F = \frac{f_{s}}{N} = \frac{100}{41} \approx 2.5$   

Discrete Fourier transform
$$
X(m) = \sum_{n=0}^{N-1} x(n) e^{-j \frac{2 \pi m n}{N}}
$$
Euler equation:
$$
e^{ix} = \cos(x) + i \sin(x)
$$
![[Pasted image 20250917131103.png]]
Amplitude:
$$
A_{m} = \frac{1}{N} |X(m)| = \frac{1}{N} \sqrt{[Re (X(m))]^{2} + [Im (X(m))]^{2}}
$$
Phase: $\angle X(m) = \tan^{-1} \left(\frac{Im (X(m))}{Re(X(m))}\right)$
Power spectrum: $P(m) = \frac{1}{N^{2}} |X(m)|^{2} = \frac{1}{N^{2}} ([Re (X(m))]^{2} + [Im (X(m))]^{2})$

Center frequency: $\omega_{c} = \sqrt{\omega_{a_{1}} \cdot \omega_{a_{2}}}$ 
Stopband frequency: $\frac{\omega_{s}}{\omega_{a}}$

Nyquist frequency: $\frac{f_{s}}{2}$

![[Pasted image 20250925093245.png]]
T is the sampling interval
$\tau$ is the pulse width
$d= \frac{\tau}{T}$ is the duty factor

![[Pasted image 20250925094345.png]]
After doing pulse-sampling:
Null is at $\frac{f_{s}}{d}$

### Z-transformation rules
![[Pasted image 20251002093707.png]]
![[Pasted image 20251002093929.png]]
![[Pasted image 20251002094547.png]]