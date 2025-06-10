I MySQL kan man automatisk generere ER-diagrammer ud fra det man har gjort.

### SQL (DDL) - CREATE OG DROP SCHEMA
Oprette små databaser (hvis man har flere forskellige der ikke snakker sammen):
CREATE SCHEMA Lystfisker;

Slette:
DROP SCHEMA Lystfisker;

SQL er caseINsensitive

### CREATE
CREATE TABLE
ud, datatype, column-modifier/constraints
AUTO_INCREMENT

CREATE TABLE fisk (
fisk_id int not null,
navn char(25) not null,
max_laengde_cm int not null,
primary key (fisk_id)
);

Man kan sætte den til at lave nye id'er (keys) selv ved at bruge AUTO_INCREMENT (f.eks. ved hver nye række)
CREATE TABLE fisk(
fisk_id int not null AUTO_INCREMENT,
navn char(25) not null,
max_laengde_cm int not null,
primary key (fisk_id)
);

### Constraints
NOT NULL
UNIQUE
PRIMARY KEY

### CONSTRAINTS
![[CONSTRAINTS.png]]

DEFAULT 
CHECK (om en værdi skal være over eller under en eller anden værdi)
FOREIGN KEY (brugeren kan ikke slette noget fordi så er foreign key ikke sat til noget)

### DEFAULT, CHECK, FOREIGN KEY
![[DEFAULT, CHECK, FOREIGN KEY.png]]

### Begreber
Rækker, kolonner, tupler, rows, columns, records, result set

### Navngivning af attributter
Det er vigtigt at man er konsekvent med ens navngivning. F.eks. fisk.fisk_id og fisk.navn.

### Opdatering - INSERT
INSERT INTO fisk
VALUES (1, 'Hornfisk', 90);

eller

INSERT INTO fisk (fisk_id, navn, max_laengde_cm)
VALUES (1, 'Hornfisk', 90);

### Simple selects
SELECT * viser alle tabellernes attributter
FROM fisk, fangst angiver hvilke tabeller vi henter data fra
WHERE betingelse der matcher rækker mellem tabellerne og undgår overflødige (kryds)tuples
fx vil SELECT * FROM fisk; Vælg alle kolonner og alle rækker fra tabellen `fisk`
Overflødige tuples kan undgås, hvis man matcher nøglerne, fx fisk.fisk_id = fangst.fisk_id

### Opdatering - UPDATE/DELETE
UPDATE fisk
SET max_laengde_cm = 53
WHERE fisk_id = 3;

DELETE FROM plads
WHERE plads_id = 5;

DELETE FROM plads;

set sql_safe_updates = 0;

### Referential integrity
Forsøg på sletning af pladser vil gå galt.
Det skyldes, at der i givet fald ville være rækker i fisketur-tabellen, som peger på ikke-eksisterende pladser.
At noget sådant ikke kan finde sted kaldes referential integrity.
Alternativt kan man anvende cascade delete.

### Nestede SELECT-statements
Opgave: Vis navnet på de pladser, hvor der ikke er fanget fisk.

SELECT plads.navn FROM plads WHERE not exists
(SELECT plads.navn FROM fangst, fisketur WHERE fangs.fisketur_id = fisketur.fisketur_id)
AND fisketur.plads_id = plads.plads_id);

### Den relationelle model

### Bibliotekssystem
Attributter:
Bogtitel
Udgivelsesår
Forfatternavn
Forfatter nationalitet
Forfatter fødselsår
Forfatter dødsår
Stregkode på eksemplar
Låners navn
Låners adresse
Låners CPR-nummer
Udlånsdato

Opgave:
Grupper dataet.
Lav relationel model.
Opret database.
Løs SQL opgaver

![[Relationel model af bibliotekssystem.png]]

### Matematiske operationer
![[Matematiske operationer.png]]
### JOIN
![[JOIN.png]]
### NATURAL JOIN 
![[NATURAL JOIN.png]]
### GROUP BY
![[GROUP BY.png]]
### GROUP BY med flere tabeller
![[GROUP BY med flere tabeller.png]]
### HAVING
![[HAVING.png]]
### Begrænsninger af antal grupper
![[Begrænsninger af antal grupper.png]]
### GROUP BY med HAVING
![[GROUP BY med HAVING.png]]