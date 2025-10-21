
| Navn               | Symbol             | Værdi | Enhed     |
| ------------------ | ------------------ | ----- | --------- |
| Ekstern kraft      | F                  | -     | N         |
| Position for vogn  | ($x_{c}$; $y_{c}$) | -     | m         |
| Vinkel for pendul  | θ                  | -     | rad       |
| Stivhed            | k                  | 0,2   | N/m       |
| Dæmpning           | b                  | 0,1   | N/(m/s)   |
| Masse af vogn      | $m_{c}$            | 1     | kg        |
| Masse af pendul    | $m_{p}$            | 0,5   | kg        |
| Længde af pendul   | l                  | 0,3   | m         |
| Tyngdeacceleration | g                  | 9,82  | $m/s^{2}$ |
# 2 Fritlegeme analyse

Jeg betragter systemet bestående af en vogn med masse $m_c$ og et pendul med masse $m_p$ og længde $l$.  
Pendulet er fastgjort i et hængsel på vognen, og vinklen $\theta$ måles **fra lodret**, positiv **med uret**.

## Kræfter på vognen

På vognen virker:
- Den eksterne kraft $F(t)$ mod højre  
- Fjederkraft $-k x_c$ mod venstre  
- Dæmpningskraft $-b \dot{x}_c$ mod venstre  
- Den vandrette komponent af stangkraften $T \sin\theta$ mod venstre (fra pendulet)

**Fritlegemeligning for vognen:**

$$
m_c \ddot{x}_c = F(t) - b\dot{x}_c - kx_c - T \sin\theta
$$

## Kræfter på pendulet

På pendulets massepunkt virker:
- Tyngdekraft $m_p g$ nedad  
- Tensionskraft $T$ langs stangen (mod pivotpunktet)

Pendulets position i globale koordinater er:

$$
x_p = x_c + l \sin\theta, \quad y_p = -l \cos\theta
$$

Accelerationer:

$$
\ddot{x}_p = \ddot{x}_c + l\ddot{\theta}\cos\theta - l\dot{\theta}^2\sin\theta
$$

$$
\ddot{y}_p = l\ddot{\theta}\sin\theta + l\dot{\theta}^2\cos\theta
$$
## Bevægelsesligninger for pendulet

Newton’s 2. lov i x- og y-retningen giver:

$$
\begin{cases}
m_p \ddot{x}_p = -T \sin\theta \\
m_p \ddot{y}_p = T \cos\theta - m_p g
\end{cases}
$$

eller indsat for $\ddot{x}_p$ og $\ddot{y}_p$:

$$
\begin{cases}
m_p(\ddot{x}_c + l\ddot{\theta}\cos\theta - l\dot{\theta}^2\sin\theta) = -T \sin\theta \\
m_p(l\ddot{\theta}\sin\theta + l\dot{\theta}^2\cos\theta) = T \cos\theta - m_p g
\end{cases}
$$
# 3 Bevægelsesligninger for systemet

Jeg ønsker at eliminere $T$ for at få to koblede 2. ordens differentialligninger.

Fra vognens ligning:

$$
m_c \ddot{x}_c = F(t) - b\dot{x}_c - kx_c - T \sin\theta
$$

Fra pendulets x-ligning:

$$
m_p \ddot{x}_c + m_p l\ddot{\theta}\cos\theta - m_p l \dot{\theta}^2\sin\theta = -T \sin\theta
$$

Jeg lægger de to sammen for at eliminere $T \sin\theta$:

$$
(m_c + m_p)\ddot{x}_c + m_p l \cos\theta\,\ddot{\theta} - m_p l \sin\theta\,\dot{\theta}^2 + kx_c + b\dot{x}_c = F(t)
$$

Dette er **bevægelsesligning (1)**.


Fra pendulets y-ligning:

$$
m_p(l\ddot{\theta}\sin\theta + l\dot{\theta}^2\cos\theta) = T \cos\theta - m_p g
$$

Omskriv for $T$:

$$
T = \frac{m_p(l\ddot{\theta}\sin\theta + l\dot{\theta}^2\cos\theta + g)}{\cos\theta}
$$

Indsæt dette i x-ligningen for pendulet, eller betragt momenten omkring pivotpunktet:

Moment omkring pivotet (positiv mod uret):

$$
m_p g l \sin\theta = m_p l^2 \ddot{\theta} + m_p l \cos\theta\,\ddot{x}_c
$$

eller

$$
m_p l^2 \ddot{\theta} + m_p l \cos\theta\,\ddot{x}_c + m_p g l \sin\theta = 0
$$

Dette er **bevægelsesligning (2)**.

## Samlede bevægelsesligninger

$$
\boxed{
\begin{aligned}
(m_c + m_p)\ddot{x}_c + m_p l \cos\theta\,\ddot{\theta} - m_p l \sin\theta\,\dot{\theta}^2 + kx_c + b\dot{x}_c &= F(t) \quad &(1) \\
m_p l^2 \ddot{\theta} + m_p l \cos\theta\,\ddot{x}_c + m_p g l \sin\theta &= 0 \quad &(2)
\end{aligned}
}
$$
Jeg isolerer for $\ddot{x}_c$:
$$
(m_c + m_p)\ddot{x}_c = F(t) - b\dot{x}_c - kx_c + m_p l \sin\theta\,\dot{\theta}^2 - m_p l \cos\theta\,\ddot{\theta}
$$
Divider med $(m_c + m_p)$:
$$
\boxed{
\ddot{x}_c = \frac{F(t) - b\dot{x}_c - kx_c + m_p l \sin\theta\,\dot{\theta}^2 - m_p l \cos\theta\,\ddot{\theta}}{m_c + m_p}
}
$$
Indsætter $\ddot{x}_c$ i (2) for at isolere $\ddot{\theta}$:
$$
m_p l^2 \ddot{\theta} + m_p l \cos\theta\,\ddot{x}_c + m_p g l \sin\theta = 0
$$
Erstat $\ddot{x}_c$ fra udtrykket ovenfor:
$$
m_p l^2 \ddot{\theta}
+ m_p l \cos\theta
\left(
\frac{F(t) - b\dot{x}_c - kx_c + m_p l \sin\theta\,\dot{\theta}^2 - m_p l \cos\theta\,\ddot{\theta}}{m_c + m_p}
\right)
+ m_p g l \sin\theta = 0
$$
Udvid og saml led med $\ddot{\theta}$:
$$
\left(
m_p l^2 - \frac{m_p^2 l^2 \cos^2\theta}{m_c + m_p}
\right)\ddot{\theta}
=
-\frac{m_p l \cos\theta}{m_c + m_p}\left(F(t) - b\dot{x}_c - kx_c + m_p l \sin\theta\,\dot{\theta}^2\right)
- m_p g l \sin\theta
$$
Divider til sidst for at isolere $\ddot{\theta}$:
$$
\boxed{
\ddot{\theta}
=
\frac{
-\frac{m_p l \cos\theta}{m_c + m_p}\left(F(t) - b\dot{x}_c - kx_c + m_p l \sin\theta\,\dot{\theta}^2\right)
- m_p g l \sin\theta
}{
m_p l^2\left(1 - \frac{m_p \cos^2\theta}{m_c + m_p}\right)
}
}
$$
Dermed får jeg altså:
$$
\boxed{
\begin{aligned}
\ddot{x}_c &= \frac{F(t) - b\dot{x}_c - kx_c + m_p l \sin\theta\,\dot{\theta}^2 - m_p l \cos\theta\,\ddot{\theta}}{m_c + m_p}, \\[6pt]
\ddot{\theta}
&=
\frac{
-\frac{m_p l \cos\theta}{m_c + m_p}\left(F(t) - b\dot{x}_c - kx_c + m_p l \sin\theta\,\dot{\theta}^2\right)
- m_p g l \sin\theta
}{
m_p l^2\left(1 - \frac{m_p \cos^2\theta}{m_c + m_p}\right)
}.
\end{aligned}
}
$$
# 4 Analyse af konservativitet

Et system er **konservativt**, hvis summen af potentiel og kinetisk energi er konstant over tid — dvs. der ingen energitab forekommer.

I dette system indgår:
- Fjederen (konservativ)  
- Tyngdekraften (konservativ)  
- Dæmperen $b$ (ikke-konservativ)  
- Den eksterne kraft $F(t)$ (ikke-konservativ)

Systemet er derfor **ikke konservativt**, da $b$ dissiperer energi som varme, og $F(t)$ kan tilføre energi. Konsekvensen af dette for systemet er at systemet mister mekanisk energi, hvilket betyder det eventuelt vil ende med at stå stille.
# 5 Potentiel og kinetisk energi

Den potentielle og kinetiske energi for systemet er:

$$
E_{\text{pot}} = \tfrac{1}{2} k x_c^2 + m_p g l(1 - \cos\theta)
$$

$$
E_{\text{kin}} = \tfrac{1}{2} m_c \dot{x}_c^2 + \tfrac{1}{2} m_p(\dot{x}_p^2 + \dot{y}_p^2)
$$

Efter indsættelse af $\dot{x}_p$ og $\dot{y}_p$:

$$
E_{\text{kin}} = \tfrac{1}{2}(m_c + m_p)\dot{x}_c^2 + m_p l \cos\theta\,\dot{x}_c \dot{\theta} + \tfrac{1}{2}m_p l^2 \dot{\theta}^2
$$

Summen $E_{\text{tot}} = E_{\text{pot}} + E_{\text{kin}}$ er konstant, hvis $b=0$ og $F(t)=0$.

# 5 Potentiel og kinetisk energi
Den totale mekaniske energi er givet ved:
$$
E_{\text{tot}} = E_{\text{kin}} + E_{\text{pot}}
$$
#### Kinetisk energi
Pivotpunktet sidder på vognen, og vinklen $\theta$ måles fra lodret, positiv med uret.  
Pendulets massepunkt har derfor koordinaterne:

$$
x_p = x_c + l\sin\theta, \qquad y_p = -\,l\cos\theta
$$

Når $\theta = 0$, hænger pendulet lodret nedad og har $y_p = -l$.

Hastigheder:

Differentierer positionerne mht. tid:

$$
\dot{x}_p = \dot{x}_c + l\cos\theta\,\dot{\theta}, \qquad 
\dot{y}_p = l\sin\theta\,\dot{\theta}.
$$
Hastighedens kvadrat:

Den totale hastighed for pendul-massen er:

$$
v_p^2 = \dot{x}_p^2 + \dot{y}_p^2
$$

Indsætter udtrykkene fra ovenfor:

$$
\begin{aligned}
v_p^2 
&= (\dot{x}_c + l\cos\theta\,\dot{\theta})^2 + (l\sin\theta\,\dot{\theta})^2 \\
&= \dot{x}_c^2 + 2l\cos\theta\,\dot{x}_c\,\dot{\theta} + l^2\underbrace{(\cos^2\theta + \sin^2\theta)}_{\cos^2\theta + \sin^2\theta = 1}\dot{\theta}^2 \\
&= \dot{x}_c^2 + 2l\cos\theta\,\dot{x}_c\,\dot{\theta} + l^2\dot{\theta}^2.
\end{aligned}
$$
Kinetisk energi:

Den kinetiske energi for systemet består af vognen og pendul-massen.

- For vognen: $\tfrac12 m_c \dot{x}_c^2$  
- For pendul-massen: $\tfrac12 m_p v_p^2$

Summen bliver:

$$
\begin{aligned}
E_{\text{kin}} 
&= \tfrac12 m_c \dot{x}_c^2 + \tfrac12 m_p(\dot{x}_c^2 + 2l\cos\theta\,\dot{x}_c\,\dot{\theta} + l^2\dot{\theta}^2) \\
&= \tfrac12 (m_c + m_p)\dot{x}_c^2 + m_p l\cos\theta\,\dot{x}_c\,\dot{\theta} + \tfrac12 m_p l^2 \dot{\theta}^2
\end{aligned}
$$

Fortolkning af leddene:
- $\tfrac12 (m_c + m_p)\dot{x}_c^2$: translationel energi for hele systemet.  
- $m_p l\cos\theta\,\dot{x}_c\,\dot{\theta}$: koblingsled mellem vognens bevægelse og pendulets rotation.  
- $\tfrac12 m_p l^2 \dot{\theta}^2$: rotationsenergi af pendulet om pivotet.
#### Potentiel energi:
Systemet har to former for potentiel energi:
1. **Fjederenergi:**
$$
E_{\text{fjeder}} = \tfrac12 k x_c^2
$$
2. **Gravitationsenergi for pendul-massen:**
Pendulets højde er $y_p = -l\cos\theta$.  
Ved $\theta=0$ er højden $y_p=-l$.  
Vi vælger denne til reference ($E_{\text{pot}}=0$ ved $\theta=0$).

Ændringen i potentiel energi bliver derfor:
$$
E_{\text{grav}} = m_p g (y_p - y_{|\theta=0}) = m_p g(-l\cos\theta + l) = m_p g l (1 - \cos\theta)
$$
Samlet potentiel energi:
$$
E_{\text{pot}} = \tfrac12 k x_c^2 + m_p g l (1 - \cos\theta)
$$
Dvs. de to er givet ved:
$$
\begin{aligned}
E_{\text{kin}} &= \tfrac12 (m_c + m_p)\dot{x}_c^2 + m_p l\cos\theta\,\dot{x}_c\,\dot{\theta} + \tfrac12 m_p l^2 \dot{\theta}^2, \\
E_{\text{pot}} &= \tfrac12 k x_c^2 + m_p g l (1 - \cos\theta).
\end{aligned}
$$
Dermed er den mekaniske energi givet ved:
$$
E_{mek} = \tfrac12 (m_c + m_p)\dot{x}_c^2 + m_p l\cos\theta\,\dot{x}_c\,\dot{\theta} + \tfrac12 m_p l^2 \dot{\theta}^2 +
\tfrac12 k x_c^2 + m_p g l (1 - \cos\theta)
$$
