FIR exercise 1:
Find the coefficients for a FIR band-pass filter, such that $f_{a_{1}} = 1.5 \space kHz$ and $f_{a_{2}} = 2.5 \space kHz$. The filter should have a sampling frequency of 8 kHz and a M-value of 22.

1. Please calculate the filter coefficients using the $c_{m}$ formula (you can still use MATLAB for the calculation).

I can use the formula for the bandpass filter from the table:
![[Pasted image 20251030101546.png]]

$$
\frac{1}{m \pi} (\sin(2 \pi m T f_{a_{2}}) - \sin(2 \pi m T f_{a_{1}}))
$$
After inserting it into MatLab:
0.020462
0.000000
0.031831
0.000000
0.025009
0.000000
0.000000
0.000000
0.032154
0.000000
-0.053052
0.000000
0.045016
-0.000000
0.000000
-0.000000
-0.075026
0.000000
0.159155
-0.000000
-0.225079
-0.000000
0.250000
0.000000
-0.225079
-0.000000
0.159155
0.000000
-0.075026
-0.000000
0.000000
-0.000000
0.045016
0.000000
-0.053052
0.000000
0.032154
0.000000
-0.000000
-0.000000
-0.025009
-0.000000
0.031831
-0.000000
-0.020462
2. You can compare the above results with Matlab function fir1().

Apparently the Matlab function fir(1) automatically uses the hamming window type, which modifies the values of the coefficients.

3. Make a transfer function and drawing the Bode plot for the designed filter.

4. Simulating the filter in Matlab by applying different input signals with frequencies of 1 kHz, 2 kHz, and 3.5 kHz. Does the response match the Bode plot? (Use lsim in MATLAB for the simulation).

Exercise FIR.2
Design an FIR highpass filter with cutoff frequency $f_{a} = 1 \space kHz$. The transition region is $\Delta f \leq 0.5 \space kHz$, and the maximum allowable stop-band attenuation is $H_{s} \leq -50 \space dB$. The sampling frequency is 5 kHz.

1. Which window function should be chosen?


2. What should the order of the filter be? What happens if the order is increased?
   
   
3. Make the final FIR filter with the selected window function.
   
   
4. Draw a Bode plot for the filter and argue that the filter specifications are met.
   
   