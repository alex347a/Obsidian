- Lineær approximation
- fejlvurdering
  
- Taylorpolynomier
- fejlvurdering

## Lineær approximation
Def: Lineariseringen af en funktion f om punktet $x=a$ er givet ved en ny funktion $L(x)$
$$L(x)=f(a)+f'(a)(x-a)$$
### Eksempel 
Lineariser $f(x)=\sqrt{1+x}$ om $x=0$:
$$
\begin{align*}
a&= 0\\
f'(x)&= \frac{1}{2\cdot \sqrt{1+x}}\\
f'(0)&= \frac{1}{2}\\
L(x)&= f(a)+f'(a)(x-a)\\
&= 1+\frac{1}{2}(x-0)\\
&= 1+\frac{x}{2}
\end{align*}
$$
### Eksempel 2
Lineariser funktionen $g(x)=\frac{1}{x}$ om $x=\frac{1}{2}$:
$$
\begin{align*}
g'(x)&= -x^{-2}\\
g'\left(\frac{1}{2}\right)&= \frac{1}{\frac{1}{2}^{2}}=-4\\
g\left(\frac{1}{2}\right)&= 2\\
L(x)&= g\left(\frac{1}{2}\right)+g'\left(\frac{1}{2}\right)\left(x-\frac{1}{2}\right)\\
2-4\left(x-\frac{1}{2}\right)
\end{align*}
$$
### Eksempel 3 Bestem en approximation til $\sqrt{26}$ vha. linearisering af $f'(x)$ om $x=25$:
$$
\begin{align*}
f'(x)&= \frac{1}{2\sqrt{x}}\\
f'(25)&= \frac{1}{2\sqrt{25}}\\
&= \frac{1}{10}\\
f(25)&= \sqrt{25}\\
&= 5\\
L(x)&= f(25)+f'(25)(x-25)\\
&= 5+\frac{1}{10}(x-25)\\
f(26)\approx L(26)&= 5+\frac{1}{10}(26-25)\\
&= \underline{5.1}\\
\sqrt{26}&\approx 5,09902\space \text{via lommeregner}
\end{align*}
$$
## Fejlvurdering af linearisering:
E = sand værdi minus approximeret værdi.
$$
E(x)=\underbrace{f(x)}_{problem}-L(x)
$$
### Sætning: Hvis f''(t) eksisterer for alle t i et interval indeholdende a og x, så eksisterer der et punkt s mellem a og x, således at 
$$E(x)=\frac{f''(s)}{2}(x-a)^{2}$$
Vi regner hvad s er i værste tilfælde, for at se hvor stor fejlen kan være:
$$
\begin{align*}
E(x)&= f(x)-L(x)\\
&= f(x)-\left(f(a)+f'(a)(x-a)\right)\\
&= f(x)-f(a)-f'(a)x+f'(a)\cdot a\\
E'(x)&= f'(x)-0-f'(a)+0\\
&= f'(x)-f'(a)
\end{align*}
$$
### Den generaliserede middelværdisætning:
$$
\frac{f(b)-f(a)}{g(b)-g(a)}=\frac{f'(c)}{g'(c)}
$$
Hvor: $c\space \epsilon \space  [a,b]$

Anvendes på $E(x)$ og $g(x)=(x-a)^{2}, \left([a,t]\right)$

$$
\begin{align*}
\frac{E(t)-E(a)}{g(t)-g(a)}&= \frac{E'(c)}{g'(c)}, c\space \epsilon \space [a,t]\\
\frac{E(t)-E(a)}{(t-a)^{2}-(a-a)^{2}}&= \frac{f'(c)-f'(a)}{2(c-a)}\\
\frac{E(t)-0}{(t-a)^{2}}&= \frac{1}{2} \underbrace{\frac{f'(c)-f'(a)}{c-a}}_{Middelværdisætningen}\\
\frac{E(t)}{(t-a)^{2}}&= \frac{1}{2}f''(s)\\
E(t)&= \frac{f''(s)}{2}(t-a)^{2}\\
\text{hvor}\space s \space \epsilon \space ]a,c[\\
c \space \epsilon \space [a,t]\\
s \space \epsilon ]a,t[
\end{align*}
$$
Middelværdisætningen:
$$
\begin{align*}
f'(s)=\frac{f'(c)-f(a)}{c-a}\\
\text{på} \space s \space \epsilon \space ]a,c[\\
f''(s)=\frac{f'(c)-f'(a)}{c-a}
\end{align*}
$$

### Eksempel
$$
\begin{align*}
f(x)&= \cos(x)\space \text{om}\space  x=\frac{\pi}{6}\\
f'(x)&= -\sin(x)\\
f''(x)&= -\cos(x)\\
f\left(\frac{\pi}{6}\right)&= \cos\left(\frac{\pi}{6}\right)=\frac{\sqrt{3}}{2}\\
f'\left(\frac{\pi}{6}\right)&= -\sin\left(\frac{\pi}{6}\right)=-\frac{1}{2}\\
f''\left(\frac{\pi}{6}\right)&= -\cos\left(\frac{\pi}{6}\right)=-\frac{\sqrt{3}}{2}\\
L(x)=f\left(\frac{\pi}{6}\right)+f'\left(\frac{\pi}{6}\right)\left(x-\frac{\pi}{6}\right)\\
&= \frac{\sqrt{3}}{2}-\frac{1}{2}\left(x-\frac{\pi}{6}\right)\\
\cos\left(\frac{\pi}{5}\right)&\approx L\left(\frac{\pi}{5}\right)=\frac{\sqrt{3}}{2}
-\frac{1}{2}\left(\frac{\pi}{5}-\frac{\pi}{6}\right)=\frac{\sqrt{3}}{2}-\frac{1}{2}\left(\frac{\pi}{30}\right)\approx 0,8136655\\
\end{align*}
$$
Fejlvurdering:
$$
\begin{align*}
|E(x)|\leq \frac{|f''(s_{max})|}{2}(x-a)^{2}\\
&= \frac{\sqrt{3}}{2}\left(x-\frac{\pi}{6}\right)^{2}\\
&= \frac{\sqrt{3}}{4}\left(x-\frac{\pi}{6}\right)^{2}\\
\left|E\left(\frac{\pi}{5}\right)\right|\leq \frac{\sqrt{3}}{4}\left(\frac{\pi}{5}-\frac{\pi}{6}\right)^{2}&= \frac{\sqrt{3}}{4}\left(\frac{\pi}{30}\right)^{2}\approx 0,00475 \\
\text{fejlens fortegn:}\\
E(x)=\underbrace{\frac{f''(s)}{2}}_{negativt}\underbrace{(x-a)^{2}}_{positivt}\\
\text{f''(s) på} \left[\frac{\pi}{6},\frac{\pi}{5}\right] \text{bliver negativt}\\
E(x)=f(x)-L(x)<0\\
f(x)<L(x)\\
\text{Interval for sand værdi}:\\
[\underbrace{0,8136655-0,00475}_{\text{rund ned}};\underbrace{0,8136655}_{\text{rund op}}]\\\\

\end{align*}
$$
### Eksempel
L(x) for x=25 og $f(x)=\sqrt{x}$
Vurder fejlen for x=26?
$$
\begin{align*}
L(26)= 5.1, f'(x)&= \frac{1}{2\sqrt{x}}=\frac{1}{2}x^{\frac{-1}{2}}\\
f''(x)&= \frac{-1}{4}x^{\frac{-3}{2}}\\
f''(25)&= -\frac{1}{4}\cdot \frac{1}{25\sqrt{25}}=-\frac{1}{500}\\
E(x)&= \underbrace{\frac{f''s}{2}}_{negativ}\underbrace{(x-a)^{2}}_{positiv}\\
|E(x)|&\leq \frac{|f''(25)|}{2}(x-25)^{2}\\
&= \frac{\frac{1}{500}}{2}(x-25)^{2}\\
\frac{1}{1000}(x-25)^{2}\\
|E(26)|&\leq \frac{1}{1000}(26-25)^{2}=\frac{1}{1000}\\\\

\text{interval}:\\
\left[5.1-\frac{1}{1000}; 5.1\right]\\
[5.099;5.1]
\end{align*}
$$
## Taylorpolynomier
Et n'te grads taylorpolynomium udviklet om x=a:
$$
P_{n}(x)=f(a)+\frac{f'(a)}{1!}(x-a)^{1}+\frac{f''a}{2!}(x-a)^{2}+\frac{f'''a}{3!}(x-a)^{3}+...+\frac{f^{(n)}a}{n!}(x-a)^{n}
$$
### Taylors sætning: Hvis $f^{(n+1)}(t)$ eksisterer for alle t i et interval indeholdende a og x, og hvis $P_{n}$ er et n'te grads taylorpolynomium for f(x) omkring x=a, så er $f(x)=P_{n}(x)+E_{n}(x)$ når:
$$
E_{n}(x)=\frac{f^{(n+1)}(s)}{(n+1)!}(x-a)^{n+1}
$$
hvor $s \space \epsilon \space ]a,x[$
### Eksempel
3 ordens taylor $f(x)=e^{x}$ om x=0 fejlvurdering ved x=1:
$$
\begin{align*}
P_{3}(x)&= f(a)+f'(a)(x-a)+\frac{f''a}{2!}(x-a)^{2}+\frac{f'''a}{3!}(x-a)^{3}\\
&= e^{0}+e^{0}x+ \frac{e^{0}}{2}x^{2}+e^\frac{0}{6}x^{3}\\
&= 1+x + \frac{1}{2}x^{2}+ \frac{1}{6}x^{3}\\
P_{3}(1)&= 1+1+ \frac{1}{2}+ \frac{1}{6}=2.5+0.1666666=2.666666\\
E_{3}(x)&= \frac{f'''(s)}{4!}(x-a)^{4},& s\space \epsilon \space ]a,x[\\
&= \underbrace{\frac{e^{s}}{4!}}_{positiv} \underbrace{x^{4}}_{positiv}\\
|E_{3}(x)|&\leq \left|\frac{e^{s_{max}}}{4!}\cdot \underbrace{x^{4}}_{unødvendig}\right|\\
&= \frac{e^{s_{max}}}{24}x^{4}=\frac{e}{24}x^{4}\\
\text{Fejl}\space x&= 1:\\
E_{3}(1)=\frac{e}{24}&\approx 0.1132617\\
\text{interval}\\
E(x)&= f(x)-L(x)>0, f(x)>L(x)\\
\left[\underbrace{2,666666}_{\text{rund ned}}, \underbrace{2,7799283}_{\text{rund op}}\right]
\end{align*}
$$