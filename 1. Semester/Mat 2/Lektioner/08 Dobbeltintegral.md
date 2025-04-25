$$\iint_{D} f(x,y)\space dA=V$$
Det bliver til volumen af en cylinder.
$$\iint_{D}1\cdot dA=areal(D)$$
Ligesom et normalt integrale tager arealet under grafen, hvor man kan approximere det med riemann sum, så i tre dimensioner kan man også approximere med riemann sum, hvor man i stedet for rektangler får 3D rektangler (cube), som approximation til volumen af cylinderen under grafen.

Sætning: f er defineret på et lukket, begrænset område D og er kontinuær.
Hvad betyder det?
område: rand: endelig antal kurver med endelig længde.
lukket: rand med
begrænset: ligge i cirkel med endelig radius

f er integrabel på D.

Ligesom i normale integraler så er arealet under grafen negativt, og de samme regneregler gælder også. 

Eks.
$$I=\iint_{x^{2}+y^{2}\leq 1} (sin(x)+4)\space dA$$
$$I=\iint sin(x)\space dA+4\iint dA$$
Fordi sinus er konstrueret sådan at man får lige mange positive værdier som negative værdier, så vil det være 0 (kig på enhedscirkel):
Arealet af en cirkel er $r^{2}\cdot \pi$:
$$=0+4\cdot \pi=4\pi$$

Beregning![[08 Dobbelt integral.pdf]]

Uegentlige integraler
Hvis enten D er ubegrænset eller f(x,y) er ubegrænset på D.
$$f(x,y)\neq 0$$

Middelværdi:
D: lukket, begrænset, f(x,y) er kontinuert:
minimum:$f(x_{1},y_{1})$
maximum:$f(x_{2},y_{2})$

$$f(x_{1},y_{1})\leq f(x,y)\leq f(x_{2},y_{2})$$

$$f(x_{1},y_{1})\cdot A=\iint_{D} f(x_{1},y_{1})\space dA\leq \iint f(x,y)\space dA\leq \iint_{D} f(x_{2},y_{2})\space dA$$
$$A=\iint dA$$
$$f(x_{1},y_{1})\leq \frac{1}{A}\iint_{D} f(x,1)\space dA\leq f(x_{2},y_{2})$$
$$f(x_{1},x_{2})\leq f\leq f(x_{2},y_{2})$$
f kont: $$(x_{0},y_{0})\epsilon f(x_{0},y_{0})=\overline f=\frac{1}{A}\iint_{D}f(x,y)$$
$\iint_{D}f\space dA$ i polære koordinater:

D: i kartesiske koordinater
R: Samme område i polære koordinater:
![[08 Dobbelt integral.pdf#page=5]]

Variabelskift: $$I=\iint_{D}f(x,y)\space dA$$
Omskrive $f$, integral over S i u-v plan:
Vi har x(u,v) og y(u,v) entydigt.


Differentialer:
$$f(x_{1},x_{2},...,x_{n})$$
$$df=\frac{df}{dx_{1}}dx_{1}+\frac{df}{dx_{2}}dx_{2}+...+\frac{df}{dx_{n}}dx_{n}$$
x(u,v)
$$dx=\frac{\delta x}{\delta u}\space du+\frac{\delta x}{\delta v}\space dv$$
y(u,v)
$$dy=\frac{\delta y}{\delta u}\space du+\frac{\delta y}{\delta v}\space dv$$
