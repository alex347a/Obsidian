### Summary
![[Pasted Images/2. Semester/Robotkinematik/10/Summary.png]]
### What is expected when using the Jacobian matrix?
![[What is expected when using the Jacobian matrix.png]]
### Multivariate functions
![[Multivariate functions.png]]
### Partial derivatives chain rule.
![[Partial derivatives chain rule..png]]
### Jacobian matrix
![[Jacobian matrix.png]]
### The forward velocity kinematics equation
![[The forward velocity kinematics equation.png]]
All characters in bold are vectors (characters in caps are matrices like J)
The jacobian is a function of the joint position **q**.
### The two Jacobians in robotics
![[The two Jacobians in robotics.png]]
### Building a geometric Jacobian
![[Building a geometric Jacobian.png]]
The derivative of z in the base frame is always 0, because it rotates around the z-axis.

Check *FK_2_link_planar_sym.m* for an in-class exercise.

### Calculating the positional Jacobian analytically
![[Calculating the positional Jacobian analytically.png]]

### Dimensions of Jacobian
![[Dimensions of Jacobian.png]]
## Singularities
### Forward and inverse velocity kinematics
![[Forward and inverse velocity kinematics.png]]
### The problem with the Jacobian inverse
![[The problem with the Jacobian inverse.png]]
If the determinant is 0 then there doesn't exist an inverse. For example if the matrix isn't square or if columns or rows are linearly dependant.
### Singularities Non-existence of inverse
![[Singularities Non-existence of inverse.png]]
### Rank & determinant of the Jacobian
![[Rank & determinant of the Jacobian.png]]
When the determinant is 0 or very close to 0 the velocity becomes close to infinite.
### Singularities of UR Relating them to IK solutions
![[Singularities of UR Relating them to IK solutions.png]]
How to avoid singularities:
1. Deviate from a linear path going through a singularity
2. Use a 7R robot to be able to rotate the shoulder joint.
### What if the Jacobian is not square
![[What if the Jacobian is not square.png]]
### Practical applications of the Jacobian
![[Practical applications of the Jacobian.png]]