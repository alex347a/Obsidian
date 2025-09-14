### Overblink over objektorienteret analyse og design
![[Overblink over objektorienteret analyse og design.png]]
Et sekvensdiagram viser en enkelt use case, hvor den viser sekvensen af beskeder mellem actors og objekter i systemet ift. tid.
### Sekvensdiagram notation
![[Sekvensdiagram notation.png]]
### Hvordan kan vi bruge det?
![[Hvordan kan vi bruge det.png]]
### Hvordan laver man et sequence diagram?
![[Hvordan laver man et sequence diagram.png]]
### Eksempel
![[Eksempel.png]]
#### Eksempel domænemodel
![[Eksempel domænemodel.png]]
#### Eksempel sekvensdiagram
![[Eksempel sekvensdiagram.png]]

![[Opgave Lav et sekvensdiagram der viser reservation af en billet.png]]
![[Opgaveløsning.png]]
### Association
![[Association.png]]
### Multiplicity
![[Noter/Pasted Images/Gennemførte fag/2. Semester/Softwareudvikling/07/Multiplicity.png]]
### Directed association
![[Directed association.png]]
### Aggregation
![[Aggregation.png]]
### Composition
![[Composition.png]]
### Inheritance
![[Inheritance.png]]
### Fra analyse til design
![[Fra analyse til design.png]]
![[Larmans udlægning.png]]
### GRASP
![[GRASP.png]]
![[GRASP 2.png]]
### Creator
![[Creator.png]]
### Low coupling
![[Low coupling.png]]
### High cohesion
![[High cohesion.png]]
### Controller
![[Controller.png]]
![[Controller implementeret.png]]
### Polymorfisme
![[Polymorfisme.png]]
![[Indirection.png]]
### Protected variations (beskyttede variationer)
![[Protected variations (beskyttede variationer).png]]
Man sørger for at der er et mellemled så det kun er noget specifikt der kan blive lavet om på, og ikke direkte noget i logikken.

Protected Variations er et designprincip inden for objektorienteret design og softwarearkitektur, der handler om at beskytte et system mod ændringer ved at indføre stabile grænseflader eller abstrahere de dele, der kan ændre sig.

Eksempel:
Forestil dig et billetsystem, hvor betaling kan ske med **kreditkort, MobilePay eller PayPal**. Hvis vi direkte kobler systemet til en specifik betalingsudbyder, bliver det svært at skifte til en ny udbyder senere.

**Løsning med Protected Variations:**

1. Definér et **interface** `PaymentProcessor` med en metode `processPayment(amount)`.
    
2. Opret specifikke klasser **CreditCardPayment, MobilePayPayment** osv., der implementerer interfacet.
    
3. Systemet behandler betalinger ved kun at interagere med `PaymentProcessor`, så vi nemt kan udskifte eller tilføje nye betalingsmuligheder uden at ændre koden andre steder.

### Opskrift på DKD (Data-Knowledge-Domain)
![[Opskrift på DKD.png]]
#### Alternativ opskrift på DKD (Data-Knowledge-Domain)
![[Alternativ opskrift på DKD.png]]

### Eksempel på opskrift på DKD
![[Eksempel på opskrift på DKD.png]]
![[Eksempel på opskrift på DKD 2.png]]
![[Eksempel på opskrift på DKD 3.png]]
![[Eksempel på opskrift på DKD 4.png]]
![[Eksempel på opskrift på DKD 5.png]]
![[Eksempel på opskrift på DKD 6.png]]
![[Eksempel på opskrift på DKD 7.png]]
![[Eksempel på opskrift på DKD 8.png]]
![[Eksempel på opskrift på DKD 9.png]]
![[Eksempel på opskrift på DKD 10.png]]
### Notation DKD detaljer
![[Notation DKD detaljer.png]]
### POS
![[POS.png]]