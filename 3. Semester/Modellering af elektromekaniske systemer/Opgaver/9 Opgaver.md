![[Pasted image 20251111141634.png]]
9.2 En tynd, homogen stang med længden $l = 1,00 \space m$ er ophængt i sit ene endepunkt. Stangen kan udføre svingninger om en vandret akse.

a) Bestem stangens svingningstid
Længden af stangen er $l$, men i formlerne plejer $l$ at være distancen ud til massemidtpunktet, så det kan jeg så for d:
$$
d = \frac{1}{2}l
$$
$$
T = 2 \pi \sqrt{\frac{I_{O}}{lmg}}
$$
For en homogen stang er inertimomentet:
$$
I_{O} = \frac{1}{3} m l^{2}
$$
$$
T = 2 \pi \sqrt{\frac{\frac{1}{3} l}{g}}
$$
Siden $l = 2d$ 
Husker at: $d = \frac{1}{2}l$, så jeg indsætter:
$$
T = 2 \pi \sqrt{\frac{\frac{2}{3}}{g}} \approx 1.64 \space s
$$
b) Stangen ophænges nu i et andet punkt på stangen.

B) Her bruges der nu Steiners sætning hvor vi har massemidtpunktet i midten af stangen: $$ I_{O} = I_{0}+md^{2}$$
her er d afstanden fra enden til midtpunktet, og eftersom vi kender starten kan vi skrive: $$I_{O}= \frac{1}{12}mL^{2} + md^{2}$$ vi har nu også $$\begin{align*} T &= 2 \pi \sqrt{ \frac {I_{O}} {mgd}}\\ T &= 2 \pi \sqrt{ \frac {mL^{2}+12md^{2}} {12mgd}}\\ T &= 2 \pi \sqrt{ \frac {L^{2}+12d^{2}} {12gd}}\\ \end{align*}$$ nu kan vi differentiere i forhold til d $$\frac{dT}{dd} = \frac{\pi \left(12d^{2} - L^{2}\right)}{2 \sqrt{3} \, g \sqrt{\frac{1}{gd}} \, d^{2} \sqrt{12d^{2} + L^{2}}}$$ dette sætter vi så lige med 0 for at finde ud af hvor T er mindst: $$\begin{align*} \pi \left(12d^{2} - L^{2}\right) &= 0\\ 12d^{2}-L^{2}= 0 \end{align*}$$ her indsættes L = 1 $$12d^{2}= 1$$ $$\begin{align*} d^{2}&= \frac{1}{12}\\ d&= \pm \sqrt{\frac{1}{12}} = \pm 0,288675 \end{align*}$$ vi kan her lægge midten oveni: $$0.5 - \sqrt{\frac{1}{12}} = 0,2113$$ det skal derfor monteres 0,2113 fra enden $$T = 2 \pi \sqrt{ \frac {L^{2}+12d^{2}} {12gd}}$$ her indsættes så det som vi har $$T = 2 \pi \sqrt{ \frac {1+1} {12 \cdot 9.82 \cdot 0.288675}} = 1,5235$$ vi her derved svingningstiden.

![[Pasted image 20251111141720.png]]
9.4 Fjederkonstanterne for fjedrene på figurerne er henholdsvis $k_{1}$ og $k_{2}$. Massen af klodserne er m.

Bestem svingningstiden for de to systemer:

