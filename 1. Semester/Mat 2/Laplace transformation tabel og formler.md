![[Laplace tabel regneregler.png]]
![[Laplace transformation tabel.png]]
$$
\begin{array}{|c|c|c|}
\hline
\text{No.} & f(t) & \mathcal{L}(f) \\
\hline
1 & 1 & \frac{1}{s} \\
2 & t & \frac{1}{s^2} \\
3 & t^2 & \frac{2!}{s^3} \\
4 & t^n \, (n = 0, 1, \dots) & \frac{n!}{s^{n+1}} \\
5 & t^a \, (a > 0) & \frac{\Gamma(a + 1)}{s^{a+1}} \\
6 & e^{at} & \frac{1}{s - a} \\
7 & \cos(\omega t) & \frac{s}{s^2 + \omega^2} \\
8 & \sin(\omega t) & \frac{\omega}{s^2 + \omega^2} \\
9 & \cosh(at) & \frac{s}{s^2 - a^2} \\
10 & \sinh(at) & \frac{a}{s^2 - a^2} \\
11 & e^{at} \cos(\omega t) & \frac{s - a}{(s - a)^2 + \omega^2} \\
12 & e^{at} \sin(\omega t) & \frac{\omega}{(s - a)^2 + \omega^2} \\
\hline
\end{array}
$$
Så hvis man skal finde den inverse, så læser man bare tabellen baglæns:

$$
\begin{array}{|c|c|}
\hline
\mathcal{L}(f) & f(t) \\
\hline
\frac{1}{s} & 1 \\
\frac{1}{s^2} & t \\
\frac{2!}{s^3} & t^2 \\
\frac{n!}{s^{n+1}} & t^n \, (n = 0, 1, \dots) \\
\frac{\Gamma(a + 1)}{s^{a+1}} & t^a \, (a > 0) \\
\frac{1}{s - a} & e^{at} \\
\frac{s}{s^2 + \omega^2} & \cos(\omega t) \\
\frac{\omega}{s^2 + \omega^2} & \sin(\omega t) \\
\frac{s}{s^2 - a^2} & \cosh(at) \\
\frac{a}{s^2 - a^2} & \sinh(at) \\
\frac{s - a}{(s - a)^2 + \omega^2} & e^{at} \cos(\omega t) \\
\frac{\omega}{(s - a)^2 + \omega^2} & e^{at} \sin(\omega t) \\
\hline
\end{array}
$$

$$\mathcal{L}(a f(t)+bg(t))=a\mathcal{L}(f(t)+b\mathcal{L}(g(t)$$
## s-shifting:
If f(t) has the transform F(s) (where s>k for some k), then $e^{at} f(t)$ has the transform F(s-a) (where s-a>k) In formulas:

$$
\mathcal{L}(e^{at}f(t)=F(s-a)
$$
or, if we take the inverse on both sides:
$$
e^{at}f(t)=\mathcal{L}^{-1}\left(F(s-a)\right)
$$

## Existence theorem for laplace transforms:
If f(t) is defined and piecewise continuous on every finite interval on the semi-axis $t\geq 0$ and satisfies s-shifting for all $t \geq 0$ and some constants M and k, then the Laplace transform $\mathcal{L}(f)$ exists for all s>k.

## Laplace transform of derivatives:
The transforms of the first and second derivatives of f(t) satisfy:
$$
\begin{align*}
\mathcal{L}(f'(t))&= s\mathcal{L}(f)-f(0)\\
\mathcal{L}(f'')&= s^{2}\mathcal{L}(f)-sf(0)-f'(0)
\end{align*}
$$
Formula 1 holds if f(t) is continuous for all $t\geq 0$ and satisfies the growth restriction in s-shifting and f'(t) is piecewise continuous on every finite interval on the semi-axis $t\geq 0$ Similarly, formula 2 holds if f and f' are continuous for all $t\geq 0$ and satisfy the growth restriction and f'' is piecewise continuous on every finite interval on the semi-axis $t\geq 0$.

### Laplace transform of derivatives of any order:
Let f, f', ..., $f^{(n-1)}$ be continuous for all $t\geq 0$ and satisfy the growth restriction. Furthermore, let $f^{(n)}$ be piecewise continuous on every finite interval on the semi-axis $t\geq 0$. Then the transform of the $f^{(n)}$ satisfies:
$$
\mathcal{L}(f^{(n)}) = s^{n}\mathcal{L}(f)-s^{n-1}f(0)-s^{n-2}f'(0)-...-f^{(n-1)}(0)
$$

## Laplace transform of an integral:
Let F(s) denote the transform of a function f(t) which is piecewise continuous for $t\geq 0$ and satisfies a growth restriction. Then, for s>0, s>k, and t>0:
$$
\begin{align*}
\mathcal{L}\left(\int^{t}_{0}f(\tau)\space d\tau \right)=\frac{1}{2}F(s), && \text{thus} &&\int^{t}_{0}f(\tau)\space d\tau =\mathcal{L}^{-1}\left(\frac{1}{2}F(s)\right)
\end{align*}
$$

## Time shifting:
If f(t) has the transform F(s), then the "shifted function"
$$
\begin{align*}
\tilde{f}(t) &= f(t-a)u(t-a)=\begin{pmatrix}0, & \text{if}\space t<a\\
f(t-a),& \text{if}\space t>a\end{pmatrix}
\end{align*}
$$
has the transform $e^{-as}F(s)$. That is, if $\mathcal{L}(f(t))=F(s)$, then:
$$
\mathcal{L}(f(t-a)u(t-a))=e^{-as}F(s).
$$
Or, if we take the inverse on both sides, we can write:
$$
f(t-a)u(t-a)=\mathcal{L}^{-1}(e^{-as}F(s))
$$