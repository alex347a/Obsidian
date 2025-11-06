Consider the following Butterworth 3rd order low-pass filter (frequency normalized filter)
$$
H(s) = \frac{1}{s+1} \cdot \frac{1}{s^{2} + s + 1}
$$
Please design a corresponding digital low-pass filter with a cut-off frequency of 1 kHz, and sample frequency of 8 kHz.

1. Design a digital low-pass filter $𝐻_{1}(𝑧)$ using matched z-transform.


2. Design a digital low-pass filter $𝐻_{2}(𝑧)$ using impulse invariant z-transform.
   
   
3. Use MATLAB to compare Bode plots for these 3 filters $𝐻(s)$, $𝐻_{1}(𝑧)$ and $𝐻_{2}(𝑧)$.
   
   
4. Use MATLAB to compare the impulse responses of $𝐻(s)$, $𝐻_{1}(𝑧)$ and $𝐻_{2}(𝑧)$.
   
   