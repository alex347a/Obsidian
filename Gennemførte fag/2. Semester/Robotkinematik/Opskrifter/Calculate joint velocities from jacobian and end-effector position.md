% Calculate joint velocities
J = [0.2, 0.1, 0; 0.1, 0.3, 0.1; 0, 0.2, 1];
xdot = [0.1; -0.1; 0.05];
% I simply use the formula
qdot = pinv(J) * xdot
which is isolated from the formula:
xdot = J * qdot
where xdot is the Cartesian velocity (linear and/or angular) of the end-effector
J is the Jacobian matrix
qdot is the resulting joint velocity vector
![[Forward and inverse velocity kinematics.png]]