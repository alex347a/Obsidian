- Når man koder skal man have gode variablenavne (korte og forklarende) og man skal være konsistent. F.eks. med hvilken case man bruger. 
- Undgå at bruge den samme kode flere gange, måske der skal laves en funktion. 
- Man kan lave kommentarer som TODO: kritisk, FIXME: nice to have. Der skal ikke være for mange kommentarer. Funktionerne skal give sig selv. Kommentarer er gode til at forklare det der er udenfor koden, f.eks. formler. 
- Undgå magic numbers.
- Undgå at genbruge variable til nye formål, i stedet for skal man give dem nye variablenavne, som er mere meningsfulde.
### Case
![[Case.png]]
### Magic numbers
![[Magic numbers.png]]
### Low coupling - High cohesion
![[Low coupling - High cohesion.png]]

### Designmønstre
![[Designmønstre.png]]
### Facade pattern
![[Facade pattern.png]]
![[Facade use cases.png]]
![[Facade pros and cons.png]]
### Strategy design pattern
![[Strategy design pattern.png]]
![[Strategy design pattern eksempel.png]]![[Strategy design pattern pros and cons.png]]
### Factory design pattern
Et factory design pattern bruges til at skabe objekter. F.eks. med helt og monstre, hvis man så vil skabe monstre der afhænger af heroens stats og/eller environment, så kan man lave et factory der producere monstre og tager hero og/eller environment som input. Dette gør at monsteret ikke skal have en advanceret constructor der skal til at indeholde alle mulige andre klasser, man har bare en factory der kan producere forskellige monstre.
![[Factory design pattern.png]]
![[Factory design pattern 2.png]]
### Memento
Det er en behavioral design pattern, som kan gemme et objekts "state" og genskabe det på et senere tidspunkt.
![[Memento.png]]![[Memento 2.png]]
![[Memento pros and cons.png]]