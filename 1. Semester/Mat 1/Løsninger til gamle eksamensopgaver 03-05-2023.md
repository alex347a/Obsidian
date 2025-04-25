$$
\begin{align*}
&\textbf{Opgave 1a: Beregning af egenværdier for matrix } A \\
&A =
\begin{pmatrix}
-1 & -8 & -4 \\
0 & 2 & 0 \\
2 & 6 & 5
\end{pmatrix} \\
&\text{Determinanten af } A - \lambda I \text{ findes som:} \\
\det(A - \lambda I) &= 
\begin{vmatrix}
-1 - \lambda & -8 & -4 \\
0 & 2 - \lambda & 0 \\
2 & 6 & 5 - \lambda
\end{vmatrix} \\
&= (-1 - \lambda) \begin{vmatrix} 2 - \lambda & 0 \\ 6 & 5 - \lambda \end{vmatrix} 
- (-8) \begin{vmatrix} 0 & 0 \\ 2 & 5 - \lambda \end{vmatrix} 
+ (-4) \begin{vmatrix} 0 & 2 - \lambda \\ 2 & 6 \end{vmatrix} \\
&= (-1 - \lambda) \big((2 - \lambda)(5 - \lambda) - 0\big) + 0 - 4 \big(0 - 2(2 - \lambda)\big) \\
&= (-1 - \lambda)(\lambda^2 - 7\lambda + 10) + 8 - 8\lambda \\
&= -\lambda^3 + 6\lambda^2 - 11\lambda - \lambda^2 + 7\lambda - 10 + 8 - 8\lambda \\
&= -\lambda^3 + 5\lambda^2 - 12\lambda - 2 \\
&\text{Da } \lambda_1 = 2 \text{ er en rod, divideres polynomiet med } (\lambda - 2): \\
-\lambda^3 + 5\lambda^2 - 12\lambda - 2 &\div (\lambda - 2) = -\lambda^2 + 3\lambda - 1 \\
&\text{De resterende rødder findes ved at løse: } -\lambda^2 + 3\lambda - 1 = 0. \\
&\text{Løsning: } \lambda_2 = 1, \lambda_3 = -1.
\end{align*}
$$

$$ \begin{align*} &\textbf{Opgave 1b: Egenvektoren for } \lambda_1 = 2 \\ &A - 2I = \begin{pmatrix} -3 & -8 & -4 \\ 0 & 0 & 0 \\ 2 & 6 & 3 \end{pmatrix} \\ &\text{Løsning af } (A - 2I)\mathbf{v} = 0: \\ &\begin{aligned} -3v_1 - 8v_2 - 4v_3 &= 0 \\ 0 &= 0 \\ 2v_1 + 6v_2 + 3v_3 &= 0 \end{aligned} \\ &\text{Første ligning: } -3v_1 - 8v_2 - 4v_3 = 0 \implies v_1 = -\frac{8}{3}v_2 - \frac{4}{3}v_3. \\ &\text{Anden ligning giver samme relation. Sæt } v_2 = t, \, v_3 = s: \\ &v_1 = -\frac{8}{3}t - \frac{4}{3}s, \quad \mathbf{v} = \begin{pmatrix} -\frac{8}{3}t - \frac{4}{3}s \\ t \\ s \end{pmatrix}. \end{align*} $$

$$
\begin{align*}
&\textbf{Opgave 2a: Taylorpolynomiet for } f(x) = x^4 - x^3 \text{ omkring } x = 2 \\
&f'(x) = 4x^3 - 3x^2, \quad f''(x) = 12x^2 - 6x \\
&f(2) = 16 - 8 = 8, \quad f'(2) = 32 - 12 = 20, \quad f''(2) = 48 - 12 = 36 \\
&P_2(x) = f(2) + f'(2)(x-2) + \frac{f''(2)}{2}(x-2)^2 \\
&P_2(x) = 8 + 20(x-2) + 18(x-2)^2
\end{align*}
$$

$$
\begin{align*}
&\textbf{Opgave 2b: Estimering af } f(1.9) \text{ ved } P_2(x) \\
&P_2(1.9) = 8 + 20(1.9 - 2) + 18(1.9 - 2)^2 \\
&P_2(1.9) = 8 - 2 + 18(0.01) = 6.18
\end{align*}
$$

$$
\begin{align*}
&\textbf{Opgave 2c: Worst case fejl } \\
&\text{Fejlen er givet ved: } \frac{f'''(c)}{6}(x-2)^3, \quad c \in [1.9, 2] \\
&f'''(x) = 24x - 6, \quad f'''(c) \leq 42 \text{ i intervallet.} \\
&\text{Worst case fejl: } \frac{42}{6}(0.1)^3 = 0.007
\end{align*}
$$

$$
\begin{align*}
&\textbf{Opgave 3a: Beregning af integralet } \\
&\int \big((x+1)^2 + \sin(2x) + \frac{3}{x}\big) \, dx = \int (x^2 + 2x + 1) \, dx + \int \sin(2x) \, dx + \int \frac{3}{x} \, dx \\
&= \frac{x^3}{3} + x^2 + x - \frac{\cos(2x)}{2} + 3\ln|x| + C
\end{align*}
$$

$$
\begin{align*}
&\textbf{Opgave 3b: Opdeling i partialbrøker } \\
&\frac{11 + 5x}{(1+x)(3+x)} = \frac{A}{1+x} + \frac{B}{3+x} \\
&11 + 5x = A(3+x) + B(1+x) \\
&11 + 5x = (A+B)x + (3A + B) \\
&A + B = 5, \quad 3A + B = 11 \\
&A = 2, \quad B = 3 \\
&\text{Partialbrøker: } \frac{2}{1+x} + \frac{3}{3+x}
\end{align*}
$$

$$ \begin{align*} &\textbf{Opgave 3c: Løsning af ligningssystemet } \\ &\text{Systemet er:} \\ &\begin{aligned} 2x + 4y - z &= 8 \\ 2x + 4y + z &= 6 \\ x + y &= \frac{11}{4} \end{aligned} \\ &\text{Træk første ligning fra anden: } (2x + 4y + z) - (2x + 4y - z) = 6 - 8 \\ &2z = -2 \implies z = -1. \\ &\text{Indsæt } z = -1 \text{ i første ligning: } \\ &2x + 4y - (-1) = 8 \implies 2x + 4y + 1 = 8 \implies 2x + 4y = 7. \\ &\text{Brug } x + y = \frac{11}{4}: \\ &x = \frac{11}{4} - y, \quad 2\left(\frac{11}{4} - y\right) + 4y = 7 \\ &\frac{22}{4} - 2y + 4y = 7 \implies \frac{22}{4} + 2y = 7 \implies 2y = 7 - \frac{22}{4} \\ &2y = \frac{28}{4} - \frac{22}{4} \implies 2y = \frac{6}{4} \implies y = \frac{3}{4}. \\ &x = \frac{11}{4} - \frac{3}{4} = 2. \\ &\text{Løsning: } x = 2, \, y = \frac{3}{4}, \, z = -1. \end{align*} $$

$$
\begin{align*}
&\textbf{Opgave 4a: Vis, at } f(x) = e^{x^2/2} \text{ er en løsning} \\
&f(x) = e^{x^2/2}, \quad f'(x) = x \cdot e^{x^2/2} = f \cdot x
\end{align*}
$$

$$ \begin{align*} &\textbf{Opgave 4b: Flere skridt til løsning af differentialligningen } \frac{dg}{dx} = 2g \cdot x \\ &\text{Omskrivning: } \frac{1}{g} \, dg = 2x \, dx. \\ &\text{Integrér begge sider:} \\ &\int \frac{1}{g} \, dg = \int 2x \, dx \\ &\ln|g| = x^2 + C_1, \quad \text{hvor } C_1 \text{ er en integrationskonstant.} \\ &\text{Omskriv til eksponentialform:} \\ &|g| = e^{x^2 + C_1} = e^{C_1} \cdot e^{x^2}. \\ &\text{Definér } A = e^{C_1}, \, A > 0 \text{ (for at bevare } |g|). \\ &g = A e^{x^2}, \quad \text{hvor } A \text{ er en vilkårlig positiv konstant.} \\ &\text{Generel løsning: } g(x) = A e^{x^2}. \end{align*} $$