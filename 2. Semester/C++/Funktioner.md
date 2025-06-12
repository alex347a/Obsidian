#### Strings
.length(): længden af string (brug .size() for samme resultat men med kompitabilitet med andre typer)
.at(): ved en position
stoi(): string to int
substr(sted, antal cifre): Vælger fra et sted givet ved et cifre og så en antal cifre frem fra det, husk det er 0 indekseret. 
string::npos

#### Vektorer
Definerer en vektor som:
vector<int/string> navn

isdigit(): tjekker om en int består kun af cifre
isNumeric(): tjekker om en string ved hver char er et cifre.
Eksempel:
	for (int i = 0; i < 9; i++)
		if (!isNumeric(nummeret.at(i)))
	
Man kan også bruge:
if (c >= '0' && c <= '9'), hvor c er en char og så kigger du i ascii alfabetet.

#### Array
ar[] = { 1, 5, 3}
Du kan sagtens gange et array over i nogle værdier med et for-loop:
Eksempel:
	int weights[] = { 4,3,2,7,6,5,4,3,2,1 };
	int sum = 0;
	for (int i = 0; i < 10; i++)
	{
		sum += stoi(etCprNr.substr(i, 1)) * weights[i];
	}
#### Modulus
Division hvor resten bliver returneret.
Eksempel:
	10 % 3 = 1