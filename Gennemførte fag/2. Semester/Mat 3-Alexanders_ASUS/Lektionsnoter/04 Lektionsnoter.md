Man kan bruge formlen til at beregne hvordan et legeme leder varmen

$$
\frac{\delta u}{\delta t} = c^{2} \frac{\delta ^{2} u}{\delta t^{2}}
$$

![[Mat 3 04.pdf]]


Eksempel:
$$
\frac{\delta^{2} u}{\delta t^{2}} = c^{2}\frac{\delta^{2}u}{\delta x^{2}}
$$
Kan også skrives som:
$$
u_{tt}= c^{2}u_{xx}
$$
#### Generelt:
$$
A \frac{\delta^{2}u}{\delta x^{2}} + B \frac{\delta^{2}u}{\delta x \delta y} + C \frac{\delta^{2}u}{\delta y^{2}}+f \left(x,y,u,\frac{\delta u}{\delta x}, \frac{\delta u}{\delta y}\right)= 0
$$
$$
\begin{align*}
B^{2}-4AC &< 0, \quad \text{Elliptisk}\\
B^{2}-4AC &= 0, \quad \text{Parabolsk}\\
B^{2}-4AC &> 0, \quad \text{Hyperbolsk}
\end{align*}
$$
Dette står der på side 555.

Så hvis vi kigger tilbage på:
$$
\frac{\delta^{2} u}{\delta t^{2}} = c^{2}\frac{\delta^{2}u}{\delta x^{2}}
$$
Så må den være hyperbolsk idet:
$$
\begin{align*}
A&=c^{2}\\
B&= 0\\
C&= -1 
\end{align*}
$$

$$
2x \frac{\delta z}{\delta x} - 3 y \frac{\delta z}{\delta y} = 0, \quad \text{hvor } z=z(x,y)
$$
Separation af de variable:
$$
\begin{align*}
z&= X(x) \cdot Y(y), \quad \text{hvor } X=X(x) \text{ og } Y=Y(y)\\
\frac{\delta z}{\delta x}&=  X' \cdot Y \text{ og } \frac{\delta z}{\delta y}=X\cdot Y'
\end{align*}
$$
Substitution:
$$
\begin{align*}
2x X'Y - 3yXY' &= 0\\
2xX'Y&= 3yXY'\\
2x \frac{X'}{X} &= 3y \frac{Y'}{Y} = k, \quad \text{ Idet x og y er uafhængige}\\
2x \frac{X'}{X}&= k \quad \text{og } \quad 3y \frac{Y'}{Y}= k\\
\frac{1}{X}\cdot \frac{dX}{dx}&= \frac{1}{2} \frac{k}{x}\\
\frac{1}{X} dX = \frac{k}{2} \frac{1}{x} \, dx\\
\int \frac{1}{X} dX = \int \frac{k}{2} \frac{1}{x} \, dx\\
\ln(X) = \frac{k}{2}\ln(x) + \ln(c_{1})\\
\ln(X) = \ln (X^{\frac{k}{2}}\cdot c_{1})\\
X = c_{1} \cdot x^{\frac{k}{2}}\\
\\
Y=c_{2}\cdot y^{\frac{k}{3}}\\
\\
c=c_{1}c_{2}\\
z = cx^{\frac{k}{2}}\cdot y^\frac{k}{3}
\end{align*}
$$
#### Bølgeligningen:
![[Mat 3 04.pdf#page=3]]
$$
\begin{align*}
\frac{\delta^{2} u}{\delta t^{2}}&= c^{2}\frac{\delta^{2} u}{\delta x^{2}}\\
\text{Eller:}\\
u_{tt}&= c^{2}u_{xx}\\
c^{2}&= \frac{T}{m}
\end{align*}
$$
Det er $c^{2}$ fordi man vil sørge for at det er et positivt tal.

$$
\begin{align*}
u(x,t) &= X(x) \cdot T(t)\\
u_{xx} &= X''T \text{ og } u_{tt}=XT'' \\
\text{substition}:\\
XT''&= c^{2}X''T\\
\frac{X''}{X}&= \frac{1}{c^{2}}\frac{T''}{T}=k \quad \text{Da de er uafhængige}\\
X''-kX&= 0\\
\frac{1}{c\\
^{2}}T''-kT&= 0\\
\\
\text{CASE 1: } k>0 \text{ og sæt } k&= p^{2}\\
\text{karakterligningen: } \lambda^{2}-p^{2}&= 0 \rightarrow \lambda = \pm p\\
X(t) &= C_{1}e^{px} + c_{2}e^{-px}\\
\\
\text{CASE 2: } k>0 \text{ og sæt } k&= -p^{2}\\
\text{karakterligningen: } \lambda^{2}+p^{2}&= 0\\
\lambda^{2}+p^{2}=0 \rightarrow \lambda &= \pm ip \text{(kompleks rod)}\\
X(x)=A_{1}\cos(px) + A_{2}\sin(px)\\
\\
\text{CASE 3: } k&= 0\\
X''=0 \rightarrow X(x) &= ax+b\\
\end{align*}
$$
I vores tilfælde skal vi bruge CASE 2:
$$
\begin{align*}
\text{CASE 2 } k<0 \text{ og } k&= -p^{2}\\
T''+p^{2}c^{2}T\\
\text{karakterligningen: } \lambda^{2}+ (pc)^{2}&= 0\\
T(t) &= A_{3}\cos(pct) + A_{y}\sin(pct)\\
u(x,t) &= (A_{1}\cos(px) + A_{2}\sin(px))(A_{3}\cos(pct) + A_{4}\sin(pct))
\end{align*}
$$
Randbetingelser
$$
\begin{align*}
u(0,t) &= 0\\
u(l,t)=0\\
u(0,t)=(A_{1}\underbrace{\cos(0)}_{=1}+A_{2}\underbrace{\sin(0)}_{=0}+A_{3}\cos(pct)+A_{4}\sin(pct))=0 \rightarrow A_{1}&=  0\\
\text{nu er: }\\
u(x,t)= A_{2}\sin(px)(A_{3}\cos(pct)+A_{4}\sin(pct))\\
u(l,t) = A_{2}\sin(pl)(A_{3}\cos(pct)+A_{4}\sin(pct))&= 0\\
\sin(pl)=0\rightarrow pl=n\pi\rightarrow p=\frac{n \pi}{l}\\
\text{Dvs. en violinsstreng ikke kan spille alle toner, kun nogle bestemte}\\
\text{dvs.}\\
u(x,t) = A_{2} \sin\frac{n \pi}{l} x(A_{3} \cos(pct)+A_{4}\sin(pct))\\
\end{align*}
$$
![[Fig 287.png]]
#### Startbetingelser
$u(0,t) = 0$
$u(l,t)=0$
Hastighed: $v= \frac{\delta u(x,0)}{\delta t}$
Position: $u(x,0)$

$$
\begin{align*}
\frac{\delta u}{\delta t}&=  A_{2}\sin\left(\frac{n \pi}{l}\right)x(-A_{3}pc \sin(pct) + A_{4}pc \cos(pct))\\
\frac{\delta u (x,0)}{\delta t}=A \sin\left(\frac{n \pi}{l}\right)x (0+A_{4}pc \cdot 1) &=  0\\
A_{4}&= 0\\
\text{nu er}\\
u_{n}(x,t)&= A_{n} \sin\left(\frac{n \pi}{l}\right)x \cdot \cos\left(\frac{n \pi c}{l}\right) t\\
\text{dvs.}\\
u(x,t) = \sum_{n \, = \, 1}^{\infty} &=  A_{n}\sin\left(\frac{n \pi}{l}\right)x \cos\left(\frac{n \pi c}{l}\right) t\\
u(x,0) = \sum_{n\,=\,1} ^{\infty} A_{n}\sin\left(\frac{n \pi}{l}\right) x &= f(x)\\
\text{hvor}\\
A_{n}= \frac{2}{l}\int_{0}^{l} f(x) \sin\left(\frac{n \pi}{l}\right)x \, dx
\end{align*}
$$
![[Mat 3 04.pdf#page=5]]
$$
\cases{\frac{8kl^{2}}{(n \pi)^{3}} & \text{n ulige} \\ 0 & \text{n lige}}
$$
$$
u(x,t)= \underbrace{\sum_{n \, = \, 1} ^{\infty}}_{\text{n ulige}} \frac{8kl^{2}}{(n \pi)^{3}} \sin\left(\frac{n \pi}{l}\right) x \cdot \cos\left(\frac{n \pi c}{l}\right)t
$$
![[Mat 3 04.pdf#page=6]]
![[Pasted Images/2. Semester/Mat 3/04/Fig 291.png]]