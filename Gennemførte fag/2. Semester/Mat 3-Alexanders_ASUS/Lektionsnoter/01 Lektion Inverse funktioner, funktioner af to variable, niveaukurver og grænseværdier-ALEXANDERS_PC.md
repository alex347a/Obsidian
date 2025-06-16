### Inverse funktioner
For at få den inverse funktion af f.eks. $\sin(x)$ så tegner man et spejl, hvor $y=x$
For at undgå at få flere y-værdier til en x-værdi så definerer man et område.

$$
\begin{align*}
y&= \arcsin(x)\\
y'&= \frac{1}{\sqrt{1-x^{2}}}
\end{align*}
$$
Eksempel:
$$
\begin{align*}
y&= \arcsin(x^{2})\\
y'&= \frac{2x}{\sqrt{1-x^{2}}}
\end{align*}
$$
Eksempel:
$$
\int\frac{1}{1+x^{2}}\, dx = \arctan(x)+c
$$
### Rolles teori (Rolle's theorem)
Mellem to punkter med samme x-værdi så skal der findes mindst et c, så $a\leq c \leq b$ hvor $f'(c) = 0$. Dvs. der er mindst et punkt hvor tangentens hældningen er 0.
![[Middelværdisætningen.png]]
Analogi: Hvis man skal fra Odense til Middelfart så er man på et eller andet tidspunkt nødt til at køre vest.

### Middelværdisætningen (Mean Value Theorem)
Der findes et c, $a \leq c \leq b$ så:
$$f'(c) = \frac{f(b)-f(a)}{b-a}$$
![[Figur 4.13.png]]
Forskel mellem Rolles teori og middelværdisætningen

| Feature            | Rolle’s Theorem                 | Mean Value Theorem                                 |
| ------------------ | ------------------------------- | -------------------------------------------------- |
| Endpoint Condition | $f(a) = f(b)$                   | No such condition                                  |
| Conclusion         | $f'(c) = 0$                     | $f'(c) = \frac{f(b) - f(a)}{b - a}$                |
| Interpretation     | Function has a stationary point | Tangent at some $c$ is parallel to the secant line |
![[Figur 4.11.png]]
Eksempel:
$$
\begin{align*}
f(x)&= \sin(x)\\
f'(x)&= \cos(x)\\
f'(c)&= \cos(c)\\
&= \frac{2}{\pi}\\
c&= \arccos\left(\frac{2}{\pi}\right)
\end{align*}
$$
### Funktioner af flere variable
En snitkurve har en dimension mindre end funktionen.

### Grænseværdier
Regneregler for grænseværdier:
![[Theorem 1 - Properties of Limits of Functions of Two Variables.png]]
Eksempel:
$$
\lim_{(x,y)\,\rightarrow \, (0,1)} \left(\frac{x-xy+3}{x^{2}y+5xy-y^{3}}\right)= \frac{0-0\cdot1+3}{0\cdot 1+5\cdot 0\cdot 1-1^{3}}=\frac{3}{-1}=-3
$$
Eksempel med division med 0:
$$
\begin{align*}
\lim_{(x,y)\, \rightarrow \, (0,0)}\left(\frac{x^{2}-xy}{\sqrt{x}-\sqrt{y}}\right)&= \lim_{(x,y)\, \rightarrow \, (0,0)}\left(\frac{(x^{2}-xy)\cdot (\sqrt{x}+\sqrt{y})}{\sqrt{x}-\sqrt{y}\cdot (\sqrt{x}+\sqrt{y})}\right)\\
\lim_{(x,y)\, \rightarrow \, (0,0)}\left(\frac{(x^{2}-xy)\cdot (\sqrt{x}+\sqrt{y})}{\sqrt{x}-\sqrt{y}\cdot (\sqrt{x}+\sqrt{y})}\right)&= \frac{x\cancel{(x-y)}(\sqrt{x}+\sqrt{y})}{\cancel{x-y}}\\
&= 0\cdot (0+0)=0
\end{align*}
$$
Eksempel med division med 0:
$$
\begin{align*}
\lim_{(x,y)\, \rightarrow \, (0,0)}\left(\frac{4xy^{2}}{x^{2}+y^{2}}\right)\\
x\rightarrow 0 \text{ og } y \text{ stationær}:\\
\frac{0}{0+y^{2}}&= 0\\
x \text{ stationær} \text{ og } y\rightarrow 0:\\
\frac{0}{x^{2}+0}&= 0\\
\end{align*}
$$
grænseværdien eksisterer, den går mod et reelt tal.