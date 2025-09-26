Mikroarkitekturen implementerer ISA der ligger ovenover og designet bliver valgt ud fra hvor hurtig chippen skal være, og hvor dyr. Man bruger fetch-decode-execute cyklus af ISA-instrukser.
Den er generelt opbygget ved at du:
1. inkrememterer det trin du er nået til
2. laver noget opkode, 
3. finder noget data (medmindre man ikke skal det)
4. fetcher data 
5. eksekverer instruktionen.

IJVM består af en ALU, regnemaskine, shifter og 10 registre:
![[4.1.png]]
Da vi kiggede på ALU i 1. lektion så var ENA og ENB altid 1 INVA og INC altid 0, så hvis man også tager dem med kan man gøre mange forskellige operationer.
![[4.2.png]]
$2^{6}$ kombinationer, så der er mange operationer der gør det samme / er ubrugelige.

Data-pathen er den del af CPUen der indeholder ALUen, dens inputs og outputs

De fire øverste står for memory
MAR og MDR er par som C går ind i, hvor adressen bliver lagt i MAR og kan fetch data og skrive det i MDR, der kan tilgås på B.
P