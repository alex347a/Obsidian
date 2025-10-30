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
