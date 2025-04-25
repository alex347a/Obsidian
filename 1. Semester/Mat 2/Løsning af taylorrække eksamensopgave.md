Compute the Taylor polynomial (3rd order) of $f(x) = x \cos(x)$ around $x = 0$.

Afledede af $f(x)$:  
$f(x) = x \cos(x), \quad f(0) = 0$  
$f'(x) = \cos(x) - x \sin(x), \quad f'(0) = \cos(0) = 1$  
$f''(x) = -2\sin(x) - x\cos(x), \quad f''(0) = 0$  
$f^{(3)}(x) = -3\cos(x) + x\sin(x), \quad f^{(3)}(0) = -3\cos(0) = -3$

Taylorrække formel for 3. ordre:
$$P_3(x) = f(0) + f'(0)x + \frac{f''(0)}{2!}x^2 + \frac{f^{(3)}(0)}{3!}x^3$$  
Substituere de beregnede afledte funktioners værdier ved 0:  
$$P_3(x) = 0 + 1x + \frac{0}{2}x^2 + \frac{-3}{6}x^3 = x - \frac{x^3}{2}$$

Beregner estimatet af $f(1)$:  
$f(1) \approx P_3(1) = 1 - \frac{1^3}{2} = 1 - 0.5 = 0.5$

Estimer fejlen ved at bruge lagrange form:  
$$R_n(x) = \frac{f^{(n+1)}(c)}{(n+1)!}x^{n+1}, \quad \text{for } c \in (0, x)$$  
For $n = 3$:  
$$R_3(1) = \frac{f^{(4)}(c)}{4!}1^4$$

Beregn $f^{(4)}(x)$:  
Fra $f^{(3)}(x) = -3\cos(x) + x\sin(x)$, differentierer jeg:  
$f^{(4)}(x) = 4\sin(x) + x\cos(x)$  
For $c \in (0, 1)$, Den største værdi ved $|f^{(4)}(c)|$ occurs at $c = 1$:  
$f^{(4)}(1) = 4\sin(1) + \cos(1)$

Udregner fejlen  
Using $\sin(1) \approx \frac{5}{6}$ and $\cos(1) \approx 0.5$:  
$$f^{(4)}(1) \approx 4\left(\frac{5}{6}\right) + 0.5 = \frac{20}{6} + 0.5 = \frac{23}{6} \approx 3.8333$$  
$$R_3(1) = \frac{f^{(4)}(c)}{4!} \approx \frac{3.8333}{24} \approx 0.16$$
$f(1) \approx 0.5$  
Fejlen udregnes til at være: $R_3(1) \approx 0.16$

Ved at bruge en lommeregner: $\sin(1) \approx 0.8415, \quad \cos(1) \approx 0.5403$ $$f^{(4)}(1) = 4(0.8415) + 0.5403 = 3.366 + 0.5403 = 3.9063$$ $$R_3(1) = \frac{f^{(4)}(c)}{4!} = \frac{3.9063}{24} \approx 0.1628$$