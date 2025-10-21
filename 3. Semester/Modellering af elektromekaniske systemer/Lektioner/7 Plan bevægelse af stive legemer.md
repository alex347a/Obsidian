### Opsummering
![[Pasted image 20251021121822.png]]
![[Pasted image 20251021121836.png]]
![[Pasted image 20251021121847.png]]
![[Pasted image 20251021121856.png]]
Lovene kommer af
Newtons 2. lov:
$$
m \overline{a} = \overline{f}_{net}
$$
og Eulers ligning / impulsmomentsætning:
$$
I \dot{\omega} = \tau_{net}
$$
### Massemidtpunktsætningen
![[Pasted image 20251021122307.png]]
### Impulsmomentsætningen
![[Pasted image 20251021122506.png]]
### Beskrivelse af plan bevægelse
![[Pasted image 20251021122532.png]]
![[Pasted image 20251021122615.png]]
Husk at krydset betyder at der peges ind i papiret, og så kan man bruge højrehåndsreglen til at finde hvilken retningen legemet roterer. Jo længere væk man er fra centrum jo højere hastighed har man, fordi hastigheden er givet ved radius gange vinkelhastighed: $v_{p} = R \omega$
![[Pasted image 20251021122802.png]]
Man adderer de to hastighedsvektorer. $v_{C}$ er hastigheden for massemidtpunktet, mens hastigheden for et punkt på skiven er givet ved vinkelhastigheden krydset med radius, idet vi kun skal bruge hastigheden der er orthogonal med radius: $\overline{\omega} \times \overline{r}$
![[Pasted image 20251021123223.png]]
Den tidsafledte af s (strækningen) er hastigheden af massemidtpunktet, mens den tidsafledte af hastigheden giver accelerationen af massemidtpunktet.
### Bevægelse af stive legemer
![[Pasted image 20251021123421.png]]Den første roterer, mens den anden ikke roterer, fordi krydsproduktet af F og R er 0, idet de to kræfter er parallelle og det er kun komposanten der er orthogonal med radius der bidrager til hastigheden. Den første bevæger sig dog ikke translatorisk, idet det er en glat overflade og det er friktionen der er skyld i at et roterende legeme bevæger sig translatorisk.
![[Pasted image 20251021124310.png]]
Det er bare ligesom robotkinematik. Man kan kun integrere vinkler ved euler vinkler og quaterioner, ellers må man IKKE.
![[Pasted image 20251021124544.png]]
![[Pasted image 20251021124605.png]]
Husk at impulsmomentet er givet ved masse gange hastighed, hvor hastigheden her er givet ved: $\overline{\omega} \times \overline{r}_{i}$ hvor vi så her kan gange massen udenfor, fordi det blot er en størrelse. Sinus fordi det er den modstående katete over hypotenusen. Husk at det kun er for z-retningen. Husk at alle partikler har samme vinkelhastighed, fordi ellers ville objektet deformere.
![[Pasted image 20251021125045.png]]
Inertimomentet er konstant, fordi massen ikke ændrer sig. Man kan regne inertimomentet ved at integrere radius ganget med massen, eller hvis man ikke har massen men i stedet har densiteten (massetætheden) og volumen, så kan dette også bruges.
![[Pasted image 20251021125302.png]]
![[Pasted image 20251021130812.png]]
![[Pasted image 20251021130831.png]]
Så længe vi bliver ved med at påtrykke en kraft så vil legemet accelerere idet der ingen friktioner er i dette eksempel, mens den i den virkelige verden med friktion vil være en tophastighed.
### Kinetisk energi og arbejde for stive legemer
![[Pasted image 20251021131229.png]]
Den øverste fordi inertimomentet afhænger af radius i anden, ligesom vi så i tidligere slide 16:
![[Pasted image 20251021125045.png]]
![[Pasted image 20251021131305.png]]
![[Pasted image 20251021131430.png]]
Vi har bare indsat i formlen for kinetisk energi:
$$
E_{kin} = \frac{1}{2} m v^{2}
$$
hvor hastigheden i anden er givet ved:
$$
v^{2}  = r^{2} \cdot \omega^{2}
$$
Dermed kan det forkortes til inertimomentet ganget med vinkelhastigheden i anden.
![[Pasted image 20251021131602.png]]
Hvis man har et legeme der både translaterer og roterer så kan man beregne det ved at addere den kinetiske energi for begge bevægelser.
### Steiners sætning / parallel access theorem
![[Pasted image 20251021131923.png]]
Vi kan sætte $\omega^{2}$ udenfor en parentes idet det indgår i begge led.
![[Pasted image 20251021132149.png]]
kaldes også for parallel-axis theorem.
![[Pasted image 20251021132427.png]]
Ligesom kraft gange arm/vej, så er det kraftmoment ganget med ændringen i vinkel.
$p = f \cdot v$
$p = \tau \cdot \omega$
![[Pasted image 20251021132612.png]]
$\theta_{i}$ står for initial og $\theta_{f}$ står for final.
