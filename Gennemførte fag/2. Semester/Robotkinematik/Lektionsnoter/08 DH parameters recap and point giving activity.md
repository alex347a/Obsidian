![[Recap DH parameters.png]]
![[Robot base.png]]
The lines under the bases are ground.
![[Revolute joints.png]]
These are revolute joints where the triangles represent how they rotate.

![[Prismatic joints.png]]
These are prismatic joints where the lines represent how they translate.
![[Example 1.png]]
![[Example 2.png]]
![[DH parameters example.png]]![[DH parameters example 2.png]]
Remember you don't need to include the tool in DH parameters.

Kode til pointgivende 2, hvis man bruger et for-loop:
  

% I'll try using a for-loop like in the example

numLinks = 4;

bodies = cell(numLinks, 1);

joints = cell(numLinks, 1);

  

for i = 1:numLinks

% Create body and joint

bodies{i} = rigidBody(['link' num2str(i)]);

joints{i} = rigidBodyJoint(['joint' num2str(i)], 'revolute');

% Apply MDH parameters

setFixedTransform(joints{i}, mhdparams_numeric(i, :), 'mdh');

bodies{i}.Joint = joints{i};

  

% Add the first body to the base frame, subsequent bodies to previous bodies

if i == 1

addBody(robot, bodies{i}, 'base');

else

addBody(robot, bodies{i}, bodies{i-1}.Name);

end

end