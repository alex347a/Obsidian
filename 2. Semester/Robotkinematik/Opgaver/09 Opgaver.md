Consider a collaborative robot working next to human operators on an assembly line. The robot
trajectory is made up of multiple via-points connected by linear segments (in Cartesian space). One
of the points passes close the human operator, and we therefore want to be able to specify a maximum acceleration when crossing that point. Given the following scenarios:

a) No constraints on the velocity profile.
b) The robot should NOT stop at the points, i.e. it should not decelerate to zero velocity when
crossing each intermediate point.

What type of trajectory(ies) would you choose and why?
I would choose two trapezoidal velocity profiles for point a) because the trapezoidal doesn't have any constraints so one to the point and one from the point to the next. 
For b) I would choose a cubical or quintic velocity profile, because it doesn't stop at the points, but instead passes through the points smoothly. It also allows for controlling the acceleration near the human operator which makes it safer.

MATLAB exercises are in the file *Opgaver 9.mlx*