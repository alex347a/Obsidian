![[Right-Hand Rule.png]]
![[Special matrices.png]]
Since the axis are always orthogonal, that means the transposed matrix is always the same as the inverse matrix, which makes calculating the inverse matrix a lot easier (as long as the axes are unit vectors).
For at se matlab funktioner tjek slides for lektion 1
![[Rotation matrix properties.png]]
![[Rotating points.png]]
![[Chains of rotations.png]]
![[Euler angles Z-Y-X to rotation matrix.png]]
![[Fixed angles x-y-z to rotation matrix.png]]
![[General Mappings (in multiple frames).png]]
![[How to save computation.png]]
![[Generic Homogenous Transformations.png]]
You can use homogenous transformations for only translations and rotations, where you just write 0 in the place where you don't have your translation or rotation.

$$
\begin{align*}
_{B}^{A}R ^{B}P =^{A}P - ^{A}P_{Borg}\\
_{A}^{B}R _{B}^{A}R ^{B}P = _{A}^{B}R (^{A}P - ^{A}P_{Borg})\\
\end{align*}
$$
![[Exercise Solution (Efficient inverse).jpg]]
![[Example 2 Space Robotics.png]]
$$
\sideset{^{T}_{A}}{}{T} = \sideset{_{T}^{B}}{}{T^{-1}} \sideset{^{Sh} _{B}}{}{T^{-1}} \sideset{^{W}_{Sh}}{}{T^{-1}} \sideset{_{Sat}^{W}}{}{T} \sideset{^{Sat}_{A}}{}{T}
$$
Essentially you look at the arrows, if you are going the opposite way you need the inverse, if you are following the arrow direction it is simply the transformation matrix. Also you can just use this rule:
![[Rotating points.png]]
![[Chains of rotations.png]]
## DH parametre
![[DH parameters procedure.png]]
DET HER ER FOR AT FINDE $\alpha_{i}$ og $a_{i}$ men i DH parameter skemaet skal man bruge $\alpha_{i-1}$ og $a_{i-1}$ Derfor er det lidt lettere at bruge:
![[Recap DH parameters.png]]
![[DH parameters example.png]]
HUSK AT PRISMATIC JOINTS SKAL LIGGE OVENI REVOLUT JOINTS, ALTSÅ NÅR DE ER FULLY EXTENDED LIGESOM HER:
![[Assignment of frames example.png]]

Tjek lektion 9 for alle de forskellige velocity profiles.
Tjek lektion 10 og 11 for Jacobian, sinuglarities og numerical IK og manipulability.