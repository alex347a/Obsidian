### Translation Mappings (with vectors)
![[Translation Mappings (with vectors).png]]
### Rotational Mappings (with rotation matrices)
![[Rotational Mappings.png]]
### General mappings (with both translation and rotation)
![[General mappings.png]]
Apply rotation first, then translation.
### General Mappings (in multiple frames)
![[General Mappings (in multiple frames).png]]
### How to save computation
![[How to save computation.png]]
### From Euclidean to Projective Geometry
![[From Euclidean to Projective Geometry.png]]
### From Cartesian to Homogenous Coordinates
![[From Cartesian to Homogenous Coordinates.png]]
### Generic Homogenous Transformations
![[Generic Homogenous Transformations.png]]
### Shearing and Scaling
![[Shearing and Scaling.png]]
### Homogenous Transformations (without shearing and scaling)
![[Homogenous Transformations (without shearing and scaling).png]]
You can use homogenous transformations for only translations and rotations, where you just write 0 in the place where you don't have your translation or rotation.

$$
\begin{align*}
_{B}^{A}R ^{B}P =^{A}P - ^{A}P_{Borg}\\
_{A}^{B}R _{B}^{A}R ^{B}P = _{A}^{B}R (^{A}P - ^{A}P_{Borg})\\
\end{align*}
$$
![[Exercise Solution (Efficient inverse).jpg]]
### A Note on Notation
![[A Note on Notation.png]]

### Opgave
![[Example 2 Space Robotics.png]]
$$
\sideset{^{T}_{A}}{}{T} = \sideset{_{T}^{B}}{}{T^{-1}} \sideset{^{Sh} _{B}}{}{T^{-1}} \sideset{^{W}_{Sh}}{}{T^{-1}} \sideset{_{Sat}^{W}}{}{T} \sideset{^{Sat}_{A}}{}{T}
$$
Essentially you look at the arrows, if you are going the opposite way you need the inverse, if you are following the arrow direction it is simply the transformation matrix.