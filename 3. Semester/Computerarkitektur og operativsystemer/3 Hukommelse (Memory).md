### Volatil/ikke-volatil
RAM (Random Access Memory) er volatil idet det bliver mistet når der slukkes for strømmen
ROM (Read-Only Memory) er ikke volatil, så det bliver gemt uanset om strømmes slukkes.

### SR latch
Hvis man vil gemme en bit så bruger man en SR latch
![[Pasted image 20250919082136.png]]
Der er to stabile tilstande: $Q=1, \overline{Q} = 0$ og $Q=0, \overline{Q} = 1$
Værdien af en latch er ikke bestemt af de nuværende input.
S: set
R: Reset
Må ikke tændes samtidigt, fordi så bliver den ustabil.

### D latch
![[Pasted image 20250919082508.png]]
D latch er mest interessant når der er en clock i. En D latch er åben idet klokken er høj

### D Flip-Flop
Hver gang clock går høj så er flip floppen høj (så den gemmer på dataet) indtil clock'en bliver høj igen.

Otte D flip-flop kan arrangeres for at lave et 8-bit register.

### Hukommelsesinterface
Memory space har alle adresser man kan adressere. I/O kan man bruge til skærme osv.

For en 8-bit hukommelsesinterface
Hvis de øverste fire adresser alle er nand sammen så befinder vi os i RAM:
$$
\overline{CS} = \overline{A_{12} \cdot A_{13} \cdot A_{14} \cdot A_{15}}
$$
RAM er altså i toppen af hukommelsen mens ROM er i bunden af hukommelsen.

ROM er kun aktiv ved lav vha. OR-gate:
$$
\overline{CS} = \overline{A_{8} + A_{9} + A_{10} + A_{11} + A_{12} + A_{13} + A_{14} + A_{15}}
$$
$\overline{WR}$ og $\overline{RD}$ bestemmer om der skal læses eller skrives fra, og de er inverted, så de er høje når signalet er 0. ROM kan ikke skrives til (sjovt nok), men det kan RAM.

Hvis man vil lave en 16-bit hukommelse så kan man bare duplikere ens 8-bit.
Ved en 16 bit har man en $\overline{BE0}$ og en $\overline{BE1}$ fordi så kan man vælge om man skriver det nederste byte eller det øverste byte.

I en 16-bit så er det sidste bit der bestemmer hvilken bank der skrives til, om det er RAM fra bank 0 eller bank 1. Her bruges der kun de tre øverste bit til at vælge RAM i stedet for de 4 der blev brugt i en 8-bit.

### Wait state
Nogle chipsets har brug for ekstra tid til at finde dataen og derfor kan der være brug for at vente. Derfor laver man et wait-state generator-kredsløb. Man bruger et shift register til at bestemme hvor mange ekstra clock-cykluser man bruger på at finde dataet.

### Adresse-demultiplexer
Bruger de tre øverste bit til at vælge mellem 8 forskellige hukommelses-chipsets når de bruges til samme adresse-blok.

### PLA Programmable Logic Array (programmerbar array-logik)
Det er en chip hvor man kan lave logik meget simpelt, fordi man kan programmere hvordan logikken skal være i stedet for at skulle lave sit eget logik kredsløb med AND og OR gates.

### Sektor split
Man kan splitte sin hukommelse op i f.eks. hurtig og langsom hukommelse, så man f.eks. kan lave wait state til kun den langsomme del af hukommelsen, eller f.eks forskellige wait states for de forskellige sektorer. SRWn1 betyder at man venter 2 clock cycles, mens SRWn0 kun venter 1 wait state, man kan aktivere begge for at vente 2 clock cycles ved læse og skrive og derefter vente en clock cycle til at outputte.
