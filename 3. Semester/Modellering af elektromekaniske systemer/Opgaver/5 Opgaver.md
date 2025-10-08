5-2
![[Pasted image 20251007141132.png]]
Et lille lod med massen m beskriver på en vandret, glat flade en jævn cirkelbevægelse med radius $r_{1}$ og fart $v_{1}$. Loddet er fæstnet til en tynd snor, der går gennem et lille hul i fladen.

a) Find snorkraften $F_{1}$, loddets impulsmoment med hensyn til centrum $L_{1}$ og loddets kinetiske energi $E_{kin,1}$

Impulsmomentet $L_{1}$ er givet ved:
$$
L_{1} = m r_{1} v_{1}
$$

Snorkraften $F_{1}$ er givet ved centripetalkraften:
$$
F_{1} = \frac{m v_{1}^{2}}{r_{1}}
$$

Den kinetiske energi $E_{kin,1}$ er givet ved:
$$
E_{kin,1} = \frac{1}{2} m \cdot v_{1}^{2}
$$

b) Ved langsomt at trække ned i snoren formindskes radius i cirkelbevægelsen, indtil den har værdien $r_{2}$ Find de værdier $F_{2}$, $L_{2}$ og $E_{kin,2}$, som snorkraften, loddets impulsmoment og loddets kinetiske energi nu har.
Impulsmomentet $L_{2}$ er givet ved:
$$
L_{2} = m r_{2} v_{2} = m r_{1} v_{1}
$$
$$
v_{2} = \frac{r_{1}}{r_{2}}v_{1}
$$

Snorkraften $F_{2}$ er givet ved centripetalkraften:
$$
F_{2} = \frac{m v_{2}^{2}}{r_{2}}
$$

Den kinetiske energi $E_{kin,2}$ er givet ved:
$$
E_{kin,2} = \frac{1}{2} m \cdot v_{2}^{2}
$$


c) Hvor stort et arbejde, $W_{12}$ er der blevet udført på systemet.
Arbejdet er ændringen i den kinetiske energi $W_{12}$:
$$
\begin{align*}
W_{12} &=  E_{kin,2} - E_{kin,1}\\
W_{12} &=  \frac{1}{2} m \cdot v_{2}^{2} - \frac{1}{2} m \cdot v_{1}^{2}
\end{align*}
$$
Hvis jeg så indsætter $v_{2} = \frac{r_{1}}{r_{2}}v_{1}$:
$$
W_{12} =  \frac{1}{2} m \cdot \left(\frac{r_{1}}{r_{2}}v_{1}\right)^{2} - \frac{1}{2} m \cdot v_{1}^{2}
$$
$$
W_{12} =  \frac{1}{2} m v_{1}^{2} \cdot \left(\frac{r_{1}^{2}}{r_{2}^{2}} - 1\right)
$$
5-7
![[Pasted image 20251007141151.png]]
Princippet i et ballistisk pendul er vist på figuren. Hastigheden af en pistolkugle bestemmes ved at måle den højde h, som træblokken når op i, efter at kuglen er skudt ind i den. Pistolkuglens masse er $m=16 \space g$. Træklodsens masse er $M = 8,0 \space kg$. Man måler $h=3,2 \space cm$.

a) Bestem pistolkuglens hastighed v.
Dette er et fuldstændig uelastisk stød.
Hvis jeg bruger impulsbevarelse under kollisionen (hvor V er fælleshastigheden lige efter kollisionen):
$$
m \cdot v = (m + M) V
$$
Energibevarelse efter kollisionen:
$$
\frac{1}{2} (m + M) V^{2} = (m + M) g h
$$
$$
V = \sqrt{2 g h}
$$

$$
m \cdot v = (m + M) \cdot \sqrt{2 g h}
$$
$$
v = \frac{m + M}{m} \cdot \sqrt{2 g h}
$$
$$
v = \frac{0.016 + 8.0}{0.016} \cdot \sqrt{2 \cdot 9.82 \cdot 0.032}
$$
$$
v = \frac{8.016}{0.016} \cdot \sqrt{0.62848} \approx 501 \cdot 0.793 \approx 397 \frac{m}{s}
$$

b) Beregn den procentdel $f_{p}$ af pistolkuglens kinetiske energi, der omdannes til varme under kuglens indtrængning i klodsen.
Jeg kan beregne den kinetiske energi for pistolkuglen og den potentielle energi for klodsen, og så ville forskellen mellem klodsens potentielle energi og pistolkuglens kinetiske energi være energien der er blevet tabt ved at blive omdannet til varme:

$$
E_{kin, kugle} = \frac{1}{2} m v^{2}
$$
$$
E_{kin, kugle} = \frac{1}{2} 0.016 \cdot 397^{2} = 0.008 \cdot 397^{2} = 1260.9 \space J
$$
$$
E_{pot, klods} = (m+M) gh
$$
$$
E_{pot, klods} = 8.016 \cdot 9.82 \cdot 0.032 = 2.519 \space J
$$
$$
\Delta  E = E_{kin,kugle} - E_{pot, klods}
$$$$
1260.9 \space J - 2.519 \space J = 1258.4 \space J
$$
$$
\frac{1258.4 \space J}{1260.9 \space J} \approx 99.8 \%
$$


5-5 (start med at opskrive en uendelig sum)
![[Pasted image 20251007141208.png]]
$$
e = \sqrt{\frac{h}{H}}
$$
Faldtiden for det første hop vil være:
$$
t_{0} = \sqrt{\frac{2H}{g}} = \sqrt{\frac{2 \cdot 0.25}{9.82}} \approx 0.2256 \space s
$$
Mens opsigtstiden for det første hop vil være $h_{1}$
Hvor:
$$
e = \sqrt{\frac{h_{1}}{H}} \Rightarrow h_{1} = e^{2} H
$$
Efter andet hop:
$$
h_{2} = e^{2}h_{1} \Rightarrow e^{4}H
$$
Tiden for et hop både op og ned vil være den samme højde:
$$
t_{hop} (h) = 2 \sqrt{\frac{2h}{g}}
$$
Det første hop bliver:
$$
t_{1} = 2 \sqrt{\frac{2e^{2}H}{g}} = 2 e \sqrt{\frac{2H}{g}}
$$
Det andet hop bliver:
$$
t_{2} = 2 \sqrt{\frac{2e^{4}H}{h}} = 2e^{2} \sqrt{\frac{2H}{g}}
$$
Dermed bliver det generelt:
$$
t_{k} = e^{k} \sqrt{\frac{2H}{g}}, \quad k = 1,2,3 \dots
$$
Den totale tid T er:
$$
T = t_{0} + \sum_{k=1} ^{\infty} t_{k}
$$
$$
T = \sqrt{\frac{2H}{g}} + 2 \sqrt{\frac{2H}{g}} \sum_{k=1}^{\infty} e^{k}
$$
Summen $\sum_{k=1}^{\infty} e^{k} = \frac{e}{1-e}$ for $0 < e < 1$:
$$
T = \sqrt{\frac{2H}{g}} \left[1 + \frac{2e}{1-e}\right]
$$
Indsætter tal:
$$
\sqrt{\frac{0.5}{9.82}} \approx 0.22564
$$
$$
T = 0.22564 \left[1 + \frac{2e}{1-e}\right]
$$
$$
36 = 0.22564 \left[1 + \frac{2e}{1-e}\right]
$$
$$
\frac{36}{0.22564} = \left[1 + \frac{2e}{1-e}\right]
$$
$$
158.47 = \frac{2e}{1-e}
$$
$$
158.47(1-e) = 2e
$$
$$
158.47 - 158.47 e = 2e
$$
$$
2e+158.47 e  = 158.47
$$
$$
160.47e = 158.47
$$
$$
e = \frac{158.47}{160.47} = 0.9875
$$
Eksempel 5.9
![[Pasted image 20251007141412.png]]