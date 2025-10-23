### Discrete time system: Transfer function
![[Pasted image 20251023082418.png]]
### Basic elements for block diagram
![[Pasted image 20251023082650.png]]
so if $x(n)$ goes through the multiplier a, then it becomes $a \cdot x(n)$ 
if $x_{1}(n)$ and $x_{2}(n)$ goes through an adder it becomes $x_{1}(n) + x_{2}(n)$
if $x(n)$ goes through a delay it becomes $x(n-1)$

### Genereal structure of realization of a digital filter
![[Pasted image 20251023083025.png]]
### Direct type 1 structure
![[Pasted image 20251023083004.png]]
For the blue part each amplification $a$ is passed through a delay and then added to all of the previous values. For the green part the only difference is the - in front of the sum, so it is a negative amplification of $b$. The function $y(n)$ is the sum of the two amplifications that are each a sum of all of the values. Its a loop that is recursive, so the function is dependent on all of the previous values of the output signal and the input signal as well.