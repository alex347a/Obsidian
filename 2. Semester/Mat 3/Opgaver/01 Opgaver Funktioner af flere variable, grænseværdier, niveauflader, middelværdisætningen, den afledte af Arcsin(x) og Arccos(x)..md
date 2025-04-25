3.9
![[Graphs of the arctangent, arccotangent, arcsecant, and arccosecant functions.png]]
![[Definitions of arctangent, arccotangent, arcsecant, and arccosecant functions.png]]
![[Derivatives of the inverse trigonometric functions table.png]]
Opgave 3.9.21
Find the derivative of y with respect to the appropriate variable.
$$
\begin{align*}
y &= \cos^{-1}(x^{2})\\
\text{formel : } \frac{d(cos^{-1}(u))}{dx}&= - \frac{1}{\sqrt{1-u^{2}}} \frac{du}{dx}, \quad |u|<1\\
\frac{dy}{dx}&= \frac{d\cos^{-1}(x^{2})}{dx}\\
\text{Kæderegel: } (f(g(x)))'=f'(g(x))\cdot g'(x)\\
&=  - \frac{1}{\sqrt{1-(x^{2})^{2}}}\cdot \frac{d}{dx}(x^{2})\\
&= - \frac{2x}{\sqrt{1-x^{4}}}
\end{align*}
$$
4.2
![[Theorem 4 The Mean Value Theorem.png]]
Opgave 4.2.3
Find the value or values of c that satisfy the equation.
$$
\frac{f(b)-f(a)}{b-a}=f'(c)
$$
in the conclusion of the Mean Value Theorem for the functions and intervals.
$$
\begin{align*}
f(x)&= \frac{x+1}{x}, \quad \left[\frac{1}{2},2\right]\\
\frac{f(b)-f(a)}{b-a}&= f'(c)\\
f(2)= \frac{2+1}{2}&= \frac{3}{2}\\
f(1)= \frac{\frac{1}{2}+1}{\frac{1}{2}}&= 3\\
\frac{\frac{3}{2}-3}{2-\frac{1}{2}}= \frac{\frac{-3}{2}}{\frac{3}{2}}&= -1\\
\text{Bruger kvotientregel:}\\
f(x) &= g\frac{x}{h(x)}\\
f'(x) &= \frac{g'(x)h(x)- g(x)h'(x)}{h(x)^{2}}\\
f'(x)&= \frac{1\cdot x - (x+1) \cdot 1}{x^{2}}\\
= \frac{x-x-1}{x^{2}}&= \frac{-1}{x^{2}}\\
\text{Sætter } f'(c) &= -1\\
\frac{-1}{c^{2}}&= -1\\
c^{2}&= 1\\
c&= \pm 1\\
\text{Siden } c&= -1 \text{ er udenfor intervallet:}\\
\left[\frac{1}{2},2\right]\\
c&= 1
\end{align*}
$$

13.1
## Contour curves
Contour curves and level curves are different things, however are both given by: $$ f(x,y)=c$$
Opgave 13.1.15
Find and sketch the level curves $f(x,y) = c$ on the same set of coordinate axes for the given values of c. We refer to these level curves as a contour map
$f(x,y) = xy, \quad c = -9, -4, -1, 0, 1, 4, 9$
![[Mat 3 01 lektier .pdf]]

Opgave 13.1.31
Match the level curves with the curves and equations
![[13.1.31 Level curve.png]]
![[13.1.31 Surface.png]]
![[13.1.31 Equation.png]]
13.2

Opgave 13.2.9
Find the limit
$$
\begin{align*}
\lim_{(x,y) \space \rightarrow \space (0,0)} \left(\frac{e^{y}\sin(x)}{x}\right) &= \frac{0}{0}\\
\text{Da man ikke kan dividere med 0:}\\
\text{Jeg kan bruge approximationen:}\\
\sin(x) &\approx x \text{ for små x-værdier}\\
\lim_{x \space \rightarrow \space 0}\left(\frac{\sin(x)}{x}\right)&= 1\\
\lim_{(x,y) \space \rightarrow \space (0,0)} e^{y}\cdot 1= e^{0}&= 1\\
\lim_{(x,y) \space \rightarrow \space (0,0)} \left(\frac{e^{y}\sin(x)}{x}\right)=0
\end{align*}
$$

Opgave 13.2.11
Find the limit
$$
\begin{align*}
\lim_{(x,y) \space \rightarrow \space (1, \pi/6)} \frac{x \sin (y)}{x^{2}+1} &=\frac{1\cdot \sin(\pi/6)}{1^{2}+1}\\
=\frac{\frac{1}{2}}{2}&= \frac{1}{4}\\
\end{align*}
$$