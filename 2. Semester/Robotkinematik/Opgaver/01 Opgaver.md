## Context and definitions
1. What differentiates robots from traditional automation?
   The main difference is flexibility. ![[Robots vs. Traditional Industrial Automation.png]]
   
2. What are the main assumptions of Kinematics?
   We assume there are no external forces, meaning the objects are rigid and the movement of the robot is smooth and continuous, meaning inertia is ignored.
   
3. What two kinds of parts is a robotic manipulator made of?
   1. Rigid links, which don't move on their own.
   2. Joints, which allow relative movement between links.
![[Rigid Body Tree.png]]

Given vectors:
$$
v_{1}= \begin{pmatrix}5 \\ -3 \\ 1\end{pmatrix} \text{ and } v_{2}= \begin{pmatrix}2 \\ 8 \\ -7\end{pmatrix}
$$
1. Calculate their lengths:
   
$$
\begin{align*}
|v_{1}|=\sqrt{5^{2}+(-3)^{2}+1^{2}}&= \sqrt{35}\\
|v_{2}|=\sqrt{2^{2}+8^{2}+(-7)^{2}}=\sqrt{68+49}&= \sqrt{117}
\end{align*}
$$
   
2. Normalize them in order to obtain $\hat{v_{1}}$, $\hat{v_{2}}$
   
$$
\begin{align*}
\hat{v}&= \frac{v}{|v|}\\
\hat{v_{1}}=\frac{1}{\sqrt{35}}\begin{pmatrix}5\\
-3\\
1\\\end{pmatrix}=\begin{pmatrix}\frac{5}{\sqrt{35}}\\
\frac{-3}{\sqrt{35}}\\
\frac{1}{\sqrt{35}}\end{pmatrix}\\
\hat{v_{2}}=\frac{1}{\sqrt{117}}\begin{pmatrix}2\\
8\\
-7\\\end{pmatrix}=\begin{pmatrix}\frac{2}{\sqrt{117}}\\
\frac{8}{\sqrt{117}}\\
\frac{-7}{\sqrt{117}}\end{pmatrix}
\end{align*}
$$
   
3. Calculate $2 v_{1} + 5 v_{2}$ 
$$
2\cdot \begin{pmatrix}5 \\ -3 \\ 1\end{pmatrix} + 5\cdot \begin{pmatrix}2 \\ 8 \\ -7\end{pmatrix}=\begin{pmatrix}10 \\ -6 \\ 2\end{pmatrix} + \begin{pmatrix}10 \\ 40 \\ -35\end{pmatrix}=\begin{pmatrix}20 \\ 34 \\ -33\end{pmatrix}
$$
4. Calculate the scalar (dot) product: $v_{1} \cdot v_{2}$
$$
\begin{align*}
\vec{a}\cdot \vec{b}&= a_{1}b_{1}+a_{2}b_{2}+a_{3}b_{3}\\
v_{1}\cdot v_{2} &=  5\cdot 2+(-3)\cdot 8+1\cdot (-7)\\
&= 10-24-7\\
&= -21\\
\end{align*}
$$
5. Calculate the vector (cross) product: $v_{1} \times v_{2}$.
$$
\begin{align*}
\vec{a} \times \vec{b} &= \begin{pmatrix}a_{2}b_{3}-a_{3}b_{2}\\
a_{3}b_{1}-a_{1}b_{3}\\
a_{1}b_{2}-a_{2}b_{1}\end{pmatrix}\\
v_{1} \times v_{2}&= \begin{pmatrix}-3\cdot (-7)-1\cdot 8\\
1\cdot 2-5\cdot (-7)\\
5\cdot 8-(-3)\cdot 2\end{pmatrix}\\
= \begin{pmatrix}21-8\\
2+35\\
40+6\end{pmatrix} &= \begin{pmatrix}13\\
37\\
46\end{pmatrix}
\end{align*}
$$
6. Show that $v_{1} \times v_{2}$ is orthogonal to both $v_{1}$ and $v_{2}$.
   To show that the cross product is orthogonal to both $v_{1}$ and $v_{2}$ the dot product of the cross product and the individual vectors are calculated, because if the dot product to both are 0, then that means that $\cos(\theta)=0$ which is only true when $\theta = 90 \degree$ 
$$
\begin{align*}
\vec{v_1} \cdot (\vec{v_1} \times \vec{v_2}) &= 5 \cdot 13 + (-3) \cdot 37 + 1 \cdot 46 \\
&= 65 - 111 + 46 \\
&= 0 \\
\vec{v_2} \cdot (\vec{v_1} \times \vec{v_2}) &= 2 \cdot 13 + 8 \cdot 37 + (-7) \cdot 46 \\
&= 26 + 296 - 322 \\
&= 0 \\
\vec{v_1} \times \vec{v_2} &\text{ is orthogonal to both } \vec{v_1} \text{ and } \vec{v_2}.
\end{align*}
$$
7. Calculate the angle between $v_{1}$ and $v_{2}$.
   This can be done by using the formula:
### Vinklen imellem to vektorer
$$
\theta=\arccos\left(\frac{{\vec{a}\cdot \vec{b}}}{|a|\cdot|b|}\right)
$$
$$
\arccos\left(\frac{-21}{\sqrt{35}\cdot\sqrt{117}}\right)= 1.9052
$$

Trigonometric identities
a) What is $\sin\left(\frac{\pi}{4}\right)$?
$$
\sin\left(\frac{\pi}{4}\right)=\frac{\sqrt{2}}{2}
$$
b) What are $\sin\left(\frac{7\pi}{12}\right)$ and $\cos\left(\frac{7\pi}{12}\right)$?
$$
\sin\left(\frac{7\pi}{12}\right) = \sin\left(\frac{3\pi}{12}+ \frac{4\pi}{12}\right)
$$
Bruger kendte værdier:

$$
\sin\left(\frac{\pi}{4}\right) = \frac{\sqrt{2}}{2}, \quad \cos\left(\frac{\pi}{4}\right) = \frac{\sqrt{2}}{2}
$$

$$
\sin\left(\frac{\pi}{3}\right) = \frac{\sqrt{3}}{2}, \quad \cos\left(\frac{\pi}{3}\right) = \frac{1}{2}
$$
Bruger formlen:
$$
\sin(x+y)=\sin(x)\cos(y)+\sin(y)\cos(x)
$$
$$
= \sin\left(\frac{\pi}{4}\right) \cos\left(\frac{\pi}{3}\right) + \cos\left(\frac{\pi}{4}\right) \sin\left(\frac{\pi}{3}\right)
$$

$$
= \left(\frac{\sqrt{2}}{2} \cdot \frac{1}{2} \right) + \left(\frac{\sqrt{2}}{2} \cdot \frac{\sqrt{3}}{2} \right)
$$

$$
= \frac{\sqrt{2}}{4} + \frac{\sqrt{6}}{4}
$$

$$
= \frac{\sqrt{2} + \sqrt{6}}{4}
$$

$$
\sin\left(\frac{7\pi}{12}\right) = \frac{\sqrt{2} + \sqrt{6}}{4}
$$
Nu for cosinus:
$$
\cos\left(\frac{7\pi}{12}\right) = \cos\left(\frac{3\pi}{12} + \frac{4\pi}{12}\right)
$$
$$
\cos(x+y)=\cos(x)\cos(y)+\sin(y)\sin(x)
$$
$$
= \cos\left(\frac{\pi}{4}\right) \cos\left(\frac{\pi}{3}\right) - \sin\left(\frac{\pi}{4}\right) \sin\left(\frac{\pi}{3}\right)
$$

$$
= \left(\frac{\sqrt{2}}{2} \cdot \frac{1}{2} \right) - \left(\frac{\sqrt{2}}{2} \cdot \frac{\sqrt{3}}{2} \right)
$$

$$
= \frac{\sqrt{2}}{4} - \frac{\sqrt{6}}{4}
$$

$$
= \frac{\sqrt{2} - \sqrt{6}}{4}
$$
$$
\cos\left(\frac{7\pi}{12}\right) = \frac{\sqrt{2} - \sqrt{6}}{4}
$$
c) What are $\sin\left(\frac{\pi}{12}\right)$ and $\cos\left(\frac{\pi}{12}\right)$ 
Since $\sin\left(\frac{\pi}{2}\right)=\frac{\sqrt{2}}{2}$ And $\sin\left(\frac{7\pi}{12}\right)=\frac{\sqrt{2} + \sqrt{6}}{4}$
Then 
$$
\begin{align*}
\sin\left(\frac{\pi}{12}\right)&= \sin\left(\frac{7\pi}{12}\right)-\sin\left(\frac{\pi}{2}\right)\\
&= \frac{\sqrt{2} + \sqrt{6}}{4}-\frac{\sqrt{2}}{2}\\
&= \frac{\sqrt{2} + \sqrt{6}}{4}-\frac{2\sqrt{2}}{4}\\
&= \frac{\sqrt{6}-\sqrt{2}}{4}\\
\end{align*}
$$
And the same for cos:
Since $\cos\left(\frac{\pi}{2}\right)=\frac{\sqrt{2}}{2}$ And $\cos\left(\frac{7\pi}{12}\right) = \frac{\sqrt{2} - \sqrt{6}}{4}$
$$
\begin{align*}
\cos\left(\frac{\pi}{12}\right)&= \cos\left(\frac{7\pi}{12}\right)-\cos\left(\frac{\pi}{2}\right)\\
&= \frac{\sqrt{2} - \sqrt{6}}{4}-\frac{\sqrt{2}}{2}\\
&= \frac{\sqrt{2} - \sqrt{6}}{4}-\frac{2\sqrt{2}}{4}\\
&= \frac{-\sqrt{2}-\sqrt{6}}{4}\\
\end{align*}
$$