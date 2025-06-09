Ved dobbeltintegraler var det over arealet dA, som gav en volumen
Ved trippel integraler er det over volumen, som giver et område i 3D, et eller andet objekt, såsom en kugle, eller en blob.
$$
\begin{align*}
\iiint_{D} f(x,y,z)\space dxdydz\\
\iiint_{D}dV=\text volumen(D)\\
\end{align*}
$$
Eksempel med masse:
Et $\underbrace{\text {legeme}}_{S}$ m. densiteten/massetæthed $\delta (x,y,z)$:
$$\text {masse}\space \text m=\iiint_{S}\delta (x,y,z)\space dV$$
Eksempel:
$$
\begin{align*}
I=\iiint_{T} y\space dV\\
\end{align*}
$$
T givet ved (0,0,0), (1,0,0), (0,1,0), (0,0,1)
Tegning 1:

$$
\begin{align*}
I&= \int_{x=0}^{1} dx \int_{y=0}
\text{punkt på et plan} \begin{pmatrix}x_{0} \\ y_{0} \\ z_{0}\end{pmatrix} \vec{n}=\begin{pmatrix}A \\ B \\ C\end{pmatrix}=\begin{pmatrix}1 \\ 1 \\ 1\end{pmatrix} \vec{n}= \vec{v_{1}} \times \vec{v_{2}}\\\\
A(x-x_{0})+B(y-y_{0})+C(z-z_{0})= 0\\
1(x-1)+1(y-0)+1(z-0)=0<=>z= 1-x-y\\

\text{så nu bliver integralet}\\
I=\int_{x=0}^{1} dx \int_{y=0}^{1-x}dy \int_{z=0}^{1-x-y}y\space dz\\
=\int_{0}^{1}kx \int_{\delta}^{1-x}y\space dy(1-x-y)=\int_{0}^{1}dx\space \int_{0}^{1-x}y(1-x)-y^{2}\space dy\\
=\int_{0}^{1}dx\int_{0}^{1-x}\left[\frac{1}{2}y^{2}(1-x)-\frac{1}{3}y^{3}\right]_{0}^{1-x}=\int_{0}^{1}dx\left(\frac{1}{2}(1-x)^{3}-\frac{1}{3}(1-x)^{3}\right)\\
\frac{1}{6}\cdot \int (1-x)^{3}\space dx=\frac{1}{6}\cdot \frac{-1}{4}\left[(x-1)^{4}\right]_{0}^{1}=\frac{-1}{24}\cdot \left(0^{4}-1^{4}\right)\\\\
= \frac{1}{24}
\end{align*}
$$
Variabelskift
$$
I=\iiint_{D}f(x,y,z)\space dxdydz
$$
Nye variable: u,v,w
x(u,v,w)
y(u,v,w)
z(u,v,w)

$$
\begin{align*}
&= \iiint_{S}f\left(x(u,v,w),\space y(u,v,w),\space z(u,v,w)\right)\underbrace{\left|\frac{\delta(x,y,z)}{\delta (u,v,w)}\right|}_{\text{numerisk}}dudvdw\\
\frac{\delta(x,y,z)}{\delta (u,v,w)}=\underbrace{\begin{vmatrix}\frac{dx}{du} & \frac{dx}{dv} & \frac{dx}{dw}\\
\frac{\delta y}{\delta u} & \frac{\delta y}{\delta v} & \frac{\delta y}{\delta u}\\
\frac{\delta z}{\delta u} & \frac{\delta z}{\delta v} & \frac{\delta z}{\delta u}\end{vmatrix}}_{determinant}\\\\
\end{align*}
$$
## Cylinder koordinater (polære +z)
![[Cylindriske koordinater trippel integrale.png]]
$$
\begin{align*}
x=r\cdot cos(\theta)\\
y=r\cdot sin(\theta)\\
z=z\\
dV=r\space dr\space d\theta \space dz
\end{align*}
$$
## Sfæriske koordianter:
![[Sfæriske koordinater trippel integrale.png]]
$$
\begin{align*}
x=R\cdot sin(\phi)\cdot cos(\theta)\\
y=R\cdot sin(\phi)\cdot sin(\theta)\\
z=R\cdot cos(\phi)\\
x^{2}+y^{2}+z^{2}=R^{2}
\end{align*}
$$
$$dV=R\cdot \sin (\phi)\space d\theta\space dR\cdot R\space d\theta =R^{2}\cdot \sin (\phi) \space dR\space d\phi\space d\theta $$

## eksempel massemidtpunkt
Legeme $R$ med densitet $\delta (x,y,z)$
masse:  $m=\iiint_{R} \delta (x,y,z)\space dV$
massemidtpunkt: $\overline{P} = (\overline{x},\overline{y},\overline{z})$ 
$$
\begin{align*}
\overline{x}&= \frac{1}{m}\iiint_{R}x\space \delta (x,y,z)\space dV\\
\overline{y}&= \frac{1}{m}\iiint_{R}y\space \delta (x,y,z)\space dV\\
\overline{z}&= \frac{1}{m}\iiint_{R}z\space \delta (x,y,z)\space dV\\
\end{align*}
$$
Legeme S i 1. oktant og $x^{2}+y^{2}+z^{2}\le a^2$
Densitet $\delta (x,y,z) = k\cdot R$, hvor $R=\sqrt{x^{2}+y^{2}+z^{2}}$
Se tegning 2

$$
m=\iiint_{S}k\cdot R\space \underbrace{dV}_{R^{2}\cdot \sin (\phi) dr\space d\phi \space d\theta}=k\cdot \int_{0}^{a}dR \int_{0}^{\frac{\pi}{2}}d\phi \cdot \int_{0}^{\frac{\pi}{2}}R\cdot R^{2}\cdot \sin(\phi)\space d\theta 
$$
$$m=k\int_{0}^{a}R^{3}\space dR\cdot \int_{0}\frac{\pi}{2}\sin(\phi)\space d\phi \cdot \int_{0}^{\frac{\pi}{2}}d\theta$$
$$=k\cdot \frac{1}{4}a^{4}\cdot \left[-cos(\phi)\right]_{0}^{\frac{\pi}{2}}\cdot \frac{\pi}{2}=\frac{k\pi\cdot a^{4}}{8}\cdot \left(\underbrace{-cos\left(\frac{\pi}{2}\right)}_{0}+\underbrace{cos(0)}_{1}\right)=\frac{k\pi a^{4}}{8}$$
Pga. symmetri er $\overline{x}=\overline{y}=\overline{z}$ og fordi densiteten er symmetrisk.
$$\overline{x}=\frac{1}{m}\iiint_{S}x\cdot k\cdot R\space dV=\frac{k}{m}\int_{0}^{a}dR\int_{0}^{\frac{\pi}{2}}d\theta\int_{0}^{\frac{\pi}{2}}R\cdot sin(\phi)\cdot cos(\theta)\cdot R\cdot R^{2}\cdot \sin(\phi)$$
$$= \frac{k}{m}\underbrace{\int _{0}^{a}=R^{4}\space dR}_{\frac{1}{5}a^{5}}\underbrace{\int_{0}^{\frac{\pi}{2}}\sin^{2}(\phi)\space d\phi}_{\frac{\pi}{4}} \underbrace{\int_{0}^{\frac{\pi}{2}}cos(\theta)\space d\theta}_{1}$$
Dette er fordi:
$${\int_{0}^{\frac{\pi}{2}}\sin^{2}(\phi)\space d\phi}=\left[\frac{\phi}{2}-\frac{1}{4}\cdot\sin(2\phi)\right]_{0}^{\frac{\pi}{2}}$$
$$=\frac{\pi}{4}-\frac{1}{4}\cdot \sin(\pi)-(0-0)=\frac{\pi}{4}$$
Og:
$${\int_{0}^{\frac{\pi}{2}}cos(\theta)\space d\theta}=[\sin(\theta)]_{0}^{\frac{\pi}{2}}=\sin\left(\frac{\pi}{2}\right)-\sin(0)=1$$
Dermed får vi:
$$\overline{x}=\frac{k}{m}\cdot \frac{1}{5}a^{5}\cdot \frac{\pi}{4}\cdot 1=\frac{8}{k\pi a^{4}}\cdot \frac{k\pi a^{5}}{20}=a^{\frac{2}{5}}$$
$$\overline{p}=a^{\frac{2}{5}}\cdot \begin{pmatrix}1 \\ 1 \\ 1\end{pmatrix}$$