$$
\begin{align*}
\text{Beregn determinanten af matricen} \quad & \begin{pmatrix} 6 & 2 & 1 \\ 4 & -2 & 2 \\ 0 & 4 & -4 \end{pmatrix} \\
\text{Determinanten af en 3x3 matrix er givet ved} \quad & \text{det}(A) = a(ei - fh) - b(di - fg) + c(dh - eg) \\
\text{For matricen} \quad & \begin{pmatrix} 6 & 2 & 1 \\ 4 & -2 & 2 \\ 0 & 4 & -4 \end{pmatrix}, \text{beregner vi determinanten som} \\
& \text{det}(A) = 6((-2)(-4) - (2)(4)) - 2((4)(-4) - (2)(0)) + 1((4)(4) - (-2)(0)) \\
& = 6(8 - 8) - 2(-16 - 0) + 1(16 - 0) \\
& = 6(0) - 2(-16) + 1(16) \\
& = 0 + 32 + 16 = 48 \\
\text{Beregn grænsen af} \quad & \lim_{x \to 2} \frac{x^3 - 3x^2 + 4}{2x^2 - 4x + 8} \\
\text{Substituer x = 2 direkte:} \quad & \frac{(2)^3 - 3(2)^2 + 4}{2(2)^2 - 4(2) + 8} = \frac{8 - 12 + 4}{8 - 8 + 8} = \frac{0}{8} = 0 \\
\text{Den generelle løsning til differentialligningen} \quad & \frac{dy}{dx} - y = e^x \\
\text{Løs ved hjælp af den integrerende faktor. Den integrerende faktor er} \quad & \mu(x) = e^{\int -1 \, dx} = e^{-x} \\
\text{Multiplicer begge sider af ligningen med} \quad & \mu(x): e^{-x} \frac{dy}{dx} - e^{-x} y = e^{-x} e^x \\
\text{Dette forenkles til:} \quad & \frac{d}{dx} (y e^{-x}) = 1 \\
\text{Integrer begge sider:} \quad & y e^{-x} = \int 1 \, dx = x + C \\
\text{Løs for y:} \quad & y = (x + C) e^x \\
\text{Beregn værdien af det bestemte integrale} \quad & \int_{-2}^{3} \frac{2}{3 + x} \, dx \\
\text{Løsningen til dette er:} \quad & \int \frac{2}{3 + x} \, dx = 2 \ln |3 + x| \\
\text{Evaluér det bestemte integral:} \quad & \left[ 2 \ln |3 + x| \right]_{-2}^{3} = 2 \ln |3 + 3| - 2 \ln |3 - 2| = 2 \ln 6 - 2 \ln 1 = 2 \ln 6 \\
\text{Det bestemte integral er derfor:} \quad & 2 \ln 6 \\
\text{Bestem udtrykket for det ubestemte integrale} \quad & \int x e^{-x} \, dx \\
\text{Brug delvis integration med} \quad & u = x, \quad dv = e^{-x} dx, \quad du = dx, \quad v = -e^{-x} \\
\text{Delvis integration giver:} \quad & \int x e^{-x} \, dx = -x e^{-x} + \int e^{-x} \, dx \\
\text{Integrer den sidste del:} \quad & \int e^{-x} \, dx = -e^{-x} \\
\text{Så den ubestemte løsning er:} \quad & -x e^{-x} - e^{-x} + C = -(x + 1)e^{-x} + C \\
\text{Opdel udtrykket i partial brøker:} \quad & \frac{4x + 13}{(x + 3)(x + 4)} \\
\text{Vi søger at finde konstantene} \quad & A \text{ og } B \text{ sådan, at} \\
& \frac{4x + 13}{(x + 3)(x + 4)} = \frac{A}{x + 3} + \frac{B}{x + 4} \\
\text{Multipliser begge sider med} \quad & (x + 3)(x + 4) \text{ for at få:} \\
& 4x + 13 = A(x + 4) + B(x + 3) \\
\text{Udvid og sammenlign koefficienterne:} \quad & 4x + 13 = A x + 4A + B x + 3B \\
\text{Samle ledene:} \quad & 4x + 13 = (A + B)x + (4A + 3B) \\
\text{Sæt koefficienterne lig hinanden:} \quad & A + B = 4, \quad 4A + 3B = 13 \\
\text{Løs dette system af ligninger for} \quad & A \text{ og } B: \quad A = 5, \quad B = -1 \\
\text{Partialbrøkdekompositionen er derfor:} \quad & \frac{4x + 13}{(x + 3)(x + 4)} = \frac{5}{x + 3} - \frac{1}{x + 4} \\
\text{Bestem den reelle og imaginære del af tallet} \quad & z = (1 + 2i)(2 - i)(1 + i) \\
\text{Beregn først de to første faktorer:} \quad & (1 + 2i)(2 - i) = 2 - i + 4i - 2i^2 = 2 - i + 4i + 2 = 4 + 3i \\
\text{Multiplicer derefter med den tredje faktor:} \quad & (4 + 3i)(1 + i) = 4 + 4i + 3i + 3i^2 = 4 + 4i + 3i - 3 = 1 + 7i \\
\text{Så den reelle del er} \quad & 1, \quad \text{og den imaginære del er} \quad 7 \\
\text{Indtegn de følgende værdier i et Argand diagram:} \quad & z_1 = 1 + 2i, \quad z_2 = 2 - i, \quad z_3 = 3 e^{i\pi/4}, \quad z_4 = 3 e^{i5\pi/4} \\
\text{Placeringen af punkterne er:} \quad & z_1 = 1 + 2i \quad \text{er i punktet} \ (1, 2) \\
& z_2 = 2 - i \quad \text{er i punktet} \ (2, -1) \\
& z_3 = 3 e^{i\pi/4} = \frac{3\sqrt{2}}{2} + i \frac{3\sqrt{2}}{2} \approx (2.121, 2.121) \\
& z_4 = 3 e^{i5\pi/4} = -\frac{3\sqrt{2}}{2} - i \frac{3\sqrt{2}}{2} \approx (-2.121, -2.121) \\
\end{align*}
$$
