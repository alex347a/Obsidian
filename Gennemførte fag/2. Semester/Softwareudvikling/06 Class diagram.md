### Forhold UML pile (relationships)
![[Relationships UML pile.png]]
### Arv (inheritance)
![[Arv (inheritance).png]]
### Multiplicity
![[Pasted Images/2. Semester/Softwareudvikling/06/Multiplicity.png]]
VIGTIG: Stjerne betyder fra 0 til uendelig^^

inheritance er defineret med de hvide pile

### Domænemodellen
![[Domænemodellen.png]]
![[Domænemodellen 2.png]]
### Domænemodellen vs. klasse diagram
![[Domænemodellen vs. klasse diagram.png]]
#### UML notation - terminologi
![[UML notation - terminologi.png]]
#### Domænemodel og resulterende softwarekomponenter
![[Domænemodel og resulterende softwarekomponenter.png]]
#### Hvordan ser en klasse ud?
![[Hvordan ser en klasse ud.png]]
![[klasse eksempel.png]]
### Domænemodellen konceptuelle klasser
![[Domænemodellen konceptuelle klasser.png]]
![[Concept.png]]
![[Domænemodellen 3.png]]
#### Et par retningslinjer
![[Et par retningslinjer.png]]
#### Strategier til identifikation af konceptuelle klasser
![[Strategier til identifikation af konceptuelle klasser.png]]
#### Kandidater til konceptuelle klasser i salgsdomænet
![[Kandidater til konceptuelle klasser i salgsdomænet.png]]
![[Kandidater til konceptuelle klasser i salgsdomænet 2.png]]
#### Retningslinjer for modellering
![[Retningslinjer for modellering.png]]
#### Domænemodellen 'vejviseren'
![[Domænemodellen 'vejviseren'.png]]
#### Ofte forekommende fejl
![[Ofte forekommende fejl.png]]
#### Specification of conceptual classes
![[Specification of conceptual classes.png]]
![[Specification of conceptual classes 2.png]]
#### Point-of-sale domænemodel
![[Point-of-sale domænemodel.png]]
### Domænemodellen - tilføj associationer
![[Domænemodellen - tilføj associationer.png]]
![[Introduktion.png]]
![[Associationer.png]]
![[Associationer 2.png]]![[Associationer eksemepel.png]]
![[Nyttige associationer.png]]
#### Associationer med høj prioritet
![[Associationer med høj prioritet.png]]
#### Retningslinjer for associationer
![[Retningslinjer for associationer.png]]
#### Roller
![[Roller.png]]
#### Kardinalitet/multiplicity
![[Kardinalitet (multiplicity).png]]
![[Multiplicity billede.png]]
![[Multiplicity billede 2.png]]
#### Navngivning af associationer
![[Navngivning af associationer.png]]
![[Navngivning af associationer billede.png]]
![[Flere associationer imellem sig.png]]
#### Implementering i domænemodellen
![[Implementering i domænemodellen.png]]
#### Udrensning af associationer
![[Udrensning af associationer.png]]
![[Udrensning af associationer 1.png]]
![[Udrensning af associationer 2.png]]
#### Konklusion
![[Konklusion.png]]

Domænemodellen kan bruges til at efterfølgende at lave et klassediagram. Domænemodellen bruges til at modellere virkeligheden og hvordan den hænger sammen, hvorefter man så kan lave klassediagrammet der beskriver hvordan softwaren skal efterligne virkeligheden.

Lektien er at lave en domænemodel over:
Billet
Kunde
Forestilling
Salg
Film
Biograf+sal
Række
Sæde
Ansat
Popcorn
Biografejer
Reservation

En _Billet_ er knyttet til én _Forestilling_ og et _Sæde_.
En _Kunde_ kan lave flere _Reservationer_.
En _Forestilling_ er forbundet med en _Film_ og en _Biograf+sal_.
En _Biograf_ har flere _Sæder_, organiseret i _Rækker_ og _Sale_.
Et _Sæde_ tilhører en _Række_ i en _Sal_ i en _Biograf_.
En _Ansat_ arbejder i en _Biograf_, og _Biografejer_ ejer _Biografen_.
_Popcorn_ kan købes af en _Kunde_, og et _Salg_ kan involvere flere _Billetter_.
En _Reservation_ kan være knyttet til flere _Billetter_.

![[Domænemodel over biograf.png]]