Laplacetransformation virker på cos, sin og eksponentialfunktioner i modsætning til fouriertransformation der kun virkede på aperiodiske funktioner, hvor man så lavede perioden uendelig. 

### Linære tidsinvariante systemer (systemer der ikke afhænger af tidspunktet det foretaget)
For eksempel hvis man taber en blyant tager det samme tid at ramme jorden om det er om mandagen eller fredagen.

### Impulsrespons og frekvensrespons
![[Impulsrespons og frekvensrespons.png]]

Overførselsfunktioner er laplacetransformationen af en impuls, som er det der giver impulsresponet.

I linære systemer så ændrer frekvensen sig *ikke* når man kigger på indgangssignalet og udgangssignalet, men det kan amplituden og fasedrejet.

![[Pasted image 20250909122518.png]]
$$
\begin{align*}
f(x+y) &=  f(x) + f(y)\\
f(\alpha x) &=  \alpha f(x)
\end{align*}
$$
Homogenitet er f.eks. hvis indgangssignalet f.eks. bliver fordoblet så bliver udgangssignalet også fordoblet.
Superposition er at de to indgangssignaler hvert for sig behandlet er det samme som at summere dem og derefter behandlet den summerede funktion.
![[Pasted image 20250909122851.png]]

### Superpositionsprincippet
![[Pasted image 20250909123009.png]]
Det er en lineær andenordens differentialligning. Den udledes ud fra Newtons 2. lov.
![[Pasted image 20250909123550.png]]
Løsningen af begge summeret er også en løsningen.

![[Pasted image 20250909123637.png]]
Ud fra en impuls kan man bestemme udgangssignallet af alle indgangssignaler.
![[Pasted image 20250909123753.png]]
Når $t = \tau$ så bliver delta nul og dermed får man funktionen $u(\tau)$ ud.
### Impulsresponset er defineret ved $h(t,\tau)$
![[Pasted image 20250909124010.png]]
### Superpositionsintegralet og foldningsintegralet
![[Pasted image 20250909124136.png]]

#### Eksempel
![[Pasted image 20250909124247.png]]
Den homogene løsning vil være 0, men vi er selvfølgelig interesseret i den partikulære løsning. Da y lige før 0 er 0 så må y lige efter 0 være 1.
![[Pasted image 20250909124536.png]]
![[Pasted image 20250909124618.png]]
Siden vi ved at startbetingelsen er 1, så er $A=1$ og dermed må $s=-k$
![[Pasted image 20250909124725.png]]
### Enheds step funktion
![[Pasted image 20250909124824.png]]
Enheds step funktionen er altså $1(t)$, som gør at $e^{-kt}$ gælder for alle tider og ikke bare for $t>0$
![[Pasted image 20250909125031.png]]
Hvis man har en kompleks eksponentiel funktion så kan man også løse for sinus og cosinus funktioner.
Hvis s kun var et kompleks tal (altså $j \omega$) så svarer det til en Fouriertransformation, men nu afhænger s af både $\sigma$ og $j \omega$, så både reelle tal og imaginære tal, og det er forskellen.
Laplacetransformationen kan bruge til at finde oscilleringsfrekvensen (egenfrekvensen) altså der hvor . 

### Laplacetransformation
![[Pasted image 20250909131622.png]]
### Overføringsfunktion
![[Pasted image 20250909131644.png]]
Overføringsfunktionen er i frekvensdomænet som er givet ved forholden af udgangssignalet divideret med indgangssignalet når de begge er laplacetransformeret.

#### Eksempel
![[Pasted image 20250909131811.png]]
Nu hvor komplekse tal er medinkluderet så svarer antallet af rødder til polynomiets grad, så et 37. grads polynomie vil have 37 rødder og der vil være 37 udtryk nede under brøkstregen.

![[Pasted image 20250909132430.png]]
### Frekvensrespons
![[Pasted image 20250909132543.png]]
![[Pasted image 20250909132754.png]]
Det er meningen j skal ganges på begge dele af den eksponentielle funktion, så:
$$
y(t) = \frac{A}{2} M (\omega) (e^{j ( \omega t + \phi(\omega))} + e^{-j (\omega t + \phi(\omega))})
$$
![[Pasted image 20250909133156.png]]
$H(s)$ har her 1 pol, fordi $s=-k$ og det har 0 nulpunkter, fordi der står 1 i tælleren, og er et 0. grads polynomie.

### Bode plot
![[Pasted image 20250909134315.png]]

### Laplacetransformation egenskaber
![[Pasted image 20250909135009.png]]
Man antager ofte at begyndelsesbetingelserne er 0, for at slippe for ekstra led.

$$
\begin{align*}
s^{2} P (s) = - \frac{k}{m} P (s) - \frac{b}{m} s P(s) + \frac{1}{m} F(s)\\
output: P(s)\\
H(s) &= \frac{P(s)}{F(s)}\\
\left(s^{2} + \frac{b}{m} s + \frac{k}{m}\right) p(s) &= \frac{1}{m} F(s)\\
H(s) = \frac{P(s)}{F(s)} &= \frac{\frac{1}{m}}{s^{2} + \frac{b}{m} s + \frac{k}{m}}\\
F(t) &= 1\\
P(t) &= ????
\end{align*}
$$
$$
F(t) = 1 = A \cos(\omega t)
$$
Derfor er $A = 1$ og $\omega = 0$
Derfor får vi at:
$$
M(\omega) = |H(s)| = |H(j \omega)|_{\omega = 0} = H(0) = \frac{\frac{1}{m}}{0 +0 + \frac{k}{m}} = \frac{1}{k}
$$
$P(t) = \frac{1}{k}$
Hvor $H(0)$ kaldes for DC gain.

![[Pasted image 20250909140411.png]]

### Relation mellem impulsrespons og polplacering
![[Pasted image 20250909140424.png]]
Man vil gerne have at ens system er i venstre halvplan, fordi man vil ikke have at det går imod uendelig. Så ud fra polerne kan man se om den er stabil/ustabil og om der er svingninger eller om det direkte konvertere mod 0.

### Invers laplacetransformation
![[Pasted image 20250909140558.png]]
![[Pasted image 20250909140607.png]]

### Partialbrøksopspaltning/partialbrøksopløsning
![[Pasted image 20250909140715.png]]

#### Eksempel
![[Pasted image 20250909141050.png]]
![[Pasted image 20250909141125.png]]
I bode plottet ser man ikke det første led i y(t), fordi man sætter det til 1, men sinusdelen vil man se i bode plottet.