Læs kapitel 1. 19-52  
Hvis man måler den elektriske strøm, så vil ladningen i coulomb som funktion af tiden i sekunder være givet ved 
$$ i(t) = \frac{dq(t)}{dt} $$ 
hvis der er en konstant strøm på 1 ampere, så er der en coulomb af ladning der passerer gennem tværsnittet hvert sekund.  
Derfor for at finde ladningen i en given elektrisk strøm være givet ved integralet:  
$$ q(t) = \int_{t_0}^{t} i(t) \, dt + q(t_0) $$  
Hvor $t_0$ er tiden, hvor ladningen er kendt.  
Man bruger $i$ til at vise retningen af strømmen; hvis $i_2$ er negativ, så går strømmen den modsatte retning af den reference retning man valgte for $i_1$. Man kan også beskrive retningen ved at bruge $i_{ab}$, hvor 
$$ i_{ab} = -i_{ba} $$  
det er strømmens retning fra $a$ til $b$.  
Spændingen indikerer retningen af energi flow; hvis positive ladninger går fra den positive polaritet gennem et element til den negative polaritet, så absorberer elementet varme, mekanisk energi, kemisk energi eller noget andet. Hvis det er modsat og den positive ladning går fra den negative polaritet til den positive polaritet, så giver elementet energi. For negative ladninger er retningen af energioverførsel modsat.  
Hvis man ikke kender polariteten af spændingen, så kan man bare lave reference polariteter.  
$$ v_1(t) = 10 \, V $$  
Er en DC-spænding, fordi den ikke ændrer værdi af spænding og polaritet.  
$$ v_2(t) = 10 \cdot \cos(200 \pi t) \, V $$  
Er en AC-spænding, fordi den ændrer værdi af spænding og polaritet. Når værdien er negativ, så er polariteten modsat reference polariteten.  
Man kan bruge pile til at indikerer reference polariteten, hvor den positive reference er hovedet af pilen.  
$$ p = v i $$  
Produktet af spænding (voltage) og strømstyrke (current) er kraften (power).  
I enheder:  
$$ V \cdot A = \frac{J}{C} \cdot \frac{C}{s} $$  
$$ \frac{J}{s} = W $$  
Kraften (power) er altså givet i watt.  
En positiv værdi for $p$ betyder, at energi bliver absorberet af elementet, mens en negativ værdi viser, at elementet giver energi.  
Nogle gange er de funktioner af tid, og derfor kan man skrive formlen som  
$$ p(t) = v(t) \cdot i(t) $$  
For at beregne energien $w$, der bliver leveret til et element mellem to tidspunkter, kan kraften (power) integreres:  
$$ w = \int_{t_1}^{t_2} p(t) \, dt $$
Tabel over enheder:  

| Prefix        | Abbreviation | Scale factor |
| ------------- | ------------ | ------------ |
| Giga-         | G            | 10^9         |
| Meg- og mega- | M            | 10^6         |
| Kilo-         | k            | 10^3         |
| Milli-        | m            | 10^-3        |
| Micro-        | μ            | 10^-6        |
| Nano-         | n            | 10^-9        |
| Pico-         | p            | 10^-12       |
| Femto-        | f            | 10^-15       |

En node er, når to eller flere kredsløb er tilkoblet hinanden.  
Kirchhoffs strøm (current) lov går ud på, at net strøm der kommer i en node er 0 og beregnes ved at plusse strømmen der går ind og trækker strømmen der går ud fra. Loven betegnes KCL. Hvis det ikke var tilfældet, så vil der være mere energi et sted og mindre et andet, som vil danne en kraft, fordi negative og positive poler tiltrækker hinanden.  
Kirchhoffs spænding (voltage) lov går ud på, at summen af spændingen i et lukket system (loop) er 0.  
Konservering af energi.  
$$ p_a + p_b + p_c = 0 $$  
Når der er en parallelforbindelse, er reference polariteten den samme for alle elementer, der er parallelt forbundet.  
En ideel leder er, når spændingen mellem begge ender er 0, uanset hvilken spænding der flyder gennem den; når to punkter i et kredsløb er forbundet med en leder, er de "shorted" sammen, derfor kaldes det også for et "short circuit". Hvis der ikke er en leder eller andre elementer i et kredsløb, er det et "open circuit"; der kan ikke være strøm i et ideelt open circuit.  
En uafhængig strømkilde har en specifik spænding uanset hvilke andre elementer der er forbundet med den og den strøm der gennemstrømmer den.  
En afhængig- eller kontrolleret strømkilde minder om en uafhængig strømkilde, men i stedet er nu en funktion af andre spændinger i kredsløbet. En spændingskontrolleret (voltage controlled) strømkilde ganger en konstant på spændingen der gennemstrømmer den. En strømstyrkekontrolleret (current controlled) strømkilde gør det samme men med strømstyrken i stedet.  
En uafhængig strømstyrkekilde (current) tvinger en specifik strømstyrke (current) igennem sig selv.  
En afhængig strømstyrkekilde (current) er bestemt af en strømstyrke eller spænding i kredsløbet. Der er altså 4 forskellige kontrollerede kilder:  
- Voltage-controlled voltage sources  
- Current-controlled voltage sources  
- Voltage-controlled current sources  
- Current-controlled current sources  

Resistorer og ohms lov:  
Spændingen $v$ (voltage) over en ideel resistor er proportional med strømstyrken $i$ (current) gennem resistoren; proportionaliteten er modstanden $R$ (resistance).  
$$ v = i \cdot R $$  
Eller:  
$$ U = I \cdot R $$  
Enheden for modstanden er $\Omega$. Conductance $G = \frac{1}{R}$ er invers ohm $\Omega^{-1}$ og kaldes for siemens $S$.  
Man betragter resistorer som formen af en lang cylinder eller bar. Tværsnitsarealet $A$ er konstant over længden af cylinderen; hvis længden $L$ er meget større end dimensionerne af tværsnittet, er resistansen ca. givet ved:  
$$ R = \frac{\rho L}{A} $$  
Hvor $\rho$ er resistiviteten af materialet, som er brugt til resistoren. Enheden for resistivitet er ohm meter $\Omega \cdot m$.  
Materialer kan være klassificeret som conductor, semiconductor eller insulator, alt efter resistiviteten. Conductor har lavest resistivitet. Insulator har højest resistivitet. Semiconductor falder ind i mellem.  
Hvis man substituerer ohms lov ind for $v$, så kan man ud fra:  
$$ p = v \cdot i $$  
få:  
$$ p = R \cdot i^2 $$  
Hvis man løser ohms lov for $i$, får man i stedet:  
$$ p = \frac{v^2}{R} $$  
Resistansen er positiv uanset hvad $v$ eller $i$ er, og derfor absorberer resistansen energi.  
Man kan bruge resistansen til at måle overanstrengelse (strain)  
$$ \epsilon = \frac{\Delta L}{L} $$  
$$ G = \frac{\Delta R}{R_0 \epsilon} $$  
Hvor $R_0$ er resistansen før overanstrengelse.  
Man kan bruge resistansen til mere end bare at danne varme, f.eks. til at lave lyde i en højtaler eller transmittere via antenna i form af elektromagnetiske bølger.  
Genopfrisk din viden om elektronen, ladning, strøm, spænding, modstand.  
Reflekter over hvordan øvelse 1 relaterer til kapitel 1.
