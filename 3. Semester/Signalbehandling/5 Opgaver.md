![[Pasted image 20251002124208.png]]
1. Derive the actual transfer function: $H(s) = \frac{V_{o}}{V_{s}}$

$$
U = I R
$$
$$
V_{o} = \frac{iR}{V_{s}} = \frac{R}{R +  sL + (sC)^{-1}}
$$
2. Assuming that $V_{s}$ is an impulse $V_{s} = \delta (0)$, can you plot $V_{o}(t)$ time response
When inverse Laplace transforming the delta function $\delta(0)$ you get 1.
Since our transfer function is:
$$
\frac{V_{o}}{V_{s}}
$$
$$
\frac{R}{R + sL + (sC)^{-1}}
$$
Jeg forlænger med s:
$$
\frac{R}{sR + s^{2}L + (C)^{-1}}
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

