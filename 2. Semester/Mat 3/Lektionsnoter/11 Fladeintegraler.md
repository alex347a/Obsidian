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
Givet en flade S
og normalvektorerne $\vec{N}$