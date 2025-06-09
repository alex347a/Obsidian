Givet en periodisk funktion:
![[Mat 3 02 Lektion.pdf#page=1]]

Kan beskrives vha sinusser og cosinusser
Funktionerne er ikke differentiable fordi de enten har knæk eller lodrette linjer 

Men hvis de laves om til en fouierrække, så er de differentiable.

## Fouierrække:
$$
f(x)=a_{0}+\sum^{\infty}_{n \, = \,  1}(a_{n}\cos(x)+b_{n}\sin(x))
$$
### Euler:
Man kan både tage fra $-\pi$ til $\pi$ eller fra $0$ til $2\pi$, det er ligegyldigt, så længe man tager en hel periode.
$$
\begin{align*}
a_{0} &=  \frac{1}{2\pi}\int_{-\pi}^{\pi} f(x) \, dx\\
a_{n}&= \frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \, \cos(x) \, dx\\
b_{n}&= \frac{1}{\pi} \int_{-\pi}^{\pi}f(x) \, \sin(x) \, dx
\end{align*}
$$
For alle n:
$$
\begin{align*}
a_0 &= \frac{1}{2\pi} \int_{-\pi}^{\pi} f(x) \, dx \\
a_n &= \frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \cos(n x) \, dx \\
b_n &= \frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \sin(n x) \, dx
\end{align*}
$$
### Eksempel:
![[Mat 3 02 Lektion.pdf#page=2]]

$$
a_{0}=\frac{1}{2\pi} \int_{-\pi}^{\pi} f(x) \, dx=0
$$
Arealet er 0, fordi arealet under x-aksen er nøjagtigt lige så stort som arealet over x-aksen.

$$
a_{n} = \frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \cos(nx) \, dx
$$
I dette tilfælde:
$$
\begin{align*}
&= \frac{1}{\pi} \int_{-\pi} ^{0}(-1) \cos(nx) \, dx + \frac{1}{\pi}\int_{0}^{\pi}1 \cdot \cos(nx) \, dx\\
&= \frac{1}{\pi} \left[\frac{-1}{n}\sin(nx)\right]_{-\pi}^{0}+\frac{1}{\pi} \left[\frac{1}{n}\sin(nx)\right]_{0}^{\pi}\\
&= \frac{1}{\pi \, n}(0-(-\sin(-\pi \, n)))+ \frac{1}{\pi \, n} (\sin(\pi \, n)-0)\\
&= 0
\end{align*}
$$
$$
b_{n}=\frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \sin(nx) \, dx
$$
I dette tilfælde:
$$
\begin{align*}
&= \frac{1}{\pi} \int_{-\pi}^{0}(-1) \cdot \sin(nx) \, dx + \frac{1}{\pi} \int_{0}^{\pi}(1) \cdot \sin(nx) \, dx\\
&= \frac{1}{\pi}\left[-\frac{1}{n}\cos(nx)\right]_{-\pi}^{0} + \frac{1}{\pi} \left[\frac{1}{n} \cos(nx)\right]_{0}^{\pi}\\
&= \frac{1}{\pi \, n} (1- \cos(- \pi \, n)) + \frac{1}{\pi \, n} (1 -\cos(\pi \, n))
\end{align*}
$$
Hvis man tegner enhedscirklen så har cos den samme værdi uanset om den er positiv eller negativ, hvis vinklen er den samme.

$$
\frac{1}{ \pi \, n} (1- \cos(\pi \, n) - \cos(\pi \, n)+1) = \frac{2}{\pi \, n} (1-\cos(\pi \, n))
$$
$n=1$:
$$
\frac{2}{\pi } (1-\cos(\pi))=\frac{4}{\pi}
$$
$n=2$:
$$
\frac{2}{2\pi } (1-\cos(2\pi))=0
$$
$n=3$:
$$
\frac{2}{3\pi } (1-\cos(3\pi))=\frac{4}{3\pi}
$$
$n=4$:
$$
\frac{2}{4\pi } (1-\cos(4\pi))=0
$$

$$
\cases{0, & \text{når n er lige} \\ \frac{4}{\pi \, n}, & \text{når n er ulige}}
$$
$f(x)= \frac{4}{\pi} \left(\sin(x) + \frac{1}{3} \sin\left(3x\right) + \frac{1}{5} \sin(5x) + \dots\right)$ 

$$f\left(\frac{\pi}{2}\right)= 1 = \frac{4}{\pi}\left(1- \frac{1}{3}+ \frac{1}{5}- \frac{1}{7}+\dots\right)$$

Men det er ikke alle funktioner der har en periode på $2\pi$.

$$
\begin{align*}
f(x)&= a_{0} + \sum^{\infty}_{n \, = \, 1} \left(a \cos\left(\frac{\pi \, n}{L}x\right) + b_{n}  \sin\left(\frac{\pi \, n}{L}x\right)\right)\\
a_{0}&=  \frac{1}{2L} \int_{-L}^{L}f(x) \, dx\\
a_{n}&= \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{\pi \, n}{L}x\right) \, dx\\
b_{n}&= \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{\pi \, n}{L}x\right) \, dx
\end{align*}
$$

## Lige og ulige funktioner
Lige funktion (at funktionen opfører sig på samme måde uanset om man går den ene eller anden vej ad x-aksen):
$$
f(-x)=f(x)
$$
Hvis funktionen er lige, så gælder det at:
$$
b_{n}=0
$$
Ulige funktion (at x-aksen spejler funktionen, forestil dig sinus):
$$
-f(-x)=f(x)
$$
Hvis funktionen er ulige, så gælder det at:
$$
\begin{align*}
a_{n}&= 0\\
a_{0}&= 0
\end{align*}
$$
## Fouiertrick
Hvis man har en funktion, hvor man har L givet, men man kun har fået en lille del af grafen i første kvadrant, så kan man forestille sig at funktionen er en ulige fouierrække, fordi så slipper man for at beregne $a_{n}$ og $a_{0}$

## Gibbs fænomenet
Uanset hvor mange led man tager i fouierrækken så vil man altid løbe ind i at der kommer støj på linjen.

$$
\begin{align*}
2\pi f=\omega\\
\omega = \frac{\pi \, n}{L} 
\end{align*}
$$
## Forced oscillations
eksempel
$$
y''+0.05y'+25y =
$$
![[Mat 3 02 Lektion.pdf#page=3]]

$$
y''+0.05y'+25 y = \sum^{\infty}_{n\,= \, 1} \frac{4}{\pi \, n^{2}} \cos(\pi \, n)
$$
Partikulær løsning
for n:

$$
y_{p}=A_{n}\cos(x \, n) + B_{n}\sin(x \, n)
$$
$$
y' = -nA_{n}\sin(x \, n)+n B_{n}\cos(x \, n)
$$
$$
y''=-n^{2}A_{n}\cos(x \, n) - n^{2}B_{n}\sin(x \, n)
$$
Substituer:
$$
-n^{2} A_{n}\cos(x \, n) - n^{2}B_{n}\sin(x \, n) + 0.05 (-nA_{n}\sin(x \, n) + nB_{n} \cos(x \, n)) + 25 (A_{n}\cos(x \, n) +B_{n}\sin(x \, n))
$$
$$
= \frac{4}{\pi \, n^{2}} \cos(x \, n) 
$$

$\cos(x \, n)$:  
$$
-n^{2}A_{n}+0.05 nB_{n}+25A_{n}= \frac{4}{\pi \, n}
$$
$\sin(x \, n)$:
$$
-n^{2}A_{n}-0.05 nA_{n}+25B_{n}= 0
$$

To ligninger med to ubekendte:
$$
\cases{(25-n^{2}) A_{n}+ 0.05 B_{n}= \frac{4}{\pi \, n} \\\\ -0.05 A_{n}+(25-n^{2})B_{n}=0}
$$

## Kramers metode (Cramer's method):
Niels bruger Cramers metode:
$$
A_{n}= \begin{pmatrix}\frac{4}{\pi \, n^{2}} & 0.05 n \\ 0 & 25-n^{2} \\ ---- & ----- \\ 25-n^{2} & 0.05 n \\ -0.05 n & 25-n^{2}\end{pmatrix}=\frac{\frac{4}{\pi \, n^{2}} (25-n^{2}) }{(25-n^{2})^{2}+0.05^{2}n^{2}} 
$$

$$
B_{n}= \begin{pmatrix}25-n^{2} & \frac{4}{\pi \, n^{2}} \\ -0.05 n & 0 \\ --- & --- \\ D_{n}\end{pmatrix}= \frac{0.05 \cdot \frac{4}{\pi \, n^{2}}}{(25-n^{2})^{2}+0.05n^{2}}
$$
### Hvordan virker kramers metode? 
Kramers' metode er en matematisk metode til at løse lineære ligningssystemer ved hjælp af determinanter. Metoden bruges især, når man har et kvadratisk system af $n$ lineære ligninger med $n$ ukendte.

---

#### Opskriv ligningssystemet

Kramers' regel gælder for et system af $n$ lineære ligninger med $n$ ukendte på formen:

$$
A \mathbf{x} = \mathbf{b}
$$

hvor:
- $A$ er en $n \times n$ koefficientmatrix
- $\mathbf{x} = (x_1, x_2, \dots, x_n)^T$ er vektoren af ukendte
- $\mathbf{b} = (b_1, b_2, \dots, b_n)^T$ er højresidevektoren

Eksempel med 2 ligninger og 2 ukendte:

$$
\begin{aligned}
a_{11} x_1 + a_{12} x_2 &= b_1 \\
a_{21} x_1 + a_{22} x_2 &= b_2
\end{aligned}
$$

Den tilsvarende matrixform er:

$$
\begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix}
\begin{bmatrix} x_1 \\ x_2 \end{bmatrix} =
\begin{bmatrix} b_1 \\ b_2 \end{bmatrix}
$$

---

#### Beregn determinanten af $A$

For at bruge Kramers' metode skal vi finde determinanten af koefficientmatricen $A$:

$$
D = \det(A)
$$

For $n = 2$:

$$
D = \begin{vmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{vmatrix} = a_{11}a_{22} - a_{12}a_{21}
$$

For $n = 3$:

$$
D = \begin{vmatrix} 
a_{11} & a_{12} & a_{13} \\ 
a_{21} & a_{22} & a_{23} \\ 
a_{31} & a_{32} & a_{33} 
\end{vmatrix}
$$

Hvis $D = 0$, kan Kramers' metode **ikke anvendes**, fordi systemet enten har uendelig mange løsninger eller ingen løsninger.

---

#### Konstruer matrix $A_i$ for hver ukendt $x_i$

For hver ukendt $x_i$, dannes en ny matrix $A_i$, hvor den $i$-te søjle i $A$ erstattes med højresidevektoren $\mathbf{b}$.

Eksempel for $x_1$ i et 2×2 system:

$$
A_1 = 
\begin{bmatrix} b_1 & a_{12} \\ b_2 & a_{22} \end{bmatrix}
$$

Og for $x_2$:

$$
A_2 = 
\begin{bmatrix} a_{11} & b_1 \\ a_{21} & b_2 \end{bmatrix}
$$

---

#### Beregn determinanterne af $A_i$

Hver determinant $D_i$ findes som:

$$
D_i = \det(A_i)
$$

Eksempel for $x_1$:

$$
D_1 = \begin{vmatrix} b_1 & a_{12} \\ b_2 & a_{22} \end{vmatrix} = b_1 a_{22} - a_{12} b_2
$$

Og for $x_2$:

$$
D_2 = \begin{vmatrix} a_{11} & b_1 \\ a_{21} & b_2 \end{vmatrix} = a_{11} b_2 - b_1 a_{21}
$$

---

#### Beregn løsningerne

Løsningerne findes ved:

$$
x_i = \frac{D_i}{D}, \quad \text{for } i = 1, 2, \dots, n
$$

For $n = 2$:

$$
x_1 = \frac{D_1}{D}, \quad x_2 = \frac{D_2}{D}
$$

---

#### Tal-eksempel

Løs følgende system:

$$
\begin{aligned}
2x_1 + 3x_2 &= 5 \\
4x_1 + x_2 &= 6
\end{aligned}
$$

#### Opskriv matricen

$$
A =
\begin{bmatrix} 2 & 3 \\ 4 & 1 \end{bmatrix}, \quad 
\mathbf{b} =
\begin{bmatrix} 5 \\ 6 \end{bmatrix}
$$

#### Beregn $D$

$$
D = \begin{vmatrix} 2 & 3 \\ 4 & 1 \end{vmatrix} = (2 \cdot 1) - (4 \cdot 3) = 2 - 12 = -10
$$

#### Konstruer $A_1$ og $A_2$

$$
A_1 = 
\begin{bmatrix} 5 & 3 \\ 6 & 1 \end{bmatrix}, \quad
A_2 = 
\begin{bmatrix} 2 & 5 \\ 4 & 6 \end{bmatrix}
$$

#### Beregn $D_1$ og $D_2$

$$
D_1 = \begin{vmatrix} 5 & 3 \\ 6 & 1 \end{vmatrix} = (5 \cdot 1) - (3 \cdot 6) = 5 - 18 = -13
$$

$$
D_2 = \begin{vmatrix} 2 & 5 \\ 4 & 6 \end{vmatrix} = (2 \cdot 6) - (5 \cdot 4) = 12 - 20 = -8
$$

#### Beregn løsningerne

$$
x_1 = \frac{D_1}{D} = \frac{-13}{-10} = 1.3
$$

$$
x_2 = \frac{D_2}{D} = \frac{-8}{-10} = 0.8
$$

Løsningen er:
$$
x_1 = 1.3, \quad x_2 = 0.8
$$

---

#### Fordele og ulemper ved Kramers' metode
Fordele:
- Let at bruge for små systemer
Ulemper:
- Kan ikke bruges, hvis $D = 0$.

Hvis man har et stort system, er Gauss elimination ofte mere praktisk.