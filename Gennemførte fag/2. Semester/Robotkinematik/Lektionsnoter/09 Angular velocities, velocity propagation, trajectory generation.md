### Summary
![[Noter/Pasted Images/Gennemførte fag/2. Semester/Robotkinematik/09/Summary.png]]
If a frame moves identically with a point then the velocity is relative 0, but if seen from another frame then the point is moving, and has a relative velocity.
### Velocity vectors as differential position
![[Velocity vectors as differential position.png]]
So at the first formula the velocity is just the time derivative of the position.
However when having multiple frames the velocity depends on the reference frame.
### Angular velocity vectors
![[Angular velocity vectors.png]]
$\Omega [\frac{rad}{s}]$
### Angular velocity
![[Angular velocity.png]]

### Linear velocity of rigid bodies
![[Linear velocity of rigid bodies.png]]
$\sideset{^{A}}{}{V}_{BORG}$ is the velocity of the frame relative to the other frame.
### Rotational velocity of rigid bodies
![[Rotational velocity of rigid bodies.png]]
So there is an angle that changes over time $\Omega \Delta t$ and a constant angle $\theta$. $\Delta Q$ is the change in distance from the two points in the circle that is projected, and is calculated using trigonometry in a right-angle triangle.
### Linear and rotational velocity of rigid bodies
![[Linear and rotational velocity of rigid bodies.png]]
### Derivative of a rotation matrix
![[Derivative of a rotation matrix.png]]
### Skew-symmetric matrices
![[Skew-symmetric matrices.png]]
For the second equation we also have plus the rotation matrix multiplied by the time derivative of the point, but since the point doesn't move it becomes 0. The last equation shows that the skew symmetric matrix is the same as the cross product of the angular velocity. 
### Other representations of angular velocity
![[Other representations of angular velocity.png]]
It's more intuitive to use axis angle when there is a change over time.
### Velocity of links
![[Velocity of links.png]]
### Velocity of links - revolute joints
![[Velocity of links - revolute joints.png]]
1. $$
\sideset{^{i+1}}{}{\omega_{i+1,\overset{.}{\theta}_{i+1}}} =\overset{.}{\theta}_{i+1} \sideset{^{i+1}}{}{\hat{Z}_{i+1}} = \begin{bmatrix}0 \\ 0 \\ \overset{.}{\theta_{i+1}}\end{bmatrix} \cdot \begin{bmatrix}0 \\ 0 \\ 1\end{bmatrix} = \begin{bmatrix}0 \\ 0 \\ \overset{.}{\theta_{i+1}}\end{bmatrix}
$$
2. 
$$
\sideset{^{i}}{}{\omega_{i+1}} = \sideset{^{i}}{}{\omega_{i}} + \sideset{^{i}_{i+1}}{}{R} \overset{.}{\theta}_{i+1} \sideset{^{i+1}}{}{\hat{Z}_{i+1}}
$$
3. 
$$
\sideset{^{i}}{}{v_{i+1}} = \sideset{^{i}}{}{v_{i}} + \sideset{^{i}}{}{\omega_{i}} \times \sideset{^i}{}{P_{i+1}}
$$
4. 
$$
\sideset{^{i+1}}{}{\omega_{i+1}} = \sideset{^{i+1}_{i}}{}{R} \cdot (\sideset{^{i}}{}{\omega_{i}} \cdot \sideset{^{i}_{i+1}}{}{R} \overset{.}{\theta}_{i+1} \sideset{^{i+1}}{}{\hat{Z}_{i+1}})
$$
Rotationsmatricerne canceller ud:
$$
\sideset{^{i+1}}{}{\omega_{i+1}} = \sideset{^{i+1}_{i}}{}{R} \cdot \sideset{^{i}}{}{\omega_{i}} + \overset{.}{\theta}_{i+1} \sideset{^{i+1}}{}{\hat{Z}_{i+1}}
$$

$$
\sideset{^{i+1}}{}{v_{i+1}} = \sideset{^{i+1}_{i}}{}{R} \cdot (\sideset{^{i}}{}{v_{i}} + \sideset{^{i}}{}{\omega_{i}} \times \sideset{^i}{}{P_{i+1}})
$$
### Velocity of links results
![[Velocity of links results.png]]
### Velocity of links - prismatic joints
![[Velocity of links - prismatic joints.png]]
## Part 2. Trajectory generation
### Offline vs. online robot trajectory control
![[Offline vs. online robot trajectory control.png]]
![[Offline vs. online robot trajectory control 2.png]]
### Multiple paths
![[Multiple paths.png]]
### Movement in joint or cartesian space
![[Movement in joint or cartesian space.png]]
### Multiple velocity profiles
![[Multiple velocity profiles.png]]
It's a GIF, but it shows you can accelerate and decelerate or go at a constant speed and still arrive at the same time.
### Different velocity profiles
![[Different velocity profiles.png]]
### Trapezoidal velocity profiles
![[Trapezoidal velocity profiles.png]]
### Exercise 
![[Exercise.png]]
$$
v(t) = \cases{ a_{max} \cdot t, \quad , t < t_{a} 
\\ v_{max}, \quad t_{a} \leq t \leq t_{a}+t_{constant} 
\\ v_{max} - a_{max} (t- (t_{a} - t_{const})) \quad t> t_{a} + t_{const}}
$$
$$
p(t) = \cases{ \int v_{max} \cdot t, \quad , t < t_{a} 
\\ \int v_{max} \cdot t_{a}  + v_{max}(t-t_{a}), \quad t_{a} \leq t \leq t_{a}+t_{constant} 
\\ \int v_{max} \cdot t_{a} + v_{max} (t-t_{a}) - \int v_{max} (t-(t_{a}-t_{const})) \quad t> t_{a} + t_{const}}
$$
$$
p(t) = \cases{ \frac{1}{2} a_{max} \cdot t^{2}, \quad , t < t_{a} 
\\ \frac{1}{2} a_{max} \cdot t_{a}^{2}  + v_{max}(t-t_{a}), \quad t_{a} \leq t \leq t_{a}+t_{constant} 
\\ \frac{1}{2} a_{max} \cdot t_{a}^{2} + v_{max} (t-t_{a}) - \frac{1}{2} a_{max} (t-(t_{a}-t_{const}))^{2}, \quad t> t_{a} + t_{const}}
$$
### Exercise results
![[Exercise results.png]]
### Trapezoidal velocity profiles: derivatives
![[Trapezoidal velocity profiles derivatives.png]]
### Cubic polynomial
![[Cubic polynomial.png]]
### Boundary constraints
![[Boundary constraints.png]]
### Higher order polynomials
![[Higher order polynomials.png]]
### Trajectories for multiple joints/dimensions
![[Trajectories for multiple joints or dimensions.png]]
Self-collision (don't consider). (They will work for the position) They don't work because in cartesian space for the orientation, since they have to be orthogonal. (can be done with quaternions however)
### Linear trajectories through multiple points
![[Linear trajectories through multiple points.png]]
For the first problem use two trapezoidal velocity profiles.
For the second problem you can use two cubic velocity profiles, where you use a constraint in the middle.
### Linear trajectories through multiple points result
![[Linear trajectories through multiple points result.png]]
### What about cartesian-space orientation?
![[What about cartesian-space orientation.png]]
### Moving in cartesian space: IK solutions
![[Moving in cartesian space IK solutions.png]]