![[Pasted image 20251020131226.png]]
6.1 En mand med massen 90 og står i en elevator. Bestem den kraft, hvormed elevatorgulvet påvirker manden, når:
a) Elevatoren går op med konstant hastighed
Her er det vigtigt at jeg skal besteme kraften elevatorgulvet påvirker manden med, hvilket svarer til normalkraften.

$$
F = m \cdot a
$$
$$
90 \space \text{kg} \cdot 9.82 \frac{m}{s^{2}} = 883.8 \space \text{N}
$$


b) Elevatoren går ned med konstant hastighed

$$
F = m \cdot a
$$
$$
90 \space \text{kg} \cdot 9.82 \frac{m}{s^{2}} = 883.8 \space \text{N}
$$
c) Elevatoren accelereres opad med 3,0 $\frac{m}{s^{2}}$

$$
a = (a_{mand} + g)
$$
$$
F_{mand} = m \cdot a
$$
$$
a_{mand} = 3.0 \frac{m}{s^{2}}
$$
Da der er tale om normalkraften så har normalkraften og tyngdekraften modsat retning, så normalkraften skal både have en størrelse der ophæver tyngdekraften og derudover er stor nok til også at accelerere med $3.0 \frac{m}{s^{2}}$.
$$
90 \space \text{kg} \cdot \left(9.82 \frac{m}{s^{2}} + 3.0 \frac{m}{s^{2}}\right) =  \space 1153.8 \space \text{N}
$$
d) Elevatoren accelereres nedad med 3,0 $\frac{m}{s^{2}}$
$$
a = (a_{mand} + g)
$$
$$
F_{mand} = m \cdot a
$$
$$
a_{mand} = 3.0 \frac{m}{s^{2}}
$$
Da der er tale om normalkraften så har normalkraften og tyngdekraften her samme retning, dette betyder at normalkraften skal accelerere med $3.0 \frac{m}{s^{2}}$ nedad, hvilket så kan trækkes fra tyngdekraften, derfor bliver normalkraften:
$$
90 \space \text{kg} \cdot \left(9.82 \frac{m}{s^{2}} - 3.0 \frac{m}{s^{2}}\right) =  \space 613.8 \space \text{N}
$$
e) Kablet knækker og elevatoren falder frit. Benyt både det faste system og et henførelsessystem, der følger elevatoren.
Hvis elevatoren falder frit, så betyder det at han i et fast system bliver påvirket med $0 \space \text{N}$ fra normalkraften, fordi han accelerere med tyngdeaccelerationen.
I et henførelsessystem så vil der være en fiktik kraft der er opadrettet og som udligner tyngdekraften:
$$
F_{fiktiv} = m \cdot a_{sys}
$$derfor bliver den samlede kraft igen $0 \space \text{N}$ 
![[Pasted image 20251020131234.png]]
En lastbil starter fra hvile til tiden $t=0$ og accelererer jævnt, således at dens fart er $v_{1} = 20 \frac{m}{s}$ til tiden $t = t_{1} = 10 \space \text{s}$. En lille kasse med massen $m = 5.0 \space \text{kg}$ er før starten anbragt i afstanden $l = 3.0 \space \text{m}$ fra bagenden. Til $t=0$ begynder kassen at glide. Gnidningskoefficienten mellem kasse og lad er $\mu_{k} = 0.15$.

a) Angiv de kræfter, der virker på kassen såvel i bilens som i vejbanens henførelsessystem.
I et inertialsystem har kassen:
1. Tyngdekraften $m \vec{g}$ lodret nedad.
2. Normalkraften $\vec{N}$ lodrat opad ($N = mg$)
3. Gnidningskraften $\vec{f_{k}}$ vandret, modsat kassens bevægelsesretning ift. ladet.
$$
f_{k} = \mu_{k} N = \mu_{k} m g
$$
Da kassen glider bagud betyder det at gnidningskraften er fremad.

I et ikke-inertialsystem er der også:
4. Fiktiv kraft $-m \vec{a}_{t}$, hvor $\vec{a}_{t}$ er lastbilens acceleration ift. jorden. I bilens system er den fiktive kraft bagud.


b) Bestem kassens acceleration i begge henførelsessystemer.
Lastbilens acceleration er givet ved:
$$
a = \frac{v_{1}}{t_{1}} = \frac{20 \space \frac{m}{s}}{10 \space \text{s}} = 2 \space \frac{m}{s^{2}}
$$
#### I vejbanens system:
Den positiv retning er lastbilens køreretning.

På kassen er der kun gnidningskraften $f_{k}$ vandret fremad:
$$
ma_{k} = f_{k} = \mu_{k} m g
$$
$$
a_{k} = \mu_{k} g = 0.15 \cdot 9.82 = 1.473 \frac{m}{s^{2}} 
$$
Dvs. kassens acceleration er $1.473 \frac{m}{s^{2}}$ fremad.

#### I bilens system:
Der er både gnidningskraften fremad og den fiktive kraft bagud $- ma_{t}$ bagud.
Den positive retning er stadigvæk lastbilens køreretning.
Gnidningskraften er: $f_{k}$
Den fiktive kraft er: $-ma_{t}$

Newtons 2. lov:
$$
m a_{rel}' = -m a_{t} + f_{k}
$$
$$
a_{rel}' = -a_{t} + \mu_{k} g
$$
$$
a_{rel}' = -2.0 \space \frac{m}{s^{2}} + 1.473 \space \frac{m}{s^{2}} = -0.537 \space \frac{m}{s^{2}}
$$
Dvs. kassen accelererer bagud med $-0.537 \frac{m}{s^{2}}$.

c) Bestem den tid, som kassen er om at nå bagenden.
For at bestemme dette skal jeg finde hvornår startpositionen af kassen har rykket sig 3 meter.
$$
x'(t) = 0 + 0 \cdot t + \frac{1}{2} a_{rel}' t^{2}
$$
Så hvis vi siger at kassen starter ved $x'(0) = 0$ så skal kassen nå $x' = -3.0 \space \text{m}$, hvilket jeg så indsætter i ligningen:
$$
-3 = \frac{1}{2} -0.537 t^{2}
$$
$$
t^{2} = \frac{2 \cdot 3}{0.537} = \frac{6}{0.537} \approx 11.17 \space \text{s}
$$
$$
\sqrt{11.17 } \space \text{s} \approx 3.342 \space \text{s}
$$
Dvs. kassen rammer bagenden ved tiden $t = 3.342 \space \text{s}$ 


d) Bestem den vandrette komposant af kassens hastighed, når kassen rammer vejen.
Kassens hastighed:
$$
v_{k}(t) = 0 + a_{k} \cdot t = 1.473 \cdot 3.342 = 4.923 \space \frac{m}{s}
$$
Lastbilens hastighed på det tidspunkt:
$$
v_{t}(t) = a_{t} \cdot t = 2.0 \cdot 3.342 = 6.684 \frac{m}{s}
$$
