#### Conceptual:
1. Name as many orientation/rotation representations as you can.
	Euler angles
	Fixed angles
	Rotation matrix
	Equivalent angle axis representation
	Quaternions
2. Explain the concept of Gimbal lock. Why and in which situations does it occur?
	Gimbal lock is when you try to reach a point but two axes line up which causes you to lose one degree of freedom, for example if you are in a WW1 plane and you try to shoot a plane passing by you above, when it passes the point directly above you, you cannot keep turning on the y-axis, you have to turn around all the way on the x-axis and then look up again.
3. Which orientation representation(s) would you use for:
	(a) Visualization 
	Angle-set conventions and equivalent angle axis
	
	(b) Calculations (e.g. applying a chain of rotations in a row after each other)
	Quaternions and rotation matrices
	
4. Do exercises 2.5 and 2.11 in the J. Craig's "Introduction to Robotics" book, p. 65.
   2.5 $_{B}^{A}R$ is a $3 \times 3$ identity matrix. What is the physical meaning of this rotation?
   If it is an identity matrix, the rotation won't do anything, but it essentially means a transform from A to B.
   2.11 Does a rotation matrix always follow commutative law for two successive rotations?
   No they do **not**. Matrix multiplication is not commutative.


#### Paper: 
1. Derive the rotation matrix corresponding to a sequence of Euler angles Z-Y-Z.
	This means a rotation first around Z, then Y and then Z again
	Since it is Euler angles, that means it is calculated from the left side to the right
	$R = R_{z}R_{y}R_{z}(\alpha)$
	$$ R_{z}(\alpha) = \begin{bmatrix} \cos \alpha & -\sin \alpha & 0 \\ \sin \alpha & \cos \alpha & 0 \\ 0 & 0 & 1 \end{bmatrix} $$
	$$ R_{y}(\beta) = \begin{bmatrix} \cos \beta & 0 & \sin \beta \\ 0 & 1 & 0 \\ -\sin \beta & 0 & \cos \beta \end{bmatrix} $$
	$$ R_{z}(\gamma) = \begin{bmatrix} \cos \gamma & -\sin \gamma & 0 \\ \sin \gamma & \cos \gamma & 0 \\ 0 & 0 & 1 \end{bmatrix} $$
	$$ R_{z}(\gamma) R_{y}(\beta) = \begin{bmatrix} \cos \gamma & -\sin \gamma & 0 \\ \sin \gamma & \cos \gamma & 0 \\ 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} \cos \beta & 0 & \sin \beta \\ 0 & 1 & 0 \\ -\sin \beta & 0 & \cos \beta \end{bmatrix} $$
	Formula for multiplying matrices:
$$
C =
\begin{bmatrix}
a_{11} b_{11} + a_{12} b_{21} + a_{13} b_{31} & a_{11} b_{12} + a_{12} b_{22} + a_{13} b_{32} & a_{11} b_{13} + a_{12} b_{23} + a_{13} b_{33} \\
a_{21} b_{11} + a_{22} b_{21} + a_{23} b_{31} & a_{21} b_{12} + a_{22} b_{22} + a_{23} b_{32} & a_{21} b_{13} + a_{22} b_{23} + a_{23} b_{33} \\
a_{31} b_{11} + a_{32} b_{21} + a_{33} b_{31} & a_{31} b_{12} + a_{32} b_{22} + a_{33} b_{32} & a_{31} b_{13} + a_{32} b_{23} + a_{33} b_{33}
\end{bmatrix}
$$
	$$
	R_z(\gamma) R_y(\beta) = \begin{bmatrix}\cos(\gamma) \cos(\beta) & -\sin(\gamma) & \cos(\gamma) \sin(\beta) \\ \sin(\gamma) \cos(\beta) & \cos(\gamma)  & \sin(\gamma) \sin(\beta)  \\ -\sin(\beta)  & 0  & \cos(\beta) \end{bmatrix} 
	$$
	$$
R_{z}(\gamma) R_{y}(\beta) R_{z}(\alpha) = \begin{bmatrix}\cos(\gamma) \cos(\beta) & -\sin(\gamma) & \cos(\gamma) \sin(\beta) \\ \sin(\gamma) \cos(\beta) & \cos(\gamma)  & \sin(\gamma) \sin(\beta)  \\ -\sin(\beta)  & 0  & \cos(\beta) \end{bmatrix} \begin{bmatrix} \cos \alpha & -\sin \alpha & 0 \\ \sin \alpha & \cos \alpha & 0 \\ 0 & 0 & 1 \end{bmatrix}
$$
	$$
	\begin{bmatrix}(\cos(\gamma) \cos(\beta)) \cos(\alpha) -\sin(\gamma) \sin(\alpha)  & -(\cos(\gamma) \cos(\beta)) -\sin(\gamma) \cos(\alpha) & \cos(\gamma) \sin(\beta) \\ (\sin(\gamma) \cos(\beta)) \cos(\alpha) + \cos(\gamma) \sin(\alpha)   & -(\sin(\gamma)\cos(\beta)) \sin(\alpha) + \cos(\gamma) \cos(\alpha)  & \sin(\gamma) \sin(\beta) \\ -\sin(\beta) \cos(\alpha)  & \sin(\beta) \sin(\alpha)  & \cos(\beta) \end{bmatrix}
	$$
2. From the matrix obtained in 1, find expressions to convert back to Euler angles Z-Y-Z.
	If I didn't have to do it by hand I would use the arctan2 function to account for which quadrant I'm in, but since I have to, I'll use arctan:
	$$
	\begin{align*}
\arccos(R_{33}) &= \beta\\
\\
R_{32}&= \sin(\alpha) \sin(\beta)\\
\sin(\alpha) &= \frac{R_{32}}{\sin(\beta)}\\
\alpha &= \arcsin\left(\frac{R_{32}}{\sin(\beta)}\right)\\
\\
\frac{R_{21}}{R_{11}}&= \frac{\sin(\gamma) \cos(\beta)}{\cos(\gamma) \cos(\beta)}\\
\tan(\gamma) &=  \frac{R_{21}}{R_{11}}\\
\gamma=\arctan\left(\frac{R_{21}}{R_{11}}\right)\\
\end{align*}
$$
Here it is important when calculating the arctan to accommodate that it only works in the range $\left(\frac{-\pi}{2}; \frac{\pi}{2}\right)$
	
3. Repeat 1 and 2 for fixed angles Z-Y-Z *(Heavy-handed hint: this is not at all double the amount of work.)*
	That would just be doing the same thing, but multiplying the opposite way, so instead of from left to right, its instead from right to left, which would make me end up with the same matrix, then after that, its the same way of extracting the variables in 2.

#### MATLAB (*See Lektier_03_robotrotation.mlx*)
1. Implement functions to convert (both ways) between:
	(a) Euler angles Z-Y-X (or fixed angles X-Y-Z) and rotation matrix.
	(b) Equivalent angle-axis and rotation matrix.
Try to reuse your existing functions from previous lectures as much as possible. 
2. Given a rotation of $35 \degree$ around the axis given by
	$$\hat{v} = \begin{pmatrix}\frac{\sqrt{2}}{2} \\ 0 \\ \frac{-\sqrt{2}}{2}\end{pmatrix}$$
	(a) Using the robot simulation from the zipped example from the previous lecture, apply this rotation to the robot tool.
	
	(b) Calculate the equivalent rotation expressed in Z-Y-X Euler angles.
	
3. The current orientation of the robot end-effector is given by: $\hat{v} = [1.566, -0.9125, 0.3780], \theta = 2.4189.$ We want to rotate $35 \degree$ around the axis that is placed on the XY-plane and place exactly in between the x- and y-axes. 
	(a) Express the desired rotation using equivalent axis-angle notation.
	
	(b) Apply this rotation onto the robot end-effector and calculate its final orientation (give the result in axis-angle notation).
	
	(c) Using the robot simulation from the zipped example from the previous lecture, write code that implements the rotations in this exercise.