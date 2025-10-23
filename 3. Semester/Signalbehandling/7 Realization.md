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
For the blue part each amplification $a$ is passed through a delay and then added to all of the previous values. For the green part the only difference is the - in front of the sum, so it is a negative amplification of $b$. The function $y(n)$ is the sum of the two amplifications that are each a sum of all of the values. Its a loop that is recursive, so the function is dependent on all of the previous values of the output signal and the input signal as well. Here it is easily visualised that if the amplification is above 1 then the signal becomes unstable, because you will keep amplifying the signal to infinity.
#### Example
![[Pasted image 20251023084256.png]]
Mistake, b should be negative, its $-b$ in the amplification.
![[Pasted image 20251023085450.png]]
Look 4 slides down (Example (type II)), he basically just isolates $y(n)$ like in the example above and then draws it, it is very simple and intuitive. This is type 1.

### Direct type 2 cascading
![[Pasted image 20251023085533.png]]
![[Pasted image 20251023085549.png]]
here $H_{1}$ should be in the green box, not in the blue one, and the opposite, the amplifications are in swapped order.
Just like multiplying in a different order mathematically.
![[Pasted image 20251023085708.png]]
Since every line is a value, reducing the total amount of lines will make computation faster.
![[Pasted image 20251023090113.png]]
### Type 1 v.s. type 2
![[Pasted image 20251023090329.png]]
### Why not always use type 2
![[Pasted image 20251023090356.png]]