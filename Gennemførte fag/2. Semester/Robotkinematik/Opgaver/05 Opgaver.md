## Exercise 1
### Paper:
Figure 1 shows a Universal Robots UR5 at its zero-position, where all of its joint angles are 0, that is, where
the joint angle vector is given by:  $\theta = [0, 0, 0, 0, 0, 0]$.
![[UR5 robot.png]]
Figure 1: Universal Robots UR5 joint axes and orientation of base and tool frames.

Given the above figure, and assuming that we follow Craig’s Modified DH Parameter convention:
1. Assign frames to each of the links.
2. Compute a table of DH Parameters for the robot.

Er ikke sikker på frames, men tabellen er i hvert fald korrekt.

![[05 Opgaver Kinematik.pdf]]

MATLAB exercises are in the file *05 Opgaver.mlx*
1. Write a function that computes a forward single link transformation, $\sideset{_{i}^{i-1}}{}{T}$ , given an input consisting of the Modified DH parameters of that link.
2. For a real UR5e: $d_{1} = 0.1625$, $a_{2}=-0.425$, $a_{3}=-0.3922$, $d_{4} = 1,333$, $d_{5} = 0,0997$, $d_{6} = 0,0996$. Using the previous function, write a second function that computes the full forward kinematics of the UR5e robot, $\sideset{_{Tool}^{Base}}{}{T}$, when given a joint position vector $\theta = [\theta_{1},\theta_{2},\theta_{3},\theta_{4},\theta_{5},\theta_{6}]$, as input.

## Exercise 2:
### Paper:
Consider an RRPR SCARA robot, such as the Kuka KR: https://www.youtube.com/watch?v=Te5AfPQFz8U.
This robot can be represented by the kinematic diagram in fig. 2

![[figure 2 SCARA robot kinematic diagram.png]]

Given the above figure, and assuming that we follow Craig’s Modified DH Parameter convention:
1. Assign frames to each of the links.
2. Compute a table of DH Parameters for the robot.