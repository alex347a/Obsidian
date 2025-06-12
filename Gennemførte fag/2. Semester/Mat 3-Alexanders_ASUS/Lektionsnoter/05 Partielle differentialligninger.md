Bølgeligningen
$$
\frac{\delta ^{2}u}{\delta t^{2}} = c^{2} \frac{\delta ^{2}u}{\delta x^{2}}
$$
Hvilket også kan skrives som:
$$
u_{tt} = c^{2} u_{xx}
$$
Løsningsmetode:
Separation af de variable.
$$
u(x,t) = X(x) \cdot T(t) = XT
$$
$$
\begin{align*}
u_{xx} = X''(x) \cdot T(t)\\
u_{tt}= X(x) \cdot T''(t)
\end{align*}
$$
$$
X'' T = \frac{1}{c^{2}} \cdot X \cdot T''
$$
$$
\frac{X''}{X}= \frac{1}{c^{2}} \frac{T''}{T} = k
$$
$$
u(x,t) = (A_{1} \cos(px) + A_{2} \sin(px)) (A_{3} \cos(pct) + A_{4}\sin(pct))
$$
### Randbetingelser
$u(0,t)=0 \rightarrow A_{1}= 0$
$u(l,t) = 0 \rightarrow p = \frac{n \pi}{l}, \quad n \text{ er et helt tal}$

Dvs.
$$
u_{n}(x,t) = A_{2} \sin\left(\frac{n \pi }{l}\right) x \left(A_{3} \cos\left(\frac{n \pi c}{l} \right)t A_{4} \sin \left(\frac{n \pi c}{l}\right)t\right)$$
#### Startbetingelser
$$\frac{\delta u}{\delta t}(x,0) = 0, \rightarrow A_{4}=0$$
$$
u(x,0) = f(x) \rightarrow u(x,0) = \sum_{n\, =\, 1} ^{\infty} \underbrace{A_{n}\sin\left(\frac{n \pi}{l}\right) x}_{\text{Fourier rækken for} f(x)=A_{n} \text{ kan bestemmes}} \cdot \underbrace{1}_{\cos(\frac{n \pi c}{l}\cdot 0)} = f(x)
$$
#### Andre startbetingelser
Hvis nu hastigheden ikke var 0, men i stedet for en funktion g(x):
$$
\frac{\delta u}{\delta t} (x,0) = g(x)
$$
$$
u(x,0) = 0
$$
Så vi skal nu finde $u_{n}'$:
$$
\frac{\delta u_{n}}{\delta t} = A_{2} \sin\left(\frac{n \pi}{l}\right)x \left(-A_{3} \frac{n \pi c}{l} \sin\left(\frac{n \pi c}{l}\right) + A_{4} \frac{n \pi c}{l} \cdot \cos\left(\frac{n \pi c}{l}\right)t\right)
$$
Så hvis:
$$
\frac{\delta u_{n}}{\delta t}(x,0) = A_{2} \sin\left(\frac{n \pi}{l}\right)x \left(0 + A_{4} \left(\frac{n \pi c}{l}\right) \cdot 1\right) = g(x)
$$
Hvis vi kalder $A_{2} \cdot A_{4} = A_{n}$ Så er hastigheden givet ved:
$$
v(x,t) = \sum_{n \, = \, 1} ^{\infty} A_{n} \frac{n \pi c}{l} \sin \left(\frac{n \pi}{l}\right) x = g(x) \rightarrow \sum_{n \, = \, 1}^{\infty} B_{n} \sin\left(\frac{n \pi}{l}\right)x = g(x)
$$
Hvor $B_{n} = A_{n} \frac{n \pi c}{l}$ 
$$
u(x,t) = \sum_{n\,=\,1} ^{\infty} \sin\left(\frac{n \pi}{l}\right)x \left(A_{2} \cos\left(\frac{n \pi c}{l}\right) t +A_{4} \sin\left(\frac{n \pi c}{l}\right) t \right)
$$
Så hvis $t=0$:
$$
u(x,0) = \sum_{n\, = \, 1}^{\infty} \sin\left(\frac{n \pi}{l}\right) x(A_{3}\cdot 1 + A_{4}\cdot 0) = 0 \rightarrow A_{3} = 0
$$
**Hvis begge af de to er forskellige fra 0 så er svaret summen af de to løsninger.**

Lad os nu kigge på den første startbetingelse:
$$
\begin{align*}
u_{t}(x,0) &=  0\\
u(x,0) &= f(x)
\end{align*}
$$
Er løsningen:
$$
u(x,t) = \sum_{n\, =\, 1}^{\infty} A_{n} \sin\left(\frac{n \pi}{l}\right) x \cdot \cos\left(\frac{n \pi c}{l}\right)t
$$
Hvis vi tager den anden startbetingelse:
Så ville det være en sin gange sin i stedet for sin gange cos:
$$
\begin{align*}
u_{t}(x,0) &=  g(x)\\
u(x,0) &= 0
\end{align*}
$$
Er løsningen:
$$
u(x,t) = \sum_{n \, = \, 1}^{\infty} B_{n} \sin\left(\frac{n \pi}{l}\right)x \cdot \sin\left(\frac{n \pi c}{l}\right)t, \quad B_{n}= A_{n} \frac{n \pi c}{l}
$$
### D'Alembert (mekanik gut)
Løser bølgeligningen på en anden måde.
Trigonometri:
$$
\sin(x) \cdot \cos(y) = \frac{1}{2}(\sin(x + y) + \sin(x-y))
$$
Der findes en tilsvarende formel for $sin(x) \cdot sin(y)$
Det skulle gerne give:
$$
sin(x) \cdot sin(y)=\frac{\cos(x-y) - \cos(x+y)}{2}
$$
$$
u(x,t) = \sum_{n\, =\, 1} ^{\infty} A_{n}\frac{1}{2} \left(\sin\left(\frac{n \pi }{l}x+\frac{n \pi c}{t}\right) + \sin\left(\frac{n \pi}{l}x - \frac{n \pi c}{l} t\right)\right)
$$
$$
u(x,t) = \frac{1}{2} \sum_{n \, = \, 1} ^{\infty} A_{n}\left(\sin\left(\frac{n \pi}{l} (x+ct)\right) + \sin\left(\frac{n \pi}{l} (x-ct)\right)\right)
$$
Her kan vi se i startbetingelse (1) at der står det samme udover at der i stedet for x står $x+ct$ 
$$
= \frac{1}{2} f(x + ct) + \frac{1}{2}f(x-ct) = \underline{\underline{\frac{1}{2}(f(x+ct) + f(x-ct))}}
$$

#### Eksempel
$$
c = \text{hastigheden}
$$
$$
c = 0,1
$$
Se side 551, fig 291

Til venstre er funktionen og til højre er summen.

Hvis $f(x) \neq 0$ og $g(x) \neq 0$:
$$
u(x,t) = \frac{1}{2} (f(x+ct) + f(x-ct)) + \frac{1}{2c} \int_{x-ct} ^ {x+ct} g(t) \, dt
$$