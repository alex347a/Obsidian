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

### USE CASE 
So we use impulse response to check if the system is stable or unstable, the complete transfer function can be considered as a lot of submodules where if any of the poles are unstable then that means the entire system is unstable.