## Chessboard og movevalidation
### Chessboard
En vektor af vektorer, som er en 8x8 matrice af karakterer hvor store bogstaver er sorte brikker og små bogstaver er hvide brikker. Boarded opdateres ved at ændre i karakterne. Chessboard holder også styr på regler der sikrer om der er remis eller skakmat.

### Specielle moves:
#### Rokering (castling)
Hvis kongen ikke har flyttet sig eller været i skak, tårnet har heller ikke flyttet sig og der er ingen brikker imellem de to, og ingen af de felter imellem de to er under angreb, så kan der ske en rokering hvor kongen får lov til at flytte 2 felter i tårnets retning og tårnet flytter over på den anden side af kongens nye position.
#### En passant
Hvis en bonde lige har flyttet sig i sidste runde og en bonde flytter to felter fra startpositionen, hvilket resulterer i at den flytter forbi det felt hvor den kunne være taget af en fjendes bonde, så kan fjendens bonde alligevel bare tage den ved at flytte til hvor bonden ville have været hvis den kun var flyttet et felt (fjendens bonde flytter altså om bag ved bonden og det dør bonden af). Det gøres ved at tjekke historikken om der lige er blevet flyttet en bonde to moves inden det nuværende move og det forrige move var en bonde der flyttede sig 2 felter frem fra startpositionen.
#### Remis
1. Hvis der ikke er nok materiale til at kunne lave et skakmat (kun to konger tilbage, konge mod konge og løber, eller konge mod konge og hest.
   
2. Hvis kongen ikke er i skak men han kan ikke flyttes og der er heller ingen andre brikker af samme farve der kan rykkes.
   
3. Hvis der har været 50 moves uden en bonde er blevet flyttet eller en brik er blevet taget. 
   
4. Hvis boarded har set identisk ud 3 gange, dvs. brikkerne står præcist samme sted, så der er ikke flyttet nogle bonder eller taget nogle brikker, og brikker som kan bevæge sig frit såsom hest, konge, dronning, løber og tårn har bevæget sig frem og tilbage på samme måde.
   
#### Skak
Der tjekkes for om der er skak ved at en funktion løber igennem hele boarded og ser om der er nogle valide træk for hver eneste brik der kan løbe hen til det felt hvor den modsatte konge står. 
#### Skakmat
Hvis kongen er i skak, der er intet der kan tage brikken der har ham i skak, der er intet der kan blokere brikken ved at flytte ind foran og kongen kan ikke bevæge sig ud af skak (enten fordi der er brikker eller fordi kongen ville ende i skak ved det nye felt). Dette tjekkes ved at tjekke om kongens felt er i skak og om alle andre felter kongen kan flytte til er enten blokeret eller også i skak, og at det der sætter kongen i skak ikke kan blive taget eller blokeret.
## Stockfish
## Vision

## ROS

## Gripper

### H-Bro
### DC-motor
![[DC Motor]]