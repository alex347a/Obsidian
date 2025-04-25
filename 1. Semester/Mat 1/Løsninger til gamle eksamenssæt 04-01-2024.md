$$
\begin{align*}
\text{Opgave 1:} \\
\text{a) Determinant:} \\
A &= \begin{pmatrix} 1-\lambda & 2 & 3 \\ 0 & -\lambda & 1 \\ 1 & 0 & 2-\lambda \end{pmatrix} \\
\text{Determinanten:} \quad \text{det}(A) &= (1-\lambda) \begin{vmatrix} -\lambda & 1 \\ 0 & 2-\lambda \end{vmatrix} - 2 \begin{vmatrix} 0 & 1 \\ 1 & 2-\lambda \end{vmatrix} + 3 \begin{vmatrix} 0 & -\lambda \\ 1 & 0 \end{vmatrix} \\
&= (1-\lambda) (-\lambda(2-\lambda) - 0) - 2 (0 - (1)(2-\lambda)) + 3 (0 - (-\lambda)) \\
&= (1-\lambda)(-\lambda(2-\lambda)) - 2(2-\lambda) + 3\lambda \\
&= (1-\lambda)(-\lambda^2 + 2\lambda) - 2(2-\lambda) + 3\lambda \\
&= -\lambda^3 + 2\lambda^2 - (-2\lambda + 2\lambda^2) + 3\lambda \\
&= -\lambda^3 + 2\lambda^2 + 2\lambda - 2\lambda^2 + 3\lambda \\
&= -\lambda^3 + 5\lambda \\
\text{Egenværdier:} \\
-\lambda^3 + 5\lambda &= 0 \\
\lambda(\lambda^2 - 5) &= 0 \\
\lambda_1 &= 0 \quad \lambda_2 = \sqrt{5} \quad \lambda_3 = -\sqrt{5} \\
\\
\text{b) Egenvektor for } \lambda_1 = 1: \\
A - \lambda_1 I &= \begin{pmatrix} 1-1 & 2 & 3 \\ 0 & -1 & 1 \\ 1 & 0 & 2-1 \end{pmatrix} \\
&= \begin{pmatrix} 0 & 2 & 3 \\ 0 & -1 & 1 \\ 1 & 0 & 1 \end{pmatrix} \\
\text{Løsning af systemet:} \\
\text{Fra } A - \lambda_1 I: \quad \begin{pmatrix} 0 & 2 & 3 \\ 0 & -1 & 1 \\ 1 & 0 & 1 \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} &= \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix} \\
\text{Løsning:} \quad x_1 = 3, x_2 = 1, x_3 = -2. \\
\text{Eigenvektor:} \quad \mathbf{v} &= \begin{pmatrix} 3 \\ 1 \\ -2 \end{pmatrix} \\
\\
\text{Opgave 2:} \\
\text{a) Taylorpolynomium P}_2(x) \text{ for } f(x) = \ln(x) \text{ omkring } x = 1: \\
f'(x) &= \frac{1}{x} \\
f''(x) &= -\frac{1}{x^2} \\
P_2(x) &= f(1) + f'(1)(x-1) + \frac{f''(1)}{2!}(x-1)^2 \\
P_2(x) &= \ln(1) + \frac{1}{1}(x-1) + \frac{-1}{2}(x-1)^2 \\
P_2(x) &= 0 + (x-1) - \frac{1}{2}(x-1)^2 \\
P_2(x) &= (x-1) - \frac{1}{2}(x-1)^2 \\
\\
\text{b) Estimering af } f(1.5) \text{ med } P_2(x): \\
P_2(1.5) &= (1.5 - 1) - \frac{1}{2}(1.5 - 1)^2 \\
P_2(1.5) &= 0.5 - \frac{1}{2}(0.5)^2 \\
P_2(1.5) &= 0.5 - 0.125 \\
P_2(1.5) &= 0.375 \\
\\
\text{c) Worst case fejl:} \\
\text{Fejl: } |f(x) - P_2(x)| \leq \frac{|f^{(3)}(c)|}{3!} |x-1|^3 \\
f^{(3)}(x) &= \frac{2}{x^3} \\
f^{(3)}(1) &= 2 \\
\text{Worst case fejl:} \quad \frac{2}{6} \cdot (0.5)^3 = \frac{2}{6} \cdot 0.125 = \frac{0.25}{6} \approx 0.04167 \\
\\
\text{Opgave 3:} \\
\text{a) Beregn:} \quad \frac{-22 - 7i}{4 + 5i} \\
\text{Multiplicer med konjugatet:} \quad \frac{-22 - 7i}{4 + 5i} \cdot \frac{4 - 5i}{4 - 5i} = \frac{(-22 - 7i)(4 - 5i)}{(4 + 5i)(4 - 5i)} \\
\text{Beregn tæller:} \quad (-22 - 7i)(4 - 5i) = -88 + 110i - 28i + 35 \\
&= -53 + 82i \\
\text{Beregn nævner:} \quad (4 + 5i)(4 - 5i) = 16 + 25 = 41 \\
\text{Resultat:} \quad \frac{-53 + 82i}{41} = \frac{-53}{41} + \frac{82}{41}i = -\frac{53}{41} + \frac{82}{41}i \\
\text{Reelle del:} \quad -\frac{53}{41} \quad \text{Imaginære del:} \quad \frac{82}{41} \\
\\
\text{b) Plot i Argand diagram:} \\
z_1 &= 4 + 5i \\
z_2 &= 4 - 5i \\
z_3 &= 6 e^{i\frac{2\pi}{3}} \quad z_4 = 6 e^{i\frac{-2\pi}{3}} \\
\text{Placer på diagrammet:} \\
z_1 &= (4, 5) \\
z_2 &= (4, -5) \\
z_3 &= (3, 3\sqrt{3}) \\
z_4 &= (3, -3\sqrt{3}) \\
\\
\text{c) Løsninger af ligningen } w^3 = -2\sqrt{2}: \\
w = \sqrt[3]{-2\sqrt{2}} \quad \text{hvor de komplekse løsninger er:} \\
w_1 = \sqrt[3]{-2\sqrt{2}} \quad w_2 = \sqrt[3]{-2\sqrt{2}} e^{i\frac{2\pi}{3}} \quad w_3 = \sqrt[3]{-2\sqrt{2}} e^{i\frac{4\pi}{3}} \\
\\
\text{Opgave 4:} \\
\text{a) Løsning af differentialligningen:} \quad \frac{dy}{dx} - \frac{y}{x} = x^2 \\
\text{Integrerende faktor:} \quad \mu(x) = e^{\int \frac{-1}{x} dx} = \frac{1}{x} \\
\frac{1}{x} \frac{dy}{dx} - \frac{y}{x^2} &= x \\
\frac{d}{dx} \left( \frac{y}{x} \right) &= x \\
\int \frac{d}{dx} \left( \frac{y}{x} \right) dx &= \int x dx \\
\frac{y}{x} &= \frac{x^2}{2} + C \\
y &= \frac{x^3}{2} + Cx \\
\\
\text{b) Bestem løsningen med begyndelsesbetingelser:} \quad f(0) = -1, f'(0) = 5 \\
y &= \frac{x^3}{2} + Cx \\
f'(x) &= \frac{3x^2}{2} + C \\
f(0) = -1 \quad \Rightarrow \quad C = -1 \\
f'(0) = 5 \quad \Rightarrow \quad C = 5 \\
\text{Løsning:} \quad y = \frac{x^3}{2} + 5x
\end{align*}
$$