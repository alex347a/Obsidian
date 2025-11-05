Exercise Realization 1
Consider the 5th order 0.5 dB Chebyshev lowpass filter
![[Pasted image 20251024152234.png]]
for a sampling frequency at 100Hz.

1. Rewrite the above transfer function to a cascade structure using first- and second-order transfer functions.

First I use MatLab to calculate the transfer functions, for cascade structure I multiply the transfer functions and for parallel structure I sum the transfer functions:

For cascade structure i use sos in matlab:
The sos matrix has the structure:
$[b0, b1, b2, 1, a1, a2]$
![[Pasted image 20251025143737.png]]
This means the cascade structure must be:
$$
H(z) = 0.06654 \cdot \frac{1 + 0.999 z^{-1}}{1-0.3345 z^{-1}} \cdot \frac{1 + 2.0015 z^{-1} + 1.0015 z^{-2}}{1 -0.0714 z^{-1} + 0.4045 z^{-2}} \cdot \frac{1 + 1.9994 z^{-1} + 0.9994 z^{-2}}{1 + 0.5884 z^{-1} + 0.8114 z^{-2}}
$$

2. Rewrite the above transfer function to a parallel structure using first- and second-order transfer functions.
For parallel structure I use the residuez function in MatLab:
![[Pasted image 20251024141035.png]]
![[Pasted image 20251024150713.png]]
This means the parallel structure must be:
$$
H(z) = -0.6060 + \frac{0.1804 - 0.0624z^{-1}}{1 - 0.0714z^{-1} + 0.4045z^{-2}} + \frac{-1.0340 + 0.3044z^{-1}}{1 + 0.5884z^{-1} + 0.8114z^{-2}} + \frac{1.5260}{1 - 0.3345z^{-1}}
$$
3. Draw the above cascade realization and parallel structure using Simulink. Check if they give you the same result with a 20Hz sinusoidal input.
![[Pasted image 20251104091448.png]]
They give the same result.
However it looks like Cheng got a completely different answer for the coefficients.

Exercise Realization 2
Consider the following transfer function:
$$
H(z) = \frac{0.0876 z^{-1} + 0.0676 z^{-2}}{1 - 1.874 z^{-1} + 1.489 z^{-2} - 0.4601 z^{-3}}
$$

1. Draw a direct type I realization structure for 𝐻(𝑧) and determine how many delay elements are needed.
	I need 5 for type 1, because I need 2 for the numerator and 3 for the denominator (however if I made a type II realization I would only need 3)

2. Determine the poles and zeros of 𝐻(𝑧), and estimate whether 𝐻(𝑧) is stable.


3. Draw a cascade realization for 𝐻(𝑧) using first- and second-order transfer functions.
4. Determine a parallel realization for 𝐻(𝑧) using first- and second-order transfer functions.
5. Identify the filter type (low pass, high pass, band pass or band stop) of 𝐻(𝑧) by plotting a Bode plot in MATLAB.
6. Use Matlab Simulink for the above realization. Check your drawing with input sinusoidal signals at different frequencies.