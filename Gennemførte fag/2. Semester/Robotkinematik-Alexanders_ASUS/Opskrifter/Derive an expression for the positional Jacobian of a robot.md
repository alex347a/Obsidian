$Jp(q)$ is given by the partial derivatives of x,y and z over the angles.
![[Pasted image 20250605171938.png]]
$$
\begin{bmatrix}
\frac{\partial p_{x}}{\partial q_{1}} & \frac{\partial p_{x}}{\partial q_{2}} & \frac{\partial p_{x}}{\partial q_{3}} \\ 
\frac{\partial p_{y}}{\partial q_{1}} & \frac{\partial p_{y}}{\partial q_{2}} & \frac{\partial p_{y}}{\partial q_{3}} \\ 
\frac{\partial p_{z}}{\partial q_{1}} & \frac{\partial p_{z}}{\partial q_{2}} & \frac{\partial p_{z}}{\partial q_{3}}
\end{bmatrix}
$$
#### example:
![[Pasted image 20250605172622.png]]
The joint angles are given by $q = [\theta_{1}, \theta_{2}, d_{3}]$
I use the formula:
$$
\begin{bmatrix}
\frac{\partial p_{x}}{\partial q_{1}} & \frac{\partial p_{x}}{\partial q_{2}} & \frac{\partial p_{x}}{\partial q_{3}} \\ 
\frac{\partial p_{y}}{\partial q_{1}} & \frac{\partial p_{y}}{\partial q_{2}} & \frac{\partial p_{y}}{\partial q_{3}} \\ 
\frac{\partial p_{z}}{\partial q_{1}} & \frac{\partial p_{z}}{\partial q_{2}} & \frac{\partial p_{z}}{\partial q_{3}}
\end{bmatrix}
$$
I insert the given link lengths: $a_{1} = 0.5$ $a_{2}= 0.4$ and differentiate:
For $p_{x} = 0.4 \cos(\theta_{1} + \theta_{2}) + 0.5 \cos(\theta_{1})$:
$$
\begin{align*}
\frac{\partial p_{x}}{\partial \theta_{1}} &= -0.4 \sin(\theta_{1} + \theta_{2}) - 0.5 \sin(\theta_{1})\\
\frac{\partial p_{x}}{\partial \theta_{2}} &= -0.4 \sin(\theta_{1} + \theta_{2})\\
\frac{\partial p_{x}}{\partial d_{3}} &= 0
\end{align*}
$$
For $p_{y} = 0.4 \sin(\theta_{1} + \theta_{2}) + 0.5 \sin(\theta_{1})$:
$$
\begin{align*}
\frac{\partial p_{y}}{\partial \theta_{1}} &= 0.4 \cos(\theta_{1} + \theta_{2}) + 0.5 \cos(\theta_{1})\\
\frac{\partial p_{y}}{\partial \theta_{2}} &= 0.4 \cos(\theta_{1} + \theta_{2})\\
\frac{\partial p_{y}}{\partial d_{3}} &= 0
\end{align*}
$$
For $p_{z} = d_{3}$:
$$
\begin{align*}
\frac{\partial p_{z}}{\partial \theta_{1}} &= 0\\
\frac{\partial p_{z}}{\partial \theta_{2}} &=0\\
\frac{\partial p_{z}}{\partial d_{3}} &= 1
\end{align*}
$$
Therefore the final positional Jacobian derived becomes:
$$
\begin{bmatrix}
 -0.4 \sin(\theta_{1} + \theta_{2}) - 0.5 \sin(\theta_{1})  & -0.4 \sin(\theta_{1} + \theta_{2})  &  0 \\ 
 0.4 \cos(\theta_{1} + \theta_{2}) + 0.5 \cos(\theta_{1})  &  0.4 \cos(\theta_{1} + \theta_{2})  &  0 \\ 
 0  &  0  &  1
\end{bmatrix}
$$
In matlab:
J_p = [-a_1 * sin(theta_1) - a_2 * sin(theta_1 + theta_2), -a_2 * sin(theta_1 + theta_2), 0;
a_1 * cos(theta_1) + a_2 * cos(theta_1 + theta_2), a_2 * cos(theta_1 + theta_2), 0;
0, 0, 1]