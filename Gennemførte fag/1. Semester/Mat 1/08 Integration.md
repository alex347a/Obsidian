![[Pasted image 20241031103339.png]]
$$\int_{a}^{b} f(x) \, dx$$
Anvendelse af integration:
Brug af integration gaskromotograf
![[Pasted image 20241031103234.png]]
Statistik

$$\int{acc\space dt}=hastighed$$
$$\int{hastighed\space dt}=position$$
Stamfunktion
$$\int_{a}^{b}{F(b)-F(a)}$$
$$\frac {d}{dx}F(x)=f(x)$$
$$\int{x^{2}}\space dx=\frac{1}{3}x^3+k$$
Hvor jeg bruger regneregl...
$$\frac {d}{dx}x^{n}= n\cdot x^{n-1}$$







$$\frac{d}{dx}x^3=3x^2$$
$$\frac{d}{dx}(\frac{1}{3}x^3)=x^2$$
$$\int{\frac{1}{\sqrt{1-x^2}}}=arcsin(x)+k$$
fordi
$$\frac{d}{dx}(arcsin(x)+k)=\frac{1}{\sqrt{1-x^2}}$$

$$\int_{2}^{5}(x^{3}+cos(x))\space dx=\left[\frac{1}{4}x^4+sin(x)\right]_{x=2}^{x=5}$$
$$\frac{1}{4}\cdot 5^4+sin(5)-(\frac{1}{4}2^4+sin(2))$$
$$\frac{1}{4}(625-16)+sin(5)-sin(2)$$
$$\frac{1}{4}\cdot609+sin(5)-sin(2)$$
![[Pasted image 20241031103339.png]]
$$\int_{a}^{b}f(x)\space dx=0$$
$$\int_{a}^{b}f(x)\space dx=F(b)-F(a)$$
$$\int_{a}^{b}f(x)\space dx=Af(x)+Bg(x)\space dx=A\cdot(F(b)-F(a))+B\cdot(G(b)-G(a))$$
$$\int_{a}^{c}f(x)\space dx=\int_{a}^{b}f(x)\space dx+\int_{b}^{c}f(x)\space dx$$
$$\left|\int_{a}^{b}f(x)\right|\space dx\leq \int_{a}^{b}|f(x)|\space dx$$
Hvis f(x) er ulige:
$$f(-x)=-f(x)$$
$$\int_{-a}^{a}f(x)\space dx=0$$
![[Pasted image 20241031105824.png]]
Hvis f(x) er lige:
$$f(-x)=f(x)$$
$$\int_{-a}^{a}f(x)\space dx=2\int_{0}^{a}f(x)\space dx$$
Integralregnings hovedsætning
$$F(x)=\int_{a}^{x}f(t)\space dt$$
$$\frac{d}{dx}F(x)=f(x)$$
$$\int_{a}^{b}f(x)\space dx=\int_{a}^{b}f(t)\space dt$$
$$\int_{a}^{t}f(t)\space dt$$
Integrationstabel

| f(x)     | F(x)    |
| -------- | ------- |
| 1        | x       |
| x        | $x^2$   |
| sin(x)   | -cos(x) |
| cos(x)   | sin(x)  |
| $e^x$    | $e^x$   |
| $x^{-1}$ | ln(x)   |
Substitutionsmetoden (kædereglen):
$$\int t\cdot sin(t^2)\space dt$$
$$
\left[
\begin{array}{l}
u = t^2 \\
\frac{du}{dt} = 2t \\
dt = \frac{du}{2t}
\end{array}
\right]
$$


Substituere med $u=t^2$:
$$\int t\cdot sin(u)\cdot \frac{du}{2t}$$
Forenkler udtrykket:
$$\frac{1}{2} \int t\cdot sin(u)\space du$$
Tabel opslag:
$$\frac{1}{2}(cos(u)+k_1)$$
Tilbage substitution:
$$\frac{1}{2}cos(u)+k_2$$
$$\frac {d}{dt}\left(\frac {-1}{2}(t^2)+k_2\right)=\frac{-1}{2}\cdot(-sin(t^{2}))\cdot2t+0=tsin(t^2)$$
$$\frac{d}{dx}f(g(x))=f'(g(x))\cdot g'(x)$$
Integrer begge sider:
$$f(g(x))=\int f'(g(x))\cdot g'(x)\space dx$$
$$u=g(x)$$
$$\frac {du}{dx}=g'(x)$$
$$\int f'(g(x))\cdot g'(x)\space dx=\int f'(u)\space du=f(u)$$
Hvor g(x) = u og g'(x) dx = du
$$\left[ \frac {-1}{2}cos\left(t^2\right) \right]_{t=2}^{t=3}$$
Eksempel
$$\int_{0}^{4}\frac{x^3}{\sqrt{x^{2+1}}\space}dx$$


$$
\left[
\begin{array}{l}
u = x^2+1 \\
\frac{du}{dt} = 2x \\
dx = \frac{du}{2x}
\end{array}
\right]
$$
$$\int_{1}^{17}\frac{x^3}{\sqrt{u}\space}\space\frac{du}{2x}$$
$$\frac{1}{2}\int_{1}^{17}\frac{x^2}{\sqrt{u}\space}\space{du}$$
$$\frac{1}{2}\int_{1}^{17}\frac{x^2}{\sqrt{4}\space}\space{du}=\frac{1}{2}\int_{1}^{17}\frac{u-1}{\sqrt{4}\space}\space{du}$$
$$\frac{1}{2}\int_{1}^{17}{u^\frac{1}{2}-u^\frac{-1}{2}}\space{du}$$
$$\frac{1}{2}\left[\frac{2}{3}u^{\frac{3}{2}}-2u^{\frac{1}{2}}\right]_{u=1}^{u=17}$$
$$\frac{1}{2}\cdot\frac{2}{3}\cdot 1+1 \approx19,9$$
Partiel integration (produktregel):
$$\int x\cdot e^{x}\space dx=u\cdot v=\int u'\cdot v\space dx$$
$u'=1$
$v=e^x$
$$x\cdot e^{x}-\int1\cdot e^{x}\space dx = xe^{x}-e^{x}+k_1$$
$$\frac {d}{dx}(xe^{x}-e^{x})=1\cdot e^{x}+x\cdot e^{x}-e^{x}$$
 $$=x\cdot e^{x}$$
$$\frac{d}{du}(u(x)\cdot v(x))=u'(x)v(x)+u(x)\cdot v'(x)$$
$$u(x)\cdot v(x)=\int u'(x)\space dx+\int u(x)\cdot v'(x)\space dx$$
$$
\boxed{
\int u(x) \cdot v'(x) \, dx = u(x) \cdot v(x) - \int u'(x) \cdot v(x) \, dx
}
$$
Eksempel:
$$\int x\cdot arctan(x)\space dx$$
Hvor:
$v'=x$
$u=arctan(x)$
Dermed er:
$v=\frac{1}{2}x^2$
$u'=\frac {1}{\sqrt{1+x^2}}$

Dermed får vi:
$$\int x\cdot arctan(x)\space dx=\frac{1}{2}x^{2}\cdot arctan(x)-\int{}$$