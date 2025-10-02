![[Pasted image 20251002124208.png]]
1. Derive the actual transfer function: $H(s) = \frac{V_{o}}{V_{s}}$

$$
U = I R
$$
$$
V_{o} = \frac{iR}{V_{s}} = \frac{R}{R +  sL + (sC)^{-1}}
$$
2. Assuming that $V_{s}$ is an impulse $V_{s} = \delta (0)$, can you plot $V_{o}(t)$ time response

I plot it in matlab:
![[Pasted image 20251002135052.png]]


I accidentally tried calculating it by hand:

When inverse Laplace transforming the delta function $\delta(0)$ you get 1.
Since our transfer function is:
$$
\frac{V_{o}}{V_{s}}
$$
$$
\frac{R}{R + sL + (sC)^{-1}}
$$
Extend with s:
$$
\frac{Rs}{sR + s^{2}L + (C)^{-1}}
$$
2nd degree polynomial
$$
d = b^{2} - 4ac
$$
In this case:
$$
\begin{align*}
a = L\\
b = R\\
c = \frac{1}{C}
\end{align*}
$$
$$
d = R^{2} - \frac{4 L}{C}
$$
$$
\frac{-b \pm \sqrt{d}}{2a}
$$
$$
\frac{-R + \sqrt{R^{2} - \frac{4 L}{C}}}{2L}
$$
$$
\frac{-R - \sqrt{R^{2} - \frac{4 L}{C}}}{2L}
$$
Insert values:
$$
\frac{-320 + \sqrt{320^{2} - \frac{4 \cdot 0.1}{10^{-7}}}}{2 \cdot 0.1}
$$
$$
d = -3897600
$$
$$
\frac{-320 + \sqrt{3897600 } j}{0.2} = -1600+ \sqrt{3897600 \cdot 5^{2}} j = -1600 +97440000 j
$$
$$
\frac{-320 - \sqrt{3897600 } j}{0.2} = -1600 - \sqrt{3897600 \cdot 5^{2}} j = -1600 -97440000 j
$$
$$

$$

Invers Laplace transformerede
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

![[Pasted image 20251002135118.png]]

So the answer is:
![[Pasted image 20251002135245.png]]

I have to find this out by deriving it using the z-transform formula, and not just using the table result or matlab.

![[Pasted image 20251002135600.png]]
![[Pasted image 20251002135619.png]]
$$
X(z) = \sum_{n = - \infty} ^{\infty} \cos(\omega_{0})
$$