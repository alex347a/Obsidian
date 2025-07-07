## Chessboard og movevalidation
### Chessboard
Chessboard klassen står for at holde styr på boardets tilstand. Chessboard opretter en vektor af vektorer, som er en 8x8 matrice af karakterer hvor store bogstaver er sorte brikker og små bogstaver er hvide brikker. Boarded opdateres ved at ændre i karakterne. Chessboard holder også styr på regler der sikrer om der er remis eller skakmat.

#### Promotion
Alle bønder der har nået enderækken (række 1 for sorte bønder, række 8 for hvide bønder) bliver automatisk promoted til en dronning lige så snart trækket er blevet lavet. Grunden til det skal være en dronning og at man ikke får et valg ligesom i rigtig skak, er fordi kameraet ikke kan differentiere imellem typer af brikker, så vi antager altid at det er en dronning. Ellers skulle man til at intergere med computeren og fortælle den hvad man promotede til, hvilket vi helst vil undgå, især når det er sådan et edge case. Vi tvinger også stockfish til at promote til en dronning uanset hvad den selv synes er det bedste træk. Måden vi gør det i praksis er ved at når det igen er dens tur efter den promotede så sender vi den movehistory hvor vi siger den promotede til en dronning, og så spiller den med den viden.
#### Remis
1. Hvis der ikke er nok materiale til at kunne lave et skakmat (kun to konger tilbage, konge mod konge og løber, eller konge mod konge og hest.
   
2. Hvis kongen ikke er i skak men han kan ikke flyttes og der er heller ingen andre brikker af samme farve der kan rykkes.
   
3. Hvis der har været 50 moves uden en bonde er blevet flyttet eller en brik er blevet taget. 
   
4. Hvis boarded har set identisk ud 3 gange og det er den samme spillers tur, dvs. brikkerne står præcist samme sted, så der er ikke flyttet nogle bonder eller taget nogle brikker, og brikker som kan bevæge sig frit såsom hest, konge, dronning, løber og tårn har bevæget sig frem og tilbage på samme måde.
   
#### Skak
Der tjekkes for om der er skak ved at en funktion løber igennem hele boarded og ser om der er nogle valide træk for hver eneste af modstanderens brik der kan løbe hen til det felt hvor ens konge står. 
#### Skakmat
Hvis kongen er i skak, der er intet der kan tage brikken der har ham i skak, der er intet der kan blokere brikken ved at flytte ind foran og kongen kan ikke bevæge sig ud af skak (enten fordi der er brikker eller fordi kongen ville ende i skak ved det nye felt). Dette tjekkes ved at gennemløbe alle valide træk for alle brikker og observere om kongens felt er i skak og om alle andre felter kongen kan flytte til er enten blokeret eller også i skak, og at det der sætter kongen i skak ikke kan blive taget eller blokeret.

### movevalidation
MoveValidator-klassen har ansvaret for at validere alle skaktræk ud fra reglerne for de enkelte brikker samt specialregler som rokade og en passant. Klassen arbejder sammen med ChessBoard og bruger boardets nuværende tilstand samt trækhistorik til at afgøre, om et træk er lovligt.

- **Farvevalidering:**  
    Sikrer, at det kun er den aktive spillers brikker, der kan flyttes.
    
- **Trækvalidering:**  
    `isValidMove` tjekker, om et træk er lovligt for den valgte briktype (bonde, tårn, springer, løber, dronning, konge).  
    For hver briktype findes en separat valideringsfunktion, der tjekker brikkens bevægelsesmønster og om destinationen er lovlig.
    
- **Specialtræk:**
    - **Rokade:**  
        Tjekker om kongen og det relevante tårn ikke har flyttet sig, om der er fri bane, og om ingen af felterne kongen passerer er under angreb.
    - **En passant:**  
        Tjekker om modstanderens sidste træk var at flytte bonden to felter fra startpositionen, og om det aktuelle træk svarer til en korrekt en passant-situation.
        
- **Skak og skakmat:**  
    Efter et træk simuleres boardet, og det tjekkes, om kongen står i skak. Hvis et træk efterlader kongen i skak, er trækket ugyldigt. Hvis der er skakmat/remis slutter spillet.
    
- **Historik:**  
    Bruges til at afgøre, om kongen eller tårnet har flyttet sig (vigtigt for rokade) og til at validere en passant.
    
- **Hjælpefunktioner:**
    - Finder kongens position på brættet.
    - Tjekker om der er fri bane mellem felter (både ortogonalt og diagonalt).
    - Underattack tjekker om et felt er under angreb ved at gennemløbe alle modstanderens brikker og tjekker, om nogen kan angribe et givent felt.

### Eksempel på brug

Når en spiller forsøger at flytte en brik, kaldes `isValidMove`, som:
1. Tjekker om brikken tilhører den aktive spiller.
2. Validerer brikkens bevægelse.
3. Simulerer trækket og tjekker, om kongen står i skak bagefter.
4. Returnerer true hvis alt er lovligt, ellers false.

### Bemærkninger
- Klassen håndterer ikke selve opdateringen af boardet, men kun valideringen af træk.
- Specialregler som rokade og en passant kræver både boardets tilstand og trækhistorik.
- For at undgå uendelig rekursion bruges flag som `calledByUnderAttack` og `calledByKing` i relevante funktioner.
## Stockfish
### Hvordan stockfish bruges i praksis
Stockfish får givet en movehistory som er en string af moves som typisk er 4 karakterer, det er to koordinater såsom a2a4, hvor den selv ved ud fra den fulde historik hvilken brik det var der stod der. Hvis den promoter så skriver den f.eks. a7a8q, hvor q er at den promoter til en dronning, hvis den skriver noget andet end q så retter vi det til q fordi vi kun håndterer promotions til en dronning pga. kameraet ikke kan differentiere mellem brikker. Derfor næste gang stockfish får movehistory så har vi pillet ved hvad den sendte til os og så tror den selv at den tidligere promotede til dronning.
### Hvordan stockfish sættes op
### 1. **Initialisering:**  
Klassen starter Stockfish-processen og sætter UCI-protokollen op.
Først kommando er uci som siger den skal bruge Universal Chess Interface.
Når den er klar sender stockfish uciok, når det er sendt så tjekker man med isready hvor stockfish svarer readyok, og så kan man sende kommander såsom hvad depth skal være ved at skrive: 
```go depth 10```
Man kan også sende positionen som vi gør ved at skrive:
```position startpos moves e2e4``` 
og
```go```

2. **Opsætning af position:**  
    Når man vil have Stockfish til at analysere en stilling, sender man den aktuelle bræt-tilstand (som trækhistorik eller FEN, vi bruger trækhistorik) til Stockfish.
    
3. **Forespørgsel på træk:**  
    Man sender en `go`-kommando (evt. med tids- eller dybdebegrænsning) til Stockfish.
    
4. **Modtagelse af bedste træk:**  
    Klassen læser Stockfishs output, finder linjen med `bestmove`, og udtrækker trækket.
    
5. **Returnerer trækket:**  
    Det bedste træk returneres til programmet, som så kan udføre det og/eller vise det til brugeren.

## Vision
Vision-systemet bruges til at:
- Lokalisere og udtrække skakbrættet fra et kamerabillede
- Analysere billeder for at finde brikkernes placering
- Bestemme hvilke træk, der er foretaget på brættet
### Centrale klasser og deres roller

#### 1. **BoardCutter**
- Finder og udskærer selve skakbrættet fra et større billede. (hvis afstanden for både den grønne og røde cirkel er mindre end 10 pixels end det forrige så gør den det ikke igen)
- Bruger farvede markører (grøn og rød cirkel) til at identificere hjørnerne på brættet.
- Kan zoome og rotere billedet, så brættet bliver korrekt orienteret og skaleret.

#### 2. **ImageFinder**
- Indeholder statiske metoder til billedbehandling, fx at finde et billede i et andet, rotere punkter, lave heatmaps over farver, og vise forskelle i HSV-farvekanaler.
- Bruges til at analysere og sammenligne billeder for at finde brikker eller markører.
- Sætter også en weight på 2x for hue, sådan at hue spiller in større rolle i billedebehandlingen når der kigges efter moves.

#### 3. **ImageDrawer**
- Har en metode der tegner gridlines på skakbrættet.

#### 4. **MoveFinder**
- Indeholder logik til at finde hvilket træk, der er blevet lavet, ved at sammenligne to billeder af brættet (før og efter et træk).
- Efter den har fundet de to felter der er er i to forskellige gridlines så konverterer den det til strings sådan at movet bliver på formen "e2e4"

#### 5. **Utill**
- Hjælpeklasse med statiske metoder til at oversætte træk mellem forskellige formater. F.eks. når der laves castling skal stringen håndteres på en unik måde. Og så kan den også lave en vector af strings om til en string.

#### 6. **VisionInterface**
- **Hovedindgangen** til visionsystemet, den styrer det hele og binder det sammen med de andre klasser som hjælpeklasser.
- Styrer kameraet (VideoCapture), håndterer billedbehandling og bruger BoardCutter til at finde og udtrække brættet.
- Metoder som `getPieceMoved` og `getPieceMovedString` bruges til at finde det seneste træk ved at sammenligne billeder før og efter et træk.

### Typisk arbejdsgang

1. **Kameraet tager et billede** af brættet.
2. **BoardCutter** finder og udskærer selve brættet fra billedet, baseret på farvede markører.
3. **ImageDrawer** tegner gridlines
4. **ImageFinder** og evt. **MoveFinder** analyserer brættet for at finde brikkernes placering og identificere, hvilket træk der er foretaget.
5. **VisionInterface** samler det hele og tilbyder nemme metoder til resten af systemet, fx at få det seneste træk som en streng.

## ROS
This code implements the core logic for controlling a robotic arm to perform chess moves using the MoveIt motion planning framework in ROS 2. The ChessMoves class manages the robot's movement, gripper actions, and coordinate transformations needed to interact with chess pieces on a board.

The constructor initializes the MoveIt interface, setting parameters such as planning time, number of planning attempts, reference frame, velocity and acceleration scaling, and starts the state monitor. This ensures the robot is ready for precise and safe motion planning. The destructor logs when the class is destroyed.

The move_to_idle function moves the robot to a predefined "idle" joint configuration by specifying target joint angles for each joint and commanding the robot to move there. This is useful for resetting the robot to a safe or neutral position.

The move function is the main dispatcher for chess actions. It takes a MoveStruct describing the move and a transformation matrix for board-to-robot coordinates. Depending on the move type (e.g., move, remove, add, promote, castle, en passant, player capture), it calls the appropriate helper function. Some moves involve additional logic, such as capturing a piece or handling castling, and may set logger values to trigger specific gripper behaviors.

Functions like remove_piece, add_piece, move_piece, and capture_piece handle the details of each chess action. They update internal arrays tracking dead pieces, compute start and end positions (using coordinate transformations), and call execute_move to perform the physical movement. The applyTransformation and applyTransformationRaw functions convert chessboard coordinates to robot coordinates using the provided transformation matrix, with or without tile centering.

The execute_move function plans and executes a sequence of Cartesian waypoints for the robot arm, including picking up and placing pieces at the correct heights. It uses MoveIt to compute and execute the trajectory, and controls the gripper to pick up or release pieces as needed. The function also ensures the robot returns to the idle position after each move.

## Gripper

### H-Bro
### DC-motor
![[DC Motor]]