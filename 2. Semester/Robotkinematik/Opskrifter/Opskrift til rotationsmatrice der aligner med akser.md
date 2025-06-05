1. Sikrer at vektorerne er unit-vectors:
   dividere vektoren med længden af vektoren.
2. De skal være orthogonale. Dvs. prikproduktet skal være 0. BEHØVER IKKE TJEKKE, DET BLIVER DE NØDT TIL AT VÆRE, Hvis ikke skal man bruge Gram-Schmidt (ikke noget vi har lært, så burde aldrig ske)
3. Når de er orthogonale så burde den sidste akse bare være krydsproduktet af de to. Husk at krydsproduktet er anti-kommutativt, så rækkefølgen gør en forskel:
$$
\begin{align*}
\hat{v}_{z} &=  \hat{v}_{x} \times \hat{v}_{y}\\
\hat{v}_{x} &= \hat{v}_{y} \times \hat{v}_{z}\\
\hat{v}_{y} &= \hat{v}_{z} \times \hat{v}_{x} 
\end{align*}
$$

I matlab:
v_x = [4,1,-2].';
v_x = v_x/norm(v_x)

v_z = [0,2,1].';
v_z = v_z/norm(v_z)
% Prikproduktet af de to skal være 0, de skal være orthogonale
% Dette kan tjekkes med dot(v_x, v_z)

v_y = cross(v_z, v_x)

% Til sidst indsæt alle værdierne i en rotationsmatrice. I dette tilfælde bliver det:
R = [4/sqrt(21), -5/sqrt(105), 0; 1/sqrt(21), 4/sqrt(105), 2/sqrt(5); -2/sqrt(21), -8/sqrt(105), 1/sqrt(5)]