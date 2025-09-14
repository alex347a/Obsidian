### Summary of this lecture:
![[Noter/Pasted Images/Gennemførte fag/2. Semester/Robotkinematik/03/Summary.png]]
![[Overview of Orientation Representations.png]]
## Quaternions  
Quaternions are a number system that extends complex numbers and are commonly used in 3D rotations. They consist of one real component and three imaginary components:  

$$ q = w + xi + yj + zk $$  

where $w, x, y, z$ are real numbers. Quaternions avoid gimbal lock and allow smooth interpolation (SLERP) in 3D rotations, making them widely used in robotics and computer graphics. 
However they use 4D and therefore we don't use them intuitively, and only need to know about the concept in this course, and not how to calculate using quaternions.  

---

## Rotation Matrices  
A rotation matrix is a $3 \times 3$ orthonormal matrix that represents a rotation in 3D space. It transforms a vector without changing its magnitude. A general rotation matrix $R$ follows the properties:  

$$ R^T R = I, \quad \det(R) = 1 $$  

For example, a rotation about the $z$-axis by an angle $\theta$ is:  

$$
R_z(\theta) =
\begin{bmatrix}
\cos\theta & -\sin\theta & 0 \\
\sin\theta & \cos\theta & 0 \\
0 & 0 & 1
\end{bmatrix}
$$  

Rotation matrices are commonly used in kinematics and transformations.  

---

## Equivalent Angle-Axis Representation  
This represents a rotation by an angle $\theta$ around a unit axis $\mathbf{\hat{n}}$ (a normalized 3D vector). Any rotation in 3D can be described by:  

$$ \mathbf{R} = \text{Rot}(\theta, \mathbf{\hat{n}}) $$  

where the rotation matrix can be derived using Rodrigues' formula:  

$$
R = I + \sin\theta [\mathbf{\hat{n}}]_\times + (1 - \cos\theta) [\mathbf{\hat{n}}]_\times^2
$$  

where $[\mathbf{\hat{n}}]_\times$ is the skew-symmetric matrix of $\mathbf{\hat{n}}$.  

**Universal Robots (UR) uses this representation**, meaning rotations are specified using an axis of rotation and an angle.  

---

## Angle-Set Conventions  
These define how a sequence of rotations is applied to describe orientation. Common conventions include:  

1. **Euler Angles (XYZ, ZYX, etc.)** – A sequence of three rotations about different axes.  
2. **Fixed Angles** – Rotations applied to a fixed coordinate frame.  
3. **Intrinsic Angles** – Rotations applied relative to the moving frame.  
4. **Tait-Bryan Angles** – A specific form of Euler angles (like yaw-pitch-roll).  

Different conventions result in different rotation sequences and interpretations of angles.  


![[Orientation Representations use cases.png]]
## Euler Angles vs. Fixed Angles
For Euler Angles we stack from left to right while fixed angles are from right to left.
That means that if the fixed angles are in the reverse order of the Euler angles, they are the same.
![[Euler angles Z-Y-X to rotation matrix.png]]
![[Fixed angles x-y-z to rotation matrix.png]]
![[Relation between fixed and euler angles.png]]
## Local vs. Global Coordinate Frame (and Pre/Post-multiplication)
![[Local vs. Global Coordinate Frame.png]]
## Gimbal-lock (An issue with Angle-sets)
![[Gimbal Lock.png]]
![[Gimbal lock, when does it happen.png]]
## Rotation Matrix to Fixed Angles
![[Rotation Matrix to Fixed Angles.png]]
![[Rotation Matrix to Fixed Angles 2.png]]
## atan vs. atan2
![[atan vs. atan2.png]]
## Rotation Matrix to Other Angle-Sets
![[Rotation Matrix to Other Angle-Sets.png]]
## Equivalent Angle-Axis (Euler Vector)
![[Equivalent Angle-Axis (Euler Vector).png]]
## Equivalent Angle-Axis to Rotation Matrix
![[Equivalent Angle-Axis to Rotation Matrix.png]]
## Rotation Matrix to Equivalent Angle-Axis
![[Rotation Matrix to Equivalent Angle-Axis.png]]