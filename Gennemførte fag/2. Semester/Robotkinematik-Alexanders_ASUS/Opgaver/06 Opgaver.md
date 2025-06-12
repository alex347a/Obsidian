Describe the subspace in which the following robots operate:
(a) A Polar manipulator, as shown in fig. 1
The polar manipulator operates in a spherical workspace, and therefore it can reach anything that isnt directly on the base. It has an entire circle of dexterous workspace, meaning it can reach all of the points in more than 1 configuration (any orientation as opposed to just 1).
(b) A SCARA robot.
The SCARA (Selective Compliance Articulated Robot Arm) operates in a cylindrical workspace, and therefore it can only reach objects horizontally, since there are two rotational joints for planar motion and one prismatic joint for vertical displacement. So it is rigid on the vertical axis and flexible on the horizontal axis.

2. Define repeatability and accuracy, and explain how these are related to the forward and inverse kinematics problems and what effect they might have on a practical robot task.
**Repeatability** measures the ability of a robot to return to the **same position repeatedly** under identical conditions. This is meanwhile **accuracy** refers to how closely a robot's end-effector reaches a **desired position**.
In **Inverse Kinematics (IK):** Computes joint angles for a given end-effector position. Poor IK solutions can cause **inconsistent repeatability**. In **Forward Kinematics (FK):** Given joint angles, it determines the end-effector’s position. Errors in FK (e.g., calibration issues) impact **accuracy**. 
In tasks like pick-and-place, **low repeatability** causes objects to be picked inconsistently. In high-precision tasks (e.g., electronics assembly), **poor accuracy** leads to incorrect placements. 

3. Make a sketch that shows the reachable and dexterous workspaces for:
(a) A 2R planar manipulator with $L_{1} \neq L_{2}$.
If $L_{1} \neq L_{2}$ then the smallest link limits the size of the dexterous circle.
![[2R planar manipulator where L1 neq L2.png]]
(b) A 2R planar manipulator with $L_{1} = L_{2}$.
If $L_{1} = L_{2}$ then they are equal size, which makes the dexterous workspace as large as possible, because the smallest link are both of them, so they are as big as possible instead of one of them being smaller and then being limited by that one.

![[2R planar L_1 = L_2.png]]

(c) A 3R planar manipulator.
Since a 3R planar manipulator has 1 more degree of freedom it can reach everything in a dexterous workspace.
![[3R planar manipulator.png]]

![[Fig 1.png]]
MATLAB exercises are in the file *ur5_inverse_kinematics.m* 

Inverse kinematics
Consider an Epson G3-251s SCARA robot. An example frame assignment can be seen in fig. 2. Note that this frame assignment diverges from the standard one following the Modified (Craig) DH convention
![[Figure 2 Scarra robot.png]]
Calculate the full analytical (closed-form) inverse kinematics for this robot 
(*Hint: Remember the strategies for closed-form IK that we have seen in class. Specifically, you already have a solution for two of the joints, if you decompose the SCARA robot into another kind of manipulator.*)

Der er 4 led variabler: $\theta_{1}, \theta_{2}, d_{3}, \theta_{4}$
Hvis der gives en position for end-effectoren på: $(x,y,z,\phi)$
Hvor x er koordinatet i x-aksen, y er koordinatet i y-retningen, z er koordinatet i z-retningen og $\phi$ er orienteringen af end-effektoren.

De to første led kan anses som en 2R planar manipulator, hvor x og y er angivet. Dette betyder at $\theta_{1}$ og $\theta_{2}$ nemt kan findes ud fra slides 20, 21 og 22:
$$
\theta_{2} = \pm \arccos\left(\frac{x^{2} + y^{2} - a_{1}^{2} -a_{2} ^{2}}{2 \cdot a_{1} \cdot a_{2}}\right)
$$
$$
\theta_{1} = atan2(x,y) \pm \left(\frac{a_{2} \cdot \sin(\theta_{2})}{\sqrt{a_{1} ^{2} + a_{2}^{2}}}\right)
$$
Da $d_{3}$ er et prismatisk led bestemmes det direkte ud fra z ift. reference højde:
$$
d_{3}  = d_{1} - z
$$
Endeffectoren har en rotationsvinkel $\phi$ ift. basen, dermed:
$$
\theta_{4} = \phi(\theta_{1} + \theta_{2})
$$
