## Chessboard og movevalidation
### Chessboard
En vektor af vektorer, som er en 8x8 matrice af karakterer hvor store bogstaver er sorte brikker og små bogstaver er hvide brikker. Boarded opdateres ved at ændre i karakterne. Chessboard holder også styr på regler der sikrer om der er remis eller skakmat.

#### Remis
1. Hvis der ikke er nok materiale til at kunne lave et skakmat (kun to konger tilbage, konge mod konge og løber, eller konge mod konge og hest.
   
2. Hvis kongen ikke er i skak men han kan ikke flyttes og der er heller ingen andre brikker af samme farve der kan rykkes.
   
3. Hvis der har været 50 moves uden en bonde er blevet flyttet eller en brik er blevet taget. 
   
4. Hvis boarded har set identisk ud 3 gange, dvs. brikkerne står præcist samme sted, så der er ikke flyttet nogle bonder eller taget nogle brikker, og brikker som kan bevæge sig frit såsom hest, konge, dronning, løber og tårn har bevæget sig frem og tilbage på samme måde.
   
#### Skak
Der tjekkes for om der er skak ved at en funktion løber igennem hele boarded og ser om der er nogle valide træk for hver eneste brik der kan løbe hen til det felt hvor den modsatte konge står. 
#### Skakmat
Hvis kongen er i skak, der er intet der kan tage brikken der har ham i skak, der er intet der kan blokere brikken ved at flytte ind foran og kongen kan ikke bevæge sig ud af skak (enten fordi der er brikker eller fordi kongen ville ende i skak ved det nye fe)
## Stockfish
## Vision

## ROS

## Gripper

### H-Bro
### DC-motor
![[DC Motor]]