![[Pasted image 20251009082806.png]]
### Impulse response
![[Pasted image 20251009082821.png]]
![[Pasted image 20251009082935.png]]
#### Example
![[Pasted image 20251009083029.png]]
![[Pasted image 20251009083130.png]]
So you just isolate k and insert the pole values to find the k-values.
![[Pasted image 20251009083610.png]]
### Matlab function
![[Pasted image 20251009083601.png]]
![[Pasted image 20251009083731.png]]Remember the 0, or else matlab won't recognize it as a second order function. So this is for the function:
$$
H(z) = \frac{z^{2} + 0.4 z + 0}{z^{2} - 0.7z + 0.1}
$$
![[Pasted image 20251009083849.png]]
Simple poles means no poles are repeated in the transfer functions, so:
$$
p_{1} \neq p_{i}, \quad i = 2 \dots N
$$
The pole determines the subsystems, which means if any subsystems are unstable, then your whole system will be unstable.

## USE CASE 
So we use impulse response to check if the system is stable or unstable, the complete transfer function can be considered as a lot of submodules where if any of the poles are unstable then that means the entire system is unstable. The amount of poles are determined by the order of the transfer function

### Relation between pole placement and impulse response
![[Pasted image 20251009084518.png]]
The first part (Modulo) determines the distance: $e^{\sigma_{i}n T}$
The second part (Argument) determines the angle: $e^{j \omega n T}$

The modulo describes the difference in values between the points (consecutive samples) in your discrete system.
### Example: Impulse response of a 2nd order system
![[Pasted image 20251009085553.png]]
![[Pasted image 20251009085703.png]]
![[Pasted image 20251009085713.png]]The blue line is $h_{1}$ and the red line is $h_{2}$. However remember this is in 3D space, which is hard to imagine from the slide. The x-axis consists of the real values while the z-axis consists of the imaginary values. If you look at the $h_{1}$ and $h_{2}$ from the previous slide the modulo is exactly the same as seen in the graph of the real part, while the phase is different, which can be seen in the graph of the imaginary part. As you can see the imaginary part is symmetric, because the phase is the same value, but with the opposite sign. Since the signal is continually increasing and unbounded the signal is unstable.
![[Pasted image 20251009090342.png]]
### Stability
![[Pasted image 20251009090359.png]]
If the impulse response of the system converges to 0 as n goes towards infinite, the system will be stable. However if the impulse response of the system diverges and goes towards infinite as n goes towards infinite, the system will be unstable.
### Determination of stability
![[Pasted image 20251009090523.png]]
If the absolute value of ALL of the poles are smaller than 1, then the system is STABLE or if the absolute value of at least.
If the absolute value of the poles are smaller than 1 or equal to one and at least one of the imaginary poles are equal to 0, then the system is MARGINALLY STABLE.
If the absolute value of ALL of the imaginary poles are less than 1 the system is UNSTABLE.

If we look at the slide 5 slides back:
![[Pasted image 20251009085703.png]]
Then we can see that $e^{0.1823 n}$ comes from the value $1.2^{n}$, where we can see that as n increases the system will be unstable because the values will increase infinitely as n approaches infinity.

![[Pasted image 20251009090748.png]]
### Impulse response in z-plane related to pole position
![[Pasted image 20251009091007.png]]
- The green is STABLE since the values are smaller than 1, so the values will converge.  
  
- The orange circle is MARGINALLY STABLE, since the values are 1 it means the sequence is a unit sequence and the input sequence is the same as the output sequence. 
  
- The red are UNSTABLE because the value is above 1, meaning the values will keep increasing.

### Are these systems stable
![[Pasted image 20251009091348.png]]
The crosses are the poles the O are the zeros, the zeros don't matter for the stability of the system.
Left is stable, middle is marginally stable, the right is unstable.
If the crosses are outside the circle then the absolute value of the poles are bigger than 1 and therefore the system is unstable, if they are on the circle they equal to 1 and are therefore marginally stable.
### What about in continuous time system (s-domain)
![[Pasted image 20251009091508.png]]
If the location of the system poles in the s-domain are on the negative side of the real axis the system is stable and if they are on the positive side of the real axis they are unstable.
### Frequency response analysis
![[Pasted image 20251009093056.png]]
In contrast to the impulse response the frequency response provides a response to a sinusoidal input sequence instead of just an impulse. The impulse response checks the stability of the system to an impulse while the frequency response checks the stability of the system to a specific frequency.
![[Pasted image 20251009093438.png]]
Here:
$$
\underbrace{H(j \omega)}_{\text{system freq response at } \omega} \quad \underbrace{e^{j \omega t}}_{\text{input signal}(\omega)}
$$

![[Pasted image 20251009093548.png]]
In the polar form you can easily identify the magnitude of the response and the phase shift.
### Bode plot
![[Pasted image 20251009094025.png]]
The bode plot shows the magnitude response and the phase response of your system for different frequencies.
![[Pasted image 20251009094120.png]]
A point on the peripheral of the circle represents a sinusoidal. $f_{0}$ is the Nyquist frequency, which is half of the sampling frequency $f_{0} = \frac{f_{s}}{2}$.
![[4 Sampling and reconstruction#Nyquist-Shannon theorem]]

#### Example
![[Pasted image 20251009094759.png]]
![[Pasted image 20251009094920.png]]
![[Pasted image 20251009095235.png]]
As we can see the amplitude is multiplied by 1.65 and the phase is shifted -56$\degree$.
### Matlab function - bode()
![[Pasted image 20251009095439.png]]
![[Pasted image 20251009095853.png]]
Its not possible, because at $\omega T = 3$ we have $\pi$ which is where the vertical line is on the bode plot.
$$
f = \frac{1}{2\pi} f_{s}
$$
Since $\frac{f_{s}}{2}$. 
### Graphical determination of frequency response
![[Pasted image 20251009101507.png]]
![[Pasted image 20251009102649.png]]
![[Pasted image 20251009102704.png]]
![[Pasted image 20251009102714.png]]
Here the line to the conjugated $p_{1}^{*}$ was forgotten by Cheng, but there is supposed to be a line from z to $p_{1}^{*}$.
![[Pasted image 20251009102803.png]]
![[Pasted image 20251009102843.png]]
![[Pasted image 20251009102948.png]]
![[Pasted image 20251009102956.png]]
If you look at the distance between $z_{1}$ to $f=0$ it will be the max, if you look at the graph for the magnitude for the frequencies, as the frequencies increase the point will move along the peripheral of the circle decreasing the length of the line from $z_{1}$ to the frequency, and therefore the magnitude is decreasing. Since the theta has a negative in front of the parenthesis the phase is negative as the frequency increases.
#### Example
![[Pasted image 20251009103614.png]]
Just look at the top half of the circle. When the frequency is close to the pole the magnitude will increase, when the frequency is close to the zero the magnitude will decrease. So in this example when you reach $2 \space kHz$ the magnitude will be at the peak, afterwards it will decrease as the frequency increases, and when it reaches $z_{1}$ which is around $5 khZ$ the magnitude will be at the lowest magnitude. The phase angle is mostly the same.
![[Pasted image 20251009103835.png]]
Here from the frequency 0 to 2k it will decrease at reach the lowest magnitude and after it will increase and peak at around $5 kHz$ and decrease again. This is a band stop filter.
### Sample rate
![[Pasted image 20251009104120.png]]
If you change the sampling frequency $T$ in $z = e^{j \omega T}$ The function will be scaled proportionally. So if you scale the sampling frequency by 5, then when it used to have a cutoff frequency at $1 \space kHz$, but if you scale it by 5 then the cutoff frequency will be at $5 \space kHz$.