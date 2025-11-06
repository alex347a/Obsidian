### Two categories of discrete-time filters
![[Pasted image 20251106084959.png]]
In IIR you also use the previous output values, while for FIR you don't.
### Recap: realization
![[Pasted image 20251106085319.png]]
### Design of digital IIR filter
![[Pasted image 20251106085344.png]]
We convert from the specifications in the s-domain to the z-domain
![[Pasted image 20251106085358.png]]
### Recap: Filter specification
![[Pasted image 20251106085524.png]]
### Transformation from an analog prototype filter
![[Pasted image 20251106085653.png]]
![[Pasted image 20251106085714.png]]
### Matched z-transform
![[Pasted image 20251106091742.png]]
Remember $T = \frac{1}{f_{s}}$ which is the sampling period.
### Matched z-transform for 1st order system
![[Pasted image 20251106091753.png]]
Remember $s = \underbrace{\sigma}_{\text{real}} + j \underbrace{\omega}_{\text{imaginary}}$

![[Pasted image 20251106091806.png]]
![[Pasted image 20251106091811.png]]
![[Pasted image 20251106091817.png]]
So we use an amplification factor to make sure the value of the transfer function is 1, when $z=1$. The reason for this is because we don't want to attenuate our DC gain, in a low-pass filter, we want the magnitude to be 1 when we have a DC signal (so $\omega = 0$, meaning the frequency is 0).
The mapping $z = e^{sT}$ perfectly maps the positions of the poles and zeros, which correctly shapes the frequency response of the filter (e.g., where the peaks and notches are). However, it does not automatically set the overall **gain** or **magnitude** of the digital filter, which is why we need to introduce an amplification factor.
#### Example
![[Pasted image 20251106091829.png]]
![[Pasted image 20251106091834.png]]

![[Pasted image 20251106091840.png]]
### Design procedure (matched z-transform)
![[Pasted image 20251106093443.png]]
### Matched z-transform for higher order system
![[Pasted image 20251106093555.png]]
### Example: 2nd order system
![[Pasted image 20251106093803.png]]
![[Pasted image 20251106093939.png]]
![[Pasted image 20251106094127.png]]
### Exercise
![[Pasted image 20251106094135.png]]
### Matlab function: Hz=c2d(Hs, Ts, method)
![[Pasted image 20251106095458.png]]

#### Example
![[Pasted image 20251106095833.png]]
### Impulse invariant z-transform
![[Pasted image 20251106102007.png]]This method is motivated by a very intuitive desire: we want the digital filter to behave similarly to the analog filter when presented with the same type of input signal, at least for the impulse response.
Step by step:
1. Start with an analogue filter defined by its Laplace transfer function.
2. Perform the inverse Laplace of $H_{a}(s)$to get $h_{a} (t)$ 
3. Sample the Impulse Response: We define the digital impulse response by sampling $ha(t)$ at intervals of T
4. Take the Z-Transform of $h_{d}[n]$ Now we find the digital transfer function $H_{d}​(z)$ by taking the Z-transform of the sampled impulse response $h_{d}[n]$ 
This is very similar to the Matched Z-Transform for poles. The key difference is in how zeros are handled. The Impulse Invariant method doesn't have a simple, direct mapping for zeros. Their positions in the z-plane are a consequence of the entire summation process.

#### Advantages:
1. **Preserves Time-Domain Shape:** For the impulse input, the output of the digital filter will be the sampled version of the analog filter's output. This is its greatest strength.
2. **Stability-Preserving:** Since a stable analog filter has poles in the left-half of the s-plane $(Re{p_{k}} < 0)$, the mapped digital poles will lie inside the unit circle $(|e^{p_{k}T}| < 1)$, guaranteeing a stable digital filter.
#### The Critical Disadvantage: Aliasing
This is the biggest drawback of the Impulse Invariant method.
The analog filter's frequency response $H_{a}​(\omega)$ is defined for all frequencies, but the digital filter's frequency response $H_{d}(\omega)$ is periodic.

**Consequence:** The Impulse Invariant method is generally **unsuitable for high-pass or band-stop filters** because these filters have significant high-frequency gain, leading to severe aliasing. It works best for **band-limited low-pass filters**.

![[Pasted image 20251106102257.png]]
![[Pasted image 20251106102729.png]]
#### Example
![[Pasted image 20251106103324.png]]
### Impulse invariant v.s. matched z-transform

| Feature          | Impulse Invariant                                                  | Matched Z-Transform                                          |
| ---------------- | ------------------------------------------------------------------ | ------------------------------------------------------------ |
| **Core Idea**    | Match the **impulse response**                                     | Match the **pole/zero locations**                            |
| **Pole Mapping** | $s = p_{k} \rightarrow z = e^{p_{k} T}$                            | $s = p_{k} \rightarrow z = e^{p_{k} T}$                      |
| **Zero Mapping** | No direct mapping. Zeros are a result of the process.              | $s = z_{k} \rightarrow z = e^{z_{k}T}$                       |
| **Aliasing**     | **Severe problem** if analog filter not band-limited.              | Less severe, but still present.                              |
| **DC Gain**      | Must be explicitly normalized after design.                        | Must be explicitly normalized after design.                  |
| **Best For**     | Simulating analog time-domain behavior (e.g., in control systems). | Designing filters where frequency response shape is primary. |
For impulse invariant:
- Use Case: It's a good choice only when the analog filter is essentially band-limited (e.g., a sharp low-pass filter with high stopband attenuation) and when preserving the time-domain shape of the impulse response is the most important requirement.
![[Pasted image 20251106103542.png]]
![[Pasted image 20251106103548.png]]
![[Pasted image 20251106103558.png]]