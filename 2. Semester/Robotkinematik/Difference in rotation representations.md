## Euler Angles vs. Fixed Angles:
Euler angles are rotations about local axes.
So XYZ Euler angles means rotate about x, then y then z

Pros: 
- Easy to visualize
Cons: 
- Gimbal Lock when two axes align
- Many sequences can represent same end rotation.

Fixed angles are rotations about global axes.
So XYZ Fixed actually means first rotate about z, then y, then x

Cons: 
- Gimbal Lock when two axes align
- Many sequences can represent same end rotation.

## Equivalent axis-angle
Its a single rotation of an angle $\theta$ about a unit axis $k = [k_{x}, k_{y}, k_{z}]$ 
