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
Her er d afstanden fra enden til midtpunktet, og eftersom vi kender starten kan vi skrive: $$I_{O}= \frac{1}{12}mL^{2} + md^{2}$$ Vi har nu også $$\begin{align*} T &= 2 \pi \sqrt{ \frac {I_{O}} {mgd}}\\ T &= 2 \pi \sqrt{ \frac {mL^{2}+12md^{2}} {12mgd}}\\ T &= 2 \pi \sqrt{ \frac {L^{2}+12d^{2}} {12gd}}\\ \end{align*}$$ Nu kan vi differentiere i forhold til d $$\frac{dT}{dd} = \frac{\pi \left(12d^{2} - L^{2}\right)}{2 \sqrt{3} \, g \sqrt{\frac{1}{gd}} \, d^{2} \sqrt{12d^{2} + L^{2}}}$$ Dette sætter vi så lige med 0 for at finde ud af hvor T er mindst: $$\begin{align*} \pi \left(12d^{2} - L^{2}\right) &= 0\\ 12d^{2}-L^{2}= 0 \end{align*}$$ Her indsættes $L = 1$  
$$12d^{2}= 1$$ $$\begin{align*} d^{2}&= \frac{1}{12}\\ d&= \pm \sqrt{\frac{1}{12}} = \pm 0.288675 \end{align*}$$ Vi kan her lægge midten oveni: $$0.5 - \sqrt{\frac{1}{12}} = 0.2113$$ Det skal derfor monteres $0.2113 m$ fra enden $$T = 2 \pi \sqrt{ \frac {L^{2}+12d^{2}} {12gd}}$$ her indsættes så det som vi har $$T = 2 \pi \sqrt{ \frac {1+1} {12 \cdot 9.82 \cdot 0.288675}} = 1.5235$$ vi her derved svingningstiden $T = 1.52 \space s$.

![[Pasted image 20251111141720.png]]
9.4 Fjederkonstanterne for fjedrene på figurerne er henholdsvis $k_{1}$ og $k_{2}$. Massen af klodserne er $m$.
Bestem svingningstiden for de to systemer:

Jeg fandt kraften i lektion 4:

Når fjedre er i serieforbindelse har de samme kraft F, hvor deres forlængelser adderer til totalforlængelsen x:
$$
x_{1} = \frac{F}{k_{1}}, \quad x_{2} = \frac{F}{k_{2}}, \quad x = F\left(\frac{1}{k_{1}} + \frac{1}{k_{2}}\right)
$$
Siden den ækvivalente fjedermodstand er:
$$
\frac{1}{k_{eq}} = \frac{1}{k_{1}} + \frac{1}{k_{2}}
$$
Så må $k_{eq}$:
$$
k_{eq} = \frac{k_{1}k_{2}}{k_{1} + k_{2}}
$$
$$
T = 2 \pi \sqrt{\frac{m}{k_{eq}}} = \sqrt{\frac{m(k_{1} + k_{2})}{k_{1}k_{2}}}
$$
Ellers kunne jeg dividere med $2 \pi$ og så havde den heddet $\frac{2 \pi}{\sqrt{\frac{k_{eq}}{m}}}$  i stedet for

Når fjedre er i parallelforbindelse har de samme forskydning x og deler den samlede kraft F:
$$
F_{1} = k_{1}x, \quad F_{2} = k_{2}x, \quad F = F_{1} + F_{2} = (k_{1} + k_{2})x
$$
Dermed er $k_{eq}$:
$$
k_{eq} = k_{1} + k_{2}
$$
$$
T = 2 \pi \sqrt{\frac{m}{k_{1} + k_{2}}}
$$
