Eks. 2 s. 377
Roterende skive

![[08 lektionsnoter.pdf#page=1]]

![[08 lektionsnoter.pdf#page=2]]

### Parameterfremstilling
Eks.
$$
x^{2}+ y^{2} = 4 \quad \text{ cirkel med radius 2}
$$
Formlen er givet ved:
$$
\vec{r} = r \cdot \cos(t), r\cdot \sin(t)
$$
Fordi radius er 2:
$$
\vec{r} = (2 \cos(t), 2 \sin(t))
$$
![[Fig 201 og 202 i eks 1 og 2.png]]
### Linjeintegralet
$$
\int \vec{F} \cdot r \, ds
$$
Det kaldes for arbejdet i fysik. Kommer i næste lektion.

### Eks. 2 Ellipse
![[Fig 201 og 202 i eks 1 og 2.png]]
$$
\frac{x^{2}}{a^{2}}+ \frac{y^{2}}{b^{2}} = 1
$$
$$
\vec{r}(t) = (\underbrace{a \cos(t)}_{x}, \underbrace{b \sin(t)}_{y}, 0)
$$
$$
\frac{\cancel{a^{2}} \cos^{2}(t)}{\cancel{a^{2}}} + \frac{\cancel{b^{2}} \sin^{2}(t)}{\cancel{b^{2}}} = 1
$$
### Eks. 3
![[Fig 203.png]]
Her plejer vi at skrive $\vec{a}$ i stedet for a, $\vec{b}$ i stedet for b. $P_{0}$ i stedet for A og $P$ som punktet ude på linjen
![[08 lektionsnoter.pdf#page=3]]

$$
\vec{r} = \vec{a} + t \vec{b} = \begin{pmatrix}a_{1} \\ a_{2} \\ a_{3}\end{pmatrix}+ t\begin{pmatrix}b_{1} \\ b_{2} \\ b_{3}\end{pmatrix}
$$
$$
\vec{r} = (a_{1}+ tb_{1}, a_{2}+ tb_{2}, a_{3}+tb_{3})
$$
Kan også skrives:
$$
\vec{r} = (a_{1}+ tb_{1})\vec{i}+ (a_{2}+ tb_{2})\vec{j}+ (a_{3}+tb_{3})\vec{k}
$$
### Eks. 4 Helix
![[Eks. 4 Fig 204 og 205.png]]
$$
\vec{r} = (a \cos(t), b \sin(t), ct)
$$
Så en cirkel hvor z-værdien stiger med en konstant.

### Eks 5.
hastighedsvektoren $\vec{v}(t) = \vec{r}'(t)$
![[Fig 200.png]]Hvor den sorte streg så er $\vec{v}(t)$

Enhedstangentvektoren
$$
\vec{u} = \frac{\vec{v}(t)}{|\vec{v}(t)|}
$$
Eks.
Ellipsen 
$$
\frac{1}{4} x^{2} + y^{2} = 1
$$
$$
P\left(\sqrt{2}, \frac{1}{\sqrt{2}}\right)
$$
Vi skal finde tangenten i det punkt på ellipsen.
a må jo så være 2 og b må være 1, idet $(\sqrt{2})^{2} = 2$ og $\frac{1}{ \sqrt{2}} = 1$ 

$$
\begin{align*}
\vec{r}(t) &=  (2 \cos(t), \sin(t))\\
\vec{r}'(t) &= (-2 \sin(t), \cos(t))\\
\end{align*}
$$

$$
\begin{align*}
2 \cos(t) &=  \sqrt{2} \rightarrow \cos(t) = \frac{\sqrt{2}}{2}\\
\rightarrow t &= \frac{\pi}{4}\\
\vec{r}'(t) &= \left(-2 \sin\left(\frac{\pi}{4}\right), \cos\left(\frac{\pi}{4}\right)\right)\\
&=  \left(-2 \cdot \frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2}\right)\\
&= \underline{\underline{\left(-\sqrt{2}, \frac{\sqrt{2}}{2}\right)}}
\end{align*}
$$
$$
\vec{r}(t) \cdot r^{-1}(t) = \begin{pmatrix}\sqrt{2} \\ \frac{1}{\sqrt{2}}\end{pmatrix} \cdot \begin{pmatrix}-\sqrt{2} \\ \frac{\sqrt{2}}{2}\end{pmatrix} = -2 + \frac{1}{2} = -1,5
$$
Fordi det er en ellipse står det ikke vinkelret på hinanden, ligesom det ville have gjort i en jævn cirkelbevægelse.

### 9.8 Divergens af et vektorfelt
Gradient af f
$$
\begin{align*}
f &=  (f_{1},f_{2}, f_{3})\\
\nabla f = \left(\frac{\delta f}{\delta x}, \frac{\delta f}{\delta y}, \frac{\delta f}{\delta z}\right)\\
\nabla = \left(\frac{\delta }{\delta x}, \frac{\delta }{\delta y}, \frac{\delta }{\delta z}\right)\\
\end{align*}
$$

#### Definition:
$\text{div }\nabla = \nabla \cdot \vec{v}$
$$
\begin{pmatrix}\frac{\delta }{\delta x} \\ \frac{\delta }{\delta y} \\ \frac{\delta }{\delta z}\end{pmatrix} \cdot \begin{pmatrix}v_{1} \\ v_{2} \\ v_{3}\end{pmatrix}
$$
$$
\text{div } \vec{v} = \frac{\delta v_{1}}{\delta x}, \frac{\delta v_{2}}{\delta y}, \frac{\delta v_{3}}{\delta z}\\
$$
Man kan indsætte et kontrolelement i form af en kasse i vektorfeltet, hvor man så kan udregne volumenflowet igennem de 6 flader af kassen. Så 3 flader der måler flow ind og 3 flader der måler flowet ud. Hvis nu det var en gas, som ekspandere så kan man støde ind i af der løber mere volumen ud af kassen end ind, i så fald vil divergensen være positiv, hvis det er noget der komprimeres vil divergensen være negativ. Hvis nu det var en væske så vil divergensen være 0.
![[Fig 218.png]]
Vektorfeltet antages at være **solenoidal** (ingen kilde eller afløb)
Volumenflowet måles med formlen 
$$
Q = v \cdot \underbrace{A}_{areal}
$$
Strømlinjen er **steady-state** hvis den ikke ændrer sig over tid.

### Eks.
Vi tager eksemplet med cirklen fra tidligere eksempel:
$$
\vec{v} = \underbrace{-w y }_{v_{1}} \vec{i} + \underbrace{w \times}_{v_{2}}  \vec{j}
$$
$$
\frac{d}{dx}(v_{1}) = 0
$$
$$
\frac{d}{dy}(v_{2}) = 0
$$

$$
\text{div } \vec{v} = 0 + 0 = \underline{\underline{0}}
$$
### Eks.
Vi tager eksemplet med pilene:
$$
\vec{v} = x \vec{i}
$$
$$
\text{div } \vec{i} = \underline{\underline{1}}
$$
Så der er i dette tilfælde ekspansion. Pilene vil blive længere jo længere de kommer ud af x-aksen. De accelerere altså.

Vi sætter en partikel i position $P = (c_{1}, c_{2}, c_{3})$ når vi starter ved tiden $t=0$

#### Hvor er partiklen kl. t?
Da den ikke bevæger sig i hverken y- eller z-retningen:
$$
v_{2}= 0, \quad v_{3}= 0
$$
i x-retningen:
$$
v_{1} = x, \quad v_{1}(0) = c_{1}
$$
$$
\begin{align*}
v =  \frac{ds}{dt} \rightarrow ds &=  v \, dt\\
s &= \int v \, dt
\end{align*}
$$

Så partiklen er:
$$
x = c_{1}+ \Delta x = c_{1}+ \int v_{1} \, dt = c_{1}+ \int x \, dt
$$
Altså:
$$
x = c_{1}+ \int x \, dt
$$
Hvis jeg differentiere på begge sider:
$$
\begin{align*}
\frac{dx}{dt} = x \rightarrow \int \frac{dx}{x} &=  \int dt\\
\ln(x) &= t + c\\
x = e^{t+c}  &= e^{t} \cdot e^{c}\\
x(0) = e^{0} \cdot e^{c} = c_{1} \rightarrow e^{c} &=  c_{1}\\
x &=  c_{1} e^{t}\\
\vec{r}(t) &= (c_{1} e^{t}, c_{2}, c_{3})
\end{align*}
$$
### 9.9 Rotation af et vektorfelt
$\underbrace{\text{Curl}}_{\text{krølle/rotation}}$ $\vec{v} = Rot(\vec{v})$
$$
Rot (\vec{v}) = \nabla \vec{v}
$$
$$
Rot(\vec{v}) = \begin{pmatrix}\vec{i} & \vec{j} & \vec{k} \\ \frac{\delta}{\delta x} & \frac{\delta}{\delta y} & \frac{\delta}{\delta z} \\ v_{1}  & v_{2} & v_{3}\end{pmatrix}
$$
Eks. Roterende vektorfelt
Jeg bruger værdierne fra tidligere eksempel med cirklen
$$
Rot(\vec{v}) = \begin{pmatrix}\vec{i} & \vec{j} & \vec{k} \\ \frac{\delta}{\delta x} & \frac{\delta}{\delta y} & \frac{\delta}{\delta z} \\ - \omega y  & \omega x & 0\end{pmatrix} = \vec{i} \cdot \begin{pmatrix} \frac{\delta}{\delta y} & \frac{\delta}{\delta z} \\ \omega x  & 0 \end{pmatrix} - \vec{j} \begin{pmatrix}\frac{\delta}{\delta x} &  \frac{\delta}{\delta z} \\ - \omega y  & 0\end{pmatrix} + \vec{k} \begin{pmatrix}\frac{\delta}{\delta x}  & \frac{\delta}{\delta y}  \\ - \omega y   & \omega x \end{pmatrix}
$$
$$
= \vec{i} (0-0) - \vec{j}(0-0) + \vec{k}(\omega + \omega) = 2 \omega \vec{k}
$$
Så rotationen er altså dobbelt så stor som vinkelhastigheden.

### Eks.
$$
Rot(\vec{v}) = \begin{pmatrix}\vec{i} & \vec{j} & \vec{k} \\ \frac{\delta}{\delta x} & \frac{\delta}{\delta y} & \frac{\delta}{\delta z} \\ yz  & 3xz & z\end{pmatrix} = \vec{i} \left(\frac{\delta z}{\delta y} - \frac{\delta 3xz}{\delta z}\right) - \vec{j}\left(\frac{\delta z}{\delta x} - \frac{\delta yz}{\delta z}\right) + \vec{k}\left(\frac{\delta 3 xz}{\delta x} - \frac{\delta yz}{\delta y}\right)
$$
$$
= \vec{i}(0-3x) - \vec{j}(0-y) + \vec{k}(3z-z)
$$
$$
Rot(\vec{v}) = \begin{pmatrix}-3x \\ -y \\ 2z\end{pmatrix}
$$
Rotationen afhænger af hvor man placerer sig.