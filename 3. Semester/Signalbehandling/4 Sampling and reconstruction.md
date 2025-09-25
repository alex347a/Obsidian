If you look at exercise 2 for lection 3 you can see for the bandpass filter the waves are kind of oscillating or at least increasing with time, this is because when N is 5 it has to pass a bigger system and therefore the signal starts at 0 and increases with time.

### Continuous - discrete (C/D) converter
This concept is VERY IMPORTANT
![[Pasted image 20250925084647.png]]

### Time domain
![[Pasted image 20250925084655.png]]
$p(t)$ is an impulse sequence. T is the sampling period. n is the amount of samples. $*$ is not a star its just a $\cdot$ its NOT A CONVOLUTION. So you just take different points of the graph, you don't care how the graph actually looks between the dots.

![[Pasted image 20250925085050.png]]
If the signal is periodic it can be represented as a Fourier transform where $C_{m}$ is the Fourier coefficient. Since the impulse signal is also periodic, it can also be Fourier transformed.
![[Pasted image 20250925085617.png]]
Remember here $*$ is wrong, it's just $\cdot$
The equation means you only have one symmetric shape until you do your pulse sampling, which then repeats the shape:
![[Pasted image 20250925090015.png]]
m is the index for the frequency copies, so $m=0$ is the original.
![[Pasted image 20250925091811.png]]
A discrete signal in the time domain becomes a periodic spectra in the frequency domain. For example a square wave becomes a sinusoidal.
A periodic signal in the time domain becomes a discrete spectra in the frequency domain. For example a sinusoidal becomes a square.
![[Pasted image 20250925092423.png]]
Aliasing is when the sample frequency is too low so the repeated spectra overlaps.
![[Pasted image 20250925092838.png]]
![[Pasted image 20250925092845.png]]
