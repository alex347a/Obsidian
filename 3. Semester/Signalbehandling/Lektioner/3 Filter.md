![[Pasted image 20250918082048.png]]
Low pass filter removes the sharpness. A sharp turn (edge) is a big difference in pixel values is considered a high frequency signal and therefore a low pass filter blurs the image by removing the sharp edges.
The high pass filter does the opposite, so you can only see the outline.
The band pass filter keeps a specific range of frequencies.
The band pass filter removes a specific range of frequencies.

![[Pasted image 20250918082545.png]]
![[Pasted image 20250918082601.png]]Its just an RC-circuit in the coaxial cable because of the copper shield around the copper wire acting as a capacitor.
![[Pasted image 20250918082806.png]]
![[Pasted image 20250918083014.png]]
![[Pasted image 20250918083122.png]]
![[Pasted image 20250918083232.png]]
![[Pasted image 20250918083240.png]]
Remember the scale of the phase is logarithmical.
![[Pasted image 20250918083947.png]]
![[Pasted image 20250918084042.png]]
$T_{g}$ is the change in phase for the frequency so the graph for $T_{g}(\omega)$ is just the derivative of the phase $\phi (\omega)$ 
 Example:
 ![[Pasted image 20250918084854.png]]
 Importance of linear phase: If tau ($T_{g}$) is linear then the signal is just shifted by a constant, but if tau is non-linear it will fuck up your signal because it the different frequencies will have different phase shifts.
 ![[Pasted image 20250918091635.png]]
 ![[Pasted image 20250918091747.png]]
 ![[Pasted image 20250918091756.png]]
 High attenuation means the line should be very steep, it should drop as fast as possible after the cutoff frequency. As you can see Bessel has a very good linear phase, however it has slow attenuation. 2 dB Chebyshev has a very steep attenuation and Butterworth is ind the middle of the two. You choose Chebyshev if you only care about the amplitude 
 ![[Pasted image 20250918092029.png]]
 ![[Pasted image 20250918092035.png]]
 ![[Pasted image 20250918093247.png]]
 ![[Pasted image 20250918093255.png]]
 ![[Pasted image 20250918093332.png]]
 ![[Pasted image 20250918093353.png]]
 's' is in the s domain.
 In Chebyshev you can set your own ripple range, when having a high ripple range you get high attenuation, but if you have low ripple range you will get a lower attenuation, so its about optimizing the filter for the application.
 ![[Pasted image 20250918094404.png]]
 ![[Pasted image 20250918101206.png]]
 The higher the order of the filter the higher the attenuation, but the system becomes more complicated and unstable at higher orders. (For example Cheng said in a filter of 5th order it has to be split up in 2 2 order filters and 1 1 order filter cascaded, so you essentially need 3 filters, which makes processing a lot slower)
![[Pasted image 20250918101421.png]]
The stopband attenuation should be at least 60 dB compared to $A_{max}$.
![[Pasted image 20250918101708.png]]
![[Pasted image 20250918102015.png]]
Normally when you design a filter you just normalise the filter and make a low pass filter, choose an order and then you denormalise the filter and get your final filter.
### Low-pass to high-pass transformation
![[Pasted image 20250918102101.png]]
![[Pasted image 20250918102145.png]]
![[Pasted image 20250918102347.png]]
Essentially you just flip the s in the denominator by making it from $s$ to $\frac{1}{s}$ 
#### Low-pass to band-pass transformation example
![[Pasted image 20250918102441.png]]
![[Pasted image 20250918102449.png]]
![[Pasted image 20250918102500.png]]
![[Pasted image 20250918102507.png]]
### Low-pass to band-pass transformation
![[Pasted image 20250918102514.png]]
![[Pasted image 20250918102524.png]]
![[Pasted image 20250918103104.png]]
![[Pasted image 20250918103119.png]]
$W_{a}$ is the bandwidth.
![[Pasted image 20250918103258.png]]
Here $f_{c}$ is the center frequency (normally written as $\omega_{c}$) and not the cutoff frequency.
#### Low-pass to band-pass transformation example
![[Pasted image 20250918103340.png]]
![[Pasted image 20250918103457.png]]
![[Pasted image 20250918103503.png]]
### Low-pass to band-stop transformation
![[Pasted image 20250918103709.png]]
![[Pasted image 20250918103815.png]]
![[Pasted image 20250918103939.png]]
### MatLab can transform filters
![[Pasted image 20250918103959.png]]
