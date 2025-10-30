FIR stands for Finite Impulse Response while IIR stands for Infinite Impulse Response
### Recap: realization
![[Pasted image 20251030083950.png]]
When your input finishes the output finishes, which means it is finite. Let's say you have 4 delays and you wait 4 steps then all of your values will be zero. If it never finishes then it is infinite.
![[Pasted image 20251030084008.png]]
![[Pasted image 20251030084442.png]]
In FIR you use only your input signal to generate your output signal, while in infinite you use both the input and output. NOT GOOD SLIDE, CHENG SAYS ITS NOT PRECISE IN RELATION TO THE POLES.
### FIR definition
![[Pasted image 20251030084600.png]]For a sixth order filter you need 7 parameters, because you need to count $a_{0}$ as well.
### FIR filter transfer function
![[Pasted image 20251030084822.png]]
The sum should be to $N$ and not $N-1$. It depends on how you define N, but normally N is the order of the filter, while rarely N is the number of samples. The order of the filter is the amount of samples minus one, so when using N is the order the amount of samples is $N+1$.
### FIR filter realization structure
![[Pasted image 20251030085008.png]]
The sum should also be to $N$ here and not $N-1$
### Matlab function convolution
![[Pasted image 20251030085606.png]]
You have to put 'same' to ensure you get an output of 5 values if you have 4 values as the input. If you don't put 'same' you will only get 4 output values from 4 values as input.
The gaussian FIR filter is normally used as a low pass filter, and ensures a smooth curve despite the noise in the input signal.
The differential filter is normally used to show when you have a transition, so because the sum of the differential filter is 0, that means when the value is 0 you don't have a change in output, but when it differs from 0 it means you have a transition.
### Poles and zeros for an FIR filter
![[Pasted image 20251030091716.png]]
$N$ here and not $N-1$
![[Pasted image 20251030091843.png]]
Stable, because the poles are all inside the circle. It can't be unstable because the output is finished when the input signal finished.
### Linear phase
![[Pasted image 20251030092010.png]]
Very confusing here: $N$ here and not $N-1$, because here in this figure N is the amount of samples, but it should be the order.
When the order is an uneven number the number of parameters are even.
The transfer function would be:
$$
a_{0} + a_{1} z^{-1} + a_{2}z^{-2} + a_{3} z^{-3} + a_{4} z^{-4} + a_{5} z^{-5}
$$
The linear phase is important because when summing signals you have to make sure all of the functions are delayed linearly, or else the signal will become distorted.
### Prove
![[Pasted image 20251030093027.png]]
### Impulse response reformulation
![[Pasted image 20251030093116.png]]
![[Pasted image 20251030093306.png]]
We replace z with $e^{j \omega T}$ to investigate a point running on the half circle in the z-plane to see the response of the filter to all of the frequencies.
![[IMG_2132.JPG]]
### Amplitude and phase
![[Pasted image 20251030094210.png]]
Then it is proven that if the FIR filter is designed symmetrically then the phase will always be linear.
### Example
![[Pasted image 20251030094303.png]]
The number of order is 10.
![[Pasted image 20251030094627.png]]
Do not be confused by 10k, its just 10000 Hz.
Checking with graphical solution:
![[Pasted image 20251030094759.png]]
### Design of FIR filter
![[Pasted image 20251030094822.png]]
### Recap: Fourier series of periodic signal
![[Pasted image 20251030095215.png]]
![[Pasted image 20251030095539.png]]
### Fourier transform of $|H(f)|$
![[Pasted image 20251030095834.png]]
m is the index of the Fourier series.
### Fourier transform of a FIR filter
![[Pasted image 20251030095859.png]]
m is the index of the Fourier series. You don't need to go to infinity, you only need to consider the finite range of the impulse, which is from $-m$ to m. But by truncating our signal we can run into some issues.
![[Pasted image 20251030100344.png]]
You shift the signal from -M to M to instead be from 0 to 2M, because the signal is not causal, meaning the values are not 0 for negative time values.
### Example: low pass filter
![[Pasted image 20251030100746.png]]
The blue part is using some sort of newton law, apparently. 
![[Pasted image 20251030101149.png]]
![[Pasted image 20251030101443.png]]
### Example: High pass filter
![[Pasted image 20251030101501.png]]
### Example: Bandpass filter
![[Pasted image 20251030101508.png]]
### Example: Bandstop filter
![[Pasted image 20251030101529.png]]
### FIR design summary
![[Pasted image 20251030101546.png]]
Remember $f_{a}$ is the cut-off frequency. m is the index of the Fourier series. $T = \frac{1}{f_{s}}$ 
### Problems of the current design. Importance of window function 
![[Pasted image 20251030103223.png]]
### Relationship between time domain and frequency domain
![[Pasted image 20251030103911.png]]
### Windows functions in FIR
![[Pasted image 20251030104121.png]]
You can use a high order of FIR to get rid of side lope, but then you will increase your computation and increase the signal time delay (Latency), the delay introduced into your filtered signal. If you are processing data in real-time (like audio or a control system), this is the lag you experience. So you need to balance it.
This is because of the group delay:
$$
\text{Group delay = }\frac{N}{2}
$$
So if you increase the order you will linearly increase the group delay.
### Frequency response
![[Pasted image 20251030104705.png]]
![[Pasted image 20251030105038.png]]
### Window function desired characteristics
![[Pasted image 20251030105324.png]]
### Typical window functions
![[Pasted image 20251030105411.png]]
### Rectangular window / rectangle window
![[Pasted image 20251030105509.png]]
This is when you don't use any window, you just directly apply the filter.
### Bartlett window
![[Pasted image 20251030105548.png]]
### Hamming window and Hanning window
![[Pasted image 20251030105600.png]]
![[Pasted image 20251030105709.png]]
If the main lobe is a bit wide like here, that means the nearby frequencies will blur together, so it's less precise but you will cut off the unwanted stuff better.

With a **rectangular window** (narrow main lobe):
- You see two distinct peaks at 100.0 and 100.2 MHz
- You can precisely identify that Station A is exactly at 100.0 MHz

With **Hanning/Hamming windows** (wider main lobe):
- The two peaks blur into one wide hump centered around 100.1 MHz
- Your measurement says "the signal is around 100.1 MHz" rather than exactly 100.0 MHz
this is called **frequency smearing**
### Kaiser window
![[Pasted image 20251030105720.png]]
![[Pasted image 20251030105732.png]]
### Matlab window functions
![[Pasted image 20251030105740.png]]
$L$ is the length of the filter, so $L = N+1$ if $N$ is the order of the filter.
### Design procedure
![[Pasted image 20251030110208.png]]
### Specs of a FIR filter
![[Pasted image 20251030110237.png]]
### Determination of the filter order
![[Pasted image 20251030110504.png]]
![[Pasted image 20251030110510.png]]
$B_{n}$ is the main lobe width. Remember $M$ is half of the filter order, $M = \frac{N-1}{2}$.
### Find Bn for different window functions
![[Pasted image 20251030110519.png]]
### Calculation of filter coefficients (with window)
![[Pasted image 20251030110838.png]]
### Design of lowpass filter
![[Pasted image 20251030110931.png]]
$f_{a}$ is the cut-off frequency, $\Delta f$  is the transition frequency. $H_{s}$ is the, $f_{s}$ is the sampling frequency
![[Pasted image 20251030111202.png]]
### Example in Matlab
![[Pasted image 20251030111309.png]]
fliplr(c) means flip left-right. Blue is with the window (hamming window) and red is without the window (rectangular window) (you can see it ripples)
### Matlab function fir1()
![[Pasted image 20251030111326.png]]
