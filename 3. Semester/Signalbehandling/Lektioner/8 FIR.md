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