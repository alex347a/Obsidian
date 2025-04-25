## Maj 2021
### Opgave 1
Bestem lineariseringen $L(x)$ omkring punktet $x = 4$:

$$
f(x) = \sqrt{x + 5}
$$

Vi beregner først $f(4)$ og $f'(x)$:

$$
f(4) = \sqrt{4 + 5} = \sqrt{9} = 3
$$

$$
f'(x) = \frac{d}{dx} \sqrt{x + 5} = \frac{1}{2\sqrt{x + 5}}
$$

$$
f'(4) = \frac{1}{2\sqrt{4 + 5}} = \frac{1}{2 \cdot 3} = \frac{1}{6}
$$

Lineariseringen er givet ved:

$$
L(x) = f(a) + f'(a)(x - a)
$$

$$
L(x) = f(4) + f'(4)(x - 4) = 3 + \frac{1}{6}(x - 4)
$$

$$
L(x) = 3 + \frac{x - 4}{6} = \frac{x}{6} + \frac{14}{6} = \frac{x}{6} + \frac{7}{3}
$$

Anvend lineariseringen $L(x)$ for at estimere værdien af $f(3)$:

$$
L(3) = \frac{3}{6} + \frac{7}{3} = \frac{1}{2} + \frac{7}{3} = \frac{3}{6} + \frac{14}{6} = \frac{17}{6}
$$

$$
f(3) \approx \frac{17}{6} \approx 2,833
$$

Estimer worst case fejlen for estimatet i b):

Fejlen kan estimeres ved at bruge den anden afledte af $f(x)$:

$$
f''(x) = \frac{d}{dx}\left(\frac{1}{2\sqrt{x + 5}}\right) = \frac{-1}{4(x + 5)^{3/2}}
$$

Maximum af $|f''(x)|$ i intervallet $[3, 4]$ findes, når $x = 3$:

$$
|f''(3)| = \frac{1}{4(3 + 5)^{3/2}} = \frac{1}{4 \cdot 8^{3/2}} = \frac{1}{4 \cdot \sqrt{64} \cdot 8} = \frac{1}{256}
$$

Worst case fejlen estimeres som:

$$
E = \frac{|f''(x)| (x - a)^2}{2}, \text{ hvor } x = 3 \text{ og } a = 4
$$

$$
E = \frac{\frac{1}{256}(3 - 4)^2}{2} = \frac{\frac{1}{256} \cdot 1}{2} = \frac{1}{512}
$$

Worst case fejlen er:

$$
E \approx 0,00195
$$
### Opgave 2
a) Bestem gradienten $\nabla f(x, y)$ i punktet $\left( \frac{\pi}{2}, 0 \right)$:

Funktionen er givet ved:

$$
f(x, y) = e^{2x + \pi y} \sin\left(\frac{1}{2} xy\right)
$$

Gradienten af $f(x, y)$ er givet ved vektoren af de partielle afledte:

$$
\nabla f(x, y) = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right)
$$

**Partielle afledte med hensyn til $x$:**

$$
\frac{\partial f}{\partial x} = \frac{\partial}{\partial x} \left( e^{2x + \pi y} \sin\left(\frac{1}{2} xy\right) \right)
$$

Anvend produktreglen:

$$
\frac{\partial f}{\partial x} = e^{2x + \pi y} \cdot \sin\left(\frac{1}{2} xy\right) \cdot 2 + e^{2x + \pi y} \cdot \cos\left(\frac{1}{2} xy\right) \cdot \frac{y}{2}
$$

**Partielle afledte med hensyn til $y$:**

$$
\frac{\partial f}{\partial y} = \frac{\partial}{\partial y} \left( e^{2x + \pi y} \sin\left(\frac{1}{2} xy\right) \right)
$$

Anvend produktreglen:

$$
\frac{\partial f}{\partial y} = e^{2x + \pi y} \cdot \sin\left(\frac{1}{2} xy\right) \cdot \pi + e^{2x + \pi y} \cdot \cos\left(\frac{1}{2} xy\right) \cdot \frac{x}{2}
$$

Så gradienten er:

$$
\nabla f(x, y) = \left( e^{2x + \pi y} \left( 2 \sin\left(\frac{1}{2} xy\right) + \frac{y}{2} \cos\left(\frac{1}{2} xy\right) \right), e^{2x + \pi y} \left( \pi \sin\left(\frac{1}{2} xy\right) + \frac{x}{2} \cos\left(\frac{1}{2} xy\right) \right) \right)
$$

Evaluering af gradienten i punktet $\left( \frac{\pi}{2}, 0 \right)$:

$$
\nabla f\left(\frac{\pi}{2}, 0\right) = \left( 0, \frac{\pi e^{\pi}}{4} \right)
$$

b) Bestem normalvektoren $n$ til overfladen $z = f(x, y)$ i punktet $\left( \frac{\pi}{2}, 0 \right)$:

Normalvektoren til overfladen $z = f(x, y)$ er givet ved gradienten af $f(x, y)$:

$$
n = \nabla f(x, y)
$$

Fra del a) ved vi, at gradienten i punktet $\left( \frac{\pi}{2}, 0 \right)$ er:

$$
n = \left( 0, \frac{\pi e^{\pi}}{4}, -1 \right)
$$

c) Bestem tangentplanens ligning i punktet $\left( \frac{\pi}{2}, 0 \right)$:

Tangentplanens ligning er givet ved:

$$
z - z_0 = \frac{\partial f}{\partial x}(x_0, y_0)(x - x_0) + \frac{\partial f}{\partial y}(x_0, y_0)(y - y_0)
$$

Hvor $(x_0, y_0) = \left( \frac{\pi}{2}, 0 \right)$ og $z_0 = f\left( \frac{\pi}{2}, 0 \right)$. Fra del a) er:

$$
f\left( \frac{\pi}{2}, 0 \right) = e^{\pi} \sin(0) = 0
$$

Så tangentplanens ligning bliver:

$$
z = \frac{\pi e^{\pi}}{4} (y - 0)
$$

Eller:

$$
z = \frac{\pi e^{\pi}}{4} y
$$


### Opgave 3
a) Betragt det komplekse tal:
$$
z = (2 + i) \cdot (5 + i) \cdot (8 + i)
$$
hvor $i$ er det komplekse tal. Beregn $|z|$ og $\arg(z)$:

Først beregner vi modulus og argument af hvert af de komplekse tal:

For $z_1 = 2 + i$, modulus $|z_1|$ er:

$$
|z_1| = \sqrt{2^2 + 1^2} = \sqrt{5}
$$

Argumentet $\arg(z_1)$ er:

$$
\arg(z_1) = \tan^{-1}\left(\frac{1}{2}\right)
$$

For $z_2 = 5 + i$, modulus $|z_2|$ er:

$$
|z_2| = \sqrt{5^2 + 1^2} = \sqrt{26}
$$

Argumentet $\arg(z_2)$ er:

$$
\arg(z_2) = \tan^{-1}\left(\frac{1}{5}\right)
$$

For $z_3 = 8 + i$, modulus $|z_3|$ er:

$$
|z_3| = \sqrt{8^2 + 1^2} = \sqrt{65}
$$

Argumentet $\arg(z_3)$ er:

$$
\arg(z_3) = \tan^{-1}\left(\frac{1}{8}\right)
$$

Nu beregner vi modulus af produktet $z$:

$$
|z| = |z_1| \cdot |z_2| \cdot |z_3| = \sqrt{5} \cdot \sqrt{26} \cdot \sqrt{65} = \sqrt{5 \cdot 26 \cdot 65} = \sqrt{8450}
$$

Argumentet af produktet er summen af argumenterne af de enkelte faktorer:

$$
\arg(z) = \arg(z_1) + \arg(z_2) + \arg(z_3)
$$

b) Betragt den komplekse ligning:
$$
\omega^4 = -256i
$$
og bestem $|\omega^4|$ og $\arg(\omega^4)$:

Modulus af $-256i$ er:

$$
| -256i | = 256
$$

Argumentet af $-256i$ er:

$$
\arg(-256i) = \frac{3\pi}{2}
$$

Så:

$$
|\omega^4| = 256, \quad \arg(\omega^4) = \frac{3\pi}{2}
$$

c) Løs den komplekse ligning fra b):

Vi kan finde løsningen ved at bruge polar form for komplekse tal. Vi har:

$$
\omega^4 = 256 e^{i3\pi/2}
$$

For at finde $\omega$, tager vi fjerde rod af begge sider:

$$
\omega = \sqrt[4]{256} e^{i\frac{3\pi}{8} + \frac{k\pi}{2}}, \quad k = 0, 1, 2, 3
$$

Så de fire løsninger er:

$$
\omega_1 = 4 e^{i3\pi/8}, \quad \omega_2 = 4 e^{i7\pi/8}, \quad \omega_3 = 4 e^{i11\pi/8}, \quad \omega_4 = 4 e^{i15\pi/8}
$$

d) Betragt de fire komplekse tal:
$$
\omega_1 = 2 e^{i3\pi/8}, \quad \omega_2 = 2 e^{-i5\pi/8}, \quad \omega_3 = 4 + 2i, \quad \omega_4 = 4 - 2i
$$
Vis hvordan punkterne kan beregnes, så de kunne afbildes i et Argand diagram:

For de komplekse tal i eksponentialform kan vi beregne deres reelle og imaginære dele ved hjælp af følgende formler:

$$
\text{Re}(\omega_1) = 2 \cos\left(\frac{3\pi}{8}\right), \quad \text{Im}(\omega_1) = 2 \sin\left(\frac{3\pi}{8}\right)
$$

$$
\text{Re}(\omega_2) = 2 \cos\left(\frac{-5\pi}{8}\right), \quad \text{Im}(\omega_2) = 2 \sin\left(\frac{-5\pi}{8}\right)
$$

For de komplekse tal i algebraisk form:

$$
\text{Re}(\omega_3) = 4, \quad \text{Im}(\omega_3) = 2
$$

$$
\text{Re}(\omega_4) = 4, \quad \text{Im}(\omega_4) = -2
$$

Disse punkter kan derefter plottes på Argand diagrammet ved at tage de reelle dele som x-koordinater og de imaginære dele som y-koordinater.

1. $\omega_1 \approx 0.7654 + 1.8478i$
2. $\omega_2 \approx -0.7654 - 1.8478i$
3. $\omega_3 = 4 + 2i$
4. $\omega_4 = 4 - 2i$

### Opgave 4
Betragt matrixen:

$$
A = \begin{pmatrix}
1 & 2 & 2 \\
0 & 1 & 1 \\
0 & 0 & 2
\end{pmatrix}
$$

### a) Beregn den anden egenværdi:

Egenværdierne findes ved at løse den karakteristiske ligning:

$$
\det(A - \lambda I) = 0
$$

Hvor $I$ er identitetsmatricen, og $\lambda$ er egenværdien.

Først beregner vi $A - \lambda I$:

$$
A - \lambda I = \begin{pmatrix}
1-\lambda & 2 & 2 \\
0 & 1-\lambda & 1 \\
0 & 0 & 2-\lambda
\end{pmatrix}
$$

Så karakteristisk determinant:

$$
\det(A - \lambda I) = \det \begin{pmatrix}
1-\lambda & 2 & 2 \\
0 & 1-\lambda & 1 \\
0 & 0 & 2-\lambda
\end{pmatrix}
$$

Da vi har en matrix i *row echelon form*, kan vi beregne determinanten ved at multiplicere diagonalelementerne:

$$
\det(A - \lambda I) = (1-\lambda) \cdot (1-\lambda) \cdot (2-\lambda)
$$

Sæt dette lig med nul:

$$
(1-\lambda)^2 \cdot (2-\lambda) = 0
$$

Dette giver de to løsninger:

1) $1-\lambda = 0 \quad \Rightarrow \quad \lambda_1 = 1$
2) $2-\lambda = 0 \quad \Rightarrow \quad \lambda_2 = 2$

Så de to egenværdier er $\lambda_1 = 1$ og $\lambda_2 = 2$.

### b) Beregn egenvektoren for $\lambda_1 = 2$:

For at finde egenvektoren til $\lambda_1 = 2$, løser vi systemet:

$$
(A - 2I) \mathbf{v} = 0
$$

Hvor $\mathbf{v}$ er egenvektoren. Først beregner vi $A - 2I$:

$$
A - 2I = \begin{pmatrix}
1-2 & 2 & 2 \\
0 & 1-2 & 1 \\
0 & 0 & 2-2
\end{pmatrix}
= \begin{pmatrix}
-1 & 2 & 2 \\
0 & -1 & 1 \\
0 & 0 & 0
\end{pmatrix}
$$

Så vi løser systemet:

$$
\begin{pmatrix}
-1 & 2 & 2 \\
0 & -1 & 1 \\
0 & 0 & 0
\end{pmatrix}
\begin{pmatrix}
v_1 \\
v_2 \\
v_3
\end{pmatrix}
= \begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$

Dette giver to ligninger:

1) $-v_1 + 2v_2 + 2v_3 = 0$
2) $-v_2 + v_3 = 0$

Fra den anden ligning får vi $v_2 = v_3$. Sæt dette ind i den første ligning:

$$
-v_1 + 2v_3 + 2v_3 = 0 \quad \Rightarrow \quad -v_1 + 4v_3 = 0 \quad \Rightarrow \quad v_1 = 4v_3
$$

Så vi får egenvektoren:

$$
\mathbf{v} = \begin{pmatrix}
4v_3 \\
v_3 \\
v_3
\end{pmatrix}
$$

Vi kan vælge $v_3 = 1$ for at få en simpel egenvektor:

$$
\mathbf{v} = \begin{pmatrix}
4 \\
1 \\
1
\end{pmatrix}
$$

Så egenvektoren for $\lambda_1 = 2$ er:

$$
\mathbf{v} = \begin{pmatrix}
4 \\
1 \\
1
\end{pmatrix}
$$


## Februar 2021
### Opgave 1
Betragt funktionen:

$$
f(x) = \sqrt{x+2}
$$

a) Bestem lineariseringen $L(x)$ omkring punktet $x=2$:

For at bestemme lineariseringen af funktionen omkring $x = 2$, bruger vi formlen for lineariseringen:

$$
L(x) = f(x_0) + f'(x_0)(x - x_0)
$$

hvor $x_0 = 2$.

Først beregner vi $f(x_0)$ og $f'(x_0)$:

1) $f(x) = \sqrt{x+2}$, så $f'(x) = \frac{1}{2\sqrt{x+2}}$.

2) Beregn $f(2)$:

$$
f(2) = \sqrt{2+2} = \sqrt{4} = 2
$$

3) Beregn $f'(2)$:

$$
f'(2) = \frac{1}{2\sqrt{2+2}} = \frac{1}{2\sqrt{4}} = \frac{1}{4}
$$

Nu kan vi skrive lineariseringen $L(x)$:

$$
L(x) = f(2) + f'(2)(x - 2) = 2 + \frac{1}{4}(x - 2)
$$

Så lineariseringen er:

$$
L(x) = 2 + \frac{1}{4}(x - 2)
$$

b) Anvend lineariseringen $L(x)$ fra a) for at estimere værdien af $f(3)=\sqrt{5}$:

For at estimere $f(3)$ bruger vi lineariseringen $L(x)$:

$$
L(3) = 2 + \frac{1}{4}(3 - 2) = 2 + \frac{1}{4} = 2.25
$$

Så estimatet for $f(3)$ ved hjælp af lineariseringen er $2.25$.

c) Estimer worst case fejlen for estimatet i b):

For at estimere worst case fejlen, bruger vi formelen for den maksimale fejl i en linearisering:

$$
|f(x) - L(x)| \leq \frac{1}{2} \cdot |f''(x)| \cdot (x - x_0)^2
$$

Vi skal først finde $f''(x)$:

1) $f(x) = \sqrt{x+2}$, så $f'(x) = \frac{1}{2\sqrt{x+2}}$.

2) Differentier $f'(x)$ for at få $f''(x)$:

$$
f''(x) = -\frac{1}{4(x+2)^{3/2}}
$$

For worst case fejlen skal vi evaluere $f''(x)$ ved $x = 3$:

$$
f''(3) = -\frac{1}{4(3+2)^{3/2}} = -\frac{1}{4(5)^{3/2}} = -\frac{1}{4 \cdot \sqrt{125}} \approx -0.028
$$

Nu kan vi estimere worst case fejlen ved at bruge $x = 3$ og $x_0 = 2$:

$$
\text{Fejl} \leq \frac{1}{2} \cdot |f''(3)| \cdot (3 - 2)^2 = \frac{1}{2} \cdot 0.028 \cdot 1^2 = 0.014
$$

Så worst case fejlen for estimatet af $f(3)$ er cirka $0.014$.

### Opgave 2

Betragt funktionen:

$$
f(x, y) = e^{x + 2y} \sin(xy)
$$

a) Bestem gradienten af $f(x, y)$ i punktet $\left( \frac{\pi}{2}, 1 \right)$:

Gradienten af en funktion $f(x, y)$ i et punkt $(x_0, y_0)$ er givet ved:

$$
\nabla f(x, y) = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right)
$$

Først bestemmer vi de partielle afledte for $f(x, y)$:

1) $\frac{\partial f}{\partial x}$:

Brug produktreglen til at differentiere:

$$
\frac{\partial f}{\partial x} = \frac{\partial}{\partial x} \left( e^{x + 2y} \sin(xy) \right)
$$

$$
\frac{\partial f}{\partial x} = e^{x + 2y} \sin(xy) + e^{x + 2y} \cdot y \cos(xy)
$$

2) $\frac{\partial f}{\partial y}$:

Brug produktreglen til at differentiere:

$$
\frac{\partial f}{\partial y} = \frac{\partial}{\partial y} \left( e^{x + 2y} \sin(xy) \right)
$$

$$
\frac{\partial f}{\partial y} = 2e^{x + 2y} \sin(xy) + e^{x + 2y} \cdot x \cos(xy)
$$

Nu evaluerer vi gradienten i punktet $\left( \frac{\pi}{2}, 1 \right)$:

1) $\frac{\partial f}{\partial x}$ i punktet $\left( \frac{\pi}{2}, 1 \right)$:

$$
\frac{\partial f}{\partial x} = e^{\frac{\pi}{2} + 2} \sin\left( \frac{\pi}{2} \cdot 1 \right) + e^{\frac{\pi}{2} + 2} \cdot 1 \cdot \cos\left( \frac{\pi}{2} \cdot 1 \right)
$$

Da $\sin\left( \frac{\pi}{2} \right) = 1$ og $\cos\left( \frac{\pi}{2} \right) = 0$, får vi:

$$
\frac{\partial f}{\partial x} = e^{\frac{\pi}{2} + 2} \cdot 1 = e^{\frac{\pi}{2} + 2}
$$

2) $\frac{\partial f}{\partial y}$ i punktet $\left( \frac{\pi}{2}, 1 \right)$:

$$
\frac{\partial f}{\partial y} = 2e^{\frac{\pi}{2} + 2} \sin\left( \frac{\pi}{2} \cdot 1 \right) + e^{\frac{\pi}{2} + 2} \cdot \frac{\pi}{2} \cos\left( \frac{\pi}{2} \cdot 1 \right)
$$

Da $\sin\left( \frac{\pi}{2} \right) = 1$ og $\cos\left( \frac{\pi}{2} \right) = 0$, får vi:

$$
\frac{\partial f}{\partial y} = 2e^{\frac{\pi}{2} + 2} \cdot 1 = 2e^{\frac{\pi}{2} + 2}
$$

Så gradienten af $f(x, y)$ i punktet $\left( \frac{\pi}{2}, 1 \right)$ er:

$$
\nabla f\left( \frac{\pi}{2}, 1 \right) = \left( e^{\frac{\pi}{2} + 2}, 2e^{\frac{\pi}{2} + 2} \right)
$$

b) Bestem normalvektoren $n$ til overfladen $z = f(x, y)$ i punktet $\left( \frac{\pi}{2}, 1 \right)$:

Normalvektoren til overfladen $z = f(x, y)$ i punktet $(x_0, y_0)$ er givet ved gradienten af $f(x, y)$ i dette punkt:

$$
n = \nabla f\left( x_0, y_0 \right)
$$

Fra a) ved vi, at gradienten i punktet $\left( \frac{\pi}{2}, 1 \right)$ er:

$$
n = \left( e^{\frac{\pi}{2} + 2}, 2e^{\frac{\pi}{2} + 2} \right)
$$

Så normalvektoren til overfladen er:

$$
n = \left( e^{\frac{\pi}{2} + 2}, 2e^{\frac{\pi}{2} + 2}, -1 \right)
$$

c) Bestem tangentplanens ligning i punktet $\left( \frac{\pi}{2}, 1 \right)$:

Tangentplanens ligning er givet ved:

$$
z - z_0 = \nabla f\left( x_0, y_0 \right) \cdot \left( x - x_0, y - y_0 \right)
$$

Hvor $(x_0, y_0, z_0)$ er punktet på overfladen, og $\nabla f\left( x_0, y_0 \right)$ er gradienten.

Først bestemmer vi $z_0 = f\left( \frac{\pi}{2}, 1 \right)$:

$$
z_0 = e^{\frac{\pi}{2} + 2} \sin\left( \frac{\pi}{2} \cdot 1 \right) = e^{\frac{\pi}{2} + 2} \cdot 1 = e^{\frac{\pi}{2} + 2}
$$

Tangentplanens ligning bliver derfor:

$$
z - e^{\frac{\pi}{2} + 2} = e^{\frac{\pi}{2} + 2} \cdot \left( x - \frac{\pi}{2} \right) + 2e^{\frac{\pi}{2} + 2} \cdot \left( y - 1 \right)
$$

Så tangentplanens ligning er:

$$
z = e^{\frac{\pi}{2} + 2} \cdot \left( x - \frac{\pi}{2} \right) + 2e^{\frac{\pi}{2} + 2} \cdot \left( y - 1 \right) + e^{\frac{\pi}{2} + 2}
$$
### Opgave 3
Betragt det komplekse tal 
$$
z = \frac{11 + 10i}{4 - i}
$$

a) Beregn $|z|$ og $\arg(z)$.

Først multipliceres tælleren og nævneren med den konjugerede værdi af nævneren:
$$
z = \frac{11 + 10i}{4 - i} \cdot \frac{4 + i}{4 + i} = \frac{(11 + 10i)(4 + i)}{(4 - i)(4 + i)}
$$
Nævneren bliver:
$$
(4 - i)(4 + i) = 4^2 + 1^2 = 16 + 1 = 17
$$
Tælleren bliver:
$$
(11 + 10i)(4 + i) = 11(4) + 11(i) + 10i(4) + 10i(i) = 44 + 11i + 40i + 10i^2
$$
Da $i^2 = -1$, får vi:
$$
44 + 11i + 40i - 10 = 34 + 51i
$$
Så 
$$
z = \frac{34 + 51i}{17} = 2 + 3i
$$

Nu kan vi beregne $|z|$ og $\arg(z)$.

Modulet af $z$ er:
$$
|z| = \sqrt{(2)^2 + (3)^2} = \sqrt{4 + 9} = \sqrt{13}
$$

Argumentet af $z$ er:
$$
\arg(z) = \tan^{-1}\left( \frac{3}{2} \right)
$$

b) Betragt den komplekse ligning 
$$
\omega^3 = 64i
$$

Først beregnes $|\omega^3|$ og $\arg(\omega^3)$.

Modulet af $64i$ er:
$$
|64i| = 64
$$
Argumentet af $64i$ er:
$$
\arg(64i) = \frac{\pi}{2}
$$

Så har vi:
$$
|\omega^3| = 64, \quad \arg(\omega^3) = \frac{\pi}{2}
$$

c) Løs den komplekse ligning fra b).

Vi har $\omega^3 = 64i$. For at finde $\omega$, tager vi den tredje rod af både modulus og argument.

Modulus af $\omega$ er:
$$
|\omega| = \sqrt[3]{64} = 4
$$

Argumentet af $\omega$ er:
$$
\arg(\omega) = \frac{\frac{\pi}{2} + 2k\pi}{3} \quad \text{for} \quad k = 0, 1, 2
$$
De tre løsninger for argumentet er:
$$
\arg(\omega) = \frac{\pi}{6}, \quad \frac{\pi}{6} + \frac{2\pi}{3} = \frac{5\pi}{6}, \quad \frac{\pi}{6} + \frac{4\pi}{3} = \frac{9\pi}{6} = \frac{3\pi}{2}
$$

Så de tre løsninger for $\omega$ er:
$$
\omega_1 = 4e^{i\frac{\pi}{6}}, \quad \omega_2 = 4e^{i\frac{5\pi}{6}}, \quad \omega_3 = 4e^{i\frac{3\pi}{2}}
$$

d) Betragt de fire komplekse tal:
$$
\omega_1 = 3 \cdot e^{i \frac{3\pi}{4}}, \quad \omega_2 = 3 \cdot e^{-i \frac{\pi}{4}}, \quad \omega_3 = 3 + i, \quad \omega_4 = 3 - i
$$

For de første to komplekse tal skal vi omforme dem til rektangulær form ved at bruge Euler's formel, hvor $e^{i\theta} = \cos(\theta) + i \sin(\theta)$.

For $\omega_1 = 3e^{i \frac{3\pi}{4}}$:
$$
\omega_1 = 3\left( \cos\left(\frac{3\pi}{4}\right) + i \sin\left(\frac{3\pi}{4}\right) \right)
$$
Ved at bruge værdierne $\cos\left(\frac{3\pi}{4}\right) = -\frac{1}{\sqrt{2}}$ og $\sin\left(\frac{3\pi}{4}\right) = \frac{1}{\sqrt{2}}$, får vi:
$$
\omega_1 = 3\left( -\frac{1}{\sqrt{2}} + i \frac{1}{\sqrt{2}} \right) = -\frac{3}{\sqrt{2}} + i \frac{3}{\sqrt{2}}
$$

For $\omega_2 = 3e^{-i \frac{\pi}{4}}$:
$$
\omega_2 = 3\left( \cos\left(-\frac{\pi}{4}\right) + i \sin\left(-\frac{\pi}{4}\right) \right)
$$
Ved at bruge værdierne $\cos\left(-\frac{\pi}{4}\right) = \frac{1}{\sqrt{2}}$ og $\sin\left(-\frac{\pi}{4}\right) = -\frac{1}{\sqrt{2}}$, får vi:
$$
\omega_2 = 3\left( \frac{1}{\sqrt{2}} - i \frac{1}{\sqrt{2}} \right) = \frac{3}{\sqrt{2}} - i \frac{3}{\sqrt{2}}
$$

De sidste to komplekse tal er allerede på rektangulær form:
$$
\omega_3 = 3 + i, \quad \omega_4 = 3 - i
$$

Så:
$$
\omega_{1}\approx -2.121+2.121 i\quad \omega_{2}\approx 2.121-2.121 i\quad \omega_3 = 3 + i, \quad \omega_4 = 3 - i
$$

### Opgave 4
Betragt en matrix
$$
A=\begin{pmatrix}1 & 2 & 2 \\ 0 & 6 & 1 \\ 0 & 0 & 2\end{pmatrix}
$$

a) Matrix $A$ har tre egenværdier. Den ene egenværdi er $\lambda_{1}=6$. Beregn de sidste to egenværdier.

For at finde egenværdierne for matrixen $A$, skal vi løse karakteristisk ligning:
$$
\det(A - \lambda I) = 0
$$
hvor $I$ er identitetsmatrixen, og $\lambda$ er egenværdien. 

Lad os først finde karakteristisk polynomium for matrixen $A$. Vi beregner $\det(A - \lambda I)$:
$$
A - \lambda I = \begin{pmatrix}1-\lambda & 2 & 2 \\ 0 & 6-\lambda & 1 \\ 0 & 0 & 2-\lambda\end{pmatrix}
$$
Bestem determinanten:
$$
\det(A - \lambda I) = (1-\lambda)\left[\det\begin{pmatrix}6-\lambda & 1 \\ 0 & 2-\lambda\end{pmatrix}\right]
$$
Først beregner vi determinanten af $2 \times 2$ matrixen:
$$
\det\begin{pmatrix}6-\lambda & 1 \\ 0 & 2-\lambda\end{pmatrix} = (6-\lambda)(2-\lambda)
$$
Så karakteristisk polynomium bliver:
$$
\det(A - \lambda I) = (1-\lambda)\left[(6-\lambda)(2-\lambda)\right]
$$
Udvid dette udtryk:
$$
(1-\lambda)\left[(6-\lambda)(2-\lambda)\right] = (1-\lambda)[12 - 8\lambda + \lambda^2]
$$
Sæt det lig med nul for at finde egenværdierne:
$$
(1-\lambda)(\lambda^2 - 8\lambda + 12) = 0
$$
Derfor har vi to faktorer:
$$
1-\lambda = 0 \quad \text{eller} \quad \lambda^2 - 8\lambda + 12 = 0
$$
Den første løsning giver:
$$
\lambda_1 = 1
$$
Nu løser vi den kvadratiske ligning:
$$
\lambda^2 - 8\lambda + 12 = 0
$$
Disse løsninger findes ved brug af kvadratsætningen:
$$
\lambda = \frac{-(-8) \pm \sqrt{(-8)^2 - 4(1)(12)}}{2(1)} = \frac{8 \pm \sqrt{64 - 48}}{2} = \frac{8 \pm \sqrt{16}}{2} = \frac{8 \pm 4}{2}
$$
Så de to løsninger er:
$$
\lambda_2 = \frac{8 + 4}{2} = 6, \quad \lambda_3 = \frac{8 - 4}{2} = 2
$$
Så de tre egenværdier for matrixen $A$ er:
$$
\lambda_1 = 6, \quad \lambda_2 = 1, \quad \lambda_3 = 2
$$

b) Beregn egenvektoren for $\lambda_1 = 6$.

For at finde egenvektoren, skal vi løse ligningen:
$$
(A - \lambda_1 I) \mathbf{v} = 0
$$
hvor $\mathbf{v}$ er egenvektoren.

Indsæt $\lambda_1 = 6$ i matrixen $A - \lambda_1 I$:
$$
A - 6I = \begin{pmatrix}1-6 & 2 & 2 \\ 0 & 6-6 & 1 \\ 0 & 0 & 2-6\end{pmatrix} = \begin{pmatrix}-5 & 2 & 2 \\ 0 & 0 & 1 \\ 0 & 0 & -4\end{pmatrix}
$$
Løs systemet:
$$
\begin{pmatrix}-5 & 2 & 2 \\ 0 & 0 & 1 \\ 0 & 0 & -4\end{pmatrix} \begin{pmatrix}v_1 \\ v_2 \\ v_3\end{pmatrix} = \begin{pmatrix}0 \\ 0 \\ 0\end{pmatrix}
$$
Første række:
$$
-5v_1 + 2v_2 + 2v_3 = 0
$$
Anden række:
$$
v_3 = 0
$$
Tredje række:
$$
-4v_3 = 0
$$
Da $v_3 = 0$, får vi:
$$
-5v_1 + 2v_2 = 0 \quad \Rightarrow \quad v_1 = \frac{2}{5}v_2
$$
Så egenvektoren er:
$$
\mathbf{v} = \begin{pmatrix}\frac{2}{5}v_2 \\ v_2 \\ 0\end{pmatrix} = v_2 \begin{pmatrix}\frac{2}{5} \\ 1 \\ 0\end{pmatrix}
$$
For en vilkårlig konstant $v_2$, er egenvektoren:
$$
\mathbf{v} = \begin{pmatrix}\frac{2}{5} \\ 1 \\ 0\end{pmatrix}
$$
Vi kunne f.eks. vælge $v_{3}=5$ for at fjerne brøken:
$$
\mathbf{v}=\begin{pmatrix}2 \\ 5 \\ 0\end{pmatrix}
$$
## Januar 2021
### Opgave 1
a) Bestem lineariseringen $L(x)$ omkring punktet $x = \frac{\pi}{4}$

Lineariseringen af en funktion $f(x)$ omkring et punkt $x = a$ er givet ved:
$$
L(x) = f(a) + f'(a)(x - a)
$$

For $f(x) = \sin(x)$, skal vi først finde $f(a)$ og $f'(a)$, hvor $a = \frac{\pi}{4}$.

1. Beregn $f(a)$:
$$
f\left(\frac{\pi}{4}\right) = \sin\left(\frac{\pi}{4}\right) = \frac{\sqrt{2}}{2}
$$

2. Beregn $f'(x)$:
$$
f'(x) = \cos(x)
$$
Så
$$
f'\left(\frac{\pi}{4}\right) = \cos\left(\frac{\pi}{4}\right) = \frac{\sqrt{2}}{2}
$$

Nu kan vi skrive lineariseringen $L(x)$:
$$
L(x) = \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2}\left(x - \frac{\pi}{4}\right)
$$

b) Anvend lineariseringen $L(x)$ fra a) for at estimere værdien af $\sin(46^\circ)$

Først konverterer vi $46^\circ$ til radianer:
$$
46^\circ = \frac{46\pi}{180} = \frac{23\pi}{90} \approx 0.402 \, \text{radianer}
$$

Nu bruger vi lineariseringen $L(x)$ til at estimere værdien af $\sin(46^\circ)$.

$$
L(0.402) = \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2}\left(0.402 - \frac{\pi}{4}\right)
$$
Da $\frac{\pi}{4} \approx 0.785$:
$$
L(0.402) = \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2}(0.402 - 0.785)
$$
$$
L(0.402) = \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2}(-0.383)
$$
$$
L(0.402) \approx \frac{\sqrt{2}}{2}(1 - 0.383) \approx \frac{\sqrt{2}}{2}(0.617)
$$
$$
L(0.402) \approx 0.436
$$

Så den estimerede værdi af $\sin(46^\circ)$ ved hjælp af lineariseringen er ca. 0.436.

c) Estimer worst-case fejlen for estimatet i b)

For at estimere worst-case fejlen, bruger vi den næste afledte værdi af funktionen. Hvis $f''(x)$ er den anden afledte af $f(x)$, så er worst-case fejlen i lineariseringen givet ved:
$$
\text{Fejl} \approx \frac{1}{2} |f''(c)| (x - a)^2
$$
hvor $c$ er et punkt mellem $x$ og $a$.

1. Beregn $f''(x)$:
$$
f''(x) = -\sin(x)
$$

Så $|f''(x)|$ er maksimalt, når $|\sin(x)|$ er størst, hvilket er 1. Derfor:
$$
|f''(x)| \leq 1
$$

2. Beregn fejlen:
$$
\text{Fejl} \approx \frac{1}{2} (x - a)^2
$$
hvor $x = 0.402$ og $a = \frac{\pi}{4} \approx 0.785$.

Så
$$
\text{Fejl} \approx \frac{1}{2} (0.402 - 0.785)^2 = \frac{1}{2} (-0.383)^2
$$
$$
\text{Fejl} \approx \frac{1}{2} (0.146) \approx 0.073
$$

Så worst-case fejlen for estimatet af $\sin(46^\circ)$ er cirka 0.073.
### Opgave 2
Betragt funktionen
$$
f(x, y) = e^{x+y} \cos(xy)
$$

a) Bestem gradienten af $f(x, y)$ i punktet $\left(\frac{\pi}{2}, 0\right)$

Gradienten af en funktion $f(x, y)$ er vektoren af de partielle afledte med hensyn til $x$ og $y$. Altså:
$$
\nabla f(x, y) = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right)
$$

Først beregner vi de partielle afledte:

1. **Partiel afledning med hensyn til $x$:**
$$
\frac{\partial f}{\partial x} = \frac{\partial}{\partial x}\left( e^{x+y} \cos(xy) \right)
$$
Brug produktreglen:
$$
\frac{\partial f}{\partial x} = e^{x+y} \cdot (-y\sin(xy)) + e^{x+y} \cdot \cos(xy)
$$
$$
\frac{\partial f}{\partial x} = e^{x+y} \left( \cos(xy) - y\sin(xy) \right)
$$

2. **Partiel afledning med hensyn til $y$:**
$$
\frac{\partial f}{\partial y} = \frac{\partial}{\partial y}\left( e^{x+y} \cos(xy) \right)
$$
Brug produktreglen:
$$
\frac{\partial f}{\partial y} = e^{x+y} \cdot \cos(xy) + e^{x+y} \cdot (-x\sin(xy))
$$
$$
\frac{\partial f}{\partial y} = e^{x+y} \left( \cos(xy) - x\sin(xy) \right)
$$

Nu evaluerer vi gradienten i punktet $\left(\frac{\pi}{2}, 0\right)$:

1. **Evaluering af $\frac{\partial f}{\partial x}$ i punktet $\left(\frac{\pi}{2}, 0\right)$:**
$$
\frac{\partial f}{\partial x} \Big|_{\left(\frac{\pi}{2}, 0\right)} = e^{\frac{\pi}{2}+0} \left( \cos\left(\frac{\pi}{2} \cdot 0\right) - 0 \cdot \sin\left(\frac{\pi}{2} \cdot 0\right) \right)
$$
$$
\frac{\partial f}{\partial x} \Big|_{\left(\frac{\pi}{2}, 0\right)} = e^{\frac{\pi}{2}} \cdot 1 = e^{\frac{\pi}{2}}
$$

2. **Evaluering af $\frac{\partial f}{\partial y}$ i punktet $\left(\frac{\pi}{2}, 0\right)$:**
$$
\frac{\partial f}{\partial y} \Big|_{\left(\frac{\pi}{2}, 0\right)} = e^{\frac{\pi}{2}+0} \left( \cos\left(\frac{\pi}{2} \cdot 0\right) - \frac{\pi}{2} \cdot \sin\left(\frac{\pi}{2} \cdot 0\right) \right)
$$
$$
\frac{\partial f}{\partial y} \Big|_{\left(\frac{\pi}{2}, 0\right)} = e^{\frac{\pi}{2}} \cdot 1 = e^{\frac{\pi}{2}}
$$

Derfor er gradienten i punktet $\left(\frac{\pi}{2}, 0\right)$:
$$
\nabla f\left(\frac{\pi}{2}, 0\right) = \left( e^{\frac{\pi}{2}}, e^{\frac{\pi}{2}} \right)
$$

b) Bestem normalvektoren $n$ til overfladen $z=f(x, y)$ i punktet $\left(\frac{\pi}{2}, 0\right)$

Normalvektoren $n$ til overfladen $z = f(x, y)$ i et punkt er givet ved gradienten af $f(x, y)$ i dette punkt, da gradienten er normal på overfladen. Så normalvektoren er:
$$
n = \nabla f\left(\frac{\pi}{2}, 0\right) = \left( e^{\frac{\pi}{2}}, e^{\frac{\pi}{2}}, -1 \right)
$$

c) Bestem tangentplanets ligning i punktet $\left(\frac{\pi}{2}, 0\right)$

Tangentplanet til overfladen $z = f(x, y)$ i punktet $(x_0, y_0)$ er givet ved:
$$
z - z_0 = \frac{\partial f}{\partial x} \Big|_{(x_0, y_0)}(x - x_0) + \frac{\partial f}{\partial y} \Big|_{(x_0, y_0)}(y - y_0)
$$

Hvor $(x_0, y_0) = \left(\frac{\pi}{2}, 0\right)$ og $z_0 = f\left(\frac{\pi}{2}, 0\right)$.

Først beregn $z_0$:
$$
z_0 = f\left(\frac{\pi}{2}, 0\right) = e^{\frac{\pi}{2} + 0} \cos\left(\frac{\pi}{2} \cdot 0\right) = e^{\frac{\pi}{2}} \cdot 1 = e^{\frac{\pi}{2}}
$$

Så tangentplanet er:
$$
z - e^{\frac{\pi}{2}} = e^{\frac{\pi}{2}}\left( x - \frac{\pi}{2} \right) + e^{\frac{\pi}{2}}(y - 0)
$$
$$
z - e^{\frac{\pi}{2}} = e^{\frac{\pi}{2}} \left( x - \frac{\pi}{2} + y \right)
$$

Endelig bliver ligningen for tangentplanet:
$$
z = e^{\frac{\pi}{2}} \left( x - \frac{\pi}{2} + y \right) + e^{\frac{\pi}{2}}
$$
### Opgave 3
Betragt det komplekse tal 
$$
z = 2e^{\left(i \frac{\pi}{2}\right)}(1 + i)
$$

a) Beregn $|z|$ og $\arg(z)$

For at beregne $|z|$ (modul) og $\arg(z)$ (argument) for det komplekse tal, bruger vi de følgende regler:

1. **Modul $|z|$:**
$$
|z| = |2e^{i \frac{\pi}{2}}| \cdot |1 + i|
$$
Hvor $|1 + i|$ kan findes som:
$$
|1 + i| = \sqrt{1^2 + 1^2} = \sqrt{2}
$$
Og $|2e^{i \frac{\pi}{2}}| = 2$, da modulus af et komplekst tal i eksponentialform $e^{i \theta}$ er 1, og konstanten 2 giver $|2e^{i \frac{\pi}{2}}| = 2$.

Så:
$$
|z| = 2 \cdot \sqrt{2} = 2\sqrt{2}
$$

2. **Argument $\arg(z)$:**
Argumentet af $z$ er summen af argumentet af $2e^{i \frac{\pi}{2}}$ og argumentet af $(1 + i)$. 

- Argumentet af $2e^{i \frac{\pi}{2}}$ er $\frac{\pi}{2}$.
- Argumentet af $1 + i$ er $\arg(1 + i) = \frac{\pi}{4}$, da det er et tal på linjen $y=x$ i første kvadrant.

Derfor er argumentet af $z$:
$$
\arg(z) = \frac{\pi}{2} + \frac{\pi}{4} = \frac{3\pi}{4}
$$

Så:
$$
|z| = 2\sqrt{2}, \quad \arg(z) = \frac{3\pi}{4}
$$

b) Betragt den komplekse ligning
$$
\omega^{3} = 8i
$$
og bestem $|\omega^{3}|$ og $\arg(\omega^{3})$

1. **Modul $|\omega^3|$:**
Modul af et komplekst tal i eksponentialform $r e^{i \theta}$ er $r$. For $8i$, som er på imaginæraksen, er modulus:
$$
|8i| = 8
$$
Så:
$$
|\omega^3| = 8
$$

2. **Argument $\arg(\omega^3)$:**
Argumentet af $8i$ er $\frac{\pi}{2}$, da det er på den positive imaginære akse. Så:
$$
\arg(\omega^3) = \frac{\pi}{2}
$$

c) Løs den komplekse ligning fra b)

For at løse ligningen $\omega^3 = 8i$, finder vi først de tredje rødder af $8i$.

Løsningen $\omega$ kan findes ved at tage den komplekse tredje rod af $8i$ i polær form. Vi skriver $8i$ som:
$$
8i = 8 e^{i \frac{\pi}{2}}
$$
Så de tredje rødder af $8i$ er:
$$
\omega = \sqrt[3]{8} e^{i \left( \frac{\frac{\pi}{2} + 2k\pi}{3} \right)}, \quad k = 0, 1, 2
$$
Hvor $\sqrt[3]{8} = 2$, og vi beregner de tre løsninger ved at sætte $k = 0, 1, 2$:

1. For $k = 0$:
$$
\omega_0 = 2 e^{i \frac{\pi}{6}}
$$

2. For $k = 1$:
$$
\omega_1 = 2 e^{i \frac{\pi}{2}}
$$

3. For $k = 2$:
$$
\omega_2 = 2 e^{i \frac{5\pi}{6}}
$$

Så de tre løsninger er:
$$
\omega_0 = 2 e^{i \frac{\pi}{6}}, \quad \omega_1 = 2 e^{i \frac{\pi}{2}}, \quad \omega_2 = 2 e^{i \frac{5\pi}{6}}
$$

d) En anden kompleks ligning har løsningerne:
$$
z_1 = 2 \cdot e^{i \frac{2\pi}{6}}, \quad z_2 = 2 \cdot e^{i \frac{5\pi}{6}}, \quad z_3 = 2 \cdot e^{-i \frac{\pi}{6}}, \quad z_4 = 2 \cdot e^{-i \frac{4\pi}{6}}
$$

For at finde disse punkter i rektangulær form (dvs. i form af $a + bi$, hvor $a$ og $b$ er reelle tal), bruger vi Euler's formel:
$$
e^{i\theta} = \cos(\theta) + i \sin(\theta)
$$

**For $z_1 = 2 \cdot e^{i \frac{2\pi}{6}}$:**

1. Beregn argumentet:
$$
\frac{2\pi}{6} = \frac{\pi}{3}
$$

2. Anvend Euler's formel:
$$
z_1 = 2 \left( \cos\left(\frac{\pi}{3}\right) + i \sin\left(\frac{\pi}{3}\right) \right)
$$

3. Værdierne for $\cos\left(\frac{\pi}{3}\right)$ og $\sin\left(\frac{\pi}{3}\right)$ er henholdsvis $\frac{1}{2}$ og $\frac{\sqrt{3}}{2}$:
$$
z_1 = 2 \left( \frac{1}{2} + i \frac{\sqrt{3}}{2} \right) = 1 + i\sqrt{3}
$$

**For $z_2 = 2 \cdot e^{i \frac{5\pi}{6}}$:**

1. Beregn argumentet:
$$
\frac{5\pi}{6}
$$

2. Anvend Euler's formel:
$$
z_2 = 2 \left( \cos\left(\frac{5\pi}{6}\right) + i \sin\left(\frac{5\pi}{6}\right) \right)
$$

3. Værdierne for $\cos\left(\frac{5\pi}{6}\right)$ og $\sin\left(\frac{5\pi}{6}\right)$ er henholdsvis $-\frac{\sqrt{3}}{2}$ og $\frac{1}{2}$:
$$
z_2 = 2 \left( -\frac{\sqrt{3}}{2} + i \frac{1}{2} \right) = -\sqrt{3} + i
$$

**For $z_3 = 2 \cdot e^{-i \frac{\pi}{6}}$:**

1. Beregn argumentet:
$$
-\frac{\pi}{6}
$$

2. Anvend Euler's formel:
$$
z_3 = 2 \left( \cos\left(-\frac{\pi}{6}\right) + i \sin\left(-\frac{\pi}{6}\right) \right)
$$

3. Værdierne for $\cos\left(-\frac{\pi}{6}\right)$ og $\sin\left(-\frac{\pi}{6}\right)$ er henholdsvis $\frac{\sqrt{3}}{2}$ og $-\frac{1}{2}$:
$$
z_3 = 2 \left( \frac{\sqrt{3}}{2} - i \frac{1}{2} \right) = \sqrt{3} - i
$$

**For $z_4 = 2 \cdot e^{-i \frac{4\pi}{6}}$:**

1. Beregn argumentet:
$$
-\frac{4\pi}{6} = -\frac{2\pi}{3}
$$

2. Anvend Euler's formel:
$$
z_4 = 2 \left( \cos\left(-\frac{2\pi}{3}\right) + i \sin\left(-\frac{2\pi}{3}\right) \right)
$$

3. Værdierne for $\cos\left(-\frac{2\pi}{3}\right)$ og $\sin\left(-\frac{2\pi}{3}\right)$ er henholdsvis $-\frac{1}{2}$ og $-\frac{\sqrt{3}}{2}$:
$$
z_4 = 2 \left( -\frac{1}{2} - i \frac{\sqrt{3}}{2} \right) = -1 - i\sqrt{3}
$$

**Så de komplekse løsninger i rektangulær form er:**

- $z_1 = 1 + i\sqrt{3}$
- $z_2 = -\sqrt{3} + i$
- $z_3 = \sqrt{3} - i$
- $z_4 = -1 - i\sqrt{3}$

### Opgave 4
Se xournal++ opgaven
