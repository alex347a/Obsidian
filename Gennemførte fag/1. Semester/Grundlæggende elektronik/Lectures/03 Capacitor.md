---
cards-deck: Noter::Grundlæggende elektronik::Lectures
---

Læs kapitel 2 igen og lav opgaverne  
Læs kapitel 3, men kun det om kapacitorer og forstå ca. halvdelen.  
A capacitor accounts for electric field effects. The unit is Farads $[F]$ which are volts per Coulomb $[V/C]$. The charge stored is given by $q=C \cdot U$  
$$i=C \frac{dv}{dt}$$
$$v(t)=\frac{1}{C} \int_{t_0}^{t} i(t) \, dt+v(t_0)$$
The energy stored is given by: $w(t)=\frac{1}{2} C v^2(t)$.  
Capacitance is in short, a component that stores energy. Dette betyder at alle to legemer der kan lede strøm i princippet, er kapacitorer. Det svarer lidt til et reservoir. Capacitance becomes used to deliver small bursts of energy to components that require high amounts of energy in a short time. Leyden jar was the first capacitor.  
There are polar and non-polar capacitors. One generally does not use polar capacitors in alternating current, because the poles change all the time.  
The closer capacitors are to each other, the more energy is required to move each charge. This is a bit counterintuitive, but it is because the electric field becomes stronger when they are close to each other. One tries to make the insulating layers as thin as possible so that the capacitors can be as small as possible and deliver as much current as possible. A thin insulating layer can be made by using aluminum and saltwater, creating a thin white layer of aluminum oxide, and both aluminum and saltwater are conductive materials. The problem is that aluminum oxide can be removed by electrolysis, so if the voltage is applied the wrong way, aluminum oxide will dissolve. The same can be done with tantalum, which is even better, but it is expensive (rare) and found in conflict zones, so if one buys it, they contribute to war. Neodymium is even better, but is even more expensive.
## Capacitance in series
Capacitance in **series** are combined in the same manner as resistances in **parallel**.  
$$
\frac{1}{C_{\text{total}}} = \frac{1}{C_1} + \frac{1}{C_2} + \frac{1}{C_3} + \dots
$$
## Capacitance in parallel
Capacitance in **parallel** are combined in the same manner as resistances in **series**.
$$
C_{\text{total}} = C_1 + C_2 + C_3 + \dots
$$
## Plate capacitor formula
The capacitance of a parallel plate capacitor is given by: $C=\frac{\epsilon A}{d}$.  
## Dielectric constant
For vacuum the dielectric constant is $\epsilon=\epsilon_0=8.85 \cdot 10^{-12} \, F/m$, for other materials, the dielectric constant is $\epsilon=\epsilon_0 \, \epsilon_r$ where $\epsilon_r$ is the relative dielectric constant.
## Parasitic effects
Real capacitors have several parasitic effects. Therefore some energy is lost.  
![[Pasted image 20241029175219.png]]
![[Pasted image 20241029175227.png]]![[Pasted image 20241029175233.png]]![[Pasted image 20241029175239.png]]![[Pasted image 20241029175241.png]]![[Pasted image 20241029175245.png]]
Kapacitorer og modstande.  
En kapacitor bliver ladt op langsommere og langsommere jo mere den er blevet ladt. Den aflades hurtigt i starten og dernæst langsommere og langsommere jo mere den nærmere sig 0.  

Digitale udgange  
Hvis man bruger Pico som eksempel, så har den digitale udgange hvor der enten er 3.3V eller 0V som giver enten 1 eller 0 som output.  
Digitale indgange  
I Picoen er der et spektrum, hvor $0-0.8 \, V$ bliver læst som falsk, $0, \, 0.8-2 \, V$ er udefineret (derfor kan det blive enten 0 eller 1 alt efter Picoens humør), mens $2-3.3 \, V$ bliver læst som sandt.  

74 HCT 04  
Har en indgang og bliver enten $5 \, V$ eller $0 \, Volt$ ved udgangen. Den vender outputtet omvendt, så hvis den kom ind som sand så kommer den ud som falsk og omvendt.

## Capacitor flashcard #Card

$$V(t) = V_{\text{max}} \left( 1 - e^{-\frac{t}{RC}} \right)$$
Hvor:
- $V(t)$ er spændingen over kondensatoren som funktion af tiden $t$.
- $V_{\text{max}}$ er den maksimale spænding (typisk forsyningsspændingen).
- $R$ er modstanden i kredsløbet.
- $C$ er kondensatorens kapacitans.
- $t$ er tiden.
^1736424664297

Tidskonstanten $\tau$ defineres som:
$\tau = RC$
