## Software Development Life Cycle (SDLC)
Softwareudviklingselementer foregår oftest i en bestemt rækkefølge
Stadier:
1. Planlægning og kravsanalyse 
2. Kravsspecifikation
	Funktionelle krav og tekniske krav
	Identificere hvilke krav der er og evaluer og prioriter dem.
	Testability, actionability, measurability, traceability, sufficiently detailed
3. Arkitektur design
	Højniveau design:
	- System arkitektur
	- Moduler og komponenter
	- [[Data flow diagrammer (DFD)]]
	- Technology stack (styresystem, programmeringssprog, teamets ekspertise, front-end, back-end, tidsramme, ydeevne, budget (omkostninger), fremtidssikring)
	Lavniveau design:
	- Objektorienteret principper
	- Analyse- og designproces
	- Designmønstre
	- [[UML-diagrammer]]
4. Udvikling af produktet
	kodestandard -- skalerbar kode -- versionskontrol -- kode review
5. Produkttest og integration
	System test -- manuel test -- automatiseret test
6. Udrulning (deployment) og vedligeholdelse (maintenance)

## Vandfaldsmodellen
Hver fase skal være afsluttet før man bevæger sig videre, og skal udføres i rækkefølge:
1. Kravindsamling
2. Systemdesign
3. Implementering
4. Integration og test
5. Udrulning
6. Vedligeholdelse

Modellen er god hvis ændringer er meget dyre. Den er god hvis det færdige produkt allerede er bestemt før udviklingen begynder.
![[Vandfaldsmodellen.png]]