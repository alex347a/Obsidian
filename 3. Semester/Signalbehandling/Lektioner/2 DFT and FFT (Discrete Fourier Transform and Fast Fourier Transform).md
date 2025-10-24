## Discrete Fourier transform
![[Pasted image 20250917122543.png]]
It's important to sample at a rate that is high enough to capture your signal, but not too high to be taxing on the system.
![[Pasted image 20250917122623.png]]
To convert from a digital signal to an analogue signal you can use FFT (Fast Fourier Transform)
![[Pasted image 20250917122733.png]]
A signal is comprised of a sum of sinusoidal signals.
### Fourier transform
![[Pasted image 20250917122818.png]]
This is for a continuous signal, not discrete.
Fourier transform
$$
X(\omega) = \mathcal{F}(x(t)) = \int_{-\infty}^{\infty} x(t) e^{-j \omega t} \, dt
$$
Inverse Fourier transform
$$
x(t) = \mathcal{F}^{-1} ({X(\omega)}) = \frac{1}{2 \pi} \int_{-\infty} ^{\infty} X(\omega) e^{j \omega t} \, d \omega
$$
### Discrete Fourier Transform
![[Pasted image 20250917123042.png]]
$$
\omega = 2 \pi f
$$
$$
X(f) = \mathcal{F}(x(t)) = \int_{- \infty} ^{\infty} x(t) e^{-j 2 \pi f t} \, dt
$$
Here you get discrete values.
![[Pasted image 20250917123234.png]]
Since the step is $0.01 s$ so $T = 0.01 s$ that means the frequency is $f_{s} = 100 Hz$
$N$ is the length of the signal, so how many data points there are. So here there are 41 values, so $N = 41$
The sampling frequency $f_{s} = NF$ which means that the frequency resolution is given by $F \approx 2.5$ because $F = \frac{f_{s}}{N} = \frac{100}{41} \approx 2.5$   
$$
X(m) = \sum_{n=0}^{N-1} x(n) e^{-j \frac{2 \pi m n}{N}}
$$
#### MatLab example
![[Pasted image 20250917131758.png]]
### Inverse discrete Fourier transform
![[Pasted image 20250917124327.png]]
![[Pasted image 20250917124910.png]]
#### example
![[Pasted image 20250917125258.png]]
![[Pasted image 20250917131100.png]]

## Fast Fourier transform
![[Pasted image 20250917133705.png]]
![[Pasted image 20250917133943.png]]
$N = 2^{r}$ is the most efficient amount of datapoints for a given signal.
You expand the Fourier transform and reorganize it to be the even n-values and uneven n-values. This is because it reduces the complexity by 2, so you only have to do half of the calculations because of the butterfly operation.

This combination of two size-`N/2` DFTs to form one size-`N` DFT is often represented by a "butterfly" structure. A single butterfly operation takes two complex numbers `(A, B)` and a twiddle factor `W` and produces two outputs:
- `A + W * B`
- `A - W * B`
This is an incredibly efficient unit of computation because it exponentially reduces the amount of operations.

fftshift shifts so the signal is symmetric about 0, instead of being symmetric at the half of the amount of samples, so instead of going from 0 to 1000 it shifts it to be from -500 to 500. Example:
![[Pasted image 20250917135755.png]]

To remove the high frequency noise you can write:
![[Pasted image 20250917135851.png]]
Which then gives you a graph like:
![[Pasted image 20250917140007.png]]
But there is still noise at the low frequency range.