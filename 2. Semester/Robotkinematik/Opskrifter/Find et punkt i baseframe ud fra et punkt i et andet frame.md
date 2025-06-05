$$
\sideset{^{B}}{}{P} = \sideset{^{B}_{C}}{}{T} \sideset{^{C}}{}{P}
$$
Hvis nu du har $\sideset{^{C}_{B}}{}{T}$ så kan du bare finde den inverse: $\sideset{^{C}_{B}}{}{T^{-1}} = \sideset{^{B}_{C}}{}{T}$ for at få det til at passe med:
![[Rotating points.png]]

I matlab:
C_P = [0.5, 0.1, 0.2].'
BC_Q = - CB_R.' * CB_Q
BC_T = inv(CB_T)
B_P = BC_T * [C_P; 1];
B_P = B_P(1:3)