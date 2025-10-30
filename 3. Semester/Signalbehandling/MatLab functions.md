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