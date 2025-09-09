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
Når $t = \tau$ så bliver delta nul og dermed får man funktionen $u(t)$ ud.