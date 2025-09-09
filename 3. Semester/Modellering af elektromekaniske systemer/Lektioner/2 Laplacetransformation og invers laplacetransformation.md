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
