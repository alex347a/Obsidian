Du kan skrive deconstructoren hvor enden du har lyst til, f.eks. lige efter constructoren
Når du bruger templates skal du ikke skrive {} i constructoren og destructoren i headerfilen.
Hvis du skal bruge en privat attribut skal du lave en getMetode
Hvis du skal nedarve, brug protected. Derfor er det god ide bare altid at lave private attributes protected, sådan at du altid kan nedarve senere uden at skulle til at ændre det.
pragmaonce og (ifndef headerfil med CAPS efterfulgt af define header fil med CAPS og endif neders i filen) er det samme.
Du skal skrive template <typename T> både før constructoren og igen før metoden.