### Opgave 1
a. Udregn linjeintegralet af
$$
\vec{F} = (2x, 2z, 2y)
$$
langs kurven C, der består af kurverne $C_{1}, C_{2}, C_{3}:$
$$
\begin{align*}
C_{1}: \vec{r}(t) &= (\cos(t), \sin(t), t)\\
C_{2}: \vec{r}(t) &= \left(0, 1, \frac{\pi}{2} (1-t)\right)\\
C_{3}: \vec{r}(t) &= (t, (1-t), 0)
\end{align*}
$$
![[Opgave 1 pointgivende 2.png]]

For at beregne linjeintegralet bruger jeg formlen:
$$
\int_{a}^{b} \vec{F} \cdot d \vec{r} = \int_{a}^{b} 
\begin{pmatrix}F_{1} \\ F_{2} \\ F_{3}\end{pmatrix}
\cdot 
\begin{pmatrix}x' \\ y' \\ z'\end{pmatrix} \, dt
= \int_{a}^{b}(F_{1}x'+F_{2}y'+F_{3}z') \, dt
$$
Hvor:
$$
\vec{F} = (F_{1}, F_{2}, F_{3})
$$
Jeg starter med $C_{1}$:
$$
\begin{align*}
\vec{r}_{1}(t) &=  (\cos(t), \sin(t), t)\\
\vec{F} &=  (2x, 2z, 2y)\\
\vec{F}(r_{1}(t)) &= (2 \cos(t), 2t, 2 \sin(t))
\end{align*}
$$
Differentierer $r_{1}(t)$:
$$
\begin{align*}
\vec{r}_{1}'(t) &= (-\sin (t), \cos(t), 1)
\end{align*}
$$
Beregner $\vec{F}(\vec{r}_{1}(t)) \cdot \vec{r}_{1}'(t)$:
$$
\begin{align*}
\vec{F}(\vec{r}_{1}(t)) \cdot \vec{r}_{1}'(t) &= 2 \cos(t) \cdot (-\sin (t)) +  2t \cdot \cos(t) + 2 \sin(t) \cdot 1\\
&= -2 \cos(t) \sin(t) + \cos(t) \cdot 2t + 2 \sin(t)
\end{align*}
$$
For at kunne beregne integralet skal jeg først finde hvad intervallet er:
Da de tre kurver skal forbindes, betyder det at endepunktet for $C_{1}$ er startpunktet for $C_{2}$
Da $C_{2}: \vec{r}(t) = (0, 1, \frac{\pi}{2} (1-t))$
Så ved  $t = 0$:
$C_{2}: \vec{r}(0) = \left(0, 1, \frac{\pi}{2} (1-0)\right) = \left(0, 1, \frac{\pi}{2}\right)$
Og jeg kigger på $C_{1}: \vec{r}(t) = (\cos(t), \sin(t), t)$ 
Så ved jeg at: 
$\cos\left(\frac{\pi}{2}\right) = 0$
$\sin\left(\frac{\pi}{2}\right) = 1$
$\frac{\pi}{2} = \frac{\pi}{2}$
Så må slutpunktet for $C_{1}$ være ved $t = \frac{\pi}{2}$
Startpunktet for $C_{1}$ er selvfølgelig ved $t=0$:
$\cos(0) = 1$
$\sin(0) = 0$
$(1,0,0)$
Hvilket også kan ses på tegningen.

Nu kan jeg begynde på integralet:
$$
\begin{align*}
\int_{0}^{\frac{\pi}{2}} \vec{F}(\vec{r}_{1}(t)) \cdot \vec{r}_{1}'(t) \, dt &= \int_{0}^{\frac{\pi}{2}}-2 \cos(t) \sin(t) + \cos(t) \cdot 2t + 2 \sin(t) \, dt\\
&= \int_{0}^{\frac{\pi}{2}} -2 \cos(t) \sin(t) \, dt + \int_{0}^{\frac{\pi}{2}} \cos(t) \cdot 2t \, dt + \int_{0}^{\frac{\pi}{2}} 2 \sin(t) \, dt
\end{align*}
$$
$$
\begin{align*}
\int_{0}^{\frac{\pi}{2}} -2 \cos(t) \sin(t) \, dt\\
\text{Jeg bruger substitution:}\\
u &=  \cos(t)\\
du &= - \sin(t) \, dt\\
\int_{0}^{\frac{\pi}{2}} -2 \cos(t) \sin(t) \, dt &= \int_{u(0)}^{u(\frac{\pi}{2})} 2u(du)\\
u(0) = \cos(0) &= 1\\
u\left(\frac{\pi}{2}\right) = \cos\left(\frac{\pi}{2}\right) &= 0\\
\int_{u(0)}^{u(\frac{\pi}{2})} 2u(du) &= \int_{1} ^{0} 2u(du)\\
\int_{1} ^{0} 2u(du) &= [u^{2}]_{1}^{0}\\
&= 0-1^{2}\\
&= -1\\
\\
\int_{0}^{\frac{\pi}{2}} \cos(t) \cdot 2t \, dt\\
\text{Bruger integration i dele:}\\
\int u \, dv = uv - \int v \, du\\
u &= 2t\\
dv &= \cos(t) \, dt\\
v = \int \cos(t) \, dt &= \sin(t)\\
\int_{0}^{\frac{\pi}{2}} 2t \cos(t) \, dt&=  [2t \sin(t)]_{0}^{\frac{\pi}{2}} - \int_{0}^{\frac{\pi}{2}} 2 \sin(t) \, dt\\
[2t \sin(t)]_{0}^{\frac{\pi}{2}} = \pi \cdot 1 - 0 &= \pi\\
\int_{0}^{\frac{\pi}{2}} 2 \sin(t) \, dt &= [-2 \cos(t)]_{0}^{\frac{\pi}{2}}\\
&= -2 (0-1)\\
&= 2\\
\text{Så det hele bliver:}\\
\int_{0}^{\frac{\pi}{2}} \cos(t) \cdot 2t \, dt &= \pi-2\\
\\
\int_{0}^{\frac{\pi}{2}} 2 \sin(t) \, dt &= [-2 \cos(t)]_{0}^{\frac{\pi}{2}}\\
&= -2(0-1)\\
&= 2\\
\\
\text{Dermed bliver alle tre integraler tilsammen:}\\
&= -1 + \pi-2 + 2\\
&= \underline{\underline{\pi-1}}
\end{align*}
$$
Nu skal jeg gøre det samme for $C_{2}$ og til sidst for $C_{3}$

$C_{2}$:
$$
\begin{align*}
\vec{r}_{2}(t) &= \left(0, 1, \frac{\pi}{2} (1-t)\right) \\
\vec{F} &=  (2x, 2z, 2y)\\
\vec{F}(r_{2}(t)) &= (0, \pi(1-t), 2)
\end{align*}
$$
Differentierer $r_{2}(t)$:
$$
\begin{align*}
\vec{r}_{2}'(t) &= (0, \pi, 0)
\end{align*}
$$
Beregner $\vec{F}(\vec{r}_{2}(t)) \cdot \vec{r}_{2}'(t)$:
$$
\vec{F}(\vec{r}_{2}(t)) \cdot \vec{r}_{2}'(t) = \pi(1-t) \cdot \pi = \pi^{2}(1-t)
$$
For at kunne beregne integralet skal jeg først finde hvad intervallet er:
Da de tre kurver skal forbindes, betyder det at endepunktet for $C_{2}$ er startpunktet for $C_{3}$
Da $C_{3}: \vec{r}(t) = (t, (1-t), 0)$ 
Så ved  $t = 0$:
$C_{3}: \vec{r}(0) = (0, 1, 0)$
Og jeg kigger på $C_{2}: \vec{r}(t) = (0, 1, \frac{\pi}{2} (1-t))$
Så ved jeg at ved t=1: 
$\frac{\pi}{2} (1-1) = 0$
Så må slutpunktet for $C_{1}$ være ved $t = 1$
Startpunktet for $C_{2}$ er selvfølgelig ved $t= 0$:
$(0,1,\frac{\pi}{2})$
Hvilket også kan ses på tegningen.

Nu kan jeg begynde på integralet:
$$
\begin{align*}
\int_{0}^{1} \vec{F}(\vec{r}_{2}(t)) \cdot \vec{r}_{2}'(t) \, dt &= \int_{0}^{1} \pi^{2}(1-t) \, dt\\
\int_{0}^{1} \pi^{2}(1-t) \, dt &= \pi^{2} \int_{0}^{1} (1-t) \, dt\\
\pi^{2} \int_{0}^{1} (1-t) \, dt&= \pi^{2} \left[\left(t-\frac{t^{2}}{2}\right)\right]_{0}^{1}\\
&= \pi^{2}\left(\frac{1-1}{2}\right)-0\\
&= \frac{\pi^{2}}{2}
\end{align*}
$$
$C_{3}$:
$$
\begin{align*}
\vec{r}_{3}(t) &= (t, (1-t), 0)\\
\vec{F} &=  (2x, 2z, 2y)\\
\vec{F}(r_{3}(t)) = (2t, 0, 2(1-t)) &= (2t, 0, 2-2t)
\end{align*}
$$
Differentierer $r_{3}(t)$:
$$
\begin{align*}
\vec{r}_{3}'(t) &= (1, -1, 0)
\end{align*}
$$
Beregner $\vec{F}(\vec{r}_{3}(t)) \cdot \vec{r}_{3}'(t)$:
$$
\vec{F}(\vec{r}_{3}(t)) \cdot \vec{r}_{3}'(t) = 2t \cdot 1 + 0 \cdot (-1) -2t \cdot 0 = 2t
$$
For at kunne beregne integralet skal jeg først finde hvad intervallet er:
Da de tre kurver skal forbindes, betyder det at endepunktet for $C_{3}$ er startpunktet for $C_{1}$
Da startpunktet for $C_{1}$ var:
$(1,0,0)$
Så skal dette være slutpunktet for $C_{3}$
Startpunktet for $C_{3}$ er selvfølgelig ved $t= 0$:
$(0,1,0)$
Hvilket også kan ses på tegningen.

Nu kan jeg begynde på integralet:
$$
\begin{align*}
\int_{0}^{1} \vec{F}(\vec{r}_{3}(t)) \cdot \vec{r}_{3}'(t) \, dt &= \int_{0}^{1} 2t \, dt\\
&= 2
\end{align*}
$$
Dermed bliver linjeintegralet af det hele:
$$
\pi-1 + \frac{\pi^{2}}{2} + 2 = \frac{\pi^{2}}{2} + \pi + 1
$$
b. Tegn projektionen af kurven C på x-y-planet
For at tegne projektionen af kurven C på x-y-planet skal jeg beregne hvordan de tre kurver den består af ser ud uden z-komponentet, ved at sætte den til 0:

$$
\begin{align*}
\vec{r}_{1}(t) &=  (\cos(t), \sin(t), t)\\
\vec{r_{1}}(t)_{proj} &= (\cos(t), \sin(t), 0)\\
\text{Det er altså en cirkel}\\
\vec{r}_{2}(t) &=  \left(0, 1, \frac{\pi}{2}(1-t)\right)\\
\vec{r_{2}}(t)_{proj} &= (0,1,0)\\
C_{2} \text{ er altså bare et punkt (i x-y-planet) ved } x&= 0 \text{ og } y=1 \text{ der ikke påvirkes af t}\\
\vec{r}_{3}(t) &= (t, 1-t, 0)\\
\vec{r_{3}}(t)_{proj} &= (t, 1-t)
\end{align*}
$$
Så ved $t=0$:
$$
\begin{align*}
\vec{r_{1}}(0)_{proj} = (\cos(0), \sin(0), 0) &= (1,0,0)\\
\vec{r_{2}}(0)_{proj} &= (0,1,0)\\
\vec{r_{3}}(0)_{proj} = (0, 1-0) &= (0,1)
\end{align*}
$$

Ved $t=1$ ($t= \frac{\pi}{2}$ for $\vec{r}_{1, proj}$): 
$$
\begin{align*}
\vec{r_{1}}\left(\frac{\pi}{2}\right)_{proj} =  \left(\cos\left(\frac{\pi}{2}\right), \sin\left(\frac{\pi}{2}\right), 0\right) &= (0,1,0)\\
\vec{r_{2}}(1)_{proj} &= (0,1,0)\\
\vec{r_{3}}(1)_{proj} = (1, 1-1) &= (1,0)
\end{align*}
$$
Tegningen:
![[1.b.png]]
### Opgave 2
For en stationær strømning i 2 dimensioner er følgende hastighedsfelt givet:
$$
\vec{v} = 
\begin{pmatrix}
x \\ 
x-2y
\end{pmatrix}
$$
a. Find strømningens rotation.
Rotation er det der svarer til curl. Formlen for curl af et 2-dimensionelt vektorfelt er givet ved:
$$
\vec{v}(x,y) = 
\begin{pmatrix}
v_{x}(x,y) \\ 
v_{y}(x,y)
\end{pmatrix}
$$
$$
\text{curl} (\vec{v}) =  \frac{\partial v_{y}}{\partial x} - \frac{\partial v_{x}}{\partial y}
$$
I dette tilfælde er:
$$
\begin{align*}
v_{x} &=  x\\
v_{y} &=  x-2y
\end{align*}
$$
Derfor skal jeg beregne de partielle afledte:
$$
\begin{align*}
\frac{\partial v_{y}}{\partial x} = \frac{\partial(x-2y)}{\partial x} &= 1\\
\frac{\partial v_{x}}{\partial y} = \frac{\partial(x)}{\partial y} &= 0
\end{align*}
$$
Derfor bliver:
$$
\text{curl} (\vec{v}) =  \frac{\partial v_{y}}{\partial x} - \frac{\partial v_{x}}{\partial y} = 1-0 = 1
$$
$$
\text{curl} (\vec{v}) = 1
$$

b. Er strømningen kompressibel eller inkompressibel?
Hvis det er inkompressible betyder det at:
$$
\text{div } (\vec{v}) = \frac{\partial v_{x}}{\partial x} + \frac{\partial v_{y}}{\partial y} = 0
$$
Hvor i dette tilfælde er:
$$
\begin{align*}
v_{x} &=  x\\
v_{y} &=  x-2y
\end{align*}
$$
Derfor beregner jeg de partielle afledte:
$$
\begin{align*}
\frac{\partial v_{x}}{\partial x} = \frac{\partial (x)}{\partial x} &= 1\\
\frac{\partial v_{y}}{\partial y} = \frac{\partial (x-2y)}{\partial y} &= -2
\end{align*}
$$
Derfor bliver divergensen:
$$
div(\vec{v}) = 1+(-2) = -1
$$
$$
div(\vec{v}) = -1
$$
Siden $div(\vec{v}) \neq 0$ betyder det at strømningen **ikke** er inkompressibel. Den er altså **kompressibel**.

c. Udregn og tegn strømlinjerne.
For at udregne strømlinjerne skal jeg løse ligninerne i formlen:
$$
\frac{dx}{v_{x}}=\frac{dy}{v_{y}}
$$
I dette tilfælde er:
$$
\begin{align*}
v_{x} &=  x\\
v_{y} &=  x-2y
\end{align*}
$$
Dvs. jeg skal integrere for at finde henholdsvis x og y, efter at have indsat værdierne for $\vec{v}$.
Siden $\vec{v}=[x,x-2y]$:
$$
\begin{align*}
\frac{dx}{x}&= \frac{dy}{x-2y}\\
\text{Omskriver udtrykket:}\\
\frac{dy}{dx} &= \frac{x-2y}{x}\\
\frac{dy}{dx} &= 1 - \frac{2y}{x}\\
\end{align*}
$$
Dette er en førsteordens differentialligning, som jeg kan løse ved at bruge seperation af variable:
$$
\frac{dy}{dx}=f(x)\cdot g(y)
$$
$$
=\int \frac{1}{g(y)}\space dy=\int f(x)\space dx
$$
Men dette kræver at y ikke er divideret med x, derfor skal jeg først substituere:
$$
\begin{align*}
u &= \frac{y}{x}\\
y &=  ux\\
\text{kæderegel: }\frac{d}{dx}[f(g(x))] &=  f'(g(x)) \cdot g'(x)\\
\frac{dy}{dx}&= u+ x \frac{du}{dx}\\
\text{Indsætter i oprindelige ligning:}\\
u+x \frac{du}{dx} = 1 - \frac{2ux}{x} &=  1 - 2u\\
\text{Dvs.}\\
x \frac{du}{dx} &= 1-3u\\
\text{Dvs. ligningen bliver:}\\
\frac{du}{1-3u} &= \frac{dx}{x}\\
\text{Dette kan jeg bruge formlen på:}\\
\int \frac{1}{g(y)}\space dy &= \int f(x)\space dx\\
\text{Starter med venstresiden}\\
\int\frac{1}{g(u)} \, du &=  \int f(x) \, dx\\
\int\frac{1}{g(u)} \, du &=  \int \frac{1}{1-3u} \, du\\
\text{Substitution:}\\
w = 1-3u, \quad dw = -3 du \rightarrow du &= \frac{-1}{3} dw\\
\int \frac{1}{w} \cdot \left(\frac{-1}{3}\right) dw\\
= - \frac{1}{3} \ln|w| + C_{1} &=  - \frac{1}{3} \ln|1-3u| + C_{1}\\
\text{Højresiden:}\\
\int f(x)\space dx &=  \int \frac{1}{x} \, dx\\
&= \ln|x| + C_{2}\\
\text{Sætter dem sammen}\\
- \frac{1}{3} \ln|1-3u| + C_{1} =& \ln|x| + C_{2}\\
\ln|1-3u| =& -3\ln|x| + C\\
\text{indsætter } u &=  \frac{y}{x}\\
\ln \left|1-3\frac{y}{x}\right| =& -3\ln|x| + C\\
\text{Logaritmeregneregel} \log_{b}(x^{a}) &=  a \cdot \log_{b}(x)\\
\ln \left|1-3\frac{y}{x}\right| =& \ln|x^{-3}| + C\\
\text{Logaritmeregneregel} \log_b\left(\frac{x}{y}\right) &=  \log_b(x) - \log_b(y)\\
\ln \left|1-3\frac{y}{x}\right| - \ln|x^{-3}| =&  C\\
\ln \left|\frac{(1-3\frac{y}{x})}{x^{-3}}\right| &= C\\
\ln \left|x^{3} - 3x^{2}y \right| &= C \\
\text{Tager eksponenten}\\
|x^{3} - 3x^{2}y| &= e^{C}\\
3x^{2}y &= x^{3} \pm e^{C}\\
y(x) &= \frac{x}{3} \pm \frac{e^{C}}{3x^{2}}\\
\end{align*}
$$
Nu indsætter jeg forskellige værdier for $e^{C}$ for at kunne tegne strømlinjerne:
$e^{C} = 1$:
$$
\begin{align*}
y(x) &=  \frac{x}{3} - \frac{1}{3x^{2}} \\
y(1) = \frac{1}{3} - \frac{1}{3 \cdot 1^{2}} &=  0 \\
y(2) = \frac{2}{3} - \frac{1}{3 \cdot 4} &=  \frac{7}{12} \\
y(-1) = \frac{-1}{3} - \frac{1}{3 \cdot 1} &=  -\frac{2}{3} \\
y(-2) = \frac{-2}{3} - \frac{1}{3 \cdot 4} =  \frac{-8}{12} - \frac{1}{12} = \frac{-9}{12} &= -\frac{3}{4}\\
\end{align*}
$$
$e^{C} = 2$:
$$
\begin{align*}
y(x) = \frac{x}{3} - \frac{2}{3x^{2}} \\
y(1) = \frac{1}{3} - \frac{2}{3} &=  -\frac{1}{3} \\
y(2) = \frac{2}{3} - \frac{2}{12} &=  \frac{1}{2} \\
y(-1) = \frac{-1}{3} - \frac{2}{3} &= -1\\
y(-2) = \frac{-2}{3} - \frac{2}{12} &=  -\frac{5}{6}
\end{align*}
$$

$e^{C} = 3$:
$$
\begin{align*}
y(x) = \frac{x}{3} - \frac{3}{3x^{2}} &=  \frac{x}{3} - \frac{1}{x^{2}} \\
y(1) = \frac{1}{3} - 1 &=  -\frac{2}{3} \\
y(2) = \frac{2}{3} - \frac{1}{4} = \frac{8}{12} - \frac{3}{12} &=  \frac{5}{12}\\
y(-1) = \frac{-1}{3} - 1 &= -\frac{4}{3}\\
y(-2) = \frac{-2}{3} - \frac{3}{12} = \frac{-8}{12} - \frac{3}{12} &= -\frac{11}{12}\\
\end{align*}
$$
Det smarteste var nok bare at tegne for positive x-værdier da der divideres med 0 ved $x=0$ 
Tegning:
![[2.C.png]]
### Opgave 3
Givet følgende vektorfelter for hastigheden af en gas:
$$
\begin{align*}
\vec{v_{1}} &=  (-x, -y, -z),\\
\vec{v_{2}} &=  (-y, x, 0),\\
\vec{v_{3}} &=  (0, z, 0) \text{ og}\\
\vec{v_{4}} &=  (x, y, z),\\
\end{align*}
$$
Skitser:
![[Vektorfelter til pointgivende 2.png]]

a. Hvilket vektorfelt hører til hver af de 4 skitser?
Vektorfelterne $\vec{v_{1}}$ og $\vec{v_{4}}$ er modsætninger, hvor $\vec{v_{1}}$ er et vektorfelt hvor vektorerne alle bliver kortere og peger ind mod origo fra alle retninger, dette passer med at koordinaterne har et negativt fortegn Derfor passer $\vec{v_{1}}$ med tegning (b). 

Derimod har $\vec{v_{4}}$ det modsatte, hvor vektorerne alle bliver længere og peger væk fra origo i alle retninger. Dette passer med at koordinaterne har et positivt fortegn. Derfor passer $\vec{v_{4}}$ med tegning (a).

$\vec{v_{3}}$ har 0 i både x- og z-koordinat. Hvilket betyder at vektorerne kun peger i y-retningen, men da y-koordinatet er givet ved z, betyder det at pilene bliver længere for større z, og peger i den modsatte retning af y-aksen for negative z-værdier. Derfor passer $\vec{v_{3}}$ med tegning (d).

$\vec{v_{2}}$ er den sidste tilbage. Den har et 0 som z-koordinat, hvilket betyder den ikke afhænger af z. Den har x, som y-koordinat, hvilket betyder at den peger vinkelret på y-aksen og peger mod x-aksen. Den har -y som x-koordinat hvilket også betyder at den peger vinkelret på x-aksen, men for positiv y er det mod negativ x og omvendt. Derfor dannes der en bevægelse mod urets retning. Derudover bliver vektorerne længere jo længere fra origo man kommer. Derfor passer $\vec{v_{2}}$ med tegning (c).

b. Udregn rotationen og divergensen for hver af de 4 vektorfelter og kommentér resultaterne:
Med rotation menes curl, hvilket beregnes med formlen:
$$
\nabla \times \vec{v} =  
\begin{vmatrix}
\hat{i} & \hat{j} & \hat{k}\\
\partial_{x} & \partial_{y} & \partial_{z}\\
v_{x} & v_{y} & v_{z}\\
\end{vmatrix}\\
= \hat{i} \left(\frac{\partial}{\partial y}(v_{z}) - \frac{\partial}{\partial z}(v_{y})\right) - \hat{j} \left(\frac{\partial}{\partial x}\left(v_{z}\right) - \frac{\partial}{\partial z}(v_{x})\right) + \hat{k} \left(\frac{\partial}{\partial x}\left(v_{y}\right) - \frac{\partial}{\partial y}(v_{x})\right)
$$

$$
\begin{align*}
\vec{v_{1}} &=  (-x, -y, -z),\\
\vec{v_{2}} &=  (-y, x, 0),\\
\vec{v_{3}} &=  (0, z, 0) \text{ og}\\
\vec{v_{4}} &=  (x, y, z),\\
\end{align*}
$$

$\vec{v_{1}}$:
$$
\begin{align*}
\hat{i} \left(\frac{\partial}{\partial y}(-z) - \frac{\partial}{\partial z}(-y)\right) - \hat{j} \left(\frac{\partial}{\partial x}\left(-z\right) - \frac{\partial}{\partial z}(-x)\right) + \hat{k} \left(\frac{\partial}{\partial x}\left(-y\right) - \frac{\partial}{\partial y}(-x)\right)\\
\text{Da alle differentiationer ikke indeholder det der differentieres mht.:}\\
= 0
\end{align*}
$$
$$
\nabla \times \vec{v} = 0
$$
Dette betyder at der ingen rotation er.

$\vec{v_{2}}$:
$$
\begin{align*}
\hat{i} \left(\frac{\partial}{\partial y}(0) - \frac{\partial}{\partial z}(x)\right) - \hat{j} \left(\frac{\partial}{\partial x}\left(0\right) - \frac{\partial}{\partial z}(-y)\right) + \hat{k} \left(\frac{\partial}{\partial x}\left(x\right) - \frac{\partial}{\partial y}(-y)\right)\\
&=  \hat{k}(1-(-1))\\
&= \hat{k}(2)
\end{align*}
$$
$$
\nabla \times \vec{v} = \hat{k}(2)
$$
Dette betyder at der er positiv rotation om z-aksen.

$\vec{v_{3}}$:
$$
\begin{align*}
\hat{i} \left(\frac{\partial}{\partial y}(0) - \frac{\partial}{\partial z}(z)\right) - \hat{j} \left(\frac{\partial}{\partial x}\left(0\right) - \frac{\partial}{\partial z}(0)\right) + \hat{k} \left(\frac{\partial}{\partial x}\left(z\right) - \frac{\partial}{\partial y}(0)\right)\\
&= \hat{i}(-1)
\end{align*}
$$
Dette betyder at der er negativ rotation om x-aksen.

$\vec{v_{4}}$:
$$
\begin{align*}
\hat{i} \left(\frac{\partial}{\partial y}(z) - \frac{\partial}{\partial z}(y)\right) - \hat{j} \left(\frac{\partial}{\partial x}\left(z\right) - \frac{\partial}{\partial z}(x)\right) + \hat{k} \left(\frac{\partial}{\partial x}\left(y\right) - \frac{\partial}{\partial y}(x)\right)\\
\text{Da alle differentiationer ikke indeholder det der differentieres mht.:}\\
= 0
\end{align*}
$$
Dette betyder at der ingen rotation er, hvilket også passer med at $\vec{v_{4}}$ bare er $\vec{v_{1}}$ med positivt fortegn.

Divergensen beregnes med formlen:
$$
\text{div } (\vec{v}) = \frac{\partial v_{x}}{\partial x} + \frac{\partial v_{y}}{\partial y} + \frac{\partial v_{z}}{\partial z}
$$
$\vec{v_{1}}$:
$$
\begin{align*}
\text{div } (\vec{v}) &=  \frac{\partial v_{x}}{\partial x} + \frac{\partial v_{y}}{\partial y} + \frac{\partial v_{z}}{\partial z}\\
&= -1 + (-1) + (-1)\\
&= -3
\end{align*}
$$
Dvs. $\vec{v_{1}}$ feltet trækker sig sammen, det "compressor", idet $\text{div} (\vec{v}) < 0$

$\vec{v_{2}}$:
$$
\begin{align*}
\text{div } (\vec{v}) &=  \frac{\partial v_{x}}{\partial x} + \frac{\partial v_{y}}{\partial y} + \frac{\partial v_{z}}{\partial z}\\
&= 0+0+0\\
&= 0
\end{align*}
$$
Dvs. $\vec{v_{2}}$ er inkompressibel, idet $\text{div} (\vec{v}) = 0$ 

$\vec{v_{3}}$:
$$
\begin{align*}
\text{div } (\vec{v}) &=  \frac{\partial v_{x}}{\partial x} + \frac{\partial v_{y}}{\partial y} + \frac{\partial v_{z}}{\partial z}\\
&= 0+0+0\\
&= 0
\end{align*}
$$
Dvs. $\vec{v_{3}}$ er inkompressibel, idet $\text{div} (\vec{v}) = 0$ 

$\vec{v_{4}}$:
$$
\begin{align*}
\text{div } (\vec{v}) &=  \frac{\partial v_{x}}{\partial x} + \frac{\partial v_{y}}{\partial y} + \frac{\partial v_{z}}{\partial z}\\
&= 1 + 1 + 1\\
&= 3
\end{align*}
$$
Dvs. $\vec{v_{1}}$ feltet udvider sig, det "decompressor", idet $\text{div} (\vec{v}) < 0$

Dermed ender jeg med svarene:
$\vec{v_{1}}$ har ingen rotation, men feltet trækker sig sammen.
$\vec{v_{2}}$ har en positiv rotation omkring z-aksen, men feltet er incompressible
$\vec{v_{3}}$ har en negativ rotation omkring x-aksen, men feltet er incompressible
$\vec{v_{4}}$ har ingen rotation. men feltet udvider sig.