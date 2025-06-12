Size_t: unsigned integer (ikke-negativt heltal) den kan holde det størst mulige objekt i systemet.

Static funktioner er funktioner der kun er synlige i den fil de er i. F.eks. i mainfilen.
## Strings
##### length(): længden af string (brug .size() for samme resultat men med kompitabilitet med andre typer)
###### eksempel:
```
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello World";
    
    // Begge metoder giver samme resultat
    std::cout << "Length: " << str.length() << std::endl;  // 11
    std::cout << "Size: " << str.size() << std::endl;      // 11
    
    return 0;
}
```

##### string::npos: Returnerer false hvis man finder noget i en tekst, returnerer true hvis man ikke finder ordet. Se evt. find()
###### eksempel:
Koden fortæller om et ord er i en tekst.
```
static bool ordITekst(string tekst, string ord)
{
	return tekst.find(ord) != string::npos;
}
```
Så find leder efter ordet, hvis den finder ordet returnerer den indexet af den første gang ordet fremkommer. Hvis den ikke kan finde ordet så returnerer find en konstant npos, hvis den dermed svarer til npos så returneres der false, hvis det er forskelligt fra npos så er ordet fundet.
##### find(): returnerer true hvis man finder string

###### eksempler:
1. Find om en substring eller char eksisterer med find():
```
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    size_t found = str.find("World"); // Searches for "World"

    if (found != std::string::npos) {
        std::cout << "Found at position: " << found << std::endl;
    } else {
        std::cout << "Not found!" << std::endl;
    }
    return 0;
}
```
2. Finde alle gange en karakter optrædder:
```
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    size_t pos = str.find('o'); // Find first 'o'

    while (pos != std::string::npos) {
        std::cout << "'o' found at position: " << pos << std::endl;
        pos = str.find('o', pos + 1); // Continue searching from next position
    }
    return 0;
}
```
3. Check om alle chars i en string er en lovlig char:
```
bool EMA::checkChars() const
{
	string legalLetters = "abcdefghijklmnopqrstuvwxyz0123456789.@%&";
	for (char c : emailAddress)
	{
		if (legalLetters.find(c) == string::npos)
		{
			return false;
		}
	}
	return true;
}
```
##### stoi(): string to int.
###### eksempel
```
#include <iostream>
#include <string>

int main() {
    std::string numStr = "123";
    int num = stoi(numStr);
    std::cout << num + 1 << std::endl; // 124
    return 0;
}
```
##### substr(sted, antal cifre)
Vælger fra et sted givet ved et cifre og så en antal cifre frem fra det, husk det er 0 indekseret. 
###### eksempel
```
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    std::string sub = str.substr(7, 5); // "World"
    std::cout << sub << std::endl;
    return 0;
}
```
## Vektorer
Definerer en vektor som:
```
vector<string> navne
```

##### isdigit(): tjekker om en int består kun af cifre
###### eksempel:
```
bool isNumeric(const string &str) {
    for (char c : str) {
        if (!isdigit(c)) return false;
    }
    return true;
}
```
##### isNumeric(): tjekker om en string ved hver char er et cifre.
###### Eksempel:
```
for (int i = 0; i < 9; i++)
		if (!isNumeric(nummeret.at(i)))
```
Man kan også bruge:
```
for (int i = 0; i < 9; i++)
		if (c >= '0' && c <= '9')
```
hvor c er en char og så kigger du i ascii alfabetet.
## Array
```
ar[] = { 1, 5, 3}
```
Du kan sagtens gange et array over i nogle værdier med et for-loop:
##### eksempel:
```
int weights[] = { 4,3,2,7,6,5,4,3,2,1 };
	int sum = 0;
	for (int i = 0; i < 10; i++)
	{
		sum += stoi(etCprNr.substr(i, 1)) * weights[i];
	}
```
## Modulus
Division hvor resten bliver returneret.
###### eksempel:
	10 % 3 = 1

## For loops
