$$
\begin{align*}
\textbf{Opgave 1a: Beregn de to sidste egenværdier for matrix } A \textbf{:} \\
A = 
\begin{pmatrix}
2 & -1 & 2 \\
0 & 1 & 3 \\
0 & 5 & 3
\end{pmatrix} \\[8pt]
\text{Find determinant af } A - \lambda I: \\
\det(A - \lambda I) =
\begin{vmatrix}
2 - \lambda & -1 & 2 \\
0 & 1 - \lambda & 3 \\
0 & 5 & 3 - \lambda
\end{vmatrix} \\
= (2 - \lambda) \begin{vmatrix}
1 - \lambda & 3 \\
5 & 3 - \lambda
\end{vmatrix} - 0 + 0 \\
= (2 - \lambda) \left((1 - \lambda)(3 - \lambda) - 15\right) \\
= (2 - \lambda) \left(3 - 4\lambda + \lambda^2 - 15\right) \\
= (2 - \lambda)(\lambda^2 - 4\lambda - 12) \\
= (\lambda - 2)(\lambda^2 - 4\lambda - 12). \\
\text{Løs } \lambda^2 - 4\lambda - 12 = 0 \text{ for de to sidste egenværdier:} \\
\lambda = \frac{4 \pm \sqrt{16 + 48}}{2} = \frac{4 \pm 8}{2} \\
\lambda_2 = 6, \, \lambda_3 = -2. \\[8pt]
\textbf{Egenværdier: } \lambda_1 = 2, \, \lambda_2 = 6, \, \lambda_3 = -2.
\end{align*}
$$

$$
\begin{align*}
\textbf{Opgave 1b: Beregn egenvektoren for } \lambda_1 = 2 \textbf{:} \\
\text{Løs ligningssystemet } (A - 2I) \mathbf{v} = \mathbf{0}: \\
A - 2I =
\begin{pmatrix}
0 & -1 & 2 \\
0 & -1 & 3 \\
0 & 5 & 1
\end{pmatrix}, \quad
\begin{pmatrix}
0 & -1 & 2 \\
0 & -1 & 3 \\
0 & 5 & 1
\end{pmatrix}
\begin{pmatrix}
v_1 \\ v_2 \\ v_3
\end{pmatrix} =
\begin{pmatrix}
0 \\ 0 \\ 0
\end{pmatrix}. \\
\text{Sæt } v_3 = t, \, v_2 = 3t, \, v_1 \text{ er frit.} \\
\textbf{Egenvektor: } \mathbf{v} =
\begin{pmatrix}
0 \\ 3 \\ 1
\end{pmatrix}.
\end{align*}
$$

---

$$
\begin{align*}
\textbf{Opgave 2a: Bestem andenordens taylorpolynomiet for } f(x) = \cos(x) - 1 \textbf{:} \\
f(x) = \cos(x) - 1, \quad f'(x) = -\sin(x), \quad f''(x) = -\cos(x). \\
\text{Omkring } x = 0: \, f(0) = -1, \, f'(0) = 0, \, f''(0) = -1. \\
P_2(x) = f(0) + f'(0)x + \frac{f''(0)x^2}{2} = -1 + 0 - \frac{x^2}{2} = -1 - \frac{x^2}{2}.
\end{align*}
$$

$$
\begin{align*}
\textbf{Opgave 2b: Brug taylorpolynomiet til at estimere } f(1): \\
P_2(1) = -1 - \frac{1^2}{2} = -1 - \frac{1}{2} = -\frac{3}{2}.
\end{align*}
$$

$$
\begin{align*}
\textbf{Opgave 2c: Estimer worst case fejlen:} \\
\text{Fejlledet: } R_2(x) = \frac{f^{(3)}(c)}{3!}x^3, \, f^{(3)}(x) = \sin(x). \\
\text{Worst case for } x \in [0, 1]: \, |R_2(1)| \leq \frac{1}{6}(1)^3 = \frac{1}{6}.
\end{align*}
$$

---

$$
\begin{align*}
\textbf{Opgave 3a: Beregn } \int \left(\frac{1}{x+1} + \frac{1}{(x+2)^2} + x\right) \, dx: \\
\int \frac{1}{x+1} \, dx = \ln|x+1|, \quad \int \frac{1}{(x+2)^2} \, dx = -\frac{1}{x+2}, \quad \int x \, dx = \frac{x^2}{2}. \\
\textbf{Samlet: } \int \left(\frac{1}{x+1} + \frac{1}{(x+2)^2} + x\right) \, dx = \ln|x+1| - \frac{1}{x+2} + \frac{x^2}{2} + C.
\end{align*}
$$

$$
\begin{align*}
\textbf{Opgave 3b: Opdel brøken } \frac{2 + 2x}{(x-1)(x-3)}: \\
\frac{2 + 2x}{(x-1)(x-3)} = \frac{A}{x-1} + \frac{B}{x-3}. \\
2 + 2x = A(x-3) + B(x-1). \\
\text{Sæt } x = 1: \, 2 + 2(1) = A(1-3) \implies A = -2. \\
\text{Sæt } x = 3: \, 2 + 2(3) = B(3-1) \implies B = 4. \\
\textbf{Resultat: } \frac{2 + 2x}{(x-1)(x-3)} = \frac{-2}{x-1} + \frac{4}{x-3}.
\end{align*}
$$

$$
\begin{align*}
\textbf{Opgave 3c: Omskriv } \frac{3x^3 + 2x - 4}{x^2 - 2} \textbf{ til ægte brøk:} \\
\text{Polynomium division: } \frac{3x^3 + 2x - 4}{x^2 - 2} = 3x + \frac{2x - 4}{x^2 - 2}. \\
\textbf{Resultat: } 3x + \frac{2x - 4}{x^2 - 2}.
\end{align*}
$$

---
$$ \begin{align*} \textbf{Opgave 4a: Beregn } y(0), \, y(10), \, \lim_{t \to \infty} y(t): \\ y(t) = \frac{600}{1 + 59 \cdot e^{\ln(29/59) \cdot 10 \cdot t}}. \\ y(0) = \frac{600}{1 + 59 \cdot e^0} = \frac{600}{60} = 10. \\ y(10) = \frac{600}{1 + 59 \cdot e^{\ln(29/59) \cdot 10}}. \\ \lim_{t \to \infty} y(t) = \frac{600}{1 + 59 \cdot 0} = 600. \end{align*} $$ $$ \begin{align*} \textbf{Opgave 4b: Bestem afledte af } f(x) = (3x+2)^{2x+5}: \\ \text{Logaritmer begge sider: } \ln(f(x)) = (2x+5) \ln(3x+2). \\ \text{Afled: } \frac{f'(x)}{f(x)} = \frac{d}{dx}[(2x+5) \ln(3x+2)] \\ = (2) \ln(3x+2) + \frac{2x+5}{3x+2}(3). \\ \textbf{Afledt: } f'(x) = (3x+2)^{2x+5} \left[2 \ln(3x+2) + \frac{6x+15}{3x+2}\right]. \end{align*} $$