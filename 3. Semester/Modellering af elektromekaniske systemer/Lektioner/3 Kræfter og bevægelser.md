I denne lektion er målet at beskrive translatorisk bevægelse (ingen rotation, men 3D bevægelse)
### Resumé
![[Pasted image 20250916121803.png]]
### Fritlegemediagram pt. 1
Et fritlegemediagram er et diagram, der beskriver hvilket kræfter en masse er påvirket af.
![[Pasted image 20250916121818.png]]
Man laver en bevægelsesligning ud fra Newtons 2. lov, så man kan beskrive samtlige sammensatte masser der har forskellige fjederkræfter der påvirker dem.
$$
m \overline{a} = \overline{f}_{net}
$$
### Impuls
Den mekaniske energi er bevaret.
Impuls er en vektor, fordi vi har en hastighedsvektor. Impuls er et stød.
![[Pasted image 20250916121943.png]]
Den samlede impuls $P$ er givet ved summen af impulserne for alle partiklerne.
### Isoleret partikelsystem, impulsbevarelsessætningen og inertialsystem
![[Pasted image 20250916122200.png]]
Et isoleret partikelsystem er et system der ikke er påvirket af nogle ydre kræfter.
$$
\frac{dP}{dt} = \frac{d (m \overline{v})}{dt} = m \cdot \frac{d \overline{v}}{dt}
$$
Hvor $\frac{d \overline{v}}{dt}$ er accelerationen.

Et inertialsystem er et system der *ikke* er accelererende. Dvs. Impulsbevarelsessætningen *ikke* gælder for systemer der *ikke* er inertialsystemer.

### Newtons 1. lov
![[Pasted image 20250916123041.png]]
Det er vigtigt at påpege at Newtons love kun gælder i et inertialsystem.

### Newtons 2. lov
![[Pasted image 20250916123146.png]]
Den siger lidt mere end impulsbevarelsessætningen, fordi i impulsbevarelsessætningen er $F=0$.
#### Eksempel
![[Pasted image 20250916123354.png]]
For hastigheden ville det være en linære streg.
$$
\dot{x}(t) = \int_{0}^{t} \ddot{x} \, d \tau
$$
$$
= a \int_{0}^{t} \underbrace{d \tau}_{v_{0}=0} = a t
$$
$$
x(t) = \int_{0}^{t} a \tau \, d \tau = a \frac{t^{2}}{2}
$$
### Superpositionsprincippet
![[Pasted image 20250916123802.png]]
### Partikelsystemer
![[Pasted image 20250916123921.png]]
Man bruger bare Newtons 2. lov på massemidtpunktet. Massemidtpunktet af givet af stedvektoren ganget med massen for alle masserne og deres stedvektorer.
### Hastigheden af massemidtpunktet
Den tidsafledte af stedvektoren er hastighedsvektoren.
![[Pasted image 20250916124138.png]]
### Massemidtpunktssætningen
![[Pasted image 20250916124430.png]]

### Newtons 3. lov
![[Pasted image 20250916124644.png]]
#### Eksempel
![[Pasted image 20250916124854.png]]
### Kraftens impuls
![[Pasted image 20250916124908.png]]
### Gængse kræfter: Tyngdekræften 
![[Pasted image 20250916125123.png]]
### Fjederkræft, Hooke's lov
![[Pasted image 20250916130737.png]]
![[Pasted image 20250916130945.png]]
![[Pasted image 20250916130953.png]]
![[Pasted image 20250916130959.png]]
![[Pasted image 20250916131004.png]]
$$
\begin{align*}
m \cdot \ddot{x} &=  f_{net}\\
f_{net} &= - kx\\
m \ddot{x} &= -k x(t)\\
\ddot{x} &= - \frac{k}{m} x(t)
\end{align*}
$$
#### Eksempel
![[Pasted image 20250916131209.png]]
### Dæmpningskraft
![[Pasted image 20250916131327.png]]
![[Pasted image 20250916131411.png]]
![[Pasted image 20250916131417.png]]
![[Pasted image 20250916131700.png]]
Kræften for en fjeder og dæmper:
$$
\begin{align*}
m \ddot{x} &=  f_{net}\\
f_{net} &= \underbrace{-kx}_{\text{fjeder}} \, \underbrace{- b \dot{x}}_{\text{dæmper}}\\
m \ddot{x} &= - kx - b \dot{x}
\end{align*}
$$
#### Eksempel
![[Pasted image 20250916131712.png]]
### Friktion
![[Pasted image 20250916131754.png]]
![[Pasted image 20250916131802.png]]
Man kan se på graferne at man kan øge kraften mere og mere indtil man overvinder normalkræften uden objektet flytter sig, men når først objektet kommer i bevægelse så falder friktionen. 
![[Pasted image 20250916131812.png]]
Det kaldes for statisk og dynamisk friktion.
### Vindmodstand
![[Pasted image 20250916132744.png]]
Ved små hastigheder betyder vindmodstanden (den polynomielle friktion) ikke så meget ift. viskos friktionen (lineære friktion), men ved større hastighed så kommer vindmodstanden til at dominere.
![[Pasted image 20250916133106.png]]
### Fritlegemediagram pt. 2
![[Pasted image 20250916133130.png]]
#### Eksempel
![[Pasted image 20250916133232.png]]
Dette er givet ved 2 2. ordens differentialligninger, fordi man skal bruge Newtons 2. lov to gange, en gang på hvert objekt.
$$
\begin{align*}
m_{1} \ddot{x}_{1} &=  f_{net,1}\\
f_{net,1} &= -k(x_{1}-x_{2}) - b(\dot{x}_{1} - \dot{x}_{2})\\
m_{1}\ddot{x_{1}} &= - k (x_{1}-x_{2}) - b(\dot{x}_{1} - \dot{x}_{2})
\end{align*}
$$
F påvirker kun legeme 2.
$$
\begin{align*}
m_{2}\ddot{x}_{2} &= f_{\text{net},2}\\
f_{\text{net}, 2} &= F - k(x_{2} - x_{1}) - b(\dot{x}_{2} - \dot{x}_{1})\\
m_{2} \ddot{x}_{2} &= F - k(x_{2} - x_{1}) - b (\dot{x}_{2} - \dot{x}_{1})
\end{align*}
$$
### 2. ordens systemer
![[Pasted image 20250916134604.png]]
$$
\begin{align*}
m \ddot{x} &=  f_{net}\\
f_{net} &= -kx \, - b \dot{x}\\
m \ddot{x} &= - kx - b \dot{x}\\
\text{Laplace transformeret:}\\
m s^{2} X(s) &= - k x(s) - b s x(s) + F(s)\\
X(s) (m s^{2} + bs + k) &= F(s)\\
\frac{X(s)}{F(s)} &= \frac{1}{m s^{2} + bs + k}\\
&= \frac{1/m}{s^{2} + \frac{b}{m} s + \frac{k}{m}}
\end{align*}
$$
Hvor $\frac{b}{m} = 2 \zeta \omega_{n}$ 
$\zeta$ kaldes for zeta
#### Poler, dæmpningsfaktoren og den udæmpede naturlige frekvens
![[Pasted image 20250916134623.png]]
Her er der enhedsforstærkning fordi der står $\omega_{n}^{2}$ i tælleren i stedet for f.eks. $\alpha \cdot \omega_{n}^{2}$ 
![[Pasted image 20250916135757.png]]
$\sigma$ er den reele del og $\omega_{d}$ er den imaginære del. O er nulpunkter og X er poler.
### Underdæmpet 2. ordens system
![[Pasted image 20250916140013.png]]