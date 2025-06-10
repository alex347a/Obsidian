1. We want to attach a Robotiq Hand-e gripper to a Universal Robots UR5. Calculate a transformation matrix between the tool flange on the robot and the tip of the gripper fingers.
   First:
   Download the Hand-E instruction manual from Robotiq’s website. Just follow this link: chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://assets.robotiq.com/website-assets/support_documents/document/Hand-E_Manual_UniversalRobots_PDF_20220114.pdf

	Now based on how the gripper should be mounted according to 3.4.1 and the measurements of the gripper in 5.1, write down the transformation matrix:
	The transformation matrix is given by:
	$$
	\begin{align*}
\begin{pmatrix}R & P\\
0 & 1\end{pmatrix}
\end{align*}
$$
	Where R is a 3x3 rotation matrix and P is a 3x1 translation vector
	So assuming the gripper is mounted without rotation:
$$
R = \begin{pmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1\end{pmatrix}
$$
	Since the gripper is 146 mm tall and it is placed along the Z-axis the translation vector P is:
$$
P=\begin{pmatrix}0 \\ 0 \\ 0.146\end{pmatrix}
$$
	Therefore the transformation matrix would be:
$$
\begin{pmatrix}1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0.146 \\ 0 & 0 & 0 & 1\end{pmatrix}
$$
	
2.   A mobile robot platform is equipped with a robot arm. The arm has a camera mounted onto the tool flange and a gripper mounted on top of that (the overall system is very similar to the Enabled Robotics platform). The robot must approach and grab an object in its environment. For this task, we consider the following frames of reference:
- {M}: The base frame of the mobile robot.
-  {B}: The base frame of the arm.
-  {F}: The tool flange of the arm.
-  {G}: The TCP of the arm gripper.
-  {C}: The camera frame.
-  {O}: The object frame.
We know:
-  The location of the base frame of the arm with respect to the base frame of the mobile robot it is mounted on.
-  The location of the tool flange as seen in the robot arm’s base frame.
-  The location of the gripper TCP with respect to the tool flange.
-  The location of the camera with respect to the tool flange.
-  The location of the object in the camera frame.

	(a) Name the transformation matrices given the information we know and the frames of reference given above.
	
	We have the transformation matrices for:
	The base frame of the mobile robot to the base frame of the arm:
	$$
	\sideset{_{Arm}^{Base}}{}{T}
$$
	
	The base frame of the arm to the tool flange of the arm.
	$$
	\sideset{^{Arm}_{Tool}}{}{T}
$$
	
	The tool flange of the arm to the TCP of the arm gripper
	$$
	\sideset{^{Tool}_{TCP}}{}{T}
$$
	
	The TCP of the arm gripper to the camera frame:
	$$
	\sideset{^{TCP}_{Camera}}{}{T}
$$
	
	The camera frame to the object frame:
	$$
	\sideset{^{Camera}_{Object}}{}{T}
$$
	
	(b) Draw a diagram/picture of the situation, showing the different elements, the different frames, and indicating which transformations are known with, e.g., filled arrows and which are unknown with, e.g., dashed arrows (or with different colours)
	![[04 Robotkinematik.pdf]]
	(c) Derive the transformation from the gripper TCP frame to the object.
	$$
	\sideset{^{TCP}_{Object}}{}{T} = \sideset{^{TCP}_{Camera}}{}{T} \cdot \sideset{^{Camera}_{Object}}{}{T}
$$
	
	(d) Derive the transformation from the mobile robot base frame to the object.
	$$
	\sideset{^{Base}_{Object}}{}{T}= \sideset{_{Arm}^{Base}}{}{T} \cdot \sideset{^{Arm}_{Tool}}{}{T} \cdot \sideset{^{Tool}_{TCP}}{}{T} \cdot 	\sideset{^{TCP}_{Camera}}{}{T} \cdot \sideset{^{Camera}_{Object}}{}{T}
$$

MATLAB exercises are in the file called *04 Lektier exercises.mlx*