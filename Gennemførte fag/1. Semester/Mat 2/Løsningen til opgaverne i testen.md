Bestem volumen af området, som ligger

over xy-planen
indeni cylinderen $x^{2}+y^{2}=4$
under planen $z=x+y+4$

Der skal anvendes integration til løsningen
Over xy-planen betyder $z\geq 0$ 

Cylinderen har formlen $x^{2}+y^{2}=4$, hvilket svarer til formlen for en cirkel $x^{2}+y^{2}=r^{2}$, hvor r i dette tilfælde er $r=\sqrt{4}=2$ 
Jeg bruger cylindriske koordinater:
$x=r\cos \theta$
$y=r\sin \theta$
$z=z$ 
Jacobianen er $r$ som skal huskes at blive ganget på
$$
\begin{align*}
\iiint_{V} dz\, dy\, dx&= \iiint_{V}r\, dz\, dr\, d\theta\\
\text{Grænserne bliver}:\\
\text{r går fra 0 til 2, fordi radius er 2}:\\
\theta \text{ går fra 0 til } 2\pi \text{ for at dække en hel cirkel}\\
\text{z går fra 0 til planen } z&= x+y+4\\
\text{Dette bliver i cylindriske koordinater til}:\\
z&= r(\cos\theta + \sin\theta)+4\\
\int_{0}^{2\pi}\int_{0}^{2}\int_{0}^{r(\cos \theta + \sin \theta)+4}r\, dz\, dr\, d\theta=r[z]_{0}^{r(\cos \theta + \sin \theta)+4}&= r(r(\cos \theta + \sin \theta)+4)\\
\int_{0}^{2}r(r(\cos \theta + \sin \theta)+4)\, dr&= \int_{0}^{2}r^{2}(\cos \theta + \sin \theta)\, dr +\int_{0}^{2}4\, dr\\
\text{Det første integrale bliver}:\\
\int_{0}^{2}r^{2}(\cos \theta + \sin \theta))\, dr=(\cos \theta+\sin \theta)\left[\frac{r^{3}}{3}\right]_{0}^{2}&= (\cos \theta+\sin \theta)\cdot \frac{8}{3}\\
\text{Det andet integrale bliver:}\\
\int_{0}^{2}4\, dr=4[r]_{0}^{2}&= 8\\
\text{Dermed bliver integralet}:\\
(\cos \theta+\sin \theta)\cdot \frac{8}{3}+8\\
\int_{0}^{2\pi}(\cos \theta+\sin \theta)\cdot \frac{8}{3}+8\, d\theta\\
\text{Hele det første udtryk giver 0}:\\
\text{fordi begge funktioner når en fuld periode}\\
\text{Og derfor er arealet 0 for begge}\\
\int_{0}^{2\pi}(\cos \theta+\sin \theta)\cdot \frac{8}{3}+8\, d\theta=[8]_{0}^{2\pi}&= 16\pi\\
\end{align*}
$$
Opgaven kan også løses med et dobbeltintegrale:
$$
V = \int_0^{2\pi} \int_0^2 \left( r(\cos\theta + \sin\theta) + 4 \right) r \, dr \, d\theta
$$

Her er $x$ og $y$ omregnet til polære koordinater, hvor $x = r \cos\theta$ og $y = r \sin\theta$, så integralet bliver:

$$
V = \int_0^{2\pi} \int_0^2 \left( r\cos\theta + r\sin\theta + 4 \right) r \, dr \, d\theta
$$

Nu kan vi udvide integralet:

$$
V = \int_0^{2\pi} \int_0^2 \left( r^2(\cos\theta + \sin\theta) + 4r \right) \, dr \, d\theta
$$

Udførelse af indre integral over $r$:

For første del:

$$
\int_0^2 r^2(\cos\theta + \sin\theta) \, dr = (\cos\theta + \sin\theta) \cdot \frac{8}{3}
$$

For anden del:

$$
\int_0^2 4r \, dr = 4 \cdot 2 = 8
$$

Så det indre integral bliver:

$$
\int_0^2 \left( r^2(\cos\theta + \sin\theta) + 4r \right) \, dr = \frac{8}{3} (\cos\theta + \sin\theta) + 8
$$

### Udførelse af ydre integral over $\theta$:

Nu skal vi integrere over $\theta$ fra $0$ til $2\pi$:

$$
V = \int_0^{2\pi} \left( \frac{8}{3} (\cos\theta + \sin\theta) + 8 \right) \, d\theta
$$

Da:

$$
\int_0^{2\pi} (\cos\theta + \sin\theta) \, d\theta = 0
$$

Så får vi:

$$
V = \int_0^{2\pi} 8 \, d\theta = 8 \cdot 2\pi = 16\pi
$$
$$
V = 16\pi
$$
Opgave 2
$y''(t)+3y'(t)+2y(t)=2, y(0)=0, y'(0)=0$

a) Bestem laplacetransformationen af differentialligningen ovenfor.
b) Bestem Y(s) ved at løse ligningen fra (a)
c) Bestem løsningen til differentialligningen vha. invers laplacetransformation af løsningen fra (b)

Laplace-transformationen af $y''(t)$, $y'(t)$, og $y(t)$ gives som:

$$
\mathcal{L}\{y''(t)\} = s^2 Y(s) - sy(0) - y'(0)
$$
$$
\mathcal{L}\{y'(t)\} = sY(s) - y(0)
$$
$$
\mathcal{L}\{y(t)\} = Y(s)
$$

Da $y(0) = 0$ og $y'(0) = 0$, får vi:

$$
\mathcal{L}\{y''(t)\} = s^2 Y(s)
$$
$$
\mathcal{L}\{y'(t)\} = s Y(s)
$$
$$
\mathcal{L}\{y(t)\} = Y(s)
$$

På den måde får vi Laplace-transformationen af hele differentialligningen:

$$
s^2 Y(s) + 3s Y(s) + 2 Y(s) = \mathcal{L}\{2\}
$$

Lad os finde Laplace-transformationen af højre side:

$$
\mathcal{L}\{2\} = \frac{2}{s}
$$

Så den Laplace-transformerede ligning bliver:

$$
s^2 Y(s) + 3s Y(s) + 2 Y(s) = \frac{2}{s}
$$

(b) Bestem $Y(s)$ ved at løse ligningen fra (a)

Vi kan faktorisere venstre side:

$$
(s^2 + 3s + 2) Y(s) = \frac{2}{s}
$$

Løs for $Y(s)$:

$$
Y(s) = \frac{2}{s(s^2 + 3s + 2)}
$$

Før vi kan fortsætte, faktoriserer vi $s^2 + 3s + 2$:

$$
s^2 + 3s + 2 = (s + 1)(s + 2)
$$

Så får vi:

$$
Y(s) = \frac{2}{s(s + 1)(s + 2)}
$$

(c) Bestem løsningen til differentialligningen ved hjælp af invers Laplace-transformation

For at finde den inverse Laplace-transformation af $Y(s)$, bruger vi partialbrøksopdeling:

$$
\frac{2}{s(s + 1)(s + 2)} = \frac{A}{s} + \frac{B}{s + 1} + \frac{C}{s + 2}
$$

Multiplicer begge sider med $s(s + 1)(s + 2)$:

$$
2 = A(s + 1)(s + 2) + B s (s + 2) + C s (s + 1)
$$
For at finde løsningerne skal vi bruge at
$$
A(s + 1)(s + 2) + B s (s + 2) + C s (s + 1)=As^{2}+3As+2A+Bs^{2}+2Bs+Cs^{2}+Cs
$$
$$
As^{2}+3As+2A+Bs^{2}+2Bs+Cs^{2}+Cs=(A+B+C)s^{2}+(3A+2B+C)s+2A
$$
Hvor:
$$
\begin{align*}
(A+B+C)s^{2}&= 0\\
(3A+2B+C)s&= 0\\
2A&= 2
\end{align*}
$$
Dvs.
$$
\begin{align*}
A&= 1\\
3+2B+C&= 0\\
C&= -2B-3\\
A+B+C&= 0\\
1+B-2B-3&= 0\\
-B&= 2\\
B&= -2\\
C&= -2B-3\\
C&= 4-3\\
C&= 1
\end{align*}
$$


Så vi har:

$$
\frac{2}{s(s + 1)(s + 2)} = \frac{1}{s} - \frac{2}{s + 1} + \frac{1}{s + 2}
$$

Nu tager vi den inverse Laplace-transformation af hver term:

$$
\mathcal{L}^{-1}\left\{\frac{1}{s}\right\} = 1
$$
$$
\mathcal{L}^{-1}\left\{\frac{1}{s + 1}\right\} = e^{-t}
$$
$$
\mathcal{L}^{-1}\left\{\frac{1}{s + 2}\right\} = e^{-2t}
$$

Så den samlede løsning $y(t)$ er:

$$
y(t) = 1 - 2e^{-t} + e^{-2t}
$$

Alle resultaterne bliver altså

a) Laplace-transformationen af differentialligningen:

$$
s^2 Y(s) + 3s Y(s) + 2 Y(s) = \frac{2}{s}
$$

b) Løsningen for $Y(s)$:

$$
Y(s) = \frac{2}{s(s + 1)(s + 2)}
$$

c) Løsningen til differentialligningen:

$$
y(t) = 1 - 2e^{-t} + e^{-2t}
$$
