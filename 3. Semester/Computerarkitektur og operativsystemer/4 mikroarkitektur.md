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
PC og MBR fungere på samme måde, PC ligger data i MBR, programmet ligger i ROM derfor er der kun 1 pil, man læser kun, man skriver ikke til den
SP pointer til toppen af stacken
LV pointer til en lokal variabel i hukommelsen
CPP pointer til konstanter i hukommelsen
TOS er toppen af stakken har har samme indhold som SP
OPC kan bruges som midlertidig data-lokation
H er hold som holder på en værdi til at blive brugt i næste operation.

Kun H og MAR kan ikke skrive på B bussen.

Man må kun ligge et tal på B bussen af gangen.
Eksempel på at ligge to tal sammen:
load et tal fra ?? sæt den på hold og så load sit næste tal og læg dem sammen.

En shifter fungerer ved at der går et clock signal ind, og så har shifteren et input, hvor man kan læse alle værdierne af alle felterne, hvis 1 ligger helt til venstre så hver gang clock cyklus ændrer sig så rykker 1-tallet en plads til højre.

![[4.3.png]]Man laver et clock signal om til et puls signal ved at 