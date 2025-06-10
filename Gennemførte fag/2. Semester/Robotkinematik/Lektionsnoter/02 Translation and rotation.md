### Summary of this lecture:
![[Noter/Pasted Images/2. Semester/Robotkinematik/02/Summary.png]]
## Types of joints
![[Types of Robot Joints.png]]
Revolute:
1 degree of freedom.

Prismatic:
1 degree of freedom.

Cylindrical:
2 degrees of freedom.
Can move in one axis and rotate around another.


Spherical:
You can use three revolute joints to simulate a spherical joint, because spherical joints are fragile and expensive.

Planar:
3 degrees of freedom.
Can move in x and y axis and rotate around the z-axis.

Screw:

## Degrees of freedom (DoF)
How many angles the joints can move in.

## Robot Workspace
![[Robot Workspace.png]]
## Common Robot Frames
![[Common Robot Frames.png]]

## Position (in a reference frame)
![[Position (in a reference frame).png]]
## Craig's notation (Position)
![[Craig's notation (Position).png]]
## Translation
![[Translation.png]]
![[Translation 2.png]]
## Translation vs. Position
![[Translation vs. Position.png]]
The position is relative to the frame while translation is an operation, where if you have the same translation in two different frames you would get different values for the position because you are using two different frames but the actual position would be the same.
## Rotation matrix
![[Rotation Matrix.png]]
## Positive or negative rotation
Use the handrule, where the thumb represents the axis that is being rotated around and the four other fingers indicate if the direction is positive or negative.

## Rotation matrix (for any angle)
Use trigonometry. 
![[Rotation matrix (for any angle).png]]
## Rotation matrix properties
![[Rotation matrix properties.png]]
It is much easier to calculate the transposed matrix compared to the inverse.

## Rotating points
![[Rotating points.png]]
## Chains of rotations
![[Chains of rotations.png]]