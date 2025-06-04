### 10.7.9
Evaluate the surface integral $\iint F \cdot n \, dA$ by the divergence theorem. Show the details.

$F = [x^{2}, 0, z^{2}]$, S the surface of the box $|x| \leq 1, |y| \leq 3, 0 \leq z \leq 2$

$$
\iiint_{T} \text{div } \vec{F} \, dV = \iint_{S} \vec{F} \cdot \vec{n} \,  dA
$$
$$
\begin{align*}
\vec{F} &=  (F_{1}, F_{2}, F_{3})\\
\text{div } \vec{F} &= \frac{\partial F_{1}}{\partial x} + \frac{\partial F_{2}}{\partial y} + \frac{\partial F_{3}}{\partial z}\\
&= \frac{\partial}{\partial x}(x^{2}) + \frac{\partial}{\partial y}(0) + \frac{\partial}{\partial z}(z^{2})\\
&= 2x + 0 + 2z\\
&= 2x + 2z
\end{align*}
$$
Volumen er defineret til at have grænserne:
$$
x \in [-1,1], \quad y \in [-3,3], \quad z \in[0,2]
$$
Derfor bliver integralet:
$$
\iiint_{V} (2x +2z) \, dV = \int_{x=-1}^{1} \, dx \int_{y=-3} ^{3} \, dy \int_{z=0}^{2} (2x + 2z) \, dz
$$
Jeg starter med det inderste integrale:
$$
\begin{align*}
\int_{z=0}^{2} (2x + 2z) \, dz &= [2xz + z^{2}]_{z=0}^{2}\\
&= (4x + 2^{2}) - (0)\\
&= 4x + 4
\end{align*}
$$
Nu indsætter jeg dette i integralet mht. y:
$$
\begin{align*}
\int_{y=-3} ^{3} (4x + 4) \,dy &=  (4x + 4) \int_{y=-3} ^{3} \,dy\\
&=  (4x + 4) \cdot (3 - (-3))\\
&= (4x + 4) \cdot 6\\
&= (24x + 24)
\end{align*}
$$
Nu indsætter jeg dette i integralet mht. x:
$$
\begin{align*}
\int_{x=-1}^{1} (24x + 24) \, dx &= [12x^{2} + 24x]_{x=-1}^{1}\\
&= 12 + 24 - (12 - 24)\\
&= 36 - (-12)\\
&= 48
\end{align*}
$$
Derfor blev:
$$
\begin{align*}
\text{div } F &=  2x + 2z\\
\iint F \cdot n \, dA &= 48
\end{align*}
$$
Svaret i bogen er:
$$
\text{div } F = 2x + 2z, 48
$$
### 10.7.13
Evaluate the surface integral $\iint F \cdot n \, dA$ by the divergence theorem. Show the details.

$F = [\sin(y), \cos(x), \cos(z)]$, S, the surface of $x^{2} + y^{2} \leq 4, \quad |z| \leq 2$ (a cylinder and two disks!)


$$
\iiint_{V} \text{div } \vec{F} \, dV = \iint_{S} \vec{F} \cdot \vec{n} \,  dA
$$
$$
\begin{align*}
\vec{F} &=  (F_{1}, F_{2}, F_{3})\\
\text{div } \vec{F} &= \frac{\partial F_{1}}{\partial x} + \frac{\partial F_{2}}{\partial y} + \frac{\partial F_{3}}{\partial z}\\
&= \frac{\partial}{\partial x}(\sin(y)) + \frac{\partial}{\partial y}(\cos(x)) + \frac{\partial}{\partial z}(\cos(z))\\
&= 0 + 0 + (- \sin(z))\\
&= - \sin(z)\\
\end{align*}
$$
Derfor bliver integralet:
$$
\iiint_{V} - \sin(z) \, dV
$$
Siden regionen V er cylindrisk, så er giver det god mening at bruge cylindriske koordinater.
$$
\begin{align*}
x &= r \cdot \cos(\theta)\\
y &= r \cdot \sin(\theta)\\
z &= z\\
dV &= r \, dr \, d \theta \, dz
\end{align*}
$$
Grænserne bliver:
$$
\begin{align*}
0 \leq r &\leq 2 \text{ (da radius er 2)}\\
0 \leq \theta &\leq 2\pi \text{ (en fuld cirkel)}\\
-2 \leq z &\leq 2
\end{align*}
$$
$$
\iiint_{V} - \sin(z) \, dV = \int_{z=-2} ^{2} - \sin(z) \,dz \int_{\theta=0} ^{2\pi} \, d \theta, \int_{r=0} ^{2} \, r \,dr
$$
$$
\begin{align*}
\int_{r=0} ^{2} \, r \,dr &= \left[\frac{1}{2} r^{2}\right]_{r=0}^{2}\\
&= 2 - 0\\
&= 2
\end{align*}
$$
$$
\begin{align*}
\int_{\theta=0} ^{2\pi} \, d \theta &= [\theta]_{\theta=0}^{2\pi}\\
&= 2\pi - 0\\
&= 2 \pi
\end{align*}
$$
$$
\begin{align*}
\int_{z=-2} ^{2} - \sin(z) \,dz &= [\cos(z)]_{z=-2}^{2}\\
&= \cos(2) - \cos(-2)\\
\text{Siden cos er en lige funktion:}\\
\cos(2) - \cos(-2) &= 0
\end{align*}
$$
Nu ganger jeg de tre integralers værdier sammen:
$$
2 \cdot 2\pi \cdot 0 = 0
$$
Dvs. jeg beregnede at:
$$
\begin{align*}
\text{div } F &=  -\sin(z)\\
\iiint_{V} - \sin(z) \, dV &= 0
\end{align*}
$$
Dette passer også med at sinus er en ulige funktion, så når regionen er symmetrisk omkring $z=0$ så bliver volumen 0.

Svaret i bogen er:
$$
\text{div } F = -\sin(z), 0
$$
### 10.7.20
Given a mass of density 1 in a region T of space, find the moment of inertia about the x-axis
$$
I_{x} = \iiint_{T} (y^{2} + z^{2}) \, dx \, dy \, dz
$$
The ball $x^{2} + y^{2} + z^{2} \leq a^{2}$

Fordi det er en sfærisk symmetri, så bruger jeg sfæriske koordinater. Derfor bliver:
$$
\begin{align*}
x &= \rho \sin(\phi) \cos(\theta)\\
y &= \rho \sin(\phi) \sin(\theta)\\
z &= \rho \cos(\phi)\\
dV &= \rho^{2} \sin(\phi) \, d \rho \, d \phi \, d \theta
\end{align*}
$$
Integranden er:
$$
y^{2} + z^{2} = (\rho \sin(\phi) \sin (\theta))^{2} + (\rho \cos(\phi))^{2} = \rho^{2} (\sin^{2}(\phi) \sin^{2}(\theta) + \cos^{2}(\phi))
$$
Grænserne er:
Da bolden er givet ved:
$$
x^{2} + y^{2} + z^{2} \leq a^{2}
$$
Så bliver det til:
$$
0 \leq \rho \leq a
$$
i sfæriske koordinater.
$\phi$ er hvor langt punktet er fra z-aksen, hvor $\phi$ skal gå fra nordpol til sydpol:
$$
\begin{align*}
\phi &=  0: \text{peger hen ad +z-akse}\\
\phi &= \frac{\phi}{2}: \text{peger hen ad xy-planet}\\
\phi &= \pi: \text{peger hen ad -z-akse}
\end{align*}
$$
Så for at dække hele sfæren bliver det:
$$
0 \leq \phi \leq \pi
$$
$\theta$ roterer omkring z-aksen og dækker alle retninger i xy-planet. En fuld rotation kræver at $\theta$ går fra 0 til $2\pi$:
$$
0 \leq \theta \leq 2\pi
$$
Dermed bliver grænserne defineret som:
$$
\begin{align*}
0 \leq \rho &\leq a\\
0 \leq \phi &\leq \pi\\
0 \leq \theta &\leq 2 \pi 
\end{align*}
$$
Integralet bliver derfor:
$$
\begin{align*}
\iiint_{T} (y^{2} z^{2}) \, dV &=  \int_{\theta} ^{2\pi} d \theta \int_{\phi=0} ^{\pi} d\phi \int_{\rho=0} ^{a} \rho^{2} (\sin^{2}(\phi) \sin^{2}(\theta) + \cos^{2}(\phi)) \cdot \rho^{2} \sin(\phi) \, d \rho\\
&= \int_{\theta} ^{2\pi} d \theta \int_{\phi=0} ^{\pi} d\phi \int_{\rho=0} ^{a} \rho^{4}((\sin^{2}(\phi) \sin^{2}(\theta) + \cos^{2}(\phi)) \sin(\phi) \, d \rho)\\
\text{Splitter integralet op i to:}\\
&= \int_{\theta} ^{2\pi} d \theta \int_{\phi=0} ^{\pi} d\phi \int_{\rho=0} ^{a} \rho^{4}\sin^{2}(\phi) \sin^{2}(\theta) \sin(\phi) \, d \rho \\
&+ \int_{\theta} ^{2\pi} d \theta \int_{\phi=0} ^{\pi} d\phi \int_{\rho=0} ^{a} \rho^{4}\cos^{2}(\phi) \sin(\phi) \, d \rho\\
= \left[\frac{\rho^{5}}{5}\right]_{\rho= 0}^{a} &= \frac{a^{5}}{5}\\
&= \frac{a^{5}}{5} \cdot \left[\int_{\theta} ^{2\pi} d \theta \int_{\phi=0} ^{\pi} \sin^{2}(\phi) \sin^{2}(\theta) \sin(\phi) \, d\phi + \int_{\theta} ^{2\pi} d \theta \int_{\phi=0} ^{\pi} \cos^{2}(\phi) \sin(\phi) \, d\phi\right]\\
\text{Først udtryk:}\\
\int_{\theta= 0} ^{2\pi} \sin^{2}(\theta) \, d \theta \int_{\phi = 0} ^{\pi} \sin^{3} \phi \, d \phi\\
\int_{\theta=0} ^{2\pi} \sin^{2}(\theta) \, d \theta &=  \int_{\theta=0} ^{2\pi}  \frac{1- \cos(2 \theta)}{2} \, d \theta = \left[\frac{\theta}{2} - \frac{\sin(2 \theta) }{4}\right]_{\theta=0} ^{2\pi} = \pi\\\\
\int_{\phi=0} ^ {\pi} \sin^{3}(\phi) \, d \phi &= \int_{\phi=0} ^{\pi} (\sin(\phi) - \sin(\phi) \cos^{2}(\phi)) \, d \phi\\
\text{Lad }u = \cos(\phi), \quad du &= -\sin(\phi) \, d \phi,\\
\text{Grænserne går fra } \phi = 0, \quad \phi &= \pi\\
\text{til } u = \cos(0) \Rightarrow 1, \quad u = - \sin(\pi) &\Rightarrow -1\\
\int_{1}^{-1} (1 - u^{2}) (- du) =  \int_{-1}^{1} (1 - u^{2}) \, du &=  \left[u - \frac{u^{3}}{3}\right]_{u = -1}^{1} &=  \left(1- \frac{1}{3}\right) - \left(-1 + \frac{1}{3}\right)\\
 = \frac{2}{3} - \left(- \frac{2}{3}\right) &=  \frac{4}{3}\\
\text{Dermed bliver det første udtryk: } \pi \cdot \frac{4}{3} &= \frac{4\pi}{3}
\end{align*}
$$
Andet udtryk:
$$
\begin{align*}
\int_{\theta=0 } ^{2\pi} \, d \theta \int_{\phi=0} ^{\pi} \cos^{2}(\phi) \sin(\phi) \, d \phi\\
\int_{\theta=0} ^{2\pi} \, d \theta &= 2 \pi\\
\int_{0}^{\pi} \cos^{2} (\phi) \sin(\phi) \, d \phi\\
\text{Lad } w = \cos(\phi), \quad dw &= - \sin(\phi) \, d \phi\\
\text{Grænserne går fra } \phi = 0, \quad \phi &= \pi\\
\text{til } w = \cos(0) \Rightarrow 1, w = - \sin(\pi) &\Rightarrow -1\\
\int_{1}^{-1} w^{2}(-dw) = \int_{-1}^{1} w^{2} \, dw &= \left[\frac{w^{3}}{3}\right]_{w = -1}^{1}\\
= \frac{1}{3} - \left(-\frac{1}{3}\right) &= \frac{2}{3}\\
\text{Dermed bliver det andet udtryk: } 2 \pi \cdot \frac{2}{3} &= \frac{4\pi}{3}
\end{align*}
$$
Jeg summere de to udtryk:
$$
\frac{4\pi}{3} + \frac{4\pi}{3} = \frac{8\pi}{3}
$$
Jeg husker at gange det led der var udenfor integralet på:
$$
\frac{a^{5}}{5} \cdot \frac{8\pi}{3} = \frac{8 \pi a^{5}}{15}
$$
Så jeg har altså beregnet at:
$$
I_{x} = \underline{\underline{\frac{8\pi a^{5}}{15}}}
$$
Hvilket også passer med standardformlen for intertien af en solid sfære om sin diameter er givet ved:
$$
I = \frac{2}{5} M a^{2}
$$
Hvor M er massen af sfæren. Siden densiteten (massefylde) var 1. Så er massen givet ved densiteten ganget med volumen givet ved:
$$
V = \frac{4}{3} \pi a^{3}
$$
$$
M = \rho \cdot V = 1 \cdot \frac{4}{3} \pi a^{3} = \frac{4}{3} \pi a^{3}
$$
Smækker det ind i fomlen for inerti:
$$
I = \frac{2}{5} M a^{2} = \frac{2}{5} \left(\frac{4}{3} \pi a^{3}\right) a^{2} = \frac{2}{5} \cdot \frac{4}{3} \pi a^{5} = \frac{8\pi a^{5}}{15}
$$
Så det er altså præcist det samme som jeg fik i min udregning.
### 10.7.21
Given a mass of density 1 in a region T of space, find the moment of inertia about the x-axis
$$
I_{x} = \iiint_{T} (y^{2} + z^{2}) \, dx \, dy \, dz
$$
The cylinder $y^{2} + z^{2} \leq a^{2}, \quad 0 \leq x \leq h$

Fordi det er en cylindrisk symmetri, så bruger jeg cylindriske koordinater. Derfor bliver:
$$
\begin{align*}
y &= r \cos(\theta)\\
z &= r \sin(\theta)\\
x &= x\\
dV &= r \, dr \, d \theta \, dx
\end{align*}
$$
Integranden bliver:
$$
y^{2} + z^{2} = (r \cos(\theta))^{2} + (r \sin(\theta))^{2} = r^{2} \cos^{2}(\theta) + r^{2} \sin^{2}(\theta) = r^{2} (cos^{2}(\theta) + \sin^{2}(\theta)) = r^{2}
$$
Grænserne er:
Da cylinderen er givet ved:
$$
\begin{align*}
y^{2} + z^{2} \leq a^{2}, \quad 0 \leq x \leq h
\end{align*}
$$
Så da $y^{2}+z^{2} = r^{2}$ Så bliver det til:
$$
\begin{align*}
r ^{2} &\leq a^{2}\\
r &\leq a
\end{align*}
$$
Dvs. grænserne bliver:
$0 \leq r \leq a$
$0 \leq \theta \leq 2\pi$
$0 \leq x \leq h$

Dermed bliver integralet:
$$
I_{x} = \int_{x=0} ^{h} \, dx \int_{\theta=0}^{2\pi} \, d \theta \int_{r=0}^{a} r^{2} \, r \, dr
$$
Siden integranden er uafhængig af både x og theta så kan integralet separeres:
$$
I_{x} = \left(\int_{x=0} ^{h} \, dx\right) \left(\int_{\theta=0}^{2\pi} \, d \theta\right) \left(\int_{r=0}^{a} r^{2} \, r \, dr\right)
$$
$$
\begin{align*}
\int_{r=0}^{a} r^{2} \, r \, dr = \int_{r=0}^{a} r^{3} \, dr = \left[\frac{r^{4}}{4}\right]_{r=0}^{a} &= \frac{a^{4}}{4}\\
\int_{\theta=0}^{2\pi} \, d \theta &=  2 \pi\\
\int_{x=0} ^{h} \, dx &=  h
\end{align*}
$$
Dermed bliver det endelige svar de tre resultater ganget sammen:
$$
\frac{a^{4}}{4} \cdot 2 \pi \cdot h = \frac{ a^{4}2\pi h }{4} = \frac{a^{4} \pi h}{2}
$$
Dette passer også med intertien for en solid cylinder om sin centrale akse:
$$
I_{x} = \frac{1}{2} M a^{2}
$$
Hvor M er massen som er givet ved volumen ganget med densiteten (massefylde). Volumen for en cylinder er givet ved $V = \pi a^{2} h$ og siden densiteten i opgaven var 1:
$$
I_{x} = \frac{1}{2}(\pi a^{2} h) a^{2} = \frac{\pi a^{4} h}{2} 
$$
Hvilket er det samme resultat som det jeg fik af integralet.
Svaret i bogen er:
$$
\left(\frac{a^{4}}{4}\right)\cdot 2\pi \cdot h = h a^{4} \frac{\pi}{2}
$$
### 10.9.13 
Calculate this line integral by Stokes' theorem for the given F and C. Assume the Cartesian coordinates to be right-handed and the z-component of the surface normal to be nonnegative.
$F = [-5y, 4x, z]$ C the circle $x^{2} + y^{2} = 16, z = 4$

Stokes teori er:
$$
\oint_{C} F \cdot dr = \iint_{S} (\nabla \times F) \cdot ds
$$
Hvor S er en flade der er begrænset af C med en normal vektor der har et ikke negatigt z-komponent, som der står i opgavens beskrivelse.
Først beregner jeg curl af F
$$
\begin{align*}
\nabla \times F &= 
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
a_{1}  & a_{2}  & a_{3}\\
b_{1}  & b_{2} &  b_{3}\\
\end{vmatrix}\\
&= \vec{i}(a_{2}b_{3} - a_{3}b_{2}) - \vec{j}(a_{1}b_{3} - a_{3}b_{1}) + \vec{k}(a_{1}b_{2} - a_{2}b_{1})\\
\text{Indsætter mine værdier:}\\
\begin{vmatrix}
\vec{i}  &  \vec{j} & \vec{k}\\
\frac{\partial}{\partial x}  & \frac{\partial}{\partial y} & \frac{\partial}{\partial z}\\
-5y  & 4x &  z\\
\end{vmatrix}\\
&= \vec{i}\left(\frac{\partial}{\partial y} \left(z\right) - \frac{\partial}{\partial z} 4x\right) - \vec{j}\left(\frac{\partial}{\partial x}\left(z\right) - \frac{\partial}{\partial z} (-5y)\right) + \vec{k}\left(\frac{\partial}{\partial x}\left(4x\right) - \frac{\partial}{\partial y}(-5y)\right)\\
&= \vec{i}(0 - 0) - 
\end{align*}
$$

Svaret i bogen er: $5k, 80 \pi$
Det må være forkert
### 10.9.15
Calculate this line integral by Stokes' theorem for the given F and C. Assume the Cartesian coordinates to be right-handed and the z-component of the surface normal to be nonnegative.
$F = [y^{2}, x^{2}, z+x]$, around the triangle with vertices $(0,0,0), (1,0,0), (1,1,0)$