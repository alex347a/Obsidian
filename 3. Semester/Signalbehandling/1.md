Analog vs. digital
Analog signal is continuos like for example $f(x) = x$
Digital signal is already discretized, so the values are already sampled, not just binary. Its a discrete time signal with quantization.

We cannot analyse analog signals, therefore we convert them to digital signals.

If your digital filter hits the natural frequency the system will be disrupted.

Unit sample sequence is an impulse, so there is a value of 1 at one moment and 0 otherwise.

![[Basic sequence.png]]

![[Basic sequence 2.png]]
$\omega_{0}$ is the sampling frequency.

### 2
Time & frequency domain
![[Discrete time signal - basic operation.png]]
### Convolution
![[Convolution.png]]
### Convolution properties
![[Convolution properties.png]]
### Example of convolution sum
![[Example of convolution sum.png]]

### LTI (Linear Time Invariant) and when a system is linear
![[LTI (Linear Time Invariant) and when a system is linear.png]]
A signal is non-linear if the input is different from the output. For example if you input two signals that go above or below the values of an ADC for example. An example would be an ADC from 0V to 3V, but if the two signals added together go above 3V or below 0V the out would be non-linear, because the ADC wouldn't catch the correct signal.
![[LTI.png]]
### Causal
![[Causal.png]]
When a system only depends on the past signal and not the future the system is causal.