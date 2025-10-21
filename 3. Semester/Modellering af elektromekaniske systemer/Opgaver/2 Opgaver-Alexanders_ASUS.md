### Opgave 1 
Betragt et masse-fjeder-dæmper system beskrevet ved
$$
m \ddot{x} = - kx - b \dot{x} + f 
$$
Opskriv en overføringsfunktion $G(s)$ for systemet med input $f$ og output $x$

Jeg kan finde overføringsfunktionen som:
$$
G(s) = \frac{X(s)}{F(s)}
$$
Jeg skal her først laplace transformeret ligningen:
$$
s^{2}mX(s)=-kX(s) -sbX(s) + F(s)
$$
Dette kan så omskrives til:
$$\begin{align*}
s^{2}mX(s) + sbX(s) + kX(s) &= F(s)\\
X(s) \cdot(s^{2}m+sb+k) &=  F(s)\\
\frac {X(s)} {F(s)} &= \frac {1} {ms^{2}+bs+ k}
\end{align*}$$
### Opgave 2 udføres i MatLab.
$k = \frac{1}{100}$
![[Opgave 2 del 1.png]]
![[Opgave 2 del 2.png]]

### Opgave 3 
Skriv et udtryk for udgangssignalet $x(t)$ for systemet, hvis indgangssignalet er $f(t) = 2 sin(5t)$. Benyt stivhed $k = 0;1 \frac{N}{m}$.

Her omskrives ligningen ovenfra til at være:
$$\begin{align*}
G(s)&= \frac{X(s)}{F(s)}\\
G(s) \cdot F(s)&= X(s)
\end{align*}$$
Først Laplace transformerer jeg $2sin(5t)$:
$$F(s) = \mathscr{L}(f)=2 \cdot \frac {5} {s^{2}+25}= \frac {10} {s^{2}+25}$$
Dette kan så indsættes:
$$\begin{align*}
\frac {1} {ms^{2}+bs+k} \cdot \frac {10} {s^{2}+25} &=  X(s)\\
\frac {10} {(ms^{2}+bs+k)(s^{2}+25)} &=  X(s)\\
\end{align*}$$
Her finder man så de 4 rødder hvor
$$\begin{align*}
p_{1}&= \frac {-b + \sqrt{b^{2}-4mk}} {2m}\\
p_{2}&= \frac {-b - \sqrt{b^{2}-4mk}} {2m}\\
p_{3}&= -5j\\
p_{4}&= 5j
\end{align*}$$
Hvis der så indsættes værdierne:
$$\begin{align*}
p_{1}&= \frac {-0.2 + \sqrt{0.04-0.4}} {2} &= -0.1 + 0.3j\\
p_{2}&= \frac {-0.2 - \sqrt{0.04-0.4}} {2} &= -0.1 - 0.3j\\
\end{align*}$$

Her indsætter jeg så værdierne for m, b og k, hvilket var $m = 1, b = 0.2, k = 0.1$
$$\frac {10} {(s^{2}+0.2s+0.1)(s^{2}+25)} =  X(s)$$
Her skriver jeg så brøken om:
$$X(s) = \frac {10} {(s^{2}+0.2s+0.1)(s^{2}+25)} = \frac {A} {s-p_{1}} + \frac {B} {s-p_{2}} + \frac {C} {s-p_{3}} + \frac {D} {s-p_{4}}$$
Her ganges der så fx med $s-p_{1}$ og der gås derved:
$$X(s) \cdot (s-p_{1}) = A + \frac {B (s- p_{1})} {s-p_{2}}+ \frac {C (s- p_{1})} {s-p_{3}}+ \frac {D (s- p_{1})} {s-p_{4}}$$
her venstre siden kan så skrives ud:
$$\frac {10 (s-p_{1})} {(s-(-0.1+0.3j)) \cdot (s-(-0.1 - 0.3j)) \cdot (s+5j) \cdot (s - 5j)} = A + \frac {B (s- p_{1})} {s-p_{2}}+ \frac {C (s- p_{1})} {s-p_{3}}+ \frac {D (s- p_{1})} {s-p_{4}}$$
Her er det skrevet ud med rødderne.

Hvis jeg så indsætter den først rod ind på s sådan at $s = p_{1}$ bliver alle led på højre side 0 ud over A og på venstre siden går det ud med et led i nævneren:
$$\begin{align*}
\frac {10 ((-0.1+0.3j)-(-0.1+0.3j))} {((-0.1+0.3j)-(-0.1+0.3j)) \cdot \cancel{((-0.1+0.3j)-(-0.1 - 0.3j))} \cdot ((-0.1+0.3j)+5j) \cdot ((-0.1+0.3j) - 5j)} &=  A\\
\end{align*}$$
(man skal scrolle for at se det hele)
Her går et led i tælleren og nævneren ud:
$$\frac {10} {((-0.1+0.3j)-(-0.1 - 0.3j)) \cdot ((-0.1+0.3j)+5j) \cdot ((-0.1+0.3j) - 5j)} =  A$$
Jeg kan nu udregne A
$$\begin{align*}
\frac {10} {((-0.1+0.3j)-(-0.1 - 0.3j)) \cdot ((-0.1+0.3j)+5j) \cdot ((-0.1+0.3j) - 5j)} &=   A\\
\frac {10} {(-0.1+0.3j+0.1 + 0.3j) \cdot (-0.1+0.3j+5j) \cdot (-0.1+0.3j - 5j)} &=   A\\
\frac {10} {0.6j \cdot (-0.1+5.3j) \cdot (-0.1-4.7j)} &=   A\\
\frac {10} {(-3.18-0.06j) \cdot (-0.1-4.7j)} &=   A\\
\frac {10} {0.318+14.946j +0.006j-0.282} &=   A\\
\frac {10} {0,036+14.952j} &=   A\\
 0.0016 - 0.6688j &=   A\\
\end{align*}$$
På denne måde har jeg regnet A og det samme gøres så for de resterende
$$\begin{align*}
A &=  0.0016 - 0.6688j\\
B &= 0.0016+0.6688j\\
C &= -0.0016-0.0401 j\\
D &= -0.0016+0.0401 j
\end{align*}$$
Jeg kan derved skrive vores svar op som være:

$$X(s) = \frac {0.0016 - 0.6688j} {s-(-0.1 + 0.3j)} + \frac {0.0016+0.6688j} {s-(-0.1 - 0.3j)} + \frac {-0.0016-0.0401 j} {s-(-5j)} + \frac {-0.0016+0.0401 j} {s-(5j)}$$
For at gøre det simpelt bruges her igen bare A B C og D
$$x(t) = A \cdot e^{(-0.1 + 0.3j)t} + B \cdot e^{(-0.1 - 0.3j)t} + C \cdot e^{-5jt}+ D \cdot e^{5jt}$$
Her kan jeg så faktorisere $e^{-0.1t}$ i de 2 første led
$$x(t) =e^{-0.1t} (A \cdot e^{0.3jt} + B \cdot e^{-0.3jt}) + C \cdot e^{-5jt}+ D \cdot e^{5jt}$$
Her kan jeg så gøre brug af eulers identiteter:
$$e^{jt}= \cos(t) + j \sin(t)$$
$$x(t) =e^{-0.1t} \Bigl(A \cdot \bigl(\cos(0.3t)+ j \sin(0.3t )\bigr) + B \cdot (\cos(-0.3t)+ j \sin(-0.3t)) \Bigr ) + C \cdot \bigl(\cos(-5t) + j \sin(-5t) \bigr)+ D \cdot \bigl(\cos(5t) + j \sin(5t) \bigr )$$
Her kan jeg så omskrive det ved hjælp af:
$$\begin{align*}
\cos(- \theta) &=  \cos (\theta)\\
\sin(- \theta) &=  -\sin (\theta)
\end{align*}$$

$$x(t) =e^{-0.1t} \Bigl(A \cdot \bigl(\cos(0.3t)+ j \sin(0.3t )\bigr) + B \cdot (\cos(0.3t)- j \sin(0.3t)) \Bigr ) + C \cdot \bigl(\cos(5t) - j \sin(5t) \bigr)+ D \cdot \bigl(\cos(5t) + j \sin(5t) \bigr )$$
Eftersom at A og B er konjugeret kan jeg skrive det op som:
$$\begin{align*}
A &=  A_{r}+jA_{i}\\
B &=  A_{r} - jA_{i}
\end{align*}$$
Det samme kan jeg gøre med C og D
$$\begin{align*}
C &=  C_{r}+jC_{i}\\
D &=  C_{r} - jC_{i}
\end{align*}$$
Jeg skriver vores original udtryk som at være:
$$\begin{align*}
c_{1}&= \cos(0.3t)\\
s_{1}&= sin(0.3t)\\
c_{2}&= cos(5t)\\
s_{2}&= sin(5t)
\end{align*}$$
Vores udtryk er nu:
$$x(t) =e^{-0.1t} \Bigl(A \cdot \bigl(c_{1}+ j s_{1} )\bigr) + B \cdot (c_{1}- j s_{1}) \Bigr ) + C \cdot \bigl(c_{2} - j s_{2} \bigr)+ D \cdot \bigl(c_{2} + j s_{2} \bigr )$$
$$x(t) =e^{-0.1t} \Bigl((A_{r}+ jA_{i}) \cdot \bigl(c_{1}+ j s_{1} )\bigr) + (A_{r}- jA_{i}) \cdot (c_{1}- j s_{1}) \Bigr ) + (C_{r}+ jC_{i}) \cdot \bigl(c_{2} - j s_{2} \bigr)+ (C_{r}- jC_{i}) \cdot \bigl(c_{2} + j s_{2} \bigr )$$
Hvis jeg her bare ganger det ud som jeg har i A vil jeg få:
$$x_{A}(t) =e^{-0.1t} \Bigl( 
A_{r}c_{1}+A_{r}js_{1}+jA_{i}c_{1}+j^{2}A_{i}s_{1} + 
A_{r}c_{1}-A_{r}js_{1}-jA_{i}c_{1}+j^{2}A_{i}s_{1}
\Bigr )$$
Dette kan så reduceres:
$$\begin{align*}
x_{A}(t) &= e^{-0.1t} \Bigl( 
2A_{r}c_{1}-2A_{i}s_{1}
\Bigr )\\
x_{A}(t) &= 2e^{-0.1t} \Bigl( 
A_{r}c_{1}-A_{i}s_{1}
\Bigr )
\end{align*}$$
Det samme kan så gøres for C da det er præcis det samme som står der:
$$\begin{align*}
x_{C}(t)&= 2C_{r}c_{2}+2C_{i}s_{2}\\
x_{C}(t)&= 2(C_{r}c_{2}+C_{i}s_{2})
\end{align*}$$
Jeg kan nu lægge dem sammen for at få x(t) igen:
$$\begin{align*}
x(t) &=  x_{A}(t)+ x_{C}(t)\\
x(t) &= 2e^{-0.1t} ( A_{r}c_{1}-A_{i}s_{1}) +  2(C_{r}c_{2}+C_{i}s_{2})\\
x(t) &= 2 \Bigl(e^{-0.1t} ( A_{r}c_{1}-A_{i}s_{1}) +  (C_{r}c_{2}+C_{i}s_{2})\Bigr)
\end{align*}$$
jeg kan så til sidst nu indsætte vores værdier:
$$
x(t) = 2 \biggl(e^{-0.1t} \Bigl( 0.0016 \cdot \cos(0.3t) +0.6688 \cdot sin(0.3t) \Bigr)
-0.0016 \cdot \cos(5t) -0.0401 \sin(5t)\biggr)
$$
![[Opgave 3.png]]
Der kan det ses at det er det rigtige resultatet eftersom, den blå linje er den numeriske simuleret linje og den røde er den som der er regnet her. Det røde er stiplet ovenpå det blå for at se at de følger den samme kurs i stedet for at den røde overlapper det hele.
