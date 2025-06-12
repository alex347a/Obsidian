#### Strings
.length(): længden af string (brug .size() for samme resultat men med kompitabilitet med andre typer)

##### stoi(): string to int.
###### eksempel
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
##### eksempel
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
##### string::npos

##### .find(): returnerer true hvis man finder string
###### eksempler:
1. Find om en substring eller char eksisterer med find():
```
#include <iostream>
#include <string>

int main() {
    std::string str = "Hello, World!";
    size_t found = str.find("Python"); // Searches for "Python"

    if (found == std::string::npos) {
        std::cout << "Substring not found!" << std::endl;
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
3. Check om en char er i en string:
```
#include <iostream>
#include <string>

bool contains(const std::string& str, char ch) {
    return str.find(ch) != std::string::npos;
}

int main() {
    std::string str = "Hello";
    std::cout << std::boolalpha << contains(str, 'e') << std::endl; // true
    std::cout << std::boolalpha << contains(str, 'z') << std::endl; // false
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