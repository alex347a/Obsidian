$$
\begin{align*}
\text{1. Beregn determinanten af matricen} \\
A &= \begin{pmatrix} 1-\lambda & 2 & 3 \\ 0 & -\lambda & 1 \\ 1 & 0 & 2-\lambda \end{pmatrix} \\
\text{Determinanten af A er:} \\
\text{det}(A) &= \begin{vmatrix} 1-\lambda & 2 & 3 \\ 0 & -\lambda & 1 \\ 1 & 0 & 2-\lambda \end{vmatrix} \\
&= (1-\lambda) \cdot \begin{vmatrix} -\lambda & 1 \\ 0 & 2-\lambda \end{vmatrix} - 2 \cdot \begin{vmatrix} 0 & 1 \\ 1 & 2-\lambda \end{vmatrix} + 3 \cdot \begin{vmatrix} 0 & -\lambda \\ 1 & 0 \end{vmatrix} \\
&= (1-\lambda) \cdot (-\lambda \cdot (2-\lambda)) - 2 \cdot (-(2-\lambda)) + 3 \cdot (\lambda) \\
&= (1-\lambda) \cdot (-\lambda(2-\lambda)) + 2 \cdot (\lambda-2) + 3\lambda \\
&= (1-\lambda) \cdot (-\lambda^2 + 2\lambda) + 2\lambda - 4 + 3\lambda \\
&= -\lambda^2 + 2\lambda - \lambda^3 + 2\lambda^2 + 5\lambda - 4 \\
&= -\lambda^3 + \lambda^2 + 7\lambda - 4
\end{align*}
$$

$$
\begin{align*}
\text{2. Anvend Gauss:} \\
3x + 2y - z &= 9 \\
2x + z + 3y &= 11 \\
x + 2y - 3z &= 3 \\
\text{Skriv systemet i matrix form:} \\
\begin{pmatrix} 3 & 2 & -1 \\ 2 & 3 & 1 \\ 1 & 2 & -3 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} &= \begin{pmatrix} 9 \\ 11 \\ 3 \end{pmatrix} \\
\text{Udfør Gauss-eliminering:} \\
\text{Efter rækkeoperationer:} \\
\begin{pmatrix} 1 & 2/3 & -1/3 \\ 0 & 7/3 & 7/3 \\ 0 & 0 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} &= \begin{pmatrix} 9 \\ 11 \\ 3 \end{pmatrix} \\
\text{Løsningen er:} \\
x &= 3, \quad y = 2, \quad z = 1
\end{align*}
$$

$$
\begin{align*}
\text{3. Bestem værdien af:} \\
\lim_{x \to 5} \frac{x^2 - 10x + 25}{(x - 5) \cdot \cos(x - 5)} \\
\text{Først faktorer } x^2 - 10x + 25: \\
x^2 - 10x + 25 &= (x-5)^2 \\
\text{Udtryk bliver:} \\
\lim_{x \to 5} \frac{(x - 5)^2}{(x - 5) \cdot \cos(x - 5)} &= \lim_{x \to 5} \frac{x - 5}{\cos(x - 5)} \\
\text{Når } x \to 5, \text{ så } \cos(0) = 1: \\
\lim_{x \to 5} \frac{x - 5}{\cos(x - 5)} &= 0
\end{align*}
$$

$$
\begin{align*}
\text{4. Bestem den afledte af:} \\
f(x) &= 3 \cdot e^{-x^2 + 1} \\
\text{Anvend kædereglen:} \\
f'(x) &= 3 \cdot e^{-x^2 + 1} \cdot (-2x) \\
f'(x) &= -6x \cdot e^{-x^2 + 1}
\end{align*}
$$

$$
\begin{align*}
\text{5. Beregn det bestemte integrale:} \\
\int_{-2}^{3} \frac{x}{1 + x^2} \, dx \\
\text{Brug substitution:} \\
u &= 1 + x^2, \quad du = 2x \, dx \\
\text{Når } x = -2, u = 5 \quad \text{og når } x = 3, u = 10 \\
\int_{-2}^{3} \frac{x}{1 + x^2} \, dx &= \frac{1}{2} \int_{5}^{10} \frac{du}{u} \\
&= \frac{1}{2} \ln(u) \Big|_5^{10} \\
&= \frac{1}{2} \ln(10) - \frac{1}{2} \ln(5) \\
&= \frac{1}{2} \ln\left( \frac{10}{5} \right) = \frac{1}{2} \ln(2)
\end{align*}
$$

$$
\begin{align*}
\text{6. Find udtrykket for det ubestemte integrale:} \\
\int x \cdot \sin(2x) \, dx \\
\text{Brug integration ved dele:} \\
u &= x, \quad dv = \sin(2x) \, dx \\
du &= dx, \quad v = -\frac{1}{2} \cos(2x) \\
\int x \cdot \sin(2x) \, dx &= -\frac{1}{2} x \cdot \cos(2x) + \frac{1}{2} \int \cos(2x) \, dx \\
&= -\frac{1}{2} x \cdot \cos(2x) + \frac{1}{4} \sin(2x) + C
\end{align*}
$$

$$
\begin{align*}
\text{7. Opdel udtrykket i partialbrøker:} \\
\frac{3x + 5}{(x - 1)(x + 3)} &= \frac{A}{x - 1} + \frac{B}{x + 3} \\
3x + 5 &= A(x + 3) + B(x - 1) \\
3x + 5 &= A(x) + 3A + B(x) - B \\
3x + 5 &= (A + B)x + (3A - B) \\
A + B &= 3 \quad \text{og} \quad 3A - B = 5 \\
A &= 4, \quad B = -1 \\
\frac{3x + 5}{(x - 1)(x + 3)} &= \frac{4}{x - 1} - \frac{1}{x + 3}
\end{align*}
$$

$$
\begin{align*}
\text{8. Angiv den reelle og imaginære del af tallet:} \\
Z &= 2 \cdot e^{i\pi/2} \cdot 3 \cdot e^{i\pi/4} \\
Z &= 6 \cdot e^{i(\pi/2 + \pi/4)} = 6 \cdot e^{i3\pi/4} \\
\text{Den reelle del af } Z &= 6 \cdot \cos(3\pi/4) = 6 \cdot (-\frac{\sqrt{2}}{2}) = -3\sqrt{2}/2 \\
\text{Den imaginære del af } Z &= 6 \cdot \sin(3\pi/4) = 6 \cdot \frac{\sqrt{2}}{2} = 3\sqrt{2}/2
\end{align*}
$$

$$
\begin{align*}
\text{9. Løs differentialligningen:} \\
\frac{dv}{dt} &= g - k \cdot v \\
\text{Træk } k \cdot v \text{ til venstre side:} \\
\frac{dv}{dt} + k \cdot v &= g \\
\text{Integrerende faktor:} \\
\mu(t) &= e^{kt} \\
\text{Multiplicer med den integrerende faktor:} \\
e^{kt} \cdot \frac{dv}{dt} + k \cdot e^{kt} \cdot v &= g \cdot e^{kt} \\
\frac{d}{dt} \left( e^{kt} \cdot v \right) &= g \cdot e^{kt} \\
\text{Integrer begge sider:} \\
e^{kt} \cdot v &= \frac{g}{k} \cdot e^{kt} + C \\
v(t) &= \frac{g}{k} + C \cdot e^{-kt}
\end{align*}
$$
