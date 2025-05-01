### Summary
![[Noter/Pasted Images/2. Semester/Robotkinematik/11/Summary.png]]
### Numerical IK: Conceptually
![[Numerical IK Conceptually.png]]
The reason we move in small steps is because the Jacobian is a function of the joint position, so when the position changes the Jacobian also changes. So you can't just take one big step because the moves in cartesian spaces changes depending on the Jacobian that depends on the joint configuration. Because we are approximating a curved line in joint space as small chunks of straight lines, there are approximation errors, just like when taking the integral you divide the function into n numbers of rectangles.
### Formally: Numerical IK using Newton-Raphson
![[Formally Numerical IK using Newton-Raphson.png]]
Se f.eks. [[Taylor udviklinger]].
### IK: Newton Raphson Algorithm
![[IK Newton Raphson Algorithm.png]]
### Convergence to different solutions
![[Convergence to different solutions.png]]
The closest solution is the one you will get as a result, so depending on your starting position you only get the one joint configuration that is closest to the point. If you solve it analytically you can get all of the joint configurations that can be used to arrive at the point, not just the closest. So in the image depending on where you start on the slope you fall either one or the other way.
### What do we want to arrive at?
![[What do we want to arrive at.png]]
If we have a redundant robot the matrix of the Jacobian is not square, therefore we don't have a determinant, and therefore can't use that to calculate how close we are to a singularity.
### In other words (in other pictures)
![[In other words (in other pictures).png]]
For the left robot for example we can move far back, but not forwards, but since we want to use an ellipsoid it has to be symmetrical, same for the last one we can move far back but not very far forwards.
### Manipulability measure
![[Manipulability measure.png]]
### Matrices as linear transformations
![[Matrices as linear transformations.png]]
### Explanding the concept to all vectors
![[Explanding the concept to all vectors.png]]
### Back to our robots
![[Back to our robots.png]]
### Deriving an ellipsoid
![[Deriving an ellipsoid.png]]
### Manipulability ellipsoid
![[Manipulability ellipsoid.png]]
### Putting it all together
![[Putting it all together.png]]
### More manipulability measures
![[More manipulability measures.png]]
In the formula on the top it is supposed to be the square root of the determinant of A.
So the correct formula is:
$$
\mu = \sqrt{\det(JJ^{T})} = \sqrt{\det(A)}
$$
### Manipulability: Practical application
![[Manipulability Practical application.png]]
You can plot the manipulability as a heatmap to see which points are close to singularities.