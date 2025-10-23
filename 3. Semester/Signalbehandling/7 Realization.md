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
The amplification need to be able to handle large margins, or else the signal will be truncated. Rounding errors can be enough to change the behaviour of the system.
### Rounding errors
![[Pasted image 20251023090921.png]]
### What can be the problems for direct realization?
![[Pasted image 20251023092647.png]]
For example if you want to amplify both low frequencies and high frequencies you create two filters and add them together.
### Cascade realization
![[Pasted image 20251023093335.png]]
![[Pasted image 20251023093354.png]]
If you have conjugated poles you put them together in one function.
![[Pasted image 20251023094356.png]]
### Organize poles and zeros into different sections
![[Pasted image 20251023094406.png]]
You want to make sure the zeros and poles that are close together in the pole-zero map , because if its far apart then it can result in the system becoming unstable, because of rounding errors. If they are close they can almost cancel each other out.
![[Pasted image 20251023094841.png]]
![[Pasted image 20251023095413.png]]
You need to consider the sequence of sections. So it should be the middle one first because it is the most gentle one, and then after it has decayed by -5dB then we should use the amplified one, which is the highest one, and then at the end use the lowest one (1st order), this makes sure there is as low of a range of amplification as possible.
### Scaling
![[Pasted image 20251023095957.png]]
You scale between the transfer functions in order to not lose your accuracy. If they are too small you amplify and if they are too big you need to reduce.
### Parallel realization
![[Pasted image 20251023100117.png]]
![[Pasted image 20251023100936.png]]
![[Pasted image 20251023100941.png]]
![[Pasted image 20251023100947.png]]
![[Pasted image 20251023100956.png]]
![[Pasted image 20251023101004.png]]
![[Pasted image 20251023101015.png]]
$a_{22}$ should be zero, since there is constant value in $-0.3624z^{2} + 0.2558z$ 
### Cascade vs. parallel structure
![[Pasted image 20251023102035.png]]
FIR and IIR will come later, but basically if you DONT consider your previous output its FIR (so parallel structure) and if you DO consider your previous output its IIR (so cascade)
### Block diagrams and signal flow graphs
![[Pasted image 20251023102101.png]]
### Transpose of the system
![[Pasted image 20251023102341.png]]
Keep in mind $y(n)$ and $x(n)$ have been swapped, and the arrows are reversed.