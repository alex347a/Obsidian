## Grænseværdier
$$\frac{d}{dx}f(x)=\lim_{h\rightarrow 0}\frac{f(x+h)-f(x)}{h}$$
Funktioners opførsel for store x-værdier
$$f'(x)=\frac{\Delta y}{\Delta x}$$
Eksempel:
$$\frac{d}{dx}x^{2}=\lim_{h\rightarrow 0}\frac{(x+h)^2-x^{2}}{h}$$
$$=\lim_{h\rightarrow 0}\frac{x^{2}+2hx+h^{2}-x^{2}}{h}$$
$$=\lim_{h\rightarrow 0}\frac{2hx+h^{2}}{h}$$
$$=\lim_{h\rightarrow 0}2x+h=2x$$


Andet eksempel:
$$\frac{d}{dx}\sqrt{x}=\lim_{h\rightarrow 0}\frac{\sqrt{x+h}-\sqrt{x}}{h}$$
$$=\lim_{h\rightarrow 0}\frac{(\sqrt{x+h}-\sqrt{x})(\sqrt{x+h}+\sqrt{x})}{h(\sqrt{x+h}+\sqrt{x})}$$

$$=\lim_{h\rightarrow 0}\frac{({x+h})+\sqrt{x+h}\sqrt{x}-\sqrt{x}\sqrt{x+h}-x}{h\sqrt{x+h}+h\sqrt{x}}$$
$$\lim_{h\rightarrow 0}\frac{x+h-x}{h\sqrt{x+h}+h\sqrt{x}}$$
$$\lim_{h\rightarrow 0}\frac{1}{\sqrt{x+h}+\sqrt{x}}$$
$$\frac{1}{2\sqrt{x}}$$
Tredje eksempel:
$$
\begin{align*}\\
A&= \lim_{x\rightarrow -2}\frac{x^{2}+x-2}{x^{2}+5x+6}\\
&= \lim_{x\rightarrow -2}\frac{(x+2)(x-1)}{(x+3)(x+2)}\\
&= \lim_{x\rightarrow -2}\frac{x-1}{x+3}\\
\frac{-3}{1}&= -3\\
\frac{4-2-2}{4-10+6}&= \frac{0}{0}\\
\end{align*}
$$
Hvornår eksisterer en grænseværdi:
$$\lim_{x\rightarrow a^+}f(x)$$
$$\lim_{x\rightarrow a^-}f(x)$$
Hvis grænserne findes gælder:
$$\lim_{x\rightarrow a}(f(x)+g(x))=\lim_{x\rightarrow a}f(x)+\lim_{x\rightarrow a}g(x)$$
$$\lim_{x\rightarrow a}f(x)\cdot g(x)=\left(\lim_{x\rightarrow a}f(x)\right)\cdot \left(\lim_{x\rightarrow a}g(x)\right)$$
$$\ne0 \space \text{og} \space \ne \infty$$

## Kapløb mellem funktioner
Store O() notation.
$$\frac{f(n)}{n^2}$$
$$O(n^2)$$
$$\frac{f(n)}{n^{1.2}}$$
$$A=\lim_{x\rightarrow \infty}\frac{2x^{2}-x+3}{3x^{2}+5}$$
Forlænger med $x^{-2}$
$$=lim_{x\rightarrow \infty}\frac{2x^{2}x^{-2}-xx^{-2}+3x^{-2}}{3x^{2}x^{-2}+5x^{-2}}$$
$$=\lim_{x\rightarrow \infty}\frac{2-x^{-1}+3x^{-2}}{3+5x^{-2}}$$
$$=\frac{lim\space2-lim\space x^{2}+lim\space 3x^{-2}}{lim\space 3+lim\space 5 x^{-2}}$$
$$=\frac{2-0+0}{3+0}$$
$$\frac{2}{3}$$
Styrkeforhold:
$$e^{x}>x^{p}>ln(x)$$
$$e^{0,0001x}>x^{1000}$$
For $a>0$:
$$\lim_{x\rightarrow \infty}\frac{x^{a}}{e^{x}}=0$$
$$\lim_{x\rightarrow \infty}=\frac{ln(x)}{x^{a}}$$
$$\lim_{x\rightarrow \infty}x^{a} \cdot ln(x)=0$$
Eksempel:
$$\lim_{x\rightarrow \infty} \frac{x^{2}+ln(x)}{e^{0.001x}+x}$$
$$A=\lim_{x\rightarrow \infty} \frac{x^{2}+ln(x)}{e^{0,001x}+x}$$
Forlænge med $e^{-0,001x}$
$$\lim_{x\rightarrow \infty} \frac{x^{2}\cdot e^{-0,001x}+ln(x)\cdot e^{-0,001x}}{e^{0,001x}\cdot e^{-0,001x}+x\cdot e^{-0,001x}}$$
$$\text lim\space \frac{x^{2}\cdot e^{-0,001x}+\text lim\space ln(x)\cdot e^{-0,001x}}{\text lim\space 1+\text lim\space x\cdot e^{-0,001x}}$$
$$\frac{0+0}{1}=0$$

Eksempel med L'Hopitals regel:
$$\lim_{x\rightarrow 1}\frac{sin(\pi \cdot x)}{x^{2}-1}$$
$$\frac{sin(\pi)}{1^{2}-1}=\frac{0}{0}$$
$$
\begin{align*}
f(x)&= sin(\pi x)\\
f'(x)&= cos(\pi x)\cdot \pi\\
L_{f}(x)&= f(1)+f'(1)\cdot (x-1)\\
&= 0+(-\pi)\cdot(x-1)\\
\\
g(x)&= x^{2}-1\\
g(x)&= 2\\
L_{g}(x)&= g(1)+g'(1)\\
&= 0+2\cdot (x-1)\\
\\
A&= lim_{x\rightarrow 1} \frac{sin(\pi x)}{x^{2}-1}\\
&= lim_{x\rightarrow 1} \frac{0-\pi(x-1)}{0+2\cdot(x-1)}\\
&= lim_{x\rightarrow 1} \frac{-\pi \cdot(x-1)}{2 \cdot(x-1)}\\
&= lim_{x\rightarrow 1} \frac{-\pi}{2}&=  \frac{-\pi}{2}
\end{align*}
$$
L'Hopitals regel:
$$
\begin{align*}
\lim_{x\rightarrow a} f(x)=\lim_{x\rightarrow a}g(x)=0\\
\lim_{x\rightarrow a}\frac{f(x)}{g(x)}=\lim_{x\rightarrow a}\frac{f'(x)}{g'(x)}
\end{align*}
$$

Eksempel:
$$
\begin{align*}
\lim_{x\rightarrow 0}\frac{\sin(x)}{x}\begin{pmatrix}0\\
0\end{pmatrix} \text{L'Hoptial}\\
&= \lim_{x\rightarrow 0}\frac{\frac{d}{dx}(\sin(x))}{\frac{d}{dx}(x)}\\
&= \lim_{x\rightarrow 0}\frac{\cos(x)}{1}\begin{pmatrix}1\\
1\end{pmatrix}\\
&= 1
\end{align*}$$
Eksempel 4:
$$\begin{align*}\\
V&= \lim_{x\rightarrow 0^{+}}\left(\frac{1}{x}-\frac{1}{sin(x)}\right)\\\\
&= \lim_{x\rightarrow 0^{+}}\frac{\sin(x)-x}{x\cdot \sin(x)}\begin{pmatrix}0\\
0\end{pmatrix} \text{L'Hopital}\\\\
&= \lim_{x\rightarrow 0^{+}}\frac{\cos(x)-1}{1 \cdot \sin(x)+x \cdot \cos(x)}\begin{pmatrix}0\\
0\end{pmatrix}\text{L'Hopital}\\\\
&= \lim_{x\rightarrow 0^{+}}\frac{-\sin(x)}{\cos(x)+\cos(x)-1 \sin(x)}\begin{pmatrix}0\\
2\end{pmatrix}\\\\
&= \frac{0}{2}=0
\end{align*}
$$
Eksempel 5:
$$
\begin{align*}\\
V&= \lim_{x\rightarrow 0^{+}}\frac{x \cdot sin(x)}{\sin(x)-x}\\\\
&= ...\\\\

&= \lim_{x\rightarrow 0^{+}}\frac{-x \sin(x)+2 \cos(x)}{-\sin(x)}\begin{pmatrix}2\\
0\end{pmatrix}\\\\
&= -\infty
\end{align*}
$$
L'Hopital
$$\lim_{x\rightarrow a} f(x)= \lim_{x\rightarrow a} g(x)=\infty$$

Eksempel
$$
\begin{align*}
V&= \lim_{x\rightarrow \infty} \frac{e^{x}}{x}\begin{pmatrix}\infty\\
\infty\end{pmatrix}\\\\
&= \lim_{x\rightarrow \infty} \frac{e^{x}}{1} \begin{pmatrix}\infty\\
1\end{pmatrix}\\
\end{align*}
$$

$$ay''+by'+cy=f(x)$$
Løs først det homogene problem.
Eksempel
## karakterligningen
$$
\begin{align*}
y''+y''-2y&= 4x\\
y''+y'-2y&= 0\\
\text{Karakterligning}\\
r^{2}+r-2&= 0\\
r&= \frac{-1 \pm \sqrt{r^{2}-4\cdot 1-(-2)}}{2}&= \frac{-1\pm 3}{2}\\
r&= -2 \lor r= 1\\
y_{h}(x)=Ae^{-2x}+Be^{1x}\\
y_{p}=C+Dx\\\\
0+D-2\cdot1(C+Dx)=4x\\
y_{p}'=D \\
D=-2\space C=-1\\
y_{p}''=0\\
y_{p}(x)=-1-2x

\end{align*}
$$