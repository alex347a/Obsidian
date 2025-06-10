#### Conceptual
1. The jacobian matrix of a Yaskawa Motoman MH5 robot at its current configuration has the value:
$$
\begin{bmatrix}
0 & 0 & 0 & -1 & 0 & -1 \\ 
0 & 1 &  -1 & 0 & -1 & 0 \\ 
1 & 0 & 0 & 0 & 0 & 0 \\ 
0 & 0.3499 & -0.0399 & 0 & 0 & 0 \\ 
0.444 & 0 & 0 & 0 & 0 & 0 \\ 
0 & -0.356 & 0.356 & 0 & 0.0510 & 0
\end{bmatrix}
$$
Is the robot currently at a singularity? Why or why not? Justify your answer using two different
computations.
The first obvious one is checking if there are two rows or columns that are linear dependant (one is a scalar of the other). Column 4 and 6 are identical by having -1 as the first element and 0 for the rest. This means that the determinant must be 0, and therefore the robot is at a singularity.
Another way to check is by expanding the determinant, by removing the third row and first column. This would result in a 5x5 matrix:
$$
\begin{bmatrix}
0 & 0 & -1 & 0 & -1 \\ 
1 &  -1 & 0 & -1 & 0 \\ 
0.3499 & -0.0399 & 0 & 0 & 0 \\ 
0 & 0 & 0 & 0 & 0 \\ 
-0.356 & 0.356 & 0 & 0.0510 & 0
\end{bmatrix}
$$
Here an entire row is 0's therefore the determinant must be 0 and therefore the robot is at a singularity.

#### Jacobian – 2R Planar Robot
A 2R planar robot with link lengths $L_{1} = 0.5$ and $L_{2} = 0.7$ is currently located at $\theta = \begin{bmatrix}0 \\ \frac{\pi}{2}\end{bmatrix}$ rad
1. Calculate the numerical value of its Jacobian at this point.
Formlen for Jacobian for en 2R planar robot er:
$$
J = 
\begin{bmatrix}
-L_{1} \sin(\theta_{1}) - L_{2} \sin(\theta_{1} + \theta_{2}) & -L_{2} \sin(\theta_{1} + \theta_{2}) \\ 
L_{1} \cos(\theta_{1}) + L_{2} \cos(\theta_{1} + \theta_{2}) & L_{2} \cos(\theta_{1} + \theta_{2})
\end{bmatrix}
$$
Jeg har fået givet disse værdier:
$L_{1} = 0.5$
$L_{2} = 0.7$
$\theta = \begin{bmatrix}0 \\ \frac{\pi}{2}\end{bmatrix}$
Dvs.
$\theta_{1} = 0$
$\theta_{2} = \frac{\pi}{2}$

Jeg starter med at beregne $\theta_{1} + \theta_{2}$:
$\theta_{1} + \theta_{2} = \frac{\pi}{2}$ 

$\sin(\theta_{1}) = \sin(0) = 0$
$\cos(\theta_{1}) = \cos(0) = 1$
$\sin(\theta_{1} + \theta_{2}) = \sin\left(\frac{\pi}{2}\right)= 1$
$\cos(\theta_{1} + \theta_{2}) = \cos\left(\frac{\pi}{2}\right) = 0$

Indsætter i formlen:
$$
J =
\begin{bmatrix}
-0.5 (0) - 0.7 (1) & -0.7 (1) \\ 
0.5 (1) + 0.7 (0) & 0.7 (0)
\end{bmatrix}
$$
$$
J =
\begin{bmatrix}
- 0.7 & -0.7 \\ 
0.5 & 0
\end{bmatrix}
$$

2. Calculate the resulting Cartesian space velocity if it suddenly starts moving with joint speed $\dot{\theta} = \begin{bmatrix}\frac{\pi}{3}  \\  - \frac{\pi}{6}\end{bmatrix}$
   To calculate the Cartesian space velocity $\dot{x}$ I use the formula:
$$
\dot{x} = J \dot{\theta}
$$
I have already calculated the Jacobian matrix $J$ and have been given $\dot{\theta} = \begin{bmatrix}\frac{\pi}{3}  \\  - \frac{\pi}{6}\end{bmatrix}$
Therefore I insert it into the formula:
$$
\dot{x} = J \dot{\theta} =
\begin{bmatrix}
- 0.7 & -0.7 \\ 
0.5 & 0
\end{bmatrix}
\begin{bmatrix}
\frac{\pi}{3}  \\  
- \frac{\pi}{6}
\end{bmatrix}\\
$$
   $$\dot{x}_{x} = (-0.7) \cdot \frac{\pi}{3} + (-0.7) \cdot \left(\frac{-\pi}{6}\right) = \frac{-0.7 \pi}{3} + \frac{0.7 \pi}{6} = \frac{-1.4 \pi}{6} + \frac{0.7 \pi}{6} = \frac{-0.7 \pi}{6} =  \frac{7 \pi }{60}$$
$$
\dot{x}_{y} = (0.5) \cdot \frac{\pi}{3} + (0) \cdot \left(\frac{-\pi}{6}\right) = \frac{\pi}{6}
$$
Dermed bliver $\dot{x} = \begin{bmatrix} \frac{7\pi}{60} \\ \frac{\pi}{6}\end{bmatrix}$
   
3. If the robot continues moving at this joint speed for t = 2.3 s: 
(a) Calculate the new joint configuration at this point in time. 
I can calculate the new joint configuration at that point in time using the formula:
$$
\theta_{new} = \theta_{initial} + \dot{\theta} \cdot t
$$
The initial joint angle was:
$$
\theta_{initial} = 
\begin{bmatrix}
0 \\ 
\frac{\pi}{2}
\end{bmatrix}
$$
Joint speed was:
$$
\dot{\theta} = 
\begin{bmatrix}
\frac{\pi}{3} \\
- \frac{\pi}{6} 
\end{bmatrix}
$$
For the time $t = 2.3 s$
I insert the values into the formula:
$$
\begin{bmatrix}
0 \\ 
\frac{\pi}{2}
\end{bmatrix}
+ 
\begin{bmatrix}
\frac{\pi}{3} \\
- \frac{\pi}{6} 
\end{bmatrix}
\cdot 2.3
$$
$$
\theta_{1} = \frac{23 \pi}{30} \text{ rad}
$$
$$
\theta_{2} = \frac{30 \pi}{60} - \frac{23\pi}{60} = \frac{7\pi}{60} \text{ rad}
$$
$$
\theta_{new} = 
\begin{bmatrix}
\frac{23\pi}{30} \\ 
\frac{7\pi}{60}
\end{bmatrix}
\text{ rad}
$$

(b) Calculate the resulting Jacobian. 
So now I have to use the $\theta_{new}$ joint angles to compute the jacobian.
Earlier I calculated the jacobian to be:
$$
J = 
\begin{bmatrix}
-L_{1} \sin(\theta_{1}) - L_{2} \sin(\theta_{1} + \theta_{2}) & -L_{2} \sin(\theta_{1} + \theta_{2}) \\ 
L_{1} \cos(\theta_{1}) + L_{2} \cos(\theta_{1} + \theta_{2}) & L_{2} \cos(\theta_{1} + \theta_{2})
\end{bmatrix}
$$

Look in MATLAB *10 Opgaver.mlx* for the calculation:
![[10 3b MATLAB.png]]

(c) Calculate the Cartesian-space end-effector velocity at this time.
To calculate the velocity in Cartesian-space I have to multiply the new Jacobian with the angles:
$$
\dot{x} = J_{new} \cdot \dot{\theta}
$$
![[10 3c MATLAB.png]]

