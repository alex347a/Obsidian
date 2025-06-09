$$
\int^{b}_{a}f(x)\space dx\\
$$
Uegentlige integraler
Type 1: grænserne er $\pm \infty$
Type 2: funktionsværdi er $\infty$

### Eksempel 1:

$$
\begin{align*}
\int^{\infty}_{-\infty}\frac{1}{1+x^{2}}\space dx\\
\text {da funktionen er symmetrisk}\\
\int^{\infty}_{-\infty}\frac{1}{1+x^{2}}\space dx&= 2\int^{\infty}_{0}\frac{1}{1+x^{2}}\space dx\\
&= \lim_{R\rightarrow \infty}2\cdot \int^{R}_{0}\frac{1}{1+x^{2}}\space dx\\
&= \lim_{R\rightarrow \infty}\left[2\cdot \arctan(x)\right]_{x=0}^{x=R}\\
\text{kig på funktionen for tangens}\\
&= 2\cdot \frac{\pi}{2}=\pi 
\end{align*}
$$Funktionen for tangens:![[tan(x).png]]
### Eksempel 2:
$$
\begin{align*}
\int^{1}_{0}\frac{1}{\sqrt{x}}\space dx\\
&= \lim_{R\rightarrow 0^{+}}\int^{1}_{R}\frac{1}{\sqrt{x}}\space dx\\
&= \lim_{R\rightarrow 0^{+}}\left[2\cdot x^\frac{1}{2}\right]_{x=R}^{x=1}\\
&= 2-\lim_{R\rightarrow 0^{+}}2\cdot R^\frac{1}{2}\\
&= 2
\end{align*}
$$
### Eksempel 3:
$$
\begin{align*}
\int^{\infty}_{1}\frac{1}{x}\space dx\\
&= \lim_{R\rightarrow \infty}\int^{R}_{1}\frac{1}{x}\space dx\\
&= \lim_{R\rightarrow \infty}ln(R)-ln(2)\\
=\infty\\
\int^{\infty}_{1}\frac{1}{x^{2}}\space dx&= \lim_{R\rightarrow\infty}\left[-1x^{-1}\right]_{x=1}^{x=R}\\
&= \lim_{R\rightarrow \infty}\frac{-1}{R}+\frac{1}{1}\\
=1
\end{align*}
$$
## Hyperbolske funktioner:
$$
\begin{align*}
\sin(x)^{2}+\cos(x)^{2}&= 1\\
\sinh&= \frac{e^{x}-e^{-x}}{2}\\
\cosh&= \frac{e^{x}+e^{-x}}{2}\\
\tanh(x)&= \frac{e^{x}-e^{-x}}{e^{x}+e^{-x}}
\end{align*}
$$
![[sinh, cosh og tanh.png]]
# Drevne dæmpede svingninger
$$
\begin{align*}
ay''+by'+cy&= 0\\
a\cdot r^{2}+b\cdot r+c&= 0\\
D&= b^{2}-4ac\\
\end{align*}
$$
## $D>0$, Overdæmpet:
$$y(t)=A\cdot e^{r_{1}\cdot t}+B\cdot e^{r_{2}\cdot t}$$
## $D=0$, Kritisk dæmpet:
$$y(t)=A\cdot e^{r\cdot t}+B\cdot t\cdot e^{r\cdot t}$$
## D< Underdæmpet:
$$y(t)=A\cdot e^{k\cdot t}\cdot \sin(\omega t)+B\cdot e^{k\cdot t}\cdot \cos(\omega t)$$
### Inhomogene tilfælde:
$$ay''+by'+cy=f(t)$$
### eksempel (hvor $y_{p}(t)$ er den partikulære løsning)
$$
\begin{align*}
y''+4y&= \sin(t)\\
y_{p}(t)&= A\cdot \sin(t)+B\cdot \cos(t)\\
y'_{p}(t)&= A\cdot \cos(t)-B\cdot \sin(t)\\
y''_{p}(t)&= -A\cdot \sin(t)-B\cdot \cos(t)\\
\text{Indsættes}\\
-A\sin(t)-B\cos(t)+4A \sin(t)+4B\cos(t)&= \sin(t)\\
3A \sin(t)+3B \cos(t) &= \sin(t)\\
\sin(t):3A&= 1\\
\cos(t): 3B&= 0\\
\text{derfor:}\\
A&= \frac{1}{3}\\
B&= 0\\
y_{p}(t)=\frac{1}{3}\sin(t)
\end{align*}
$$
### Eksempel:
$$
\begin{align*}
y''+4y&= \sin(2t)\\
y_{p}(t)&=A \sin(2t)+B \cos (2t)\\
y_{p}(t)'&= 2A \cos(2t)+B \sin(2t)\\
y''_{p}(t)=-4A \sin(2t)-4B \cos(2t)\\
sin(2t)&= \cancel{-4A \sin(2t)}\cancel{-4B \cos(2t)} + \cancel{4A \sin(2t)}+\cancel{4B \cos(2t)}\\
0&= sin(2t)\\
\text{Nyt gæt}\\
y_{p}(t)&= A t \sin(2t)+B t \cos(2t)\\
y'_{p}(t)&= A \sin(2t)+ 2At \sin(2t)+B \cos(2t)-2B t \sin(2t)\\
\end{align*}
$$
Det sidste udtryk skriver jeg udenfor feltet så jeg kan se det:
$$y''_{p}(t)= 2A \cos(2t)+2A \cos(2t)+ 4At \sin(2t) - 2B \sin(2t)-2B \sin(2t) -4Bt \cos(2t)$$
Indsættes i ligningen:
$$
\begin{align*}
\sin(2t)&= y''+4y \\
&= 4A \cos(2t)-4At \sin(2t)-4B \sin(2t)- 4Bt \cos(2t)+ 4\cdot (At \sin(2t)+Bt \cos(2t))\\
&= 4A \cos(2t)-4B \sin(2t)\\
y_{p}(t)&= \frac{1}{4}t\cdot sin(2t)
\end{align*}
$$
![[Mat 1 resonans.png]]
### Udenfor pensum:
Svingende kraft:
$$
\begin{align*}
y''+D\cdot y'+\omega_{0}^{2}\cdot y = \frac{F}{m}\sin(\omega t)\\
\text{Gætter på en løsning}\\
y_{p}(t)&= A \sin (\omega t) + B \cos(\omega t)\\
y'_{p}(t)&= A \omega \cos(\omega t ) - B \omega \sin(\omega t)\\
y''_{p}(t)&= -A\omega^{2} \sin(\omega t) - B \omega^{2} \cos(\omega t)\\
\text{indsættes i differentialligningen}\\
A \cdot \omega_{0}^{2}-B\cdot D \omega - A \omega^{2} = \frac{F}{m}\\
B \cdot \omega_{0}^{2} + A\cdot D \omega -B \omega^{2}= 0\\
y_{p}(t)&= A \sin(\omega t) + B \cos(\omega t)\\
&= \frac{F}{m}\cdot \frac{\omega_{0}^{2}-\omega^{2}}{(\omega^{2}-\omega_{0}^{2})^{2}+\omega ^{2}\cdot D^{2}}\cdot \sin(\omega t)-\frac{F}{m}\cdot frac\\

\end{align*}
$$
