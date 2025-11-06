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
So we use an amplification factor to make sure the value of the transfer function is 1, when $z=$
#### Example
![[Pasted image 20251106091829.png]]
![[Pasted image 20251106091834.png]]
![[Pasted image 20251106091840.png]]