First I use MatLab to calculate the transfer functions, for cascade structure I multiply the transfer functions and for parallel structure I sum the transfer functions:

For cascade structure i use sos in matlab:
The sos matrix has the structure:
$[b0, b1, b2, 1, a1, a2]$
![[Pasted image 20251024142903.png]]
This means the cascade structure must be:
$$
H(z) = \frac{1 + 0.999 z^{-1}}{1-0.3345 z^{-1}} \cdot \frac{1 + 2.0015 z^{-1} + 1.0015 z^{-2}}{1 -0.0714 z^{-1} + 0.4045 z^{-2}} \cdot \frac{1 + 1.9994 z^{-1} + 0.9994 z^{-2}}{1 + 0.5884 z^{-1} + 0.8114 z^{-2}}
$$

For parallel structure I use the residuez function in MatLab:
![[Pasted image 20251024141035.png]]
This means the parallel structure must be:
$$
H(z) = -0.6060 \cdot \frac{0.0902 + 0.0678 i}{z - (0.0357 + 0.6350 i)} + \frac{0.0902 - 0.0678 i}{z - (0.0357 - 0.6350 i)} - \frac{0.5170 - 0.0123 i}{z - (-0.2942 + 0.8514 i)} - \frac{0.5170 + 0.0123 i}{z - (-0.2942 - 0.8514 i)}
$$