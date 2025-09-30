![[Pasted image 20250930140343.png]]
Klodsen starter i hvile og glider ned ad skråplanet uden gnidning. Den taber potentiel energi:
$$
E_{\text{pot}} = \sin(\theta) l m g
$$
Dette bliver til kinetisk energi:
$$
E_{\text{kin}} = \frac{1}{2} m v^{2}\\
$$
Jeg sætter de to ligmed hinanden:

$$
\sin(\theta) l m g = \frac{1}{2} m v^{2}
$$
Forkorter m:
$$
\sin(\theta) l g = \frac{1}{2} v^{2}
$$
Isolerer v:
$$
v^{2} = 2 \sin(\theta) l g
$$
$$
v = \sqrt{2 \sin(\theta) l g}
$$

b) Bestem den maksimale sammenpresning d af fjederen
Den tabte tyngdeenergi svarer til fjederenergien ved maksimal kompression.
Den tabte tyngdeenergi er den potentielle energi over både l og d, siden d er distancen fjederen bliver komprimeret:
$$
\begin{align*}
\sin(\theta) (l+d) m g &=  \frac{1}{2} k d^{2}\\
 k d^{2} - 2\sin(\theta) (l+d) m g &= 0\\
k d^{2} - 2 \sin(\theta) l m g - 2 \sin(\theta) d m g &= 0
\end{align*}
$$
$$
a = k, \quad b = -2mg \sin(\theta), \quad c = - 2 mg \sin(\theta) l
$$
Diskriminantformel (med D for ikke at forveksle det med d i opgaven)
$$
D=b^{2} - 4 ac
$$
$$
D = (2 mg \sin(\theta))^{2} + 8 k m g l \sin(\theta)
$$
Indsætter i rod-formlen
$$
\frac{b^{2} \pm \sqrt{D}}{2a}
$$
Hvor jeg kun beregner den positive rod:
$$
\frac{2 mg \sin(\theta) + \sqrt{(2 m g \sin(\theta))^{2} + 8 k m g l \sin(\theta)}}{2k}
$$
c) Hvor har klodsen sin maksimale hastighed?
Det er når fjederkraften er ligeså stor som tyngdekraften i bevægelsesretningen:
$$
\begin{align*}
kx = mg \cdot \sin(\theta)\\
x = \frac{mg \cdot \sin(\theta)}{k}
\end{align*}
$$
Det svarer til toppunktet af funktionen:
$$
\frac{-b}{2a}
$$
$$
x = \frac{\cancel{2} mg \cdot \sin(\theta)}{\cancel{2}k} = \frac{mg \sin(\theta)}{k}
$$
4.4
![[Pasted image 20250930145051.png]]

a)
Energi ved starten er givet ved:
$$
E_{s,0} = \frac{1}{2} k d^{2}
$$
Under udfoldning fra komprimeret til naturlig længde udfører friktionen arbejde $W_{fr}=F_{fr} d$ Restenergien er kinetisk energi ved $x = d$ (fjeder neutral):
$$
\frac{1}{2} m v_{0}^{2} = \frac{1}{2} k d^{2} - F_{fr} d
$$
Løser for $v_{0}$:
$$
v_{0} = \sqrt{\frac{k d^{2} - 2 F_{fr} d}{m}}
$$
Indsætter tallene:
$$
\frac{1}{2} k d^{2} = \frac{1}{2} \cdot 1000 \cdot 0.15^{2} = 11.25 J
$$
$$
W_{fr} = 5.0 \cdot 0.15 = 0.75 J
$$
$$
\frac{1}{2} m v_{0}^{2} = 11.25 - 0.75 = 10.5 J
$$
$$
v_{0} = \sqrt{\frac{2 \cdot 10.5}{8.0}} = \sqrt{2.625} \approx 1.62 \frac{m}{s}
$$
Efter fjederens naturlige længde virker kun friktionen og tager den kinetiske energi væk. Den samlede kinetiske energi $E_{k} = \frac{1}{2} m v_{0}^{2} = 10.5 J$ bruges på at overvinde friktionen over længden $l$:
$$
F_{fr} l = E_{k} \Rightarrow l = \frac{E_{k}}{F_{fr}}= \frac{10.5 \space J}{5.0 \space J} = 2.10 \space m
$$
