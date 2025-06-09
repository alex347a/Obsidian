## Første ordens differentialligninger
eksempel:
$$\frac{dy}{dx}=-0.2\cdot y+sin(x)$$
Betydning af de enkelte dele:
$\left[\frac{dy}{dx}\right]$ - 1. orden
$[x]$ - uafhængig variabel 
$[y]$ - afhængig variabel 

## Slope plot af en differentialligning

![[Slopeplot af -0.2 y sin(x).png]]
## Differentialligning generel løsning:
$$y(x)=Ae^{-1x}$$
Sammen med en begyndelsesværdi kan man finde den specifikke løsning:
$$y(0)=2$$
$$y(x)=2e^{-x}$$
![[En løsning af -0.2 y sin(x).png]]
$$\frac{dy}{dx}=x^{2}$$$$\frac{dh}{dt}=-g$$$$\frac{dT}{dt}=(T_{0}-T)\cdot k$$
Generel form
$$\frac{dy}{dx}=h(x,y)$$
$$h(x,y)=x+y+e^{x\cdot y+y}$$
### Efterprøve en løsning:
$$\frac{dy}{dt}=3\cdot y$$
Gæt: $y(t)=4e^{3t}$
$$\frac{dy}{dt}=\frac{d}{dt}\left(4e^{3t}\right)$$
$$=4\cdot 3\cdot e^{3t}$$
$$=12\cdot e^{3t}$$
$$3y=3\cdot \left(4\cdot e^{3t}\right)$$
$$=3\cdot 4\cdot e^{3t}$$
$$=12\cdot e^{3t}$$
Begge sider er altså ens, og dermed er $y(t)=4e^{3t}$ en løsning til differentialligningen.

## Separable differentialligninger. (Seperation af variable)
$$\frac{dy}{dx}=f(x)\cdot g(y)$$

$$\frac{1}{g(y)}\cdot \frac{dy}{dx}=f(x)$$
$$\int \frac{1}{g(y)}\cdot \frac{dy}{dx}\cdot dx=\int f(x)\space dx$$
$$=\int \frac{1}{g(y)}\space dy=\int f(x)\space dx$$
$$\frac{dy}{dx}=3x^{2}\cdot e^{-y}$$
$f(x)=3x^{2}$ og $g(y)=e^{-y}$:
$$
\begin{align}

\end{align}
$$
$$e^{y}\cdot \frac{dy}{dx}=3x^{2}$$
$$\int e^{y}\space dy=\int 3x^{2}\space dx$$
$$e^{y}+k_{1}=x^{3}+k_2$$
$$e^{y}=x^{3}+\underbrace{k_{2}-k_{1}}_{k_{3}}$$
$$e^{y}=x^{3}+k_{3}$$
$$ln(e^{y})=ln(x^{3}+k_{3})$$
$$y=ln(x^{3}+k_3)$$
$$\frac{d}{dx}\left(ln(x^{3}+k_{3})\right)$$
$$=\frac{1}{x^{3}+k_{3}}\cdot 3x^{2}$$
$$=3x^{2}\cdot e^{-ln(x^{3}+k_{3})}$$
$$=3x^{2}\cdot \frac{1}{e^{ln(x^{3}+k_{3})}}$$
$$=3x^{2}\cdot \frac{1}{x^{3}+k_{3}}$$

Eksempel 2:
$$\frac{dy}{dx}=\frac{x}{y}=x\cdot \frac{1}{y}$$
$$\int y\cdot \frac{dy}{dx}=\int x\space dx$$
$$\frac{1}{2}y^{2}=\frac{1}{2}x^{2}+k$$
$$y^{2}=x^{2}+2k$$
$$y=\sqrt{x^{2}+k}$$
$$=\pm \sqrt{x^{2}+k}$$
Eksempel:
$$y(x)=3+2\int_{1}^{x}t\cdot y(t)\space dt$$
Differentier:
$$\frac{dy}{dx}=2\cdot x\cdot y$$
$$\int \frac{1}{y}\cdot \frac{dy}{dx}=\int 2x\space dx$$
$$ln(y)=x^{2}+k_{1}$$
$$y=e^{x^{2}+k_{1}}$$
$$=e^{x^{2}\cdot k_{1}}$$
Generel løsning:
$$k_{2}\cdot e^{x^{2}}$$
$$y(1)=3$$
$$k_{2}\cdot e^{1^{2}}$$
$$k_{2}=\frac{3}{e}$$
$$y(x)=\frac{3}{e}e^{x^{2}}$$
## Lineær første ordens differentialligninger:
$$\frac{dy}{dx}+p(x)\cdot y=q(x)$$
### Homogene tilfælde
Hvis $q(x)=0$ så er den ret let at løse, fordi man kan flytte $p(x)\cdot y$ over på højresiden og så separere, hvilket er det der kaldes for homogene tilfælde.
### Inhomogene tilfælde:
Hvis $q(x)\ne 0$, hvilket kaldes for inhomogene tilfælde:
$$
\begin{align*}
\gamma\cdot \frac{dy}{dx}+\gamma \cdot p(x)\cdot y=\gamma(x) \cdot q(x)\\
\frac{d}{dx}(\gamma(x)\cdot y)=\gamma'(x)\cdot y+\gamma(x)\cdot \frac{dy}{dx}\\
\text Sammenlign:\\
\gamma'(x\cdot y=\gamma(x)\cdot p(x)\cdot y\\
\gamma'(x)=\gamma(x)\cdot p(x)\\
\int \frac{1}{y(x)}\cdot \frac{dy}{dx}\space dx=\int p(x)\space dx\\
ln(\gamma)=P(x)\\
\gamma(x)=e^{\int p(x)\space dx}\\
\frac{d}{dx}(\gamma(x)\cdot y)=\gamma(x)\cdot q(x)\\
\gamma(x)\cdot y=\int \gamma(x)\cdot q(x)\space dx\\
y(x)=\frac{1}{\gamma(x)}\cdot \int \gamma(x)\cdot q(x)\space dx
\end{align*}
$$
Eksempel:
$$
\begin{align*}
\frac{dy}{dx}+\frac{y}{x}=1\\
\frac{dy}{dx}+\frac{1}{x}\cdot \underbrace{y}_{p(x)}=\underbrace{1}_{q(x)}\\
\gamma(x)=e^{\int \frac{1}{x}\space dx}\\
=e^{ln(x)}\\
=x\\
y(x)=\frac{1}{\gamma(x)}\cdot \int \gamma(x)\cdot q(x)\space dx\\
=\frac{1}{x}\cdot \int x\cdot 1\space dx\\
=\frac{1}{x}\cdot \left(\frac{1}{2}x^{2}+k\right)\\
=\frac{x}{2}+\frac{k}{x}
\end{align*}
$$
Tjek af løsning:
$$
\begin{align*}
\frac{dy}{dx}=\frac{dy}{dx}\left(\frac{x}{2}+\frac{k}{x}\right)\\
=\frac{1}{2}-k\cdot x^{-2}\\\\

\frac{y}{x}=\frac{\frac{x}{2}+\frac{k}{x}}{x}\\
=\frac{1}{2}+\frac{k}{x^{2}}\\\\
\text Det\space hele\space skulle\space være\space 1\\
\frac{1}{2}-\underbrace{k\cdot x^{-2}}+\frac{1}{2}+\underbrace{\frac{k}{x^{2}}}=1\\
\end{align*}
$$
Eksempel:
Hvis du ikke kan se det der står øverst:
$$\frac{dy}{dx}+\underbrace{x}_{p(x)}\cdot y=\underbrace{x^{3}}_{q(x)}$$
$$\gamma(x)=e^{\int x\space dx}=e^{\frac{1}{2}x^2}$$
![[Mat 1 lektion 10 eksempel 8.jpg]]




