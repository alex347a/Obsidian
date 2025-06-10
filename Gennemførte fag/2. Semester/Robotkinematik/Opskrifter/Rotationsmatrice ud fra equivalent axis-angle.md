Formel for axis-angle til rotationsmatrice:
![[Equivalent Angle-Axis to Rotation Matrix.png]]

I matlab:
axis = [sqrt(2)/2, 0, -sqrt(2)/2]; % Indsæt de tre koordinater
theta = pi/4; % Indsæt vinkel
CB_R = axang2rotm([axis theta]) % Indbyggede
CB_Q = [-0.2, -0.3, 0.5].' % Indsæt translationen
CB_T = [CB_R, CB_Q; 0, 0, 0, 1]