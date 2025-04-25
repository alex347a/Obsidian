Der er to metoder. 
1. Diagonalprodukt via Række Echelon Form:
$$
\text{Det}(A) = a_{11} \cdot a_{22} \cdot \dots \cdot a_{nn}, \quad \text{hvis A er på Row Echelon Form.}
$$
2. Udvikling via Søjle eller Række (Cofaktor Udvikling):
$$
\text{Det}(A) = \sum_{i=1}^n (-1)^{i+j} a_{ij} \cdot \text{Det}(M_{ij}),
$$
$$
\text{hvor } a_{ij} \text{ er elementet i den valgte søjle/række, og } \text{Det}(M_{ij}) \text{ er determinanten af minoren.}
$$
$$
A =
\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{bmatrix}
$$

Eksempel:
Diagonalprodukt via Række Echelon Form:
Reducer $A$ til øvre trekantform:
$$
\text{Række-reduktion:}
\quad
\begin{bmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & 0 & 0
\end{bmatrix}
$$
$$
\text{Det}(A) = 1 \cdot (-3) \cdot 0 = 0.
$$

Cofaktor Udvikling:
Udvikling langs første række:
$$
\text{Det}(A) = 1 \cdot 
\begin{vmatrix}
5 & 6 \\
8 & 9
\end{vmatrix}
- 2 \cdot 
\begin{vmatrix}
4 & 6 \\
7 & 9
\end{vmatrix}
+ 3 \cdot 
\begin{vmatrix}
4 & 5 \\
7 & 8
\end{vmatrix}
$$
Beregn determinant for hver $2 \times 2$ minor:
$$
\begin{vmatrix}
5 & 6 \\
8 & 9
\end{vmatrix}
= (5 \cdot 9) - (6 \cdot 8) = 45 - 48 = -3
$$
$$
\begin{vmatrix}
4 & 6 \\
7 & 9
\end{vmatrix}
= (4 \cdot 9) - (6 \cdot 7) = 36 - 42 = -6
$$
$$
\begin{vmatrix}
4 & 5 \\
7 & 8
\end{vmatrix}
= (4 \cdot 8) - (5 \cdot 7) = 32 - 35 = -3
$$

Sæt det sammen:
$$
\text{Det}(A) = 1 \cdot (-3) - 2 \cdot (-6) + 3 \cdot (-3)
$$
$$
\text{Det}(A) = -3 + 12 - 9 = 0.
$$
