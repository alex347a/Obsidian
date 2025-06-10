>![[02 Opgaver.png]]
1. 
b) Find $^{A}P_{1}$ and $^{A}P_{2}$
$$
\begin{align*}
^{A}P_{1}=\begin{pmatrix}0.1\\
-0.4\\
0.3\end{pmatrix}\\
^{B}P_{2}=\begin{pmatrix}-0.2\\
-0.3\\
0.5\end{pmatrix}\\
{}^{A} P_{BORG}=\begin{pmatrix}0.7\\
0.3\\
-0.2\\
\end{pmatrix}\\
\end{align*}
$$

$$
\begin{align*}
{}^{A}P_{2}&= {}^{A} P_{BORG}+ {}^{B}P_{2}\\
\begin{pmatrix}0.7\\
0.3\\
-0.2\end{pmatrix}+
\begin{pmatrix}-0.2\\
-0.3\\
0.5\end{pmatrix}=\begin{pmatrix}0.5\\
0\\
0.3\end{pmatrix}\\
\\
\end{align*}
$$
C) Find $^{B}P_{1}$ and $^{B}P_{2}$
$$
\begin{align*}
{}^{B}P_{2} =\begin{pmatrix}-0.2\\
-0.3\\
0.5\end{pmatrix}
\end{align*}
$$
$$
\begin{align*}
{}^{B}P_{1}={}^{A}P_{1}-{}^{A}P_{BORG}\\
\begin{pmatrix}0.1\\
-0.4\\
0.3\end{pmatrix}-
\begin{pmatrix}0.7\\
0.3\\
-0.2\\
\end{pmatrix}=\begin{pmatrix}-0.6\\
-0.7\\
0.5\end{pmatrix}\\
\end{align*}
$$

D) Find ${}^{C}P_{1}$ and ${}^{C}P_{2}$
$$
\begin{align*}
{}^{C}P_{1}&= {}^{B}P_{1}-{}^{B}P_{CORG}\\
\begin{pmatrix}-0.6\\
-0.7\\
0.5\end{pmatrix}-\begin{pmatrix}0.0\\
0.1\\
0.5\end{pmatrix}&= \begin{pmatrix}-0.6\\
-0.8\\
0\end{pmatrix}\\ 
\end{align*}
$$
$$
\begin{align*}
{}^{C}P_{2}&= {}^{B}P_{2}-{}^{B}P_{CORG}\\
\begin{pmatrix}-0.2\\
-0.3\\
0.5\end{pmatrix}-\begin{pmatrix}0.0\\
0.1\\
0.5\end{pmatrix}&= \begin{pmatrix}-0.2\\
-0.4\\
0\end{pmatrix}\\ 
\end{align*}
$$
E) Find ${}^{D}P_{1}$ and ${}^{D}P_{2}$ 
![[Rotating points.png]]
$$
\begin{align*}
{}^{D}P_{1}={}^{A}_{D}R^{T}+{}^{A}P_{1}\\
\begin{pmatrix}\cos\left(\frac{\pi}{4}\right) & \sin\left(\frac{\pi}{4}\right) & 0\\
-\sin\left(\frac{\pi}{4}\right) & \cos\left(\frac{\pi}{4}\right) & 0\\
0 & 0 & 1\end{pmatrix}\begin{pmatrix}0.1\\
-0.4\\
0.3\end{pmatrix}
\end{align*}
$$
$$
{}^{D}P_{1} = {}^{A}_{D}R^{T} \cdot {}^{A}P_{1}
$$
$$
\begin{pmatrix}
\cos\left(\frac{\pi}{4}\right) & \sin\left(\frac{\pi}{4}\right) & 0\\
-\sin\left(\frac{\pi}{4}\right) & \cos\left(\frac{\pi}{4}\right) & 0\\
0 & 0 & 1
\end{pmatrix}
\begin{pmatrix} 0.1 \\ -0.4 \\ 0.3 \end{pmatrix}
=
\begin{pmatrix}
\frac{\sqrt{2}}{2} \cdot 0.1 + \frac{\sqrt{2}}{2} \cdot (-0.4) + 0 \cdot 0.3 \\
-\frac{\sqrt{2}}{2} \cdot 0.1 + \frac{\sqrt{2}}{2} \cdot (-0.4) + 0 \cdot 0.3 \\
0 \cdot 0.1 + 0 \cdot (-0.4) + 1 \cdot 0.3
\end{pmatrix}
$$
$$
=
\begin{pmatrix}
\frac{\sqrt{2}}{2} \cdot (-0.3) \\
\frac{\sqrt{2}}{2} \cdot (-0.5) \\
0.3
\end{pmatrix}
=
\begin{pmatrix}
-0.2121 \\
-0.3535 \\
0.3
\end{pmatrix}
$$


$$
{}^{D}P_{2} = {}^{A}_{D}R^{T} \cdot {}^{A}P_{2}
$$
$$
\begin{pmatrix}
\cos\left(\frac{\pi}{4}\right) & -\sin\left(\frac{\pi}{4}\right) & 0\\
\sin\left(\frac{\pi}{4}\right) & \cos\left(\frac{\pi}{4}\right) & 0\\
0 & 0 & 1
\end{pmatrix}
\begin{pmatrix} 0.5 \\ 0 \\ 0.3 \end{pmatrix}
=
\begin{pmatrix}
\frac{\sqrt{2}}{2} \cdot 0.5 + 0 + 0 \cdot 0.3 \\
\frac{\sqrt{2}}{2} \cdot 0.5 + 0 + 0 \cdot 0.3 \\
0 \cdot 0.5 + 0 + 1 \cdot 0.3
\end{pmatrix}
$$
$$
=
\begin{pmatrix}
\frac{\sqrt{2}}{2} \cdot 0.5 \\
\frac{\sqrt{2}}{2} \cdot 0.5 \\
0.3
\end{pmatrix}
=
\begin{pmatrix}
0.3535 \\
0.3535 \\
0.3
\end{pmatrix}
$$
2. On paper derive expressions for rotation matrices that rotate:
(a) around the x-axis by theta degrees $R_{x}(\theta)$:

A counterclockwise rotation about the x-axis affects only the y- and z-coordinates, while the x-coordinate remains unchanged.

In a 2D plane where vertical is y and horizontal is z, then in polar coordinates:

$$
y = r\cdot \cos(\phi), \quad z = \sin(\phi)
$$
where r is the distance of the point from the origin (radius) and $\phi$ is the original angle of the point in the yz-plane. Then when rotating counterclockwise by the angle $\theta$:
$$
\phi' = \phi+\theta
$$
the new coordinates are:
$$
\begin{align*}
y'&= r \cdot \cos(\phi+\theta)\\
z'&= r \cdot \sin(\phi+\theta)
\end{align*}
$$
Using the [[trigonometric identities]]:
$$
\begin{align*}
\cos(a+b)&=  \cos(a) \cos(b) - \sin(a) \sin(b)\\
\sin(a+b) &= \sin(a)\cos(b) + \cos(a) \sin(b)
\end{align*}
$$
Then when substituting $\phi+\theta$:

$$
\begin{align*}
y'=\cos(\phi+\theta)&= \cos(\phi) \cos(\theta) - \sin(\phi) \sin(\theta)\\
z'= \sin(\phi+\theta) &= \sin(\phi) \cos(\theta) + \cos(\phi) \sin(\theta)
\end{align*}
$$
And since:
$$
\cos(\phi) = \frac{y}{r}, \quad \sin(\phi) = \frac{z}{r}
$$
Multiplying everything by r (since it'll cancel out):
$$
\begin{align*}
y'&= y\cos(\theta) - z \sin(\theta)\\
z' &= y \sin(\theta) + z \cos(\theta) 
\end{align*}

$$
Therefore the rotation matrix should be:
$$
\begin{pmatrix}1 & 0 & 0 \\ 0 & \cos(\theta) & -\sin(\theta) \\ 0 & \sin(\theta) & \cos(\theta)\end{pmatrix}
$$

(b) around the y-axis by theta degrees $R_{y}(\theta)$:

A counterclockwise rotation about the y-axis affects only the x- and z-coordinates, while the y-coordinate remains unchanged.

In a 2D plane where horizontal is x and vertical is z, then in polar coordinates:

$$
x = r\cdot \cos(\phi), \quad z = \sin(\phi)
$$
where r is the distance of the point from the origin (radius) and $\phi$ is the original angle of the point in the xz-plane. Then when rotating counterclockwise by the angle $\theta$:
$$
\phi' = \phi+\theta
$$
the new coordinates are:
$$
\begin{align*}
x'&= r \cdot \cos(\phi+\theta)\\
z'&= r \cdot \sin(\phi+\theta)
\end{align*}
$$
Using the [[trigonometric identities]]:
$$
\begin{align*}
\cos(a+b)&=  \cos(a) \cos(b) - \sin(a) \sin(b)\\
\sin(a+b) &= \sin(a)\cos(b) + \cos(a) \sin(b)
\end{align*}
$$
Then when substituting $\phi+\theta$:

$$
\begin{align*}
x'=\cos(\phi+\theta)&= \cos(\phi) \cos(\theta) - \sin(\phi) \sin(\theta)\\
z'= \sin(\phi+\theta) &= \sin(\phi) \cos(\theta) + \cos(\phi) \sin(\theta)
\end{align*}
$$
And since:
$$
\cos(\phi) = \frac{x}{r}, \quad \sin(\phi) = \frac{z}{r}
$$
Multiplying everything by r (since it'll cancel out):
$$
\begin{align*}
x'&= x\cos(\theta) + z \sin(\theta)\\
z' &= -x \sin(\theta) + z \cos(\theta) 
\end{align*}
$$
Therefore the rotation matrix should be:
$$
\begin{pmatrix}\cos(\theta) & 0 & \sin(\theta) \\ 0 & 1 & 0 \\ -\sin(\theta) & 0 & \cos(\theta)\end{pmatrix}
$$
MATLAB exercises (found in *Lektier_exercises_02.m*)
1. In MATLAB, implement a function $rotz(θ)$, that performs a rotation of $θ$ degrees around the $z$-axis (i.e. that implements $R_{z}(θ))$.
2. Implement the expressions from the previous exercise as functions $rotx(θ)$ and $roty(θ)$ in MATLAB.
3. Download the zipped MATLAB example from itslearning.

(a) Test your $rotx(θ)$, $roty(θ)$ and $rotz(θ)$ functions with the simulated robot model.

(b) Apply a translation $Q = \begin{pmatrix}0.2 \\ -0.05 \\ 0.15\end{pmatrix}$ on the simulated robot’s tool.4. 
4. Using combinations of $R_{x}(θ)$, $R_{y}(θ)$) and $R_{z}(θ)$, compute the following chains of rotations:
(a) Rotate $160 \degree$ around the $z$-axis, followed by $30 \degree$ around the $y$-axis.

(b) Rotate $30 \degree$ around they-axis, followed by $160 \degree$ around the $z$-axis.
5. Do you arrive at the same result in 4a and 4b? Why or why not?
I **don't** arrive at the same result in 4a and 4b because the order of rotations matter. That is because the order of rotations determine in which order the rotation matrices are multiplied, and since matrix multiplication isn't commutative (meaning $AB \neq BA$), the order changes the answer.