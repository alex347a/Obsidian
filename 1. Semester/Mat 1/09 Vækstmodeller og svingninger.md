- Eksponentiel vækst
- Logistisk vækst

Eksponentiel vækst
$$\frac {dy}{dx}=k\cdot y$$
Man kan tegne det i et [[linjeelement plot]].
Generel løsning
$$y(t)=y_0\cdot e^{k\cdot t}$$
## Fordoblingstid og halveringstid
$$T_{\frac{1}{2}}=\frac{-ln(2)}{k}$$
$$y(t+T_{d})=2\cdot y(t)$$
$$\cancel {y_{0}}\cdot e^{k(t+T_d)}=2\cdot \cancel {y_{0}}\cdot e^{kt}$$
$$\cancel {e^{kt}}\cdot e^{kT_d}=2\cdot \cancel {e^{kt}}$$
$$ln(e^{kT_d})=ln(2)$$
$$k\cdot T_{d}=ln(2)$$
$$T_{d}=\frac{ln(2)}{k}$$
Hvis det er halveringstid er der et minus, hvis ikke er det en fordoblingstid.

Eksempel
$$T(0)=80\degree C$$
$$T(5)=50\degree C$$
$$T(?)=40\degree C$$
$$\frac{dy}{dt}=-k(y-20)$$
For at løse dette bestemmer vi værdien af k:
Substituere:
$$u(t)=y(t)-20$$
$$u'(t)=y'(t)$$
$$\frac {du}{dt}=-k\cdot u(t)$$
$$u(t)=u_{0}\cdot e^{-k\cdot t}$$
$$u(0)=y(0)-20=80-20=60$$
$$u(5)=y(5)-20=50-20=30$$
$$u(0)=u_{0}\cdot e^{-k\cdot0}=60$$
Hvor $e^{-k\cdot 0}=1$:
$$u_0=60$$
$$u(5)=u_{0}\cdot e^{-k\cdot 5}$$
$$e^{-k\cdot 5}=\frac {30}{60}=\frac {1}{2}$$
$$-k\cdot 5=ln\left(\frac {1}{2}\right)$$
$$k=\frac {-ln(\frac{1}{2})}{5}$$
$$=\frac {ln(2)}{5}$$
Indsæt k og $u_0$ i generel løsning:
$$u(t)=60\cdot e^{\frac{-ln(2)}{2}}$$
$$u(t)=20$$
$$20=60\cdot e^{\frac{-ln(2)}{2}\cdot t}$$
$$\frac {1}{3}=e^{-ln(2)\cdot \frac{t}{5}}$$
$$ln\left(\frac {1}{3}\right)=-ln(2)\cdot \frac {t}{5}$$
$$t=\frac {-ln(\frac {1}{3})\cdot 5}{ln(2)} = \frac {ln(3)}{ln(2)}\cdot 5\approx 7.9$$
## Logistisk vækst
$$\frac {dy}{dt}=k\cdot y\cdot \left(1-\frac{y}{L}\right)$$
$$y\approx L\rightarrow \frac{dy}{dt}\approx 0$$
Løsning:
$$y(t)=\frac{L\cdot y_{0}}{y_{0}+(L-y_{0}\cdot e^{-k\cdot t})}$$
Grænseværdien:
$$\lim_{t\rightarrow \infty}(e^{-k\cdot t})=0$$
$$\lim_{t\rightarrow \infty}(y(t))=L$$
$$\lim_{t\rightarrow -\infty}(e^{-k\cdot t})=\infty$$
$$\lim_{t\rightarrow -\infty}(y(t))=0$$
$$\frac {dy}{dt}=k\cdot y\cdot \left(1-\frac{y}{L}\right)$$
Højresiden svarer til: $f(x)\cdot g(x)$.
$$=\int \frac {k}{L}\cdot y\cdot (L-y)\space dt$$
$$\int \frac {1}{y\cdot (L-y)}\space dy=\frac {k}{L}\space dt$$
$$\int \frac {1}{y}+\frac {1}{L\cdot y}\space dy=\frac {k}{L}\cdot t+C_{1}$$
$$ln(y)-ln(L-y)=\frac {kt}{L}+C_1$$
$$ln\left(\frac {y}{L-y}\right)=\frac {kt}{L}+C_{1}$$
$$\frac {y}{L\cdot y}=e^{\frac{kt+C_1}{L}}$$
$$y=(L-y)e^{\frac {kt}{L}+C_1}$$
$$=L\cdot e^{\frac {kt}{L}+C_{1}}-y\cdot e^{\frac{kt}{C}+C_1}$$
$$y(1+e^{\frac{kt}{L}}+C_{1})=L\cdot e^{\frac{kt}{L}}$$
$$y=\frac {e^{\frac{kt}{L}}+C_1}{1+e^{\frac{kt}{L}}+C_1}$$
$$\frac {L}{e^{\frac{-kt}{L}}+C_1+1}$$
Her er der en fejl med L, som Henrik vil vende tilbage til

Anden orderns differentialligninger med konstante koefficienter
$$a\cdot y''+b\cdot y'+c\cdot y=0$$
Givet løsningerne u(t) og v(t)
$$y(t)=A\cdot u(t)+B\cdot v(t)$$
Gæt på y(t)=$e^{r\cdot t}$ 
$$y'(t)=r\cdot e^{r\cdot t}$$
$$y''(t)=r^{2}\cdot e^{r\cdot t}$$
Indsæt i dfferentialligningen:
$$a\cdot r^{2}\cdot e^{r\cdot t}+b\cdot r\cdot e^{r\cdot t}+c\cdot e^{r\cdot t}=0$$
$$e^{r\cdot t}\cdot \left(ar^{2}+br+c \right)=0$$
Dette er opfyldt hvis enten det på den ene side eller den anden side af gangetegnet er 0, men da e opløftet i noget aldrig kan give 0, så skal det være det på højresiden af gangetegnet.

Opskrift
Løs karakterligningen:
$$ar^{2}+br+c=0$$
Vi bruger diskriminantformlen:
$$r=\frac {-b\pm \sqrt{D}}{2a}$$
$$D=b^{2}-4ac$$
Tilfælde 1:
$$D>0$$
$$r_{1}=\frac {-b+\sqrt D}{2a}$$
$$r_{2}=\frac {-b-\sqrt D}{2a}$$
$$y(t)=A\cdot e^{r_{1}\cdot t}+B\cdot e^{r_{2}\cdot t}$$
Tilfælde 2:
$$D=0$$
$$r=\frac {-b}{2a}$$
$$y(t)=A\cdot e^{r\cdot t}+B\cdot t\cdot e^{r\cdot t}$$
Tilfælde 3:
$$D<0$$
$$r=\frac {-b\pm \sqrt D}{2a}$$
$$=\frac {-b}{2a}\pm i\cdot \frac{\sqrt{D}}{2a}$$
$$=k\pm i\cdot \omega$$
$$y(t)=A\cdot e^{kt}\cdot cos(\omega \cdot t)+B\cdot e^{kt}\cdot sin(\omega \cdot t)$$
### Underdæmpet, kritiskdæmpet og overdæmpet system:
Underdæmpet:
![[Underdæmpet system.png]]
Kritiskdæmpet: ![[Kritiskdæmpet system.png]]
Overdæmpet:![[Overdæmpet system.png]]
Praktisk eksempel: fjeder![[Fjeder.png]]
Eksempel 1
$$y''+y'-2y=0$$
$$r^{2}+r-2=0$$
$$r=\frac {-1\pm \sqrt{1^{2}-4\cdot 1\cdot (-2)}}{2\cdot 1}$$
$$=\frac {-1+\pm \space 3}{2}\rightarrow r=-2 \lor r=1$$
$$y(t)=A\cdot e^{-2t}+Be^{t}$$
Eksempel 2
$$y''+6y'+9y=0$$
$$r^{2}+6r+9=0$$
$$r=\frac {-6\pm \sqrt {6^{2}-4\cdot 1\cdot 9}}{2\cdot 1}$$
$$=\frac {-6}{2}=-3$$
$$y(t)=A\cdot e^{3t}+B\cdot t\cdot e^{3t}$$
Eksempel 3
$$y''+4y'+13y=0$$
$$\frac{4\pm \sqrt {4^{2}-4\cdot 1\cdot 3}}{2\cdot 1}$$
$$=\frac{-4\pm \sqrt{-36}}{2}$$
$$=-2\pm i\cdot 3$$
$$y(t)=A\cdot e^{-2t}\cdot cos(3t)+B\cdot e^{-2t}\cdot sin(3t)$$