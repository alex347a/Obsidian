The number of rows in the DH parameter table that describes a robot depends on the amount and type of joints.
1 revolute joint = 1 row
1 prismatic joint = 1 row
(Screw joint (Helical joint) is equivalent to both a revolute and prismatic, however since the motion is coupled, it would be described by 1 row, where the joint angle $\theta$ and joint distance $d$ are related by the pitch $d = p \cdot \theta$ where $p$ is pitch)
1 cylindrical joint = 1 revolute + 1 prismatic = 2 rows
1 spherical joint = 3 revolute = 3 rows
