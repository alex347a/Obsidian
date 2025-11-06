### roots()
![[Pasted image 20251002101147.png]]
Even if you dont have the value for c (here -4) you should still type 0, because it needs three inputs.
### tf2zp()
![[Pasted image 20251002101157.png]]
### zplane()
![[Pasted image 20251002101208.png]]
### ztrans()
### iztrans()
![[Pasted image 20251002105027.png]]
### Transfer function tf()
![[Pasted image 20251009083601.png]]
### impulse()
![[Pasted image 20251009083731.png]]
### bode() 
![[Pasted image 20251009095439.png]]
### impz()
![[Pasted image 20251015122700.png]]
### filter()
![[Pasted image 20251015122712.png]]
For an FIR filter you can actually use convolute as well, but not for IIR.
### $[p,z]$  = pzmap(H_z)
combined with roots() can be used to calculate the zeros and poles. Pzmap means poles-zero-map
This is used for cascade structure.
### residuez() and residue()
![[Pasted image 20251023101226.png]]
This is used for parallel structure
### simplify() and vpa()
Simplify simplifies an equation by reducing it. vpa() simplifies to a specified value, so for example you only want to keep 3 numbers after the decimal, for example vpa(tmp, 3)

### conv(input_sig, fir_filter, 'same')
![[Pasted image 20251030085606.png]]
### Matlab window functions
![[Pasted image 20251030105755.png]]
### Matlab function fir1()
![[Pasted image 20251030111326.png]]
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
![[Pasted image 20251106103002.png]]
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
