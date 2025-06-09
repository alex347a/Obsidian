# Kinematics in Robotics

Kinematics is the study of the relationship between a robot's joint coordinates and its spatial layout. It plays a crucial role in robotics, enabling accurate calculations for tasks such as positioning a gripper, moving a tool from point A to point B, and predicting potential collisions. Kinematics focuses on the instantaneous values of the robot's coordinates, excluding the effects of forces and torques, which are covered under dynamics.

This chapter covers the kinematics of various robot mechanisms, including the concepts of configuration space and workspace, and the process of forward kinematics.

## 1. Configuration Space and Workspace

A robot's kinematic structure is described by a set of links (rigid bodies) and joints that constrain their relative movement. These joints may allow rotational, translational, or spherical movements.

### Robot Layout Descriptions

- **Joint Coordinates**: A list of coordinates (angles or distances) relative to a reference frame (zero position).
- **Spatial Representation**: A representation of links in the 2D or 3D world, using matrices to describe each link's frame relative to a world coordinate system.

- **Configuration**: The joint coordinates of the robot, which serve as a minimal, non-redundant representation of its layout.
- **Workspace**: The 2D or 3D world in which the robot operates.

Configuration space is a simplified representation, unlike maximal coordinates, which store the frame of each link. The configuration space ensures joint constraints are satisfied.

### Robot Structure Types

- **Joint Types**:
  - **Revolute**: Allows rotation about a common axis.
  - **Prismatic**: Allows translation along a common axis.
  - **Spherical**: Allows rotation around a point.

- **Mechanism Topology**:
  - **Serial**: Links form a single ordered chain.
  - **Branched**: Links may have multiple child links.
  - **Parallel**: Joints form a closed loop, allowing movement without disconnecting the system.

Mechanisms are characterized by the sequence of joint types:
- **3P**: xyz gantry
- **3P3R**: 6-axis CNC machine
- **6R**: Industrial robot with revolute joints

- **Base Types**:
  - **Fixed Base**: A base link is rigidly attached to the world.
  - **Floating Base**: All links are free to move in space.
  - **Mobile Base**: The base link moves in a 2D plane while other links are free in 3D space.

### 1.2 Configurations and Configuration Space

- **Degrees of Freedom (DOF)**: The number of independently moving dimensions of the robot.
  - For serial or branched fixed-base mechanisms, DOF is the sum of the joint mobilities.
  - For floating or mobile bases, the DOF is increased to account for the movement of the base link.

#### Floating Bases and Virtual Linkages

- **Virtual Linkages**: Used to represent the mobility of the base link in floating or mobile robots. For example, a 2D floating base can be represented by a 2PR manipulator, while a 3D floating base uses a 3P3R manipulator.

#### Joint Limits and Configuration Space

- Joint mobility is often limited by mechanical stops, and these limits define the valid joint values.
- The **configuration space** is the Cartesian product of the joint ranges, representing all possible configurations of the robot.

Example: For a 2RPR mechanism with joint limits, the configuration space is:
\[ [−\frac{\pi}{2}, \frac{\pi}{2}]^2 × [z_{min}, z_{max}] × SO(2) \]

#### Parallel Mechanisms

Determining the configuration space of parallel mechanisms is more complex. The mobility is calculated using a formula that accounts for the links and joints' degrees of freedom.

Example: For a 4-bar linkage in 2D, the mobility is calculated as:
$[ M = 3 \times 4 - 4 \times (3-1) - (3-0) = 1 ]$

## 1.3 End Effectors and Reachable Workspaces

- **Workspace**: Refers to the range of positions and orientations of a robot's end effector, often at the far end of a serial chain of links.
- The **reachable workspace** is the area in the workspace that can be accessed by any valid configuration.

### 1.4 Examples

- A 2R manipulator with joint limits of ±45° for the first joint and ±90° for the second joint results in a reachable workspace shaped like an annulus (a planar donut shape).

## 2. Forward Kinematics

Forward kinematics involves calculating the frames of a robot's links given its configuration and kinematic structure. It can be derived mathematically or computed in software for tasks like motion prediction and collision detection.

### 2.1 2D Forward Kinematics for a Serial Robot
First, let us derive the forward kinematics for an $n$-link serial robot. There are $n$ links $l_1, \dots, l_n$, with the first link attached to the world by a revolute joint, and the remaining $n-1$ links attached to the prior link by a revolute joint. Assume that at the 0 position, the links' coordinate frames are defined by their reference transforms: 
$$
T_{1,ref}, T_{2,ref}, \dots, T_{n,ref}
$$
each expressed relative to the world coordinate system. To make notation more convenient, we shall represent these by $3 \times 3$ matrices in homogeneous coordinates. We shall also assume that each joint $j_1, \dots, j_n$ is placed at the origin of the frame of $l_i$, and each joint angle $q_i$ gives the angle of link $l_i$ relative to its parent link, not in absolute heading.

2.1.1
When the first joint rotates by angle $q_1$, the frame of the first link $T_1(q_1)$ is changed. $T_1(q_1)$ can be derived by observing how a point $X$ attached to $l_i$ would be moved. Let $x_1$ be the coordinates of this point relative to the link's frame (augmented with a 1, in homogeneous coordinates).

First, observe that relative to $l_1$'s reference frame, $X$ has coordinates
$$
x_{1,ref} = R(q_1)x_1 = \begin{bmatrix} \cos q_1 & \sin q_1 & 0 \\ -\sin q_1 & \cos q_1 & 0 \\ 0 & 0 & 1 \end{bmatrix} x_1.
$$

Next, we can convert coordinates in $l_1$'s reference frame to the world via multiplication by $T_{1,ref}$ to obtain the final value of $X$'s world coordinates, $x_W$:
$$
x_W = T_{1,ref} R(q_1) x_1.
$$
We can now define $T_1(q_1) \equiv T_{1,ref} R(q_1)$ as the frame of link 1.

Let us proceed to link 2, which moves in space as a function of both $q_1$ and $q_2$. Imagine $X$ now be a point attached to link 2, and let $x_2$ be its coordinates with respect to the link's frame. Due to the serial nature of the chain, we can imagine first rotating link 2 by angle $q_2$ and then rotating link 1 by angle $q_1$. To perform this operation, let us proceed with the following order of transformations:

As before, the first transform consists of a rotation about the origin:
$$
x_{2,ref} = R(q_2) x_2.
$$

Next, we convert to link 1's coordinates. Note that those coordinates will be the same whether link 1 is rotated or not, since the entire substructure after link 1 rotates in unison. As a result, we can perform this change of coordinates at the reference configuration, which yields the following formula:
$$
x_1 = (T_{1,ref})^{-1} T_{2,ref} x_{2,ref}.
$$
Finally, the third step is simply an application of $T_1(q_1)$ as before:
$$
x_W = T_1(q_1) x_1.
$$

Putting this all together, we obtain the equation:
$$
x_W = T_1(q_1) (T_{1,ref})^{-1} T_{2,ref} R(q_2) x_2 = T_2(q_1, q_2) x_2,
$$
where 
$$
T_2(q_1, q_2) = T_1(q_1) (T_{1,ref})^{-1} T_{2,ref} R(q_2).
$$

Repeating this step down the chain, we find the following recursive equation holds for $i > 1$:
$$
T_i(q_1, \dots, q_i) = T_{i-1}(q_1, \dots, q_{i-1}) (T_{i-1,ref})^{-1} T_{i,ref} R(q_i).
$$

This can be simplified further by assuming the reference parent transforms are given by the relative transforms 
$$
T_{i-1,ref} i_{ref} \equiv (T_{i-1,ref})^{-1} T_{i,ref}.
$$
Then, the simplified equation is:
$$
T_i(q) = T_{i-1}(q) T_{i-1,ref} i_{ref} R(q_i).
$$

Reading this equation from right to left, the three steps described above become clear: 
1) rotate about the joint, 
2) convert to the coordinates of the parent link, 
3) transform by the parent's transform.

2.1.2 Canonical examples
Let us now work out an example analytically. By judiciously choosing reference frames, a canonical planar $n$-link robot is defined by link lengths $L_1, \dots, L_{n-1}$ giving the distance between subsequent joints. The reference transform of link 1 is placed $L_0$ units away from the world coordinate system on the $x$ axis, and the reference transform of link $i > 1$ is placed $L_i$ units away from its parent along the $x$ axis. We will also define an end effector point at distance $L_n$ from the origin of the $n$th joint, also translated along the $x$ axis.

With this convention, we have the reference transforms given by:
$$
T_{i-1,ref} i_{ref} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ L_i & 0 & 1 \end{bmatrix}.
$$
Hence, we derive the first link's transform:
$$
T_1(q_1) = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & L_0 \\ 0 & 0 & 1 \end{bmatrix}
\begin{bmatrix} \cos q_1 & \sin q_1 & 0 \\ -\sin q_1 & \cos q_1 & 0 \\ 0 & 0 & 1 \end{bmatrix}
= \begin{bmatrix} \cos q_1 & \sin q_1 & 0 \\ -\sin q_1 & \cos q_1 & 0 \\ L_0 & 0 & 1 \end{bmatrix}.
$$

Then, the second link's transform is given by:
$$
T_2(q_1, q_2) = T_1(q_1)
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & L_1 \\ 0 & 0 & 1 \end{bmatrix}
\begin{bmatrix} \cos q_2 & \sin q_2 & 0 \\ -\sin q_2 & \cos q_2 & 0 \\ 0 & 0 & 1 \end{bmatrix}
= \begin{bmatrix} c_1 & s_1 & 0 \\ -s_1 & c_1 & 0 \\ L_0 + c_1 L_1 & L_1 s_1 & 1 \end{bmatrix}.
$$

If this were a 2R manipulator, and we wished to derive the coordinates of the end effector point, we simply apply this transform to the point $(L_2, 0, 1)$ to obtain:
$$
T_2(q_1, q_2) \begin{bmatrix} L_2 \\ 0 \\ 1 \end{bmatrix}
= \begin{bmatrix} L_0 + c_1 L_1 + c_1^2 L_2 \\ s_1 L_1 + s_1^2 L_2 \\ 1 \end{bmatrix}.
$$

More generally, if we are given an $n$-link robot and define $c_1, \dots, c_k = \cos \left( \sum_{i=1}^k q_i \right)$ and $s_1, \dots, s_k = \sin \left( \sum_{i=1}^k q_i \right)$, we have the world coordinates of the end effector point given by:
$$
T_n(q) \begin{bmatrix} L_n \\ 0 \\ 1 \end{bmatrix}
= \begin{bmatrix} L_0 \\ 0 \\ 1 \end{bmatrix} + \sum_{i=1}^n \begin{bmatrix} L_i c_1, \dots, c_i \\ L_i s_1, \dots, s_i \\ 0 \end{bmatrix}.
$$

2.2  2D Forward Kinematics for Branched Revolute Robots

Branched robots can be handled by a similar formula, except additional bookkeeping is necessary to represent the robot's structure. We order the parent and child of each joint with the convention that each link is the child of exactly one joint, and hence has only one parent. The parent of link $i$ is denoted $p[i]$, with the base link attached by a joint to the world, denoted by $p[i]=W$.

The modification to (14) is simple. Rather than using the prior index in the recursive formula, we use the parent index:
$$
T_i(q) = T_{p[i]}(q) T_{p[i],ref} i_{ref} R(q_i) \quad \text{if} \quad p[i] \neq W
$$
and
$$
T_i(q) = T_{i,ref} R(q_i) \quad \text{otherwise}.
$$

2.3 Handling 2D Prismatic Joints

To handle prismatic joints in 2D, we must modify the forward kinematics to replace the rotations $R(q_i)$ with a translation that depends on $q_i$. In addition to link lengths, we will also need to define the axis of translation $a_i = (a_{i,x}, a_{i,y})$, with coordinates given relative to the child link's frame.

For those, we will replace the expression of $R(q_i)$ with the following:
$$
P(q_i) = \begin{bmatrix} 
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
a_{i,x} q_i & a_{i,y} q_i & 0 & 1
\end{bmatrix}
$$
(23)

For example, we derive the transform of the second link of an RP manipulator, whose prismatic axis moves along the $x$ axis, as follows:
$$
T_2(q_1, q_2) = T_1(q_1) \begin{bmatrix} 
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
L_1 & 0 & 1 & 0
\end{bmatrix} 
\begin{bmatrix} 
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
q_2 & 0 & 1 & 0
\end{bmatrix}
$$
(24)

$$
= \begin{bmatrix} 
c_1 & s_1 & 0 & -s_1 c_1 \\
-s_1 & c_1 & 0 & L_0 \\
0 & 0 & 1 & 0 \\
c_1 (L_1 + q_2) & s_1 (L_1 + q_2) & 1 & 0 
\end{bmatrix}
$$
(25)

$$
= \begin{bmatrix} 
c_1 & s_1 & 0 & L_0 + c_1 (L_1 + q_2) \\
-s_1 & c_1 & 0 & L_1 + q_2 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
$$
(26)

To represent this compactly, we slightly modify (21). Let us define for $i = 1, \dots, n$, the following kinematic parameters:

- The parent index $p[i]$.
- The reference transform $T_{p[i], ref} i, ref$.
- An indicator variable $z_i$ which is 1 if the joint is revolute, and 0 if the joint is prismatic.
- The translational axis $a_i$, given in link $i$'s local frame. (Ignored for revolute joints.)

Then, the forward kinematics are defined by:
$$
T_i(q) = T_{p[i]}(q) T_{p[i], ref} i, ref L_{z_i, a_i}(q_i)
$$
(27)

where $T_W(q)$ is the identity and $L_{z_i, a_i}(q)$ is the local joint transform
$$
L_{z, a}(q) = \begin{bmatrix} 
\cos(zq) & \sin(zq) & 0 & -\sin(zq) \\
\cos(zq) & \sin(zq) & 0 & (1 - z) a_x q \\
(1 - z) a_y q & 0 & 1 & 0 \\
(1 - z) a_x q & (1 - z) a_y q & 1 & 0
\end{bmatrix}
$$
(28)

2.4 3D Forward Kinematics

In 3D, forward kinematics is essentially identical to (27), except that homogeneous coordinate matrices are $4 \times 4$, and both prismatic and revolute joints must be defined according to an axis $a_i = (a_{i,x}, a_{i,y}, a_{i,z})$. As before, this axis is specified in coordinates relative to the child link's frame.

In the case of a prismatic joint, we replace $L_{0,a}(q_i)$ with the matrix:
$$
L_{0,a}(q_i) = \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & a_{i,x} q_i \\
0 & 0 & 0 & 1
\end{bmatrix}
$$
(29)

In the case of a revolute joint, we use the axis-angle parametrization:
$$
L_{1,a}(q_i) = \begin{bmatrix}
0 & R_{aa}(a, q_i) & 0 \\
0 & 0 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
(30)

(This block matrix representation indicates that the upper-left $3 \times 3$ matrix is replaced by the rotation matrix derived from the axis-angle parameterization $R_{aa}$.)

2.5 Examples

2.5.1 2RP Manipulator

Consider a 2RP spherical manipulator whose first axis rotates about the $z$ axis, the second about the $y$ axis, and the prismatic joint translates about the $x$ axis. All reference frames are aligned with the world frame (that is, $L_1 = 0$ in Fig. 3).

![[Fig 3.png]]
Figure 3. A spherical manipulator.} Without loss of generality, we can consider the "shoulder" to be the world origin ($L_1 = 0$), and the third configuration variable $q_3$ to be the distance of the end effector to the shoulder. (Generalizing to other coordinate conventions simply requires adding the right offsets.)

Without loss of generality, we can consider the "shoulder" to be the world origin ($L_1 = 0$), and the third configuration variable $q_3$ to be the distance of the end effector to the shoulder. (Generalizing to other coordinate conventions simply requires adding the right offsets.)

With this definition, $T_{p[i], \text{ref}} = I$ for each link. So, the transform of the third link is given by:
$$
T_3(q) = \begin{bmatrix} 0 & R_z(q_1) & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} 
\begin{bmatrix} 0 & R_y(q_2) & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} 
\begin{bmatrix} 0 & I & 0 & q_3 \\ 0 & 0 & 0 & 1 \end{bmatrix}
$$
(31)

The first two matrix multiplications compute the homogeneous representation of:
$$
R_z(q_1)R_y(q_2) = \begin{bmatrix} c_1 & s_1 & 0 \\ -s_1 & c_1 & 0 \\ 0 & 0 & 1 \end{bmatrix} 
\begin{bmatrix} c_2 & 0 & -s_2 \\ 0 & 1 & 0 \\ s_2 & 0 & c_2 \end{bmatrix} 
= \begin{bmatrix} c_1 c_2 & s_1 c_2 & -s_2 \\ -s_1 & c_1 & 0 \\ c_1 s_2 & s_1 s_2 & c_2 \end{bmatrix}
$$
(32)

Hence, the final result is:
$$
T_3(q) = \begin{bmatrix} 0 & R_z(q_1) R_y(q_2) & 0 & 0 \\ 0 & R_z(q_1) R_y(q_2) & e_1 & q_3 \\ 0 & 0 & 0 & 1 \end{bmatrix}
$$
(33)
where we have used block matrix representation, and $e_1 = (1, 0, 0)$. In other words, the origin of the third frame is:
$$
T_3(q) \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} 
= \begin{bmatrix} R_z(q_1) R_y(q_2) e_1 \\ q_3 \end{bmatrix} 
= \begin{bmatrix} c_1 c_2 q_3 \\ s_1 c_2 q_3 \\ -s_2 q_3 \end{bmatrix}
$$
(34)

Note that the vertical component of this point is proportional to the negative of $\sin q_2$, which may not be expected because $q_2$ could be mistakenly considered to be an elevation angle of the translation axis. The reason is that rotations about the $y$ axis rotate CCW about the $(z, x)$ plane, not the $(x, z)$ plane. To change the interpretation so that $q_2$ measures the elevation angle, the second axis of rotation could be rotated so that $a_2 = (0, -1, 0)$, or equivalently, that the reference transform $T_{2, \text{ref}}$ rotates $\pi$ radians about either the $x$ or $z$ axis.

2.5.2 6R Manipulator

Now consider a more typical 6R industrial robot arm, configured with the reference coordinate system as shown in Figure 4. (Ignore the gripper degree of freedom.) The shoulder axes and wrist axes intersect at a common point, indicated by the marked coordinate frames.

![[Fig 4.png]]
Figure 4. A typical kinematic configuration for a 6R industrial manipulator. The "shoulder" has 2 degrees of freedom, the "elbow" has 1, and the "wrist" has 3.

In this definition, the joint axes are aligned to the $Z, Y, Y, X, Y, Z$ axes, listed from the base to the end effector. All reference orientations are aligned to the world coordinate frame. The coordinate frames are also oriented such that positive joint angles turn counterclockwise with respect to their local coordinate frames, and hence we can more specifically list the joint axes as $+Z, +Y, +Y, +X, +Y, +Z$.

Let us place the relative reference transforms so that both of the first 2 link transforms are at the intersection of the shoulder, and the last 3 link transforms are at the intersection of the wrist. All relative transforms have the identity matrix as their rotation component. Link 1's reference transform shifts by $L_1$ units in the $Z$ direction, link 3 shifts by $L_2$ units in the $X$ direction, and link 4 shifts by $L_3$ units in the $X$ direction, while links 2, 5, and 6 induce no translation.

Ultimately, forward kinematics yields the following transforms of each link:
$$
T_1(q) = \begin{bmatrix} 0 & R_z(q_1) & 0 & 0 \\ 0 & 0 & 0 & L_1 \\ 0 & 0 & 0 & 1 \end{bmatrix}
$$
(35)
$$
T_2(q) = T_1(q) \begin{bmatrix} 0 & R_y(q_2) & 0 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
$$
(36)
$$
T_3(q) = T_2(q) \begin{bmatrix} 0 & R_y(q_3) & 0 & L_2 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 0 & 1 \end{bmatrix}
$$
(37)
$$
T_4(q) = T_3(q) \begin{bmatrix} 0 & R_x(q_4) & 0 & L_3 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 0 & 1 \end{bmatrix}
$$
(38)
$$
T_5(q) = T_4(q) \begin{bmatrix} 0 & R_y(q_5) & 0 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
$$
(39)
$$
T_6(q) = T_5(q) \begin{bmatrix} 0 & R_z(q_6) & 0 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
$$
(40)

To obtain the world-space position of the end effector, we simply apply $T_6(q)$ to the local coordinates of the end effector in link 6's frame:
$$
x(q) = T_6(q) \begin{bmatrix} L_6 \\ 0 \\ 0 \\ 1 \end{bmatrix}
$$
(41)

2.6  Kinematics conventions

As we defined the layout of a robot's kinematic structure above, we store the following parameters for each link $i = 1, \dots, n$: 
parents $p[i]$, reference relative transforms $T_{p[i], \text{ref}}^{i,\text{ref}}$, joint types $z_i$, and translational or rotational axes $a_i$.

However, our 2RP example showed that there are multiple choices of frames and axes that define the exact same robot dimensions. In fact, there are an infinite number of equivalent representations formed by modifying reference frames and joint axes so that the axes represent the same quantities in world coordinates. Moreover, we may rotate or translate a link's reference frame arbitrarily around its joint axis, as long as we correct for the shift in its zero position. For some purposes, it is useful to reduce the number of parameters specifying a robot's reference frame by choosing a convention. We have already seen a convention where we have chosen to place joint axes at the origin of the child frame; in general, the joint could have been placed arbitrarily in space.

2.6.1  Planar robot convention

We have also seen the standard convention for 2D planar robots in the $nR$ example, in which we chose to align the reference frame with the $x$ axis. Here, by a change of world frame and zero positions, we need only represent the lengths between joints $L_0, L_1, \dots, L_n$. By a shift of the world frame, we could also eliminate the parameter $L_0$.

In the case where prismatic joints are present, we only need to represent the direction of translation $a_i$. But even these two parameters are excessive, since directions are unit vectors. Hence, we can simply represent the heading angle $\theta_i$ such that $a_i = (\cos\theta_i, \sin\theta_i)$.

As a result, a minimum set of kinematic parameters for a 2D robot are the link lengths $L_1, \dots, L_n$ and the headings of any translational axes $\theta_i$.

2.6.2  Denavit-Hartenberg convention

The Denavit-Hartenberg convention is a well-known minimal parameter convention for 3D serial robot kinematics. In this convention, joint axes are always aligned to the $z$ axis of each child link, and the offset between joints is always pointing along the $x$ axis of the parent link. It is usually not the most convenient representation for the purposes of robot design and forward kinematics calculations, but due to the minimal number of parameters used (4 per link), it remains popular for robot structure optimization problems, like in robot calibration.

2.7
Algorithm 1. Forward kinematics

1. TW(q) ← I
   (Initialize the world frame transformation as the identity matrix)

2. For i = 1, ..., N in topologically sorted order:

    a. Use Equation (27) to calculate Ti(q) using the stored value of Tp[i](q).
    
    b. Store Ti(q).
   
3. Return T1, ..., TN
   (At the end of the algorithm, all link frames T1, ..., TN are calculated with respect to the world frame)

3.1 Key takeaways

- The kinematics of a robot relate the joint angles of a robot to the coordinate frames of its links.

- A robot's configuration is a minimal expression of its links position, usually consisting of the robot's joint angles. The variables defining the configuration are the robot's degrees of freedom.

- The topology of a robot structure is defined by its joint types (e.g., revolute, prismatic, and spherical) and how they are connected. Along with its link lengths and joint axes, this defines its kinematic structure.

- A robot's reachable workspace is the range of end effector locations it could reach (and optionally orientations).

- Forward kinematics computes the coordinate frames corresponding to the robot's configuration. It can be computed for all links in a serial or branched robot with a single-pass algorithm.

- Software for calculating forward kinematics should be available in any major robotics package.

- [Configuration](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#Configurations-and-configuration-space): A minimal mathematical representation of the geometric layout of a robot. It usually represents all of the joint angles and possibly the degrees of freedom of a virutal linkage.
- [Degree of freedom](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#Degrees-of-freedom): A single parameter in a configuration.
- [Virtual linkage](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#Floating-bases-and-virtual-linkages): For robots that are not rigidly attached to the environment, 3 (in 2D) or 6 (in 3D) virtual degrees of freedom are added to the robot's configuration.
- [Configuration space](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#Configurations-and-configuration-space): The set of all theoretically possible configurations of a robot, ignoring collision constraints.
- [Workspace](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#Configuration-space-and-workspace): The 2D or 3D physical space in which a robot exists.
- [Serial robot](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#topology): A robot structure in which each link except the last has exactly one child.
- [Branched robot](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#topology): A robot structure in which some links have multiple children.
- [Parallel robot](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#topology): A robot structure in which there is one or more cycles of connected joints.
- [Forward kinematics](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#Forward-kinematics): The process of computing coordinate frames for robot links given a robot configuration as input. A basic subroutine used throughout robotics.
- [URDF file](https://motion.cs.illinois.edu/RoboticSystems/Kinematics.html#Robot-kinematic-definition-files): a popular XML-based format for robot kinematic definitions.

