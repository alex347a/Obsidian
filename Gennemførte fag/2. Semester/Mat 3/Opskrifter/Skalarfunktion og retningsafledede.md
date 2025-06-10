## Eksempel
Givet en skalarfunktion: $f: R^{2} \rightarrow R$
$$
f(x,y) = x^{2} \sin(y)
$$
#### a) Bestem gradienten til $f(x,y)$ i punktet $P \left(1, \frac{\pi}{4}\right)$
Jeg bruger formlen for gradienten:
$$
\nabla f(x,y) = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}\right)
$$
Derfor skal jeg beregne de partielle afledede mht. x og y. Jeg starter med x:
$$
\begin{align*}
f(x,y) &=  x^{2} \sin(y)\\
\frac{\partial f}{\partial x} &=  2x \sin(y)
\end{align*}
$$
Dernæst den partielle afledede mht. y:
$$
\begin{align*}
f(x,y) &=  x^{2} \sin(y)\\
\frac{\partial f}{\partial y} &=  x^{2} \cos(y)
\end{align*}
$$
Derfor bliver gradienten:
$$
\nabla f(x,y) = (2x \sin(y), x^{2} \cos(y))
$$
Jeg indsætter punktet $P\left(1, \frac{\pi}{4}\right)$:
$$
\begin{align*}
2 \cdot 1 \sin\left(\frac{\pi}{4}\right) = 2 \cdot \frac{\sqrt{2}}{2} &= \sqrt{2}\\
1^{2} \sin\left(\frac{\pi}{4}\right) &= \frac{\sqrt{2}}{2}\\
\nabla f\left(1, \frac{\pi}{4}\right) &= \left(\sqrt{2}, \frac{\sqrt{2}}{2}\right)
\end{align*}
$$
#### b) Bestem de punkter $(x,y)$, hvor den retningsafledede $D_{\overline{v}} f(x,y)$ i retningen $\overline{v} = \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right)$ er ligmed 0.
Den retningsafledede er givet ved:
$$
D_{\overline{v}} f (x,y) = \nabla f(x,y) \cdot \frac{\overline{v}}{||\overline{v}||}
$$
Derfor beregner jeg først enhedsnormalvektoren:
$$
||\overline{v}|| = \sqrt{\left(\frac{1}{\sqrt{2}}\right)^{2} + \left(\frac{1}{\sqrt{2}}\right)^{2}} = \sqrt{\frac{1}{2} + \frac{1}{2}} = \sqrt{1} = 1
$$
$$
\frac{\overline{v}}{||\overline{v}||} = \left(\frac{\frac{1}{\sqrt{2}}}{1}, \frac{\frac{1}{\sqrt{2}}}{1}\right) = \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right)
$$
Efter jeg har sikret det er en enhedsnormalvektor kan jeg indsætte det i formlen:
$$
\begin{align*}
D_{\overline{v}} f (x,y) &=  \nabla f(x,y) \cdot \frac{\overline{v}}{||\overline{v}||}\\
\nabla f(x,y) &= \left(\sqrt{2}, \frac{\sqrt{2}}{2}\right)\\
\frac{\overline{v}}{||\overline{v}||} &= \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right)\\
\text{indsætter det:}\\
&= (2x \sin(y), x^{2} \cos(y)) \cdot \left(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right)\\
&= \frac{2x \sin(y) + x^{2} \cos(y)}{\sqrt{2}}
\end{align*}
$$
Jeg skulle finde hvornår den var ligmed 0:
$$
\begin{align*}
\frac{2x \sin(y) + x^{2} \cos(y)}{\sqrt{2}} = 0 &\Rightarrow 2x \sin(y) + x^{2} \cos(y) = 0\\
\text{Faktoriserer:}\\
x(2 \sin(y ) + x \cos(y)) &= 0\\
\text{Hvis } x=0, \text{er det i hvert fald en løsning}\\
\text{Anden løsning er hvis: } 2 \sin(y) + x \cos(y) &=  0\\
x \cos(y) = -2 \sin(y) \Rightarrow x &=  - 2 \tan(y)\\
\text{Så længe } \cos(y) &\neq 0
\end{align*}
$$
For at $\cos(y) \neq 0$ så skal $y \neq \frac{\pi}{2} + k \pi$. Derfor bliver løsningerne:
$$
\cases{(x,y) = (0,y) \quad \text{for alle y, } y \in \mathbb{R},\\
\text{eller}\\
(x,y) = (-2 \tan(y),y) \quad \text{for } y \neq \frac{\pi}{2} + k \pi, k \in \mathbb{Z}}
$$

## Andet eksempel
Givet en skalarfunktion: $f: R^{2} \rightarrow R$
$$
f(x,y) = x \tan(y)
$$
#### a) Bestem gradienten til $f(x,y)$ i punktet $P \left(1, \frac{\pi}{4}\right)$ 
Jeg bruger formlen for gradienten:
$$
\nabla f(x,y) = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}\right)
$$
Derfor skal jeg beregne de partielle afledede mht. x og y. Jeg starter med x:
$$
\begin{align*}
f(x,y) &= x \tan(y)\\
\frac{\partial f}{\partial x} = \tan(y)
\end{align*}
$$
Dernæst den partielle afledede mht. y:
$$
\begin{align*}
f(x,y) &= x \tan(y)\\
\frac{\partial f}{\partial y} &=  x \sec^{2}(y)
\end{align*}
$$
Derfor bliver gradienten:
$$
\nabla f(x,y) = (\tan(y), x \sec^{2}(y))
$$
Jeg indsætter punktet $P\left(1, \frac{\pi}{4}\right)$:
$$
\begin{align*}
\tan\left(\frac{\pi}{4}\right) &=  1\\
1 \cdot \sec\left(\frac{\pi}{4}\right) = \sqrt{2} \Rightarrow \sec^{2}\left(\frac{\pi}{4}\right) &= 2\\
\nabla f\left(1, \frac{\pi}{4}\right) &= (1,2)
\end{align*}
$$

#### b) Bestem den retningsafledede
$$
D_{\overline{v}} f (x,y) \text{ i punktet } P\left(1, \frac{\pi}{4}\right) \text{ i retningen } \overline{v} = (3,4)
$$
Den retningsafledede $D_{\overline{v}} f (x,y)$ er givet ved formlen:
$$
D_{\overline{v}} f (x,y) = \nabla f(x,y) \cdot \frac{\overline{v}}{||\overline{v}||}
$$
Først skal jeg normalisere retningsvektoren $\overline{v} = (3,4)$:
$$
||\overline{v}|| = \sqrt{3^{2} + 4^{2}} = 5 \Rightarrow \frac{\overline{v}}{||\overline{v}||} = \left(\frac{3}{5}, \frac{4}{5}\right)
$$
Gradienten er allerede beregnet i a), så nu indsætter jeg værdierne i formlen for den retningsafledede og beregner:
$$
\begin{align*}
D_{\overline{v}} f (x,y) &=  \nabla f(x,y) \cdot \frac{\overline{v}}{||\overline{v}||}\\
\nabla f(x,y) &= (1,2)\\
\frac{\overline{v}}{||\overline{v}||} &= \left(\frac{3}{5}, \frac{4}{5}\right)\\
(1,2) \cdot \left(\frac{3}{5}, \frac{4}{5}\right) &= 1 \cdot \frac{3}{5} + 2 \cdot \frac{4}{5}\\
&= \frac{3}{5} + \frac{8}{5}\\
&= \frac{11}{5}
\end{align*}
$$
Dermed har jeg beregnet at den retningsafledede $D_{\overline{v}} f (x,y)$ er givet ved:
$$
D_{\overline{v}} f (x,y) = \frac{11}{5}
$$
