### Repetition
### Massemidtpunktssætningen
![[Pasted image 20251104122720.png]]
### Impulsmomentssætningen
![[Pasted image 20251104122730.png]]
Den største kraft er der hvor de to vektorer er orthogonale
### Kinetisk energi af stift legeme
![[Pasted image 20251104122829.png]]
### Udregning af impulsmomenter
![[Pasted image 20251104122946.png]]
Det er bare stedvektoren krydset med partiklernes impuls, hvor impulset er givet ved hastigheden ganget med massen, som ganges udenfor parentesen.
![[Pasted image 20251104123246.png]]
rød er 1, grøn er 2, blå er 3. Husk der skal være minus foran den anden determinant.
![[Pasted image 20251104123711.png]]
Det ligner fuldstændigt formlen for impulsmomentet i 2 dimensioner, udover nu er det en inertitensor og en vinkelfrekvensvektor, istedet for inertimomentet ganget med vinkelfrekvensen. Udfordringen kan være at både inertitensoren og impulsmomenter er tidsafhængige.
Det er en symmetrisk matrix.
![[Pasted image 20251104123729.png]]
### Perpendicular axis theorem
![[Pasted image 20251104124042.png]]
For et plan-objekt så er intertimomentet omkring z-aksen givet ved summen af intertimomentet omkring x-aksen og y-aksen summeret.
#### Eksempel inertitensor for cylinder
![[Pasted image 20251104124137.png]]
volumen af en cylinder er givet ved: $V = \pi \cdot r^{2} \cdot L$ så det er en fejl der står 2, men heldigvis går det ud med hinanden.
![[Pasted image 20251104124932.png]]
![[Pasted image 20251104125001.png]]
![[Pasted image 20251104125017.png]]
Steiners sætningen skal bruges, fordi det er ikke alle skriver der har massemidtpunkt det samme sted, så afstanden i anden skal også plusses på. Dernæst kan der integreres for at finde summen af alle cirkelskiverne.
#### Eksempel svinghjul
![[Pasted image 20251104125143.png]]
Dette kommer af det der var for to slides siden med at z-aksen er givet ved summen af de to andre akser, og dermed skal de være halvdelen af z hver, når de er ligmed hinanden.
![[Pasted image 20251104125404.png]]
vinkelfrekvensen afhænger af vinklen, fordi når disken roterer så ændrer retningen som x- og y-aksen peger i sig også.
![[Pasted image 20251104125414.png]]
Her er det $\frac{1}{2} \sin(\theta)$ fordi, $e_{2}$ aksen er $\frac{1}{4}$ mens $e_{1}$ var $\frac{1}{2}$ 
## Kinetisk energi for stive legemer
![[Pasted image 20251104130038.png]]
Husk at $E_{kin} = \frac{1}{2} \space m \space v^{2}$ og derfor står hastigheden der to gange, så deler vi hastigheden og så kan vinkelfrekvensen ganges ud foran summen. Da det resterende svarer til stedvektoren ganget med partiklernes impuls, så svarer det til impulmomentet.
![[Pasted image 20251104130325.png]]
### Almen bevægelse
![[Pasted image 20251104130350.png]]
#### Eksempel svinghjul
![[Pasted image 20251104130409.png]]
## Bevægelsesligning for stift legeme
![[Pasted image 20251104132126.png]]
#### Eksempel snurren
![[Pasted image 20251104132228.png]]
![[Pasted image 20251104132414.png]]
#### Eksempel snurre ophængt i en ende
![[Pasted image 20251104132619.png]]
![[Pasted image 20251104132639.png]]
![[Pasted image 20251104132650.png]]
![[Pasted image 20251104132701.png]]
Så hvis man påfører et kraftmoment i den modsatte retning bliver $\Omega$ med negativ fortegn og drejer den modsatte vej.
## Kinematik
![[Pasted image 20251104133403.png]]
### Rotationsmatrix
![[Pasted image 20251104133629.png]]
### Rotationsmatrix egenskaber
![[Pasted image 20251104133648.png]]
### Homogen transformation
![[Pasted image 20251104133754.png]]
![[Pasted image 20251104134005.png]]
Husk at punkterne skal homogeniseret for at passe med $4 \times 4$ transformationsmatricen, da punkterne er givet ved $3 \times 1$ matricer.
![[Pasted image 20251104134239.png]]
$J_{P}$ er den positionelle del $J_{O}$ er orienteringsdelen.
### Hastighed: tidsafledte af en rotationsmatrix
![[Pasted image 20251104134411.png]]
antisymmetrisk kaldes på engelsk for "skew-symmetric".
![[Pasted image 20251104134655.png]]
![[Pasted image 20251104134915.png]]
### Hastighed af punkt i en anden ramme
![[Pasted image 20251104135201.png]]
### Link hastighed
![[Pasted image 20251104135342.png]]
### Translatorisk link hastighed
![[Pasted image 20251104135401.png]]
### Vinkelhastighed af link
![[Pasted image 20251104135451.png]]
### Link hastighed (drejeled)
![[Pasted image 20251104135537.png]]
### Jakobiant for drejeled
![[Pasted image 20251104135659.png]]
![[Pasted image 20251104135944.png]]
![[Pasted image 20251104140017.png]]
I modificeret Craig ville der så stå $i$, men fordi det er Craig notation så står der $i-1$.
### Opsummering af Jakobiant
![[Pasted image 20251104140211.png]]For at få $z_{i-1}$ så kigger man på rotationsmatricen og tager den tredje søjle som er $z$