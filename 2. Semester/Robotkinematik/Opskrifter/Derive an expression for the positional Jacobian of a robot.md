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
\frac{\partial p_{y}}{\partial \theta_{1}} &= -0.4 \sin(\theta_{1} + \theta_{2}) - 0.5 \sin(\theta_{1})\\
\frac{\partial p_{x}}{\partial \theta_{2}} &= -0.4 \sin(\theta_{1} + \theta_{2})\\
\frac{\partial p_{x}}{\partial d_{3}} &= 0
\end{align*}
$$
$$
\begin{bmatrix}
\frac{\partial p_{x}}{\partial \theta_{1}} & \frac{\partial p_{x}}{\partial \theta_{2}} & \frac{\partial p_{x}}{\partial d_{3}} \\ 
\frac{\partial p_{y}}{\partial \theta_{1}} & \frac{\partial y}{\partial \theta_{2}} & \frac{\partial y}{\partial d_{3}} \\ 
\frac{\partial p_{z}}{\partial \theta_{1}} & \frac{\partial z}{\partial \theta_{2}} & \frac{\partial z}{\partial d{3}}
\end{bmatrix}
$$