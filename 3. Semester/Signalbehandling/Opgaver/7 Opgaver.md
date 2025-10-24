First I use MatLab to calculate the transfer functions, for cascade structure I multiply the transfer functions and for parallel structure I sum the transfer functions:

For cascade 
The sos matrix has the structure:
$[b0, b1, b2, 1, a1, a2]$



![[Pasted image 20251024141035.png]]
This means the parallel structure must be:
$$
-0.6060 \cdot \frac{0.0902 + 0.0678 i}{z - (0.0357 + 0.6350 i)} + \frac{0.0902 - 0.0678 i}{z - (0.0357 - 0.6350 i)} - \frac{0.5170 - 0.0123 i}{z - (-0.2942 + 0.8514 i)} - \frac{0.5170 + 0.0123 i}{z - (-0.2942 - 0.8514 i)}
$$