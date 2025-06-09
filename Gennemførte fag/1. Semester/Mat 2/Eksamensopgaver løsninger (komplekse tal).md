Opgave 3
a) Betragt det komplekse tal: $z=2e^(i pi/2) (1+i)$ hvor i er det komplekse tal. Beregn $[z]$ og $arg(z)$
$$
\begin{align*}
\text{eulers formel}:\\
e^{i \theta}&= \cos(\theta)+i \sin(\theta)\\
\text{Derfor får jeg}:\\
e^{\frac{i \pi }{2}}&= i\\
z&= 2i(1+i)\\
&= 2i+2i^{2}\\
\text{Da }i^{2}&= -1\\
&= -2+2i\\
\text{Jeg beregner nu }|z|:\\
|z|&= \sqrt{(-2)^{2}+(2)^{2}}\\
&= \sqrt{4+4}=\sqrt{8}=2\sqrt{2}\\
\end{align*}
$$
Argumentet for z er vinklen z og den positive reele akse. 
$$
\arg(z)=\arctan\left(\frac{Im(z)}{Re(z)}\right)
$$
For $z=-2+2i$, ligger z i anden kvadrant, hvor vinklen derfor kan udtrykkes ved at addere $\pi$:
$$
\begin{align*}
\arg(z)&= \arctan\left(\frac{Im(z)}{Re(z)}\right)+\pi\\
Im(z)=2,\quad Re(z)&= -2\\
\arg(z)&= \left(\frac{2}{-2}\right)+\pi\\
&= \arctan(-1)+\pi\\
\text{Da }\arctan(-1)&= \frac{-\pi}{4}:\\
\arg(z)=\frac{-\pi}{4}+\pi&= \frac{3\pi}{4}
\end{align*}
$$b) Betragt den komplekse ligning:
$$
\omega^{3}=81
$$
og bestem $|\omega^{3}|$ og $\arg(\omega^{3})$
$$
\begin{align*}
|z|&= \sqrt{a^{2}+b^{2}}\\
z=a+ib\\
\text{Dette er mens}\\
\omega^{3}=81+0i\\
|\omega^{3}|=\sqrt{81^{2}+0^{2}}&= 81\\
\end{align*}
$$
For at beregne argumentet $\arg(\omega^{3})$ så kan jeg se at da 81 er et positivt reelt tal, så ligger det på den positive reele akse i det komplekse plan. Argumentet for et tal på den positive reele akse er:
$$
\begin{align*}
\arg(\omega^{3})&= 0\\
\text{Da}:\\
\arg(z)&=  \arctan\left(\frac{Im(z)}{Re(z)}\right)\\
\arctan\left(\frac{0}{81}\right)&= 0
\end{align*}
$$

c) Løs den komplekse ligning
For at løse den skriver jeg den først i polær form og derefter finder de tre rødder:
$$
81=81e^{i0}
$$
Hvor modulus er 81 og argumentet er 0 (da 81 ligger på den positive reele akse)

$$
\begin{align*}
\omega=\sqrt[3]{81}e^{i \frac{\arg(81)+2k\pi}{3}},\quad k=0,1,2\\
|\omega|=\sqrt[3]{81}=3 \sqrt{3}\\
\arg(\omega)=\frac{0+2k \pi}{3}=\frac{2k \pi}{3}\\
\end{align*}
$$
De tre løsninger er $k=0,1,2$:

For $k=0$
$$
\begin{align*}
\omega_{0}=3 \sqrt{3}e^{i \frac{2\cdot 0}{3}}&= 3\sqrt{3}\\\\
\text{for k=1}\\
\omega_{1}= 3 \sqrt{3}e^{i \frac{2\pi}{3}}&= 3 \sqrt{3}\left(\cos\left(\frac{2\pi}{3}\right)+i \sin\left(\frac{2\pi}{3}\right)\right)\\
&= 3 \sqrt{3} \left(- \frac{1}{2}+ i \frac{\sqrt{3}}{2}\right)\\
\omega_{1}&= - \frac{3\sqrt{3}}{2}+i \frac{9}{2}\\
\\
\text{for k=2}\\
\omega2 = 3 \sqrt{3}e^{i \frac{4\pi}{3}}&=  3 \sqrt{3}\left(\cos\frac{4\pi}{3}+i \sin\left(\frac{4\pi}{3}\right)\right)\\
&= 3 \sqrt{3}\left(- \frac{1}{2}-i \frac{\sqrt{3}}{2}\right)\\
\omega_{2}&= - \frac{3\sqrt{3}}{2}-i \frac{9}{2}
\end{align*}
$$
De tre komplekse løsninger til ligningen $\omega^{3}=81$ er:
$$
\begin{align*}
\omega_{0}&= 3\sqrt{3}\\
\omega_{1}&= - \frac{3\sqrt{3}}{2}+i \frac{9}{2}\\
\omega_{2}&= - \frac{3\sqrt{3}}{2}-i \frac{9}{2}\\\\
\end{align*}
$$
d) En anden kompleks ligning har løsningerne

Afbild $z_{1}, z_{2}, z_{3}$ og $z_{4}$ i et Argand diagram. Husk at illustrere, hvordan du er kommet
frem til punkternes placering.

$z_1 = 2\cdot e^{\frac{i\cdot 2\pi}{6}} z_2 = 2\cdot e^{\frac{i\cdot 5\pi}{6}} z_3 = 2\cdot e^{\frac{-i\cdot \pi}{6}} z_4 = 2\cdot e^{\frac{-i\cdot 4\pi}{6}}$

Jeg beregner kan afbilde placeringen af punkterne ved at konvertere dem fra polær form til rektangulær form:
$$
\begin{align*}
e^{i \theta}=\cos(\theta)+i\sin(\theta)\\
z_1 = 2\cdot e^{\frac{i\cdot 2\pi}{6}}=2\left(\cos\left(\frac{2\pi}{6}\right)+i \sin\left(\frac{2\pi}{6}\right)\right)= 2\left(\frac{1}{2}+i \frac{\sqrt{3}}{2}\right)&= 1+i \sqrt{3}\\
z_2 = 2\cdot e^{\frac{i\cdot 5\pi}{6}}=2\left(\cos\left(\frac{5\pi}{6}\right)+i \sin\left(\frac{5\pi}{6}\right)\right)= 2\left(-\frac{\sqrt{3}}{2}+i \frac{1}{2}\right)&= \sqrt{3}+i\\
z_3 = 2\cdot e^{\frac{-i\cdot \pi}{6}}=2\left(\cos\left(\frac{-\pi}{6}\right)+i \sin\left(\frac{-\pi}{6}\right)\right)= 2\left(\frac{\sqrt{3}}{2}+i \frac{1}{2}\right)&= \sqrt{3}-i\\
z_4 = 2\cdot e^{\frac{-i\cdot 4\pi}{6}}=2\left(\cos\left(\frac{-4\pi}{6}\right)+i \sin\left(\frac{-4\pi}{6}\right)\right)= 2\left(-\frac{1}{2}-i \frac{\sqrt{3}}{2}\right)&= -1-i \sqrt{3}\\
\end{align*}
$$
Det kan også bruges at der uanset hvad kommer til at være lige stort mellemrum i vinkel mellem alle vinklerne. Hvor cirklen i dette tilfælde har en radius på 2, da $z=re^{i \theta}$. 
Hvis du kan forestille dig en cirkel hvor det først punkt er 30 grader opad og så er der 90 grader imellem hvert punkt.