# Lektion 1: (VIGTIGT: Her er opgaverne fra Thomas og IKKE Kreyszig)
## Opgave 3.9.21 Find the derivative of y with respect to the appropriate variable.
Find the derivative of y with respect to the appropriate variable.
$$
\begin{align*}
y &= \cos^{-1}(x^{2})\\
\text{formel : } \frac{d(cos^{-1}(u))}{dx}&= - \frac{1}{\sqrt{1-u^{2}}} \frac{du}{dx}, \quad |u|<1\\
\text{Kæderegel: } (f(g(x)))'=f'(g(x))\cdot g'(x)\\
&=  - \frac{1}{\sqrt{1-(x^{2})^{2}}}\cdot \frac{d}{dx}(x^{2})\\
&= - \frac{2x}{\sqrt{1-x^{4}}}
\end{align*}
$$
## Opgave 4.2.3 Find the value or values of c that satisfy the equation.
Find the value or values of c that satisfy the equation.
$$
\frac{f(b)-f(a)}{b-a}=f'(c)
$$
in the conclusion of the Mean Value Theorem for the functions and intervals.
$$
\begin{align*}
f(x)&= \frac{x+1}{x}, \quad \left[\frac{1}{2},2\right]\\
\frac{f(b)-f(a)}{b-a}&= f'(c)\\
\text{Beregner de to funktionsværdier:} f(2)= \frac{2+1}{2}&= \frac{3}{2}\\
f\left(\frac{1}{2}\right)= \frac{\frac{1}{2}+1}{\frac{1}{2}}&= 3\\
\text{Indsætter i formlen:} \frac{\frac{3}{2}-3}{2-\frac{1}{2}}= \frac{\frac{-3}{2}}{\frac{3}{2}}&= -1\\
\text{Bruger kvotientregel:}\\
f'(x) &= \frac{g'(x)h(x)- g(x)h'(x)}{h(x)^{2}}\\
f'(x)&= \frac{(x+1)'\cdot x - (x+1) \cdot x'}{x^{2}}\\
&= \frac{1\cdot x - (x+1) \cdot 1}{x^{2}}\\
= \frac{x-x-1}{x^{2}}&= \frac{-1}{x^{2}}\\
\text{Sætter } f'(c) &= -1\\
\frac{-1}{c^{2}}&= -1\\
c^{2}&= 1\\
c&= \pm 1\\
\text{Siden } c&= -1 \text{ er udenfor intervallet:}\\
\left[\frac{1}{2},2\right]\\
\text{Så må }c&= 1 \text{ være den eneste løsning}
\end{align*}
$$

## Opgave 13.1.15 Find and sketch the level curves $f(x,y) = c$ on the same set of coordinate axes for the given values of c. We refer to these level curves as a contour map
Find and sketch the level curves $f(x,y) = c$ on the same set of coordinate axes for the given values of c. We refer to these level curves as a contour map
$f(x,y) = xy, \quad c = -9, -4, -1, 0, 1, 4, 9$
![[13.1.5 billede.png]]

## Opgave 13.1.31 Match the level curves with the curves and equations
Match the level curves with the curves and equations
![[13.1.31 Level curve.png]]
Denne niveaukurve passer med (f) og (h). 
Niveaukurven passer med billedet (f) idet det kan observeres at funktionen er meget stejl ude i siderne og bliver mindre og mindre stejl tættere på origo i y-retningen. Det kan ikke ses på niveaukurven om funktionen enten er stejl op eller ned ad z-aksen, men på billedet (f) kan det set at det er ned ad z-aksen dvs. i den negative retning.
Niveaukurven passer med funktionen (h) idet det kan observeres at funktionen i y retningen er en fjerdegradsligning, mens det kun er en andengradsligning i x-retningen, og da (h) er den eneste fjerdegradsligning kan det kun være denne.
![[13.1.31 Surface.png]]
![[13.1.31 Equation.png]]

## Opgave 13.2.9 Find the limit
Find the limit
$$
\begin{align*}
\lim_{(x,y) \space \rightarrow \space (0,0)} \left(\frac{e^{y}\sin(x)}{x}\right) &= \frac{0}{0}\\
\text{Da man ikke kan dividere med 0:}\\
\text{Jeg kan bruge approximationen:}\\
\sin(x) &\approx x \text{ for små x-værdier}\\
\lim_{x \space \rightarrow \space 0}\left(\frac{\sin(x)}{x}\right)&= 1\\
\text{Så mangler jeg bare }e^{y}:\\
\lim_{(x,y) \space \rightarrow \space (0,0)} e^{y}\cdot 1= e^{0}&= 1\\
\lim_{(x,y) \space \rightarrow \space (0,0)} \left(\frac{e^{y}\sin(x)}{x}\right)=1
\end{align*}
$$
## Opgave 13.2.11 Find the limit $\lim_{(x,y) \space \rightarrow \space (1, \pi/6)} \frac{x \sin (y)}{x^{2}+1}$ 
Find the limit $\lim_{(x,y) \space \rightarrow \space (1, \pi/6)} \frac{x \sin (y)}{x^{2}+1}$ 
Jeg starter med at indsætte værdierne for x og y:
$$
\begin{align*}
\lim_{(x,y) \space \rightarrow \space (1, \pi/6)} \frac{x \sin (y)}{x^{2}+1} &=\frac{1\cdot \sin\left(\frac{\pi}{6}\right)}{1^{2}+1}\\
\frac{\pi}{6} \text{ svarer til 30 grader}:\\
\sin\left(\frac{\pi}{6}\right)&= \frac{1}{2}\\
\text{Derfor bliver brøken:}\\
=\frac{\frac{1}{2}}{2}&= \frac{1}{4}\\
\end{align*}
$$

# Lektion 2:

## Opgave 11.1.17 Find the Fourier series of the given function $f(x)$, which is assumed to have the period $2\pi$. Show the details of your work. Sketch or graph the partial sums up to that including $\cos(5x)$ and $\sin(5x)$

Find the Fourier series of the given function $f(x)$, which is assumed to have the period $2\pi$. Show the details of your work. Sketch or graph the partial sums up to that including $\cos(5x)$ and $\sin(5x)$

Funktionen:
$$
\quad f(x) =
\begin{cases}
x + \pi, & -\pi \leq x < 0, \\
\pi - x, & 0 \leq x \leq \pi.
\end{cases}
$$

Fourier serie representation:
$$
f(x) = \frac{a_0}{2} + \sum_{n=1}^{\infty} a_n \cos(nx) + \sum_{n=1}^{\infty} b_n \sin(nx).
$$

Først beregnes $a_{0}$ med formlen:
$$
a_0 = \frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \, dx.
$$
Jeg deler funktionen op i to integraler:
$$
\begin{align*}
a_{0} &=  \frac{1}{\pi} \left( \int_{-\pi}^{0} (x + \pi) \, dx + \int_{0}^{\pi} (\pi - x) \, dx \right)\\
\text{Jeg starter med den første:}\\
\int_{-\pi}^{0} (x + \pi) \, dx &=  \int_{-\pi}^{0} x \, dx + \int_{-\pi}^{0} \pi \, dx\\
= \left[ \frac{x^2}{2} \right]_{-\pi}^{0} + \pi \left[ x \right]_{-\pi}^{0}
&=  \left(0 - \frac{\pi^{2}}{2} \right) + \pi (0 + \pi)\\
=  -\frac{\pi^{2}}{2} + \pi^{2} &=   \frac{\pi^2}{2}\\
\text{Nu til det andet integrale:}\\
\int_{0}^{\pi} (\pi - x) \, dx &=  \int_{0}^{\pi} \pi \, dx - \int_{0}^{\pi} x \, dx\\
= \pi \left[ x \right]_{0}^{\pi} - \left[ \frac{x^2}{2} \right]_{0}^{\pi}
= \pi^{2} - \frac{\pi^{2}}{2} &=  \frac{\pi^{2}}{2}\\
\end{align*}
$$
De to svar sættes sammen, hvor konstanten udenfor de to integraler huskes:
$$
a_{0} = \frac{1}{\pi} \left( \frac{\pi^{2}}{2} + \frac{\pi^{2}}{2} \right) = \frac{\pi^{2}}{\pi} =  \pi
$$
Nu beregnes $a_{n}$ med formlen:
$$
a_n = \frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \cos(nx) \, dx
$$
Jeg deler funktionen op i to integraler:
$$
a_n = \frac{1}{\pi} \left( \int_{-\pi}^{0} (x + \pi) \cos(nx) \, dx + \int_{0}^{\pi} (\pi - x) \cos(nx) \, dx \right)
$$
Først defineres $a_n$ som:

$$
a_n = \frac{1}{\pi} \int_{-\pi}^{\pi} f(x) \cos(nx) \, dx
$$

Jeg deler funktionen op i to integraler:

$$
a_n = \frac{1}{\pi} \left( \int_{-\pi}^{0} (x + \pi) \cos(nx) \, dx + \int_{0}^{\pi} (\pi - x) \cos(nx) \, dx \right)
$$
For det første integral, $\int_{-\pi}^{0} (x + \pi) \cos(nx) \, dx$, bruger jeg integration med dele:
$$
\begin{align*}
\int u \, dv &=  uv - \int v \, du\\
u = x + \pi, du &= dx\\
dv = \cos(nx) \, dx, v = \frac{1}{n} \sin(nx)
\end{align*}
$$
Så bliver integralet:
$$
\left[x+\pi \frac{1}{n} \sin(nx)\right]_{-\pi}^{0} - \int_{\pi} ^{0} \frac{1}{n}\sin(nx) \, dx
$$
Det første led:
$$
\begin{align*}
\left[x+\pi \frac{1}{n} \sin(nx)\right]_{-\pi}^{0} &= (0 + \pi) \frac{1}{n} \sin(0) - \left(-\pi + \pi \frac{1}{n} \sin(-\pi n)\right)\\
\text{Da } \sin(0) &=  0\\
= 0-0&= 0\\
\end{align*}
$$
Det andet led:
$$
\begin{align*}
- \int_{\pi} ^{0} \frac{1}{n}\sin(nx) \, dx &= -\left[- \frac{1}{n^{2}}\cos(nx)\right]_{-\pi} ^{0} \\
&= \frac{1}{n^{2}} (\cos(0) - \cos(-\pi n))\\
\text{Da } \cos(0) = 1 \text{ og } \cos(-\pi n ) &= (-1)^{n}:\\
&= \frac{1}{n^{2}}(1 - (-1) ^{n})\\
\end{align*}
$$
Nu skal jeg finde:
$$
\int_{0}^{\pi} (\pi - x) \cos(nx) \, dx
$$
Men da denne funktion er lige, så må det betyde at dette integrale givet det præcist samme som det forrige:

$$
\int_{0}^{\pi} (\pi - x) \cos(nx) \, dx = \frac{1}{n^{2}}(1 - (-1) ^{n})
$$
$a_{n}$:

$$
\begin{align*}
a_{n} &=  \frac{1}{\pi} \left(\frac{1}{n^{2}}\left(1 - (-1) ^{n}\right)+\frac{1}{n^{2}}(1 - (-1) ^{n})\right)\\
&= \frac{2}{\pi}\cdot \frac{1}{n^{2}}(1 - (-1) ^{n})
\end{align*}
$$

Siden $f(x)$ er en lige funktion og cosinus er en lige funktion så skal $a_{n}$ beregnes, men det skal $b_{n}$ ikke, idet sinus er en ulige funktion og derfor er $b_{n}$ uanset hvad 0.
$$
b_{n} = 0
$$


Derfor bliver Fourier serien:
$$
f(x) = \frac{a_0}{2} + \sum_{n=1}^{\infty} a_n \cos(nx) + \sum_{n=1}^{\infty} b_n \sin(nx).
$$
$$
\begin{align*}
a_{0}&= \pi\\
a_{n}&= \frac{2}{\pi}\cdot \frac{1}{n^{2}}(1 - (-1) ^{n})\\
b_{n} &= 0
\end{align*}
$$
Jeg beregner nogle n-værdier:
$n= 2$
$$
\frac{1}{4}(1-1)\cos(2x) = 0
$$
$n=3$
$$
\frac{1}{9}(1+1)\cos(3x) = \frac{2}{9}\cos(3x)
$$
Hvor 2 tallet kan trækkes udenfor parentesen. Derfor bliver Fourier rækken:
$$
f(x) =\frac{\pi}{2} + \frac{4}{\pi} \left(\cos(x) + \frac{1}{9} \cos\left(3x\right) + \frac{1}{25}\cos(5x) + \dots\right)
$$
Tegning:
![[13.1.7 billede.png]]
Svaret i bogen er:
$$
f(x) =\frac{\pi}{2} + \frac{4}{\pi} \left(\cos(x) + \frac{1}{9} \cos\left(3x\right) + \frac{1}{25}\cos(5x) + \dots\right)
$$
## Opgave 11.2.13 Is the given function even or odd or neither even nor odd? Find its Fourier series. Show details of your work.
Is the given function even or odd or neither even nor odd? Find its Fourier series. Show details of your work.
![[11.2.13.png]]

Funktionen er givet ved

$$
f(x) =
\begin{cases}
0, & -\frac{1}{2} \leq x < 0, \\
x, & 0 \leq x \leq \frac{1}{2}.
\end{cases}
$$

En funktion er defineret som lige hvis:

$$
f(-x) = f(x).
$$

En funktion er defineret som ulige hvis:

$$
f(-x) = -f(x).
$$

Hvis jeg indsætter nogle værdier for $f(x)$:

- For x i $[0, \frac{1}{2}]$, $f(x)=x$
- For x in $[\frac{-1}{2}, 0]$, $f(x)=0$

f(-x):

- For x i $[0, \frac{1}{2}]$, -x i $[\frac{-1}{2}, 0]$, så f(-x) = 0
- For x i $[\frac{-1}{2}, 0]$, -x i $[0, \frac{1}{2}]$, så f(-x) = -(-x) = x.

Derfor da:

$$
\begin{align*}
f(-x) &\neq  f(x) \quad \text{(ikke lige)}\\
f(-x) &\neq  -f(x) \quad \text{(ikke ulige)}
\end{align*}
$$

Siden ingen af betingelserne er opfyldt så er funktionen hverken lige eller ulige.

Fourier serie representationen:

Standard formlen er givet ved:
$$
f(x) = \frac{a_0}{2} + \sum_{n=1}^{\infty} a_{n} \cos\left(\frac{2 \pi n}{P}x\right) + \sum_{n=1}^{\infty} b_{n} \sin\left(\frac{2 \pi n}{P}x\right)
$$
Da funktionen er defineret på intervallet $\left[\frac{-1}{2}, \frac{1}{2}\right]$ hvilket er en periode på 1, så hvis dette indsættes på P's plads, så bliver Fourier serien givet ved:
$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1}^{\infty} a_{n} \cos(2\pi n x) + \sum_{n=1}^{\infty} b_{n} \sin(2\pi n x)
$$
Hvor koefficienterne er givet ved:

$$
\begin{align*}
a_{0} &=  \int_{\frac{-1}{2}}^{\frac{1}{2}} f(x) \,dx.\\
a_{n} &=  2 \int_{\frac{-1}{2}}^{\frac{1}{2}} f(x) \cos(2\pi n x) \,dx.\\
b_{n} &=  2 \int_{\frac{-1}{2}}^{\frac{1}{2}} f(x) \sin(2\pi n x) \,dx.
\end{align*}
$$
Siden $f(x) = 0$ når $-1/2 \leq x < 0$, Så skal jeg bare regne integralet over intervallet $[0,\frac{1}{2}]$
$a_{0}$:

$$
\begin{align*}
a_{0} =  \int_{\frac{-1}{2}}^{\frac{1}{2}} f(x) \,dx &= \int_{0}^{\frac{1}{2}} x \,dx.\\
a_{0} = \left[ \frac{x^{2}}{2} \right]_{0}^{\frac{1}{2}} = \frac{(\frac{1}{2})^{2}}{2} - 0 &=  \frac{1}{8}\\
\end{align*}
$$
$a_{n}$:
$$
a_{n} = 2 \int_{0}^{\frac{1}{2}} x \cos(2 \pi n x) \,dx
$$
Jeg bruger integration i dele:
- $u = x$, så $du = dx$.
- $dv = \cos(2\pi n x) dx$, så $v = \frac{\sin(2\pi n x)}{2\pi n}$

Derfor bliver udtrykket nu givet ved:
$$
\begin{align*}
\int x \cos(2\pi n x) \, dx &=  \frac{x \sin(2\pi n x)}{2\pi n} - \int \frac{\sin(2\pi n x)}{2\pi n} dx\\
&=  \frac{x \sin(2\pi n x)}{2\pi n} + \frac{\cos(2\pi n x)}{(2\pi n)^2}
\end{align*}
$$
Nu indsætter jeg grænserne og husker 2 tallet udenfor integralet:
$$
\begin{align*}
&=  2 \left[ \frac{x \sin(2\pi n x)}{2\pi n} + \frac{\cos(2\pi n x)}{(2\pi n)^2} \right]_{0}^{1/2}\\
&=  2 \left( \frac{(1/2) \sin(\pi n)}{2\pi n} + \frac{\cos(\pi n)}{(2\pi n)^2} - 0 \right)
\end{align*}
$$
Siden $\sin(\pi n) = 0$, så forsvinder hele det første led:
$$
\begin{align*}
&=  2 \cdot \frac{\cos(\pi n)}{(4\pi^2 n^2)}\\
a_{n}&=  \frac{\cos(\pi n)}{2\pi^2 n^2}
\end{align*}
$$
$b_{n}$:
$$
b_n = 2 \int_{0}^{1/2} x \sin(2\pi n x) \,dx.
$$

Jeg bruger igen integration i dele:
- $u = x$, så $du = dx$.
- $dv = \sin(2\pi n x) \, dx$, så $v = -\frac{\cos(2\pi n x)}{2\pi n}$
$$
\begin{align*}
\int x \sin(2\pi n x) dx &=  -\frac{x \cos(2\pi n x)}{2\pi n} - \left(- \int \frac{\cos(2\pi n x)}{2\pi n} \, dx\right)\\
&=  -\frac{x \cos(2\pi n x)}{2\pi n} + \frac{\sin(2\pi n x)}{(2\pi n)^2}
\end{align*}
$$
Indsætter grænserne:
$$
b_{n} = 2 \left( -\frac{(\frac{1}{2}) \cos(\pi n)}{2\pi n} + \frac{\sin(\pi n)}{(2\pi n)^2} - 0 \right).
$$
Siden $\sin(\pi n) = 0$, så ligesom sidst så forsvinder et led, denne gang er det det andet led.
$$
\begin{align*}
b_{n} &=  -2 \cdot \frac{\cos(\pi n)}{4\pi n}\\
b_{n} &=  -\frac{\cos(\pi n)}{2\pi n}
\end{align*}
$$
Jeg samler alt det jeg har beregnet til at lave Fourier serien:
$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1}^{\infty} a_{n} \cos(2\pi n x) + \sum_{n=1}^{\infty} b_{n} \sin(2\pi n x)
$$
Indsætter:
$$
\begin{align*}
a_{0}&=  \frac{1}{8}\\
a_{n}&=  \frac{\cos(\pi n)}{2\pi^2 n^2}\\
b_{n} &=  -\frac{\cos(\pi n)}{2\pi n}
\end{align*}
$$
$$
\begin{align*}
\frac{\frac{1}{8}}{2} + \sum_{n=1}^{\infty} \frac{\cos(\pi n)}{2\pi^2 n^2} \cos(2\pi n x) + \sum_{n=1}^{\infty} -\frac{\cos(\pi n)}{2\pi n} \sin(2\pi n x)\\
\frac{1}{16} + \sum_{n=1}^{\infty} \frac{\cos(\pi n)}{2\pi^2 n^2} \cos(2\pi n x) - \sum_{n=1}^{\infty} \frac{\cos(\pi n)}{2\pi n} \sin(2\pi n x)
\end{align*}
$$
Hvis det skal stå ligesom i bogen skal jeg indsætte de første par n-værdier og $\pi$ sættes udenfor parentesen. For udtrykket med cosinus er $\pi^{2}$ i nævneren af brøken, mens det er $\pi$ for sinus udtrykket. Da cosinus er en symmetrisk funktion, så hver gang n er et lige tal for cosinus udtrykket vil integralet udligne hinanden på intervallet $[0, \frac{1}{2}]$. Da $\cos(2 \pi) = 1$:
$$
\begin{align*}
\frac{1}{16} - \frac{1}{\pi^{2}} \left(\cos(2\pi x))+ \frac{1}{9} \cos(6 \pi x) + \frac{1}{25} \cos(10 \pi x) + \dots\right) \\
+ \frac{1}{\pi} \left(\frac{1}{2} \sin\left(2\pi x\right) - \frac{1}{4} \sin(4 \pi x) + \frac{1}{6} \sin(6 \pi x) - \frac{1}{8} \sin(8 \pi x) + - \dots\right)
\end{align*}
$$
## Opgave 11.2.29 Find (a) the Fourier cosine series, (b) the Fourier sine series. Sketch f(x) and its two periodic extensions. Show the details.
Find (a) the Fourier cosine series, (b) the Fourier sine series. Sketch f(x) and its two periodic extensions. Show the details.
$f(x)=\sin(x), \quad (0<x<\pi)$

(a) Fourier cosinus serien:

Fourier cosinus serien er givet ved:
$$
f(x) = \frac{a_0}{2} + \sum_{n=1}^{\infty} a_n \cos(n x),
$$
Hvor:

$$
\begin{align*}
a_{0} &=  \frac{2}{\pi} \int_{0}^{\pi} \sin (x) \,dx\\
a_{n} &=  \frac{2}{\pi} \int_0^{\pi} \sin (x) \cos(n x) \,dx
\end{align*}
$$
Jeg troede at ulige funktioner såsom $\sin(x)$ så ville $a_{0}$ og $a_{n}$ være 0 begge to og dermed ville den ikke kunne beskrives med en cosinusrække, men jeg prøver at beregne det, idet bogen giver et andet svar end 0.

Jeg starter med at beregne $a_{0}$:

$$
\begin{align*}
a_{0} &=  \frac{2}{\pi} \int_{0}^{\pi} \sin (x) \,dx\\
&=  \frac{2}{\pi} [-\cos (x)]_0^{\pi}\\
&=  \frac{2}{\pi} (-\cos (\pi) + \cos (0))\\
\text{Da } \cos(0) &= 1 \text{ og} \cos(\pi) = -1\\
&=  \frac{2}{\pi} (-(-1) + 1) = \frac{4}{\pi}\\
a_{0}&= \frac{4}{\pi}
\end{align*}
$$
Nu beregner jeg $a_{n}$:
$$
a_{n}= \frac{2}{\pi} \int_{0}^{\pi} f(x) \cos(nx) \, dx
$$
Der findes en trigonometrisk identitet der ser således ud:
$$
\sin (x) \cos(n x) = \frac{1}{2} [\sin((n + 1)x) + \sin((n-1)x)]
$$
Så det udtryk integrerer jeg:

$$
\begin{align*}
a_{n} &=  \frac{2}{\pi} \int_{0}^{\pi} \frac{1}{2} [\sin((n + 1)x) + \sin((n-1)x)] \, dx\\
&= \frac{2}{\pi}\cdot \frac{1}{2} \int_{0}^{\pi}[\sin((n + 1)x) + \sin((n-1)x)] \, dx\\
&= \frac{1}{ \pi} \int_{0}^{\pi}[\sin((n + 1)x) + \sin((n-1)x)] \, dx\\
&= \frac{1}{\pi} \left(\int_{0}^{\pi}\sin\left((n + 1)x\right) + \int_{0}^{\pi}\sin((n-1)x)\right)\\
\end{align*}
$$
Jeg starter med det første integrale:
$$
\int_{0}^{\pi}\sin((n + 1)x)
$$
Jeg bruger formlen:
$$
\int \sin(kx) \, dx = - \frac{1}{k} \cos(kx)
$$
$$
\begin{align*}
\int_{0}^{\pi}\sin((n + 1)x)&= \left[- \frac{1}{n+1} \cos((n+1)x))\right]_{0}^{\pi}\\
&= - \frac{1}{n+1}\cos((n+1)\pi) - \left(- \frac{1}{n+1}\cos((n+1)0)\right)\\
\text{Da } \cos(0) &= 1\\
&= - \frac{1}{n+1}\cos((n+1)\pi) + \frac{1}{n+1}\\
&= - \frac{1}{n+1}\cos((n+1)\pi)-1)\\
\text{Da } \cos((n+1)\pi) = (-1)^{n+1}:\\
&= - \frac{1}{n+1}((-1)^{n+1}-1)\\
&= \frac{2(-1)^{n+1}}{n+1}\\
\end{align*}
$$
Jeg får altså:
$$
\int_{0}^{\pi}\sin((n + 1)x)= \frac{2(-1)^{n+1}}{n+1}
$$
Det samme kan gøres for $\int_{0}^{\pi}\sin((n - 1)x)$
Hvor svaret så er på samme form, men med et negativt fortegn ved tælleren og ved eksponenten:
$$
\int_{0}^{\pi}\sin((n - 1)x) = \frac{2(-1)^{n-1}}{n-1}
$$
Derfor når jeg husker $\frac{\pi}{1}$ så er $a_{n}$ givet ved:
$$
a_{n}= \frac{1}{\pi} \cdot \left(\frac{2(-1)^{n+1}}{n+1} + \frac{2(-1)^{n-1}}{n-1}\right)
$$
Her ses det at n ikke må være 1, da det så vil resultere i division med 0.
$$
\frac{1}{\pi} \cdot \left(\frac{2(-1)^{n+1}}{n+1} + \frac{2(-1)^{n-1}}{n-1}\right), \quad n>1
$$
Hvis jeg indsætter $n=2$:
$$
\begin{align*}
&= \frac{1}{\pi} \cdot \left(\frac{2(-1)^{2+1}}{2+1} + \frac{2(-1)^{2-1}}{2-1}\right)\\
&= \frac{1}{\pi} \cdot \left( \frac{-2}{3} + \frac{-2}{1}\right)\\
&= \frac{1}{\pi} \cdot \left(\frac{-8}{3}\right)\\
&= \frac{-8}{3 \pi}
\end{align*}
$$
Det giver altså ikke 0, selvom bogen påstår at det gør.

Hvis jeg indsætter $n=3$:
$$
\begin{align*}
&= \frac{1}{\pi} \cdot \left(\frac{2(-1)^{3+1}}{3+1} + \frac{2(-1)^{3-1}}{3-1}\right)\\
&= \frac{1}{\pi} \cdot \left( \frac{2}{4} + \frac{2}{2}\right)\\
&= \frac{1}{\pi}\left(\frac{3}{2}\right)\\
&= \frac{3}{2\pi}\\
\end{align*}
$$
Det giver heller ikke 0.
Bogens svar er:
$$
\frac{2}{\pi} - \frac{4}{\pi} \left(\frac{1}{1\cdot 3 } \cos(x)+\frac{1}{3\cdot 5 } \cos(3x)+\frac{1}{5\cdot 7 } \cos(5x)+ \dots\right)
$$
Hvilket betyder at bogen påstår at hver gang n er et lige tal så bliver udtrykket 0.

(b) Fourier Sine Series

For at finde Fourier sinus serien, så skal jeg bruge formlen:
$$
f(x) = \sum_{n=1}^{\infty} b_n \sin(n x)
$$
$$
b_n = \frac{2}{\pi} \int_0^{\pi} \sin (x) \sin(n x) \,dx
$$
Jeg bruger produkt-identiteten for sinus:  

$$
\sin(A) \sin(B) = \frac{1}{2} \left[ \cos(A - B) - \cos(A + B) \right]
$$
Her er $A = x$ og $B = n x$:
$$
\sin(x) \sin(n x) = \frac{1}{2} \left[ \cos((n-1)x) - \cos((n+1)x) \right]
$$
Sætter ind i integralet:
$$
= \int_0^{\pi} \frac{1}{2} \left[ \cos((n-1)x) - \cos((n+1)x) \right] dx
$$
Jeg opdeler integralet:
$$
I_n = \frac{1}{2} \int_0^{\pi} \cos((n-1)x) \,dx - \frac{1}{2} \int_0^{\pi} \cos((n+1)x) \,dx
$$
Jeg bruger formlen:

$$
\int \cos(kx) \,dx = \frac{\sin(kx)}{k}
$$
For det første integral:

$$
\begin{align*}
\int_0^{\pi} \cos((n-1)x) \,dx &=  \left[ \frac{\sin((n-1)x)}{n-1} \right]_0^{\pi}\\
&=  \frac{\sin((n-1)\pi)}{n-1} - \frac{\sin(0)}{n-1}
\end{align*}
$$
Da $\sin(k\pi) = 0$ for ethvert heltal $k$, bliver dette **nul**. Det samme gælder for det andet integral. Så for $n \neq 1$ bliver integralet 0.

For $n = 1$:

$$
\int_0^{\pi} \sin(x) \sin(x) \,dx = \int_0^{\pi} \sin^2(x) \,dx
$$
Jeg bruger identiteten:

$$
\begin{align*}
\sin^{2}(x) &=  \frac{1 - \cos(2x)}{2}\\
&=  \int_{0}^{\pi} \frac{1 - \cos(2x)}{2} \,dx\\
&=  \frac{1}{2} \int_{0}^{\pi} 1 \,dx - \frac{1}{2} \int_{0}^{\pi} \cos(2x) \,dx
\end{align*}
$$
Det første integral:
$$
\frac{1}{2} \int_0^{\pi} 1 \,dx = \frac{\pi}{2}
$$
Det andet integral:
$$
-\frac{1}{2} \int_0^{\pi} \cos(2x) \,dx = -\frac{1}{2} \left[ \frac{\sin(2x)}{2} \right]_0^{\pi} = 0
$$
Så når $n=1$:
$$
\int_{0}^{\pi} \sin^{2}(x) \,dx =\frac{\pi}{2}
$$
Dvs.
$$
\int_0^{\pi} \sin (x) \sin(n x) \,dx =
\begin{cases}
\frac{\pi}{2}, & n = 1, \\
0, & n \neq 1.
\end{cases}
$$
Dermed bliver:
$$
b_1 = \frac{2}{\pi} \cdot \frac{\pi}{2} = 1, \quad b_n = 0 \text{ for } n \neq 1.
$$
Da $\sin\left(\frac{\pi}{2}\right)= 1$ så er Fourier sinus serien givet ved:
$$
f(x) = \sin x.
$$
![[11.2.29 billede.png]]
## Opgave 11.3.13 Find the steady-state oscillations of $y'' + cy' + y = r(t)$ with $c > 0$ and $r(t)$ as given. Note that the spring constant is $k=1$. Show the details.
Find the steady-state oscillations of $y'' + cy' + y = r(t)$ with $c > 0$ and $r(t)$ as given. Note that the spring constant is $k=1$. Show the details.
$$r(t) = \sum_{n=1}^{N} \left( a_n \cos(n t) + b_n \sin(n t) \right)$$
Jeg bruger formlen:
$$
y_n'' + c y_n' + y_n = a_n \cos(n t) + b_n \sin(n t)
$$
Jeg skal beregne:

$$
\begin{align*}
y_{n} &=  A_{n} \cos(n t) + B_{n} \sin(n t)\\
y_{n}' &=  -A_{n} n \sin(n t) + B_{n} n \cos(n t)\\
y_{n}'' &=  -A_{n} n^2 \cos(n t) - B_{n} n^2 \sin(n t)
\end{align*}
$$
Hvis jeg så substituere alle værdierne ind i differentialligningen får jeg dette lange udtryk:
$$
\begin{align*}
(-A_n n^2 \cos(n t) - B_n n^2 \sin(n t)) + c (-A_n n \sin(n t) + \\
B_n n \cos(n t)) + (A_n \cos(n t) + B_n \sin(n t)) = a_n \cos(n t) + b_n \sin(n t)
\end{align*}
$$
Så er det bare at gå i gang med at reducere/gruppere udtryk:
$$
(A_n (1 - n^2) + B_n c n) \cos(n t) + (B_n (1 - n^2) - A_n c n) \sin(n t) = a_n \cos(n t) + b_n \sin(n t)
$$
Dvs. $\cos(n t)$:
   $$
   A_{n} (1 - n^{2}) + B_{n} c n = a_{n}
   $$
$\sin(n t)$:
   $$
   B_{n} (1 - n^{2}) - A_{n} c n = b_{n}
   $$
Nu skal jeg så isolere $A_{n}$ og $B_{n}$:
Her kan jeg bruge kramers metode som Niels introducerede i timen.
$$
A_{n}= \frac{\det\left(\begin{bmatrix}
1-n^{2} & nc  \\  -nc & -n^{2}+1
\end{bmatrix}\right)}{\det(A)}
$$
Jeg starter med at regne $\det(A)$:
$$
\begin{align*}
\begin{bmatrix}
1-n^{2} & nc  \\  -nc & -n^{2}+1
\end{bmatrix} \begin{bmatrix}A_{n} \\
B_{n}\end{bmatrix} &= \begin{bmatrix}a_{n} \\
b_{n}\end{bmatrix}
\end{align*}
$$
Her er:
$$
\begin{align*}
A &=  \begin{bmatrix}
1-n^{2} & nc  \\  -nc & -n^{2}+1
\end{bmatrix}\\
B&= \begin{bmatrix}a_{n} \\
b_{n}\end{bmatrix}
\end{align*}
$$
$$
\begin{align*}
\det(A) &=  (1-n^{2})(1-n^{2}) - (-cn)(cn)\\
&=  (1-n^{2})^{2} - c^{2}n^{2}
\end{align*}
$$
Nu regner jeg $\det\left(\begin{bmatrix} 1-n^{2} & nc  \\  -nc & -n^{2}+1 \end{bmatrix}\right)$ :
$$
\begin{align*}
\\
\det\left(\begin{bmatrix}
1-n^{2} & nc  \\  -nc & -n^{2}+1
\end{bmatrix}\right)&= a_{n}(1-n^{2}) - b_{n}cn\\
A_{n} \text{ bliver derfor:}\\
A_{n}&= \frac{a_{n}(1-n^{2}) - b_{n}cn}{(1-n^{2})^{2} - c^{2}n^{2}}
\end{align*}
$$
Nu gør jeg det samme for $B_{n}$:
$$
\begin{align*}
B_{n}&= \frac{\det\left(\begin{bmatrix}(1-n^{2}) & a_{n} \\
-cn  & b_{n}\end{bmatrix}\right)}{\det(A)}\\
\text{Jeg har allerede regnet } \det(A).\\
\det\left(\begin{bmatrix}(1-n^{2}) & a_{n} \\
-cn  & b_{n}\end{bmatrix}\right) &= (1-n^{2})b_{n}- (-cn)a_{n}\\
&= (1-n^{2})b_{n}+cna_{n}\\
B_{n}&= \frac{(1-n^{2})b_{n}+cna_{n}}{(1-n^{2})^{2} - c^{2}n^{2}} 
\end{align*}
$$
$$
\begin{align*}
A_{n} &=  \frac{a_{n} (1 - n^{2}) - b_{n} c n}{(1 - n^{2})^{2} - c^{2} n^{2}}\\
B_{n} &=  \frac{b_{n} (1 - n^{2}) + a_{n} c n}{(1 - n^{2})^{2} - c^{2} n^{2}}
\end{align*}
$$
Den generelle steady-state løsning er givet ved formlen:
$$
y_{\text{ss}}(t) = \sum_{n=1}^{N} \left( A_n \cos(n t) + B_n \sin(n t) \right)
$$
Hvor:
$$
A_n = \frac{a_n (1 - n^2) - b_n c n}{(1 - n^2)^2 + c^2 n^2}, \quad
B_n = \frac{b_n (1 - n^2) + a_n c n}{(1 - n^2)^2 + c^2 n^2}
$$
Hvilket jeg så kan indsætte:
$$
y_{\text{ss}}(t) = \sum_{n=1}^{N} \left( \frac{a_n (1 - n^2) - b_n c n}{(1 - n^2)^2 + c^2 n^2} \cos(n t) + \frac{b_n (1 - n^2) + a_n c n}{(1 - n^2)^2 + c^2 n^2} \sin(n t) \right)
$$
Svaret i bogen er givet ved:
$$
y = \sum_{n \, = \, 1} ^{N} (A_{n}\cos(nt) + B_{n}\sin(nt)), A_{n}= \frac{1(1 -n^{2}) a_{n}- nb_{n}c}{D_{n}}
$$
# Lektion 3:
## 11.7.7 Represent $f(x)$ as an integral
Represent $f(x)$ as an integral
$$
f(x) = \cases{1 \text{ if } & 0 < x < 1\\ 0 \text{ if } & x>1}
$$

$$
\begin{align*}
\text{Jeg bruger formlerne:}\\
f(x) = \int_{0}^{\infty}A(w) \, \cos(wx) \, dw\\
A(w) =  \frac{2}{\pi}\int_{0}^{\infty}f(v) \, \cos(wv) \, dv
\end{align*}
$$
Funktionen der er givet i opgaven går til 1 og derfor bliver integralet:
$$
\begin{align*}
A(w) &=  \frac{2}{\pi} \int_{0}^{1} f(v) \cos(wv) \, dv\\
\text{Kæderegel:}\\
\int \cos(wv) \, dv &= \frac{\sin(wv)}{w}\\
\frac{2}{\pi}\left[\frac{\sin(wv)}{w}\right]_{0}^{1} &= \frac{2}{\pi} \frac{\sin(w)}{w}-\frac{\sin(0)}{w}\\
\text{Da } \sin(0) &= 0:\\
&= \frac{2}{\pi} \frac{\sin(w)}{w}\\
\text{Substituerer i f(x):}\\
f(x)&= \int_{0}^{\infty} \frac{2}{\pi} \frac{\sin(w)}{w} \cos(wx) \, dw\\
\text{Derfor bliver svaret:}\\
\int_{0}^{\infty} \frac{2}{\pi} \frac{\sin(w)}{w} \cos(wv) \, dw &= \frac{\pi}{2}, \quad 0>v>1
\end{align*}
$$

## 11.7.17 Represent $f(x)$ as an integral
Represent $f(x)$ as an integral
$$
f(x) = \cases{1 \text{ if } & 0 < x < 1\\ 0 \text{ if } & x>1}
$$
Jeg bruger formlerne:
$$
\begin{align*}
f(x) = \int_{0}^{\infty}B(w) \, \sin(wx) \, dw\\
B(w) =  \frac{2}{\pi}\int_{0}^{\infty}f(v) \, \sin(wv) \, dv
\end{align*}
$$
Da funktionen går op til 1:
$$
\begin{align*}
B(w) &=   \frac{2}{\pi}\int_{0}^{1}f(v) \, \sin(wv) \, dv\\
\text{Kæderegel:}\\
\int \sin(wv) \, dv &= \frac{-\cos(wv)}{w}\\
\frac{2}{\pi} \left[\frac{-\cos(wv)}{w}\right]_{0}^{1} &= \frac{2}{\pi}- \frac{\cos(1)}{w} + \frac{\cos(0)}{w}\\
\text{Da } \cos(0)&= 1:\\
&= \frac{2}{\pi}\frac{-\cos(1)}{w} + \frac{1}{w}\\
&= \frac{2}{\pi} \frac{1-\cos(w)}{w}\\
\text{Derfor bliver svaret:}\\
f(x)&= \int_{0}^{\infty} \frac{2}{\pi} \frac{1-\cos(w)}{w} \sin(wv) \, dw, \quad 0<v<1
\end{align*}
$$

## 11.9.3 **Fourier transforms by integration**.
Find the Fourier transform of $f(x)$ (without using table III in Sec. 11.10) Show the details.
**Fourier transforms by integration**.
Find the Fourier transform of $f(x)$ (without using table III in Sec. 11.10) Show the details.
$$
f(x)=\cases{1 \text{ if } a<x<b \\ 0 \text{ otherwise}}
$$
Jeg bruger formlerne:
$$
\begin{align*}
\int_{-\infty}^{\infty}f(x) e^{-iwx} \, dx\\
\mathcal{F} (w) &=  \int_{a}^{b} e^{-iwx} \, dx\\
\int e ^{-iwx}\, dx &= \frac{e^{-iwx}}{-iw}\\
\text{Indsætter grænserne i opgaven}\\
&= \left[\frac{e^{-iwx}}{-iw}\right]_{a}^{b}\\
&= \frac{e^{-iwb} - e^{-iwa}}{-iw}\\
\text{Siden } i=\sqrt{-1}\\
\frac{1}{i}=-i\\
\frac{1}{-i}=i\\
&= \frac{i(e^{-iwb} - e^{-iwa})}{w}\\
\text{Da bogen bruger faktoren } \frac{1}{\sqrt{2 \pi}}:\\
&= \frac{i(e^{iwb} - e^{iwa})}{w \sqrt{2\pi}}
\end{align*}
$$
## 11.9.5 Find the Fourier transform of f(x) (without using Table III in Sec. 11.10). Show details.
Find the Fourier transform of f(x) (without using Table III in Sec. 11.10). Show details.

$$
f(x) = \cases{e^{x}, \quad \text{if } -a < x <a \\ 0, \quad \text{ otherwise} }
$$
Fourier transformationen af $f(x)$ er givet ved formlen:
$$
F(\omega) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} f(x) e^{-i\omega x} \,dx.
$$
Opgavens funktion er:

$$
f(x) =
\begin{cases}
e^x, & -a < x < a, \\
0, & \text{otherwise},
\end{cases}
$$
Derfor bliver Fourier transformationen:

$$
F(\omega) = \frac{1}{\sqrt{2\pi}} \int_{-a}^{a} e^x e^{-i\omega x} \,dx.
$$
Ganger exponenterne og faktoriserer x:

$$
F(\omega) = \frac{1}{\sqrt{2\pi}} \int_{-a}^{a} e^{(1 - i\omega)x} \,dx.
$$

Siden integralet af $e^{\lambda x}$ er:

$$
\int e^{k x} \,dx = \frac{e^{k x}}{k},
$$
I dette tilfælde er $k = 1 - i\omega$:

$$
F(\omega) = \frac{1}{\sqrt{2\pi}} \left[ \frac{e^{(1 - i\omega)x}}{1 - i\omega} \right]_{-a}^{a}.
$$
$$
F(\omega) = \frac{1}{\sqrt{2\pi}} \left( \frac{e^{(1 - i\omega)a} - e^{(1 - i\omega)(-a)}}{1 - i\omega} \right).
$$

Faktoriserer $e^{-a}$ 

$$
F(\omega) = \frac{1}{\sqrt{2\pi}} \cdot \frac{e^{(1 - i\omega)a} - e^{-(1 - i\omega)a}}{1 - i\omega}.
$$

Resultatet bliver:

$$
F(\omega) = \frac{e^{(1 - i\omega)a} - e^{-(1 - i\omega)a}}{\sqrt{2\pi} (1 - i\omega)}.
$$
# Lektion 4:
## Opgave fra Niels: Løs: $\frac{\delta u}{\delta x} = 2 \frac{\delta u}{\delta t}+u$ hvor $u(x,0) = 6e^{-3x}$
Løs: $\frac{\delta u}{\delta x} = 2 \frac{\delta u}{\delta t}+u$ hvor $u(x,0) = 6e^{-3x}$

$$
\begin{align*}
\text{Separerer variable: }\\
u(x,t) &= X(x) T(t)\\
X'(x)T(t) &= 2X(x)T'(t)+X(x)T(t)\\
\text{Dividerer med } X(x)T(t)\\
\frac{X'(x)}{X(x)} &= 2\frac{T'(t)}{T(t)}+1\\
\frac{X'(x)}{X(x)}-1 &= 2\frac{T'(t)}{T(t)}\\
\text{Sætter de to ligmed en konstant}\\
\frac{X'(x)}{X(x)}-1&= k, \quad 2\frac{T'(t)}{T(t)} = k\\
X'(x) &= (k+1)X(x)\\
T'(t)&= \frac{k}{2}T(t)\\
X(x)&= c_{1}e^{(k+1)x}\\
T(t) &= c_{2}e^{\frac{k}{2}t}\\
\text{Så }\\
c&= c_{1}c_{2}\\
u(x,t) = ce^{(k+1)x}e^{\frac{k}{2}t}&= c e^{(k+1)x + \frac{k}{2}t}\\
\text{Jeg bruger nu startbetingelsen}\\
u(x,0) &=  6e^{-3x}\\
6e^{-3x} &= c e^{(k+1)x}\\
\text{Da } k+1 &=  -3\\
k&= -4\\
u(x,t)&= ce ^{(-4+1)x+ \frac{-4}{2}t}\\
u(x,t)&= ce ^{-3x-2t}\\
c&= 6\\
u(x,t)&= 6e ^{-3x-2t}\\
\end{align*}
$$

## 12.1.3 Wave equation (1) with suitable c. $u = \cos(4t) \sin(2x)$ Separerer variable:
$u = \cos(4t) \sin(2x)$
Separerer variable:
$$
\begin{align*}
u(x,t) = \cos(4t) \sin(2x)\\
\frac{\delta u}{\delta t} &= -4 \sin(4t) \sin(2x)\\
\frac{\delta^{2} u}{\delta t^{2}} &= -16 \cos(4t) \sin(2x)\\
\\
\frac{\delta u}{\delta x} &= \cos(4t) 2\cos(2x)\\
\frac{\delta^{2} u}{\delta x^{2}} &= -4\cos(4t)\sin(2x)\\
\text{Substituerer i bølgeligningen (1):}\\
\frac{\delta^{2} u}{\delta t^{2}}&= c^{2}\frac{\delta^{2} u}{\delta x^{2}}\\
-16 \cos(4t) \sin(2x)&= c^{2}(-4\cos(4t)\sin(2x))\\
\text{Så længe } \cos(4t) \sin(2x) &\neq 0\\
-16&= -4c^{2}\\
4&= c^{2}\\
c&= 2\\
\end{align*}
$$

## 12.3.5 Find $u(x,t)$ for the string of length $L = 1$ and $c^{2}= 1$ when the initial velocity is zero and the initial deflection with small $k$ (say 0.01) is as follows. Sketch or graph $u(x,t)$ as in Fig. 291 in the text.
Find $u(x,t)$ for the string of length $L = 1$ and $c^{2}= 1$ when
the initial velocity is zero and the initial deflection with small $k$ (say 0.01) is as follows. Sketch or graph $u(x,t)$ as in Fig. 291 in the text.

$k \sin(3 \pi x)$

Hvis "inital deflection" dvs. start afbøjningen er med en lille værdi af k:
$$
u(x,0) = k \cdot \sin(3 \pi x)
$$
Hvis "initial velocity", dvs. starthastigheden er 0, så må det betyde at:
$$
\frac{\delta u}{\delta t} (x,0) = 0
$$
Den generelle formel:
$$
\begin{align*}
u(x,t) &= \sum_{n \, = \, 1} ^{\infty} (A_{n} \cos(n \pi t) + B_{n} \sin(n \pi t)) \sin(n \pi x)\\
\text{Indsætter startbetingelser (afbøjning):}\\
u(x,0) = \sum_{n \, = \, 1} ^{\infty} A_{n} \cos(n \pi t) &=  k \cdot \sin
(3 \pi x)\\
\text{Så:} \\
A_{n}&= \cases{k, \quad n=3\\
0, \quad \text{ellers}}\\
\end{align*}
$$
Før jeg kan indsætte startbetingelserne for hastighed skal jeg først regne den partielle afledte mht. t:
$$
\begin{align*}
\frac{\delta u}{\delta t} (x,t)&= \sum_{n \, = \, 1} ^{\infty} (-A_{n} n \pi \sin (n \pi t) + B_{n} n \pi \cos(n \pi t) \sin (n \pi t ))\\
\text{Indsætter startbetingelser (hastighed):}\\
\frac{\delta u}{\delta t} (x,0) &= \sum_{n \, = \, 1} ^{\infty} (-A_{n} n \pi \sin (n \pi 0) + B_{n} n \pi \cos(n \pi 0) \sin (n \pi 0)) \\
\text{Da } \sin(0) = 0 \text{ og } \cos(0) &= 1\\
&= \sum_{n \, = \, 1} ^{\infty}  0 + B_{n} n \pi \cdot 1 \cdot 0\\
&= 0\\
\text{Så } B_{n}&= 0 \text{ for alle n-værdier}\\
\end{align*}
$$
Jeg har nu beregnet at:
$$
\begin{align*}
A_{n}= k \cdot \sin(3 \pi x)\\
B_{n} = 0
\end{align*}
$$
Da den generelle løsning var:
$$
u(x,t) = \sum_{n \, = \, 1} ^{\infty} (A_{n} \cos(n \pi t) + B_{n} \sin(n \pi t)) \sin(n \pi x)
$$
Så indsætter jeg mine værdier for n=3:
$$
u(x,t) = (\underbrace{A_{n}}_{k \cdot \sin(3 \pi x)} \cos(3 \pi t) + \underbrace{B_{n} \sin(n \pi t)) \sin(n \pi x)}_{0}
$$
$$
\begin{align*}
\\
u(x,t) &= k \cdot \cos(3 \pi t) \sin(3 \pi x)\\
\text{Hvis jeg så indsætter } k&= 0.01\\
u(x,t) &= 0.01 \cdot \cos(3 \pi t) \sin(3 \pi x)\\
\end{align*}
$$
Hvis jeg tegner den når $t=0$, så bliver $\cos(n \pi 0) = 0$:
![[12.3.5 billede.png]]
## 12.3.9 Opgaven er givet ved den tegnede funktion: 
Opgaven er givet ved den tegnede funktion: ![[12.3.9.png]]
Ud fra grafen kan det ses at:
$$
u(x,0) = \cases{0.2 x, \quad 0 \leq x \leq 0.5, \\ 0.2 (1-x), \quad 0.5 \leq x \leq 1}
$$
Siden funktionen starter i (0,0) tyder det på at funktionen kun består af en serie af sinus funktioner.
$$
u(x,t) = \sum_{n \, = \, 1} ^{\infty} A_{n} \cos(n \pi t)\sin(n \pi x)
$$
Da $\cos(0) = 1$:
$$
u(x,0) = \sum_{n \, = \, 1} ^{\infty} A_{n} \sin(n \pi x)
$$
Formlen for $A_{n}$ er:
$$
A_{n}= \frac{2}{L} \int_{0}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx
$$
Siden $L=1$:
$$
A_{n}= 2 \int_{0} ^{1} u (x,0) \sin(n \pi x) \, dx
$$
Jeg beregner nu integralet:
$$
\begin{align*}
2 \int_{0} ^{1} u (x,0) \sin(n \pi x) &= 2 \left(\int_{0}^{0.5} 0.2 x \sin(n \pi x) \, dx + \int_{0.5}^{1} 0.2 (1-x) \sin(n \pi x) \, dx\right)\\
\text{Regner det første integrale:}\\
\int_{0}^{0.5} 0.2 x \sin(n \pi x) \, dx\\
\text{Jeg bruger integration i dele:}\\
\int u \, dv &=  uv - \int v \, du\\
u = x, du &=  dx\\
dv = \sin(n \pi x) \, dx, v &= - \frac{\cos(n \pi x)}{nx}\\
&= 0.2 \left[x\cdot \left(- \frac{\cos(n \pi x)}{n\pi}\right) - \int \left(- \frac{\cos(n \pi x)}{n \pi}\right) \, dx\right]_{0}^{0.5}\\
\text{Hvor:}\\
\int \left(- \frac{\cos(n \pi x)}{n \pi}\right) &=  - \frac{\sin(n \pi x)}{(n \pi)^{2}}\\
\text{Derfor bliver udtrykket:}\\
&= 0.2 \left[x\cdot \left(- \frac{\cos(n \pi x)}{n\pi}\right) + \frac{\sin(n \pi x)}{(n \pi)^{2}} \right]_{0}^{0.5}\\
&= 0.2 \cdot \left(0.5 \cdot \left(- \frac{\cos(n \pi 0.5)}{n\pi}\right) + \frac{\sin(n \pi 0.5)}{(n \pi)^{2}}-\left(0\cdot \left(- \frac{\cos(n \pi 0)}{n\pi}\right) + \frac{\sin(n \pi 0)}{(n \pi)^{2}}\right)\right)\\
&= 0.2 \cdot \left(0.5 \cdot \left(- \frac{\cos(n \pi 0.5)}{n\pi}\right) + \frac{\sin(n \pi 0.5)}{(n \pi)^{2}}-\left(\frac{\sin(n \pi 0)}{(n \pi)^{2}}\right)\right)\\
\text{Da } \sin(0) &=  0 \\
&= 0.2 \cdot \left(0.5 \cdot \left(- \frac{\cos(n \pi 0.5)}{n\pi}\right) + \frac{\sin(n \pi 0.5)}{(n \pi)^{2}}\right)\\
&= 0.2 \cdot \left(- \frac{0.5\cos(n \pi 0.5)}{n\pi} + \frac{\sin(n \pi 0.5)}{(n \pi)^{2}}\right)\\
\end{align*}
$$
Nu til det andet integrale:
$$
\begin{align*}
\int_{0.5}^{1} 0.2 (1-x) \sin(n \pi x) \, dx\\
\text{Jeg bruger integration i dele:}\\
\int u \, dv &=  uv - \int v \, du\\
u = 1-x, du &=  -dx\\
dv = \sin(n \pi x), v&= - \frac{\cos(n \pi x) }{n \pi}\\
&= 0.2 \left[1-x \cdot \left(- \frac{\cos(n \pi x)}{n \pi}\right)-  \int \left(- \frac{\cos(n \pi x)}{n \pi}\right) \, (-dx) \right]_{0.5}^{1}\\
\text{Udregner integralet}\\
\int - \frac{\cos(n \pi x)}{n \pi} \, (-dx) &= \int \frac{\cos(n \pi x)}{n \pi} \, dx \\
&= \frac{\sin(n \pi x) }{(n \pi )^{2}}\\
\text{Derfor bliver udtrykket}\\
&= 0.2 \left[(1-x) \cdot \left(- \frac{\cos(n \pi x)}{n \pi}\right) +\frac{\sin(n \pi x) }{(n \pi )^{2}}\right]_{0.5}^{1}\\
&= 0.2 \left[- \frac{ (1-x)\cos(n \pi x)}{n \pi} +\frac{\sin(n \pi x) }{(n \pi )^{2}}\right]_{0.5}^{1}\\
&= 0.2\left(-  \frac{(0) \cos(n \pi 1)}{n \pi} +\frac{\sin(n \pi 1)}{(n \pi)^{2}} - \left(- \frac{ (0.5)\cos(n \pi 0.5)}{n \pi} +\frac{\sin(n \pi 0.5) }{(n \pi )^{2}}\right)\right)\\
&= 0.2\left(0 + \frac{\sin(n \pi 1)}{(n \pi)^{2}} - \left(- \frac{ (0.5)\cos(n \pi 0.5)}{n \pi} +\frac{\sin(n \pi 0.5) }{(n \pi )^{2}}\right)\right)\\
\text{Da } \sin(n \pi) &= 0\\
&= 0.2\left(\frac{ (0.5)\cos(n \pi 0.5)}{n \pi} - \frac{\sin(n \pi 0.5) }{(n \pi )^{2}}\right)\\
\end{align*}
$$
Dermed bliver $A_{n}$:
$$
\begin{align*}
A_{n}&=  2 \int_{0} ^{1} u (x,0) \sin(n \pi x)\\
&= 2 \cdot \left(0.2 \cdot \left(- \frac{0.5\cos(n \pi 0.5)}{n\pi} + \frac{\sin(n \pi 0.5)}{(n \pi)^{2}}\right) + 0.2\left(\frac{ (0.5)\cos(n \pi 0.5)}{n \pi} - \frac{\sin(n \pi 0.5) }{(n \pi )^{2}}\right)\right)
\end{align*}
$$
Det hele går ud med hinanden og giver 0. Så jeg ved ikke hvordan man kommer frem til svaret i bogen:
$$
\frac{0.8}{\pi^{2}}\left(\cos (\pi t ) \sin (\pi x) - \frac{1}{9} \cos(3 \pi t) \sin\left(3 \pi x\right) + \frac{1}{25} \cos(5 \pi t) \sin(5 \pi x) - + \dots\right)
$$