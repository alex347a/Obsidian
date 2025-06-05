## Euler Angles vs. Fixed Angles:
#### Euler angles are rotations about local axes.
So XYZ Euler angles means rotate about x, then y then z

Pros: 
- Easy to visualize
Cons: 
- Gimbal Lock when two axes align
- Many sequences can represent same end rotation.

#### Fixed angles are rotations about global axes.
So XYZ Fixed actually means first rotate about z, then y, then x

Cons: 
- Gimbal Lock when two axes align
- Many sequences can represent same end rotation.

To covert between the two remember to both reverse the order of the rotations but also the order of the angles, so the angle for x in Euler is also the angle for x in fixed.
## Equivalent axis-angle
Its a single rotation of an angle $\theta$ about a unit axis $k = [k_{x}, k_{y}, k_{z}]$ 

Pros: 
- NO gimbal lock
- Compact, just 4 numbers instead of 9
Cons:
- Not intuitive

## Rotation matrices (SO(3))
A 3x3 orthogonal matrix where each column represents the new basis vectors.

Pros:
- NO singularities
Cons:
- 9 numbers, which is redundant since there are only 3 DOF
## Quaternions
4D extension of complex numbers: $q = [w,x,y,z]$ where $w = \cos\left(\frac{\theta}{2}\right)$ and $[x,y,z] = k \cdot \sin\left(\frac{\theta}{2}\right)$

Pros:
- NO gimbal lock
- NO singularities
Cons:
- Not intuitive.