Consider the following Butterworth 3rd order low-pass filter (frequency normalized filter)
$$
H(s) = \frac{1}{s+1} \cdot \frac{1}{s^{2} + s + 1}
$$
Please design a corresponding digital low-pass filter with a cut-off frequency of 1 kHz, and sample frequency of 8 kHz.

1. Design a digital low-pass filter $𝐻_{1}(𝑧)$ using matched z-transform.
![[Pasted image 20251106174620.png]]

2. Design a digital low-pass filter $𝐻_{2}(𝑧)$ using impulse invariant z-transform.
![[Pasted image 20251106174634.png]]
   
3. Use MATLAB to compare Bode plots for these 3 filters $𝐻(s)$, $𝐻_{1}(𝑧)$ and $𝐻_{2}(𝑧)$.
![[Pasted image 20251106175436.png]]
4. Use MATLAB to compare the impulse responses of $𝐻(s)$, $𝐻_{1}(𝑧)$ and $𝐻_{2}(𝑧)$.
![[Pasted image 20251106180446.png]]
![[Pasted image 20251106180441.png]]
![[Pasted image 20251106180415.png]]
![[Pasted image 20251106180421.png]]