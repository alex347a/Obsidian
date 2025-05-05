#### Overflader
Kugle:
$$
x^{2} + y^{2} + z^{2} = a^{2}
$$
Man kan enten skrive:
$$
z = f(x,y) \quad \text{ eller } \quad g(x,y,z) = 0
$$
$$
z = \pm \sqrt{a^{2} - x^{2} - y^{2}} \quad \text{ eller } \quad g(x,y,z) =  x^{2} + y^{2} + z^{2} - a^{2} = 0
$$
Der er altså to forskellige parametre til at fremstille en flade.
![[Fig 241.png]]
Enten kan det gives ved en kurve fra a til b eller ved en flade ved at tag en vektor der peger rundt i fladen.

![[Fig 242 og 243.png]]
Overflade udpeges af:
$$
\vec{r} (u,v)
$$
#### Normalvektor:
$$
\vec{r}_{u} = \frac{\partial \vec{r}(u,v)}{\partial u} \quad \text{ og } \quad \vec{r}_{v} = \quad \frac{\partial \vec{r} (u,v)}{\partial v}
$$
er tangentvektorer til planen. De danner basis for faldens tangentplan i P.
Normalvektoren:
$$
\vec{N} = \vec{r}_{u} \times \vec{r}_{v}
$$

Enhedsnormalvektoren:
$$
\vec{n} = \frac{\text{grad g}}{\text{|grad g|}} = \frac{\nabla g}{|\nabla g|}
$$
hvor fladen S afgrænses af $g(x,y,z) = 0$

#### Eksempel:
Kugleoverfladen $g(x,y,z) = x^{2} + y^{2} + z^{2} - a^{2} = 0$
$$
\begin{align*}
\vec{r} (u,v) &=  a\cos(v) \cos(u) \vec{i} + a\cos(v) \sin(u) \vec{j} + a \sin(v) \vec{k}\\
\vec{r}_{u} &= - a \cos(v) \sin(u) \vec{i} + a \cos(v) \cos(u) \vec{j}\\
\vec{r}_{v} &= - a \sin(v) \cos(u) \vec{i} + a \sin(v) \sin(u) \vec{j} + a \cos(v) \vec{k}\\
\nabla g &= (2x, 2y, 2z)\\
|\nabla g| &= \sqrt{4x^{2}  + 4y^{2} + 4z^{2}} = 2 \sqrt{x^{2} + y^{2} + z^{2}} = 2a\\
\vec{n} &= \frac{(2x,2y,2z)}{2a} = \underline{\underline{\left(\frac{x}{a}, \frac{y}{a}, \frac{z}{a}\right)}}
\end{align*}
$$
Det kan også skrives som:
$$
\vec{n} = \frac{x}{a} \vec{i} + \frac{y}{a} \vec{j} + \frac{z}{a} \vec{k}
$$
Man kunne også godt krydse, men det er mere besværligt end at dividere med længden, i hvert fald i dette tilfælde.

### Fladeintegraler
Givet en flade S $\vec{r} (u,v) = x(u,v) \vec{i} + y(u,v) \vec{j} + z(u,v) \vec{k}$
og normalvektorerne $\vec{N} = \vec{r}_{u} \times \vec{r_{v}}$ og $\vec{n} = \frac{\vec{N}}{|\vec{N}|}$
For en vektorfunktion $\vec{F}$ defineres fladeintegralet:
$$
\iint_{S} \vec{F} \cdot \vec{n} \, dA = \iint_{R} \vec{F} (\vec{r} (u,v)) \cdot \vec{N} (u,v) \, du \, dv
$$
Siden $\vec{n} = \frac{\vec{N}}{|\vec{N}|}$
Så er:
$$
\vec{N} = \vec{n}|\vec{N}|
$$

Flux: $\vec{F} = \rho \vec{\underbrace{v}_{\text{hastighed}}}$
Fluxintegrale:
$$
\iint_{S} \vec{F} \cdot \vec{n} \, dA = \iint_{R} \vec{F} (\vec{r} (u,v)) \cdot \vec{N} (u,v) \, du \, dv = \underline{\iint_{S} F_{1} \, dy \, dz + F_{2} \, dx \, dz + F_{3} \, dx \, dy}
$$
Så det er bare en specialudgave af fladeintegralet.

Parabolsk cylinder S (en parabel man trækker i z-retningen)
$$
\begin{align*}
y &=  x^{2}, \quad 0 \leq x \leq 2, \quad 0 \leq z \leq 3\\
u &= x, \quad v = z
\end{align*}
$$
u og v skal være uafhængige, fordi ellers kan man ikke køre i området.
Vi får ud fra y, at y variere mellem $0 \leq y \leq 4$ da $0 \leq x \leq 2$ og $0^{2} = 0$ og $2^{2} = 4$
$$
F (u,v) = (u,u^{2}, v)
$$
Indsæt billede af grafen for V over u, hvor V går op ad y-aksen til 3 og u går ud af x-aksen til 2.

$$
F_{u} (1, 2u, 0), \quad F_{v} = (0,0,1)
$$
Finder normalvektoren ved at krydse dem:
$$
\begin{align*}
\vec{N} = \vec{r}_{u} \times \vec{r}_{v}\\
\vec{N} 
&= 
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
1  & 2u & 0\\
0 & 0 & 0
\end{vmatrix}
= 2u \vec{i} - \vec{j} + 0 \vec{k} = 2 u \vec{i} - \vec{j}\\
|\vec{N}| &= \sqrt{4u^{2} + 1} \Rightarrow \vec{n} = \frac{\vec{N}}{|\vec{N}|} \\
&= \underline{\underline{\frac{2u}{\sqrt{4u^{2} + 1}} \vec{i} - \frac{1}{\sqrt{4u^{2} + 1}}\vec{j}}}
\end{align*}
$$
$$
\vec{F} = (3z^{2}, 6, 6xz) \Rightarrow \vec{F}(\vec{r}(u,v)) = (3v^{2}, 6, 6uv)
$$
$$
\iint 
\begin{pmatrix}
3v^{2}  \\ 
6 \\ 
6uv
\end{pmatrix}
\cdot
\begin{pmatrix}
2u \\ 
-1 \\ 
0
\end{pmatrix}
\, du \, dv
= 
\int_{0}^{3} \int_{0}^{2} (6 uv^{2} - 6) \, du \, dv
$$
$$
\begin{align*}
\int_{0}^{3} [3 u^{2} v^{2} - 6u]_{0}^{2} \, dv &=  \int (12 v^{2} - 12) \, dv\\
= {[4v^{3} - 12v]_{0}^{3}} = 108 - 36 &=  72
\end{align*}
$$
Man kan også regne det med krydsproduktet:
$$
\begin{align*}
\vec{N} \cdot \vec{i} &= 
\begin{pmatrix}
2u\\
-1\\
0
\end{pmatrix}
\cdot
\begin{pmatrix}
1\\
0\\
0
\end{pmatrix}
= 2u \text{ er positiv}
\\
\vec{N} \cdot \vec{j} &= 
\begin{pmatrix}
2u\\
-1\\
0
\end{pmatrix}
\cdot
\begin{pmatrix}
0\\
1\\
0
\end{pmatrix}
= -1 \text{ er negativt}\\
\vec{N} \cdot \vec{k} &=  
\begin{pmatrix}
2u  &  0\\
-1  &  0\\
0  &  1
\end{pmatrix}
= 0
\end{align*}
$$
$$
\begin{align*}
\iint_{R} \vec{F}(\vec{r}(\vec{u}, \vec{v})) \cdot \vec{N} (u,v) \, du \, dv &=  \iint_{S} F_{1} \, dy \, dz - F_{2} \, dx \, dz\\
\int_{0}^{3} \int_{0}^{4} 3z^{2} \, dy \, dz - \int_{0}^{3} \int_{0}^{2} 6 \, dx \, dz
&= \int_{0}^{3} [3yz^{2}]_{0}^{4} \, dz - \int_{0}^{3} [6x]_{0}^{2} \, dz\\
&=  \int_{0}^{3} 12 z^{2} \, dz - \int_{0}^{3} 12 \, dz\\
= [4z^{3}]_{0}^{3} - [12z]_{0}^{3} = 108 - 36 &=  \underline{\underline{72}}
\end{align*}
$$
Det giver altså det samme.