$$
\begin{align*}
\textbf{Opgave 1} \\
\text{Matrixen } A = 
\begin{pmatrix}
3 & -1 & 2 \\
0 & 4 & 5 \\
0 & 3 & 2
\end{pmatrix} \\[8pt]
\textbf{(a) Beregn de to sidste egenværdier:} \\
\text{Karakteristisk polynomium: } \det(A - \lambda I) = 
\begin{vmatrix}
3 - \lambda & -1 & 2 \\
0 & 4 - \lambda & 5 \\
0 & 3 & 2 - \lambda
\end{vmatrix} \\
\text{Udvikling langs første række:} \\
\det(A - \lambda I) = (3 - \lambda) 
\begin{vmatrix}
4 - \lambda & 5 \\
3 & 2 - \lambda
\end{vmatrix}
+ 0 - 2
\begin{vmatrix}
0 & 5 \\
0 & 2 - \lambda
\end{vmatrix} \\
\det(A - \lambda I) = (3 - \lambda)((4 - \lambda)(2 - \lambda) - 15) \\
= (3 - \lambda)((8 - 6\lambda + \lambda^2) - 15) \\
= (3 - \lambda)(\lambda^2 - 6\lambda - 7) \\
= (3 - \lambda)(\lambda + 1)(\lambda - 7) \\
\text{Egenværdier: } \lambda_1 = -1, \lambda_2 = 3, \lambda_3 = 7. \\[12pt]
\textbf{(b) Egenvektor for } \lambda_1 = -1: \\
(A - (-1)I)v = 0 \implies 
\begin{pmatrix}
4 & -1 & 2 \\
0 & 5 & 5 \\
0 & 3 & 3
\end{pmatrix}
\begin{pmatrix}
v_1 \\ v_2 \\ v_3
\end{pmatrix}
= 0 \\
\text{Løsning: } v = 
\begin{pmatrix}
-1 \\ 1 \\ 0
\end{pmatrix}. \\[12pt]

\textbf{Opgave 2} \\
f(x) = \sin(x) - 1 \\[8pt]
\textbf{(a) Andenordens Taylorpolynomium:} \\
f(x) \approx f(\pi/2) + f'(\pi/2)(x - \pi/2) + \frac{f''(\pi/2)}{2}(x - \pi/2)^2 \\
f(\pi/2) = 0, \quad f'(\pi/2) = \cos(\pi/2) = 0, \quad f''(\pi/2) = -\sin(\pi/2) = -1 \\
P_2(x) = 0 + 0 \cdot (x - \pi/2) - \frac{1}{2}(x - \pi/2)^2 \\
P_2(x) = -\frac{1}{2}(x - \pi/2)^2. \\[8pt]
\textbf{(b) Estimer } f(1): \\
P_2(1) = -\frac{1}{2}(1 - \pi/2)^2. \\[8pt]
\textbf{(c) Worst case fejl:} \\
R_2(x) = \frac{f^{(3)}(c)}{6}(x - \pi/2)^3, \quad c \in (\pi/2, x). \\
f^{(3)}(x) = -\cos(x) \implies |R_2(x)| \leq \frac{1}{6}|x - \pi/2|^3. \\[12pt]

\textbf{Opgave 3} \\
\textbf{(a) Bestem værdien af integralet:} \\
\int (e^{2x} + 2\sin(x) + x^3) \, dx \\
= \frac{1}{2}e^{2x} - 2\cos(x) + \frac{x^4}{4} + C. \\[8pt]
\textbf{(b) Partialbrøker:} \\
\frac{3x + 7}{(x + 3)(x + 2)} = \frac{A}{x + 3} + \frac{B}{x + 2} \\
3x + 7 = A(x + 2) + B(x + 3) \\
3x + 7 = Ax + 2A + Bx + 3B \\
3x + 7 = (A + B)x + (2A + 3B) \\
\implies A + B = 3, \quad 2A + 3B = 7 \\
\text{Løsning: } A = 2, \, B = 1 \implies \frac{3x + 7}{(x + 3)(x + 2)} = \frac{2}{x + 3} + \frac{1}{x + 2}. \\[8pt]
\textbf{Opgave 3c: Bestem værdien af integralet:} \\
\int x(\sin(x) + e^x) \, dx = \int x \sin(x) \, dx + \int x e^x \, dx \\[8pt]
\textbf{Del 1: } \int x \sin(x) \, dx \\
\text{Brug delvis integration: } u = x, \, dv = \sin(x) \, dx \implies du = dx, \, v = -\cos(x) \\
\int x \sin(x) \, dx = -x \cos(x) + \int \cos(x) \, dx \\
= -x \cos(x) + \sin(x). \\[8pt]
\textbf{Del 2: } \int x e^x \, dx \\
\text{Brug delvis integration: } u = x, \, dv = e^x \, dx \implies du = dx, \, v = e^x \\
\int x e^x \, dx = x e^x - \int e^x \, dx \\
= x e^x - e^x. \\[8pt]
\textbf{Samlet resultat:} \\
\int x (\sin(x) + e^x) \, dx = (-x \cos(x) + \sin(x)) + (x e^x - e^x) + C \\
= -x \cos(x) + \sin(x) + x e^x - e^x + C.\\


\textbf{Opgave 4} \\
\textbf{(a) Bestem grænseværdien:} \\
\lim_{x \to \infty} \frac{x + x^2 + \ln(x)}{2x^2 + 1/x} \\
\text{Dominerende led i tæller og nævner: } \frac{x^2}{2x^2} = \frac{1}{2}. \\[8pt]
\textbf{(b) Forenkl logaritmen:} \\
\log_4\left(\frac{24 \cdot 32}{8 \cdot 27}\right) - \log_4\left(\frac{9}{8}\right) \\
= \log_4\left(\frac{24 \cdot 32}{8 \cdot 27} \cdot \frac{8}{9}\right) \\
= \log_4\left(\frac{24 \cdot 32}{27} \cdot \frac{1}{9}\right) \\
= \log_4\left(\frac{24 \cdot 32}{243}\right) \\
= \log_4(2^3 \cdot 2^5 \cdot 3^{-5}) \\
= 8 + \log_4(3^{-5}) = 8 - 5 \log_4(3).
\end{align*}
$$
