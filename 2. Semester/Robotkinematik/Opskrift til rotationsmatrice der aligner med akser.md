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