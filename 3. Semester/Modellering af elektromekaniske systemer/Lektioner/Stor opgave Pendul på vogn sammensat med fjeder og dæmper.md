
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

---

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

---

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

---

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

---

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

---

## Samlede bevægelsesligninger

$$
\boxed{
\begin{aligned}
(m_c + m_p)\ddot{x}_c + m_p l \cos\theta\,\ddot{\theta} - m_p l \sin\theta\,\dot{\theta}^2 + kx_c + b\dot{x}_c &= F(t) \quad &(1) \\
m_p l^2 \ddot{\theta} + m_p l \cos\theta\,\ddot{x}_c + m_p g l \sin\theta &= 0 \quad &(2)
\end{aligned}
}
$$

---

# 4 Analyse af konservativitet

Et system er **konservativt**, hvis summen af potentiel og kinetisk energi er konstant over tid — dvs. der ingen energitab forekommer.

I dette system indgår:
- Fjederen (konservativ)  
- Tyngdekraften (konservativ)  
- Dæmperen $b$ (ikke-konservativ)  
- Den eksterne kraft $F(t)$ (ikke-konservativ)

Systemet er derfor **ikke konservativt**, da $b$ dissipaterer energi som varme, og $F(t)$ kan tilføre energi. Konsekvensen af dette for systemet er at 

---

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

---

# (Valgfrit) Linearisering for små vinkler

For små $\theta$ ($\sin\theta \approx \theta$, $\cos\theta \approx 1$):

$$
\begin{cases}
(m_c + m_p)\ddot{x}_c + m_p l \ddot{\theta} + kx_c + b\dot{x}_c = F(t) \\
m_p l^2 \ddot{\theta} + m_p l \ddot{x}_c + m_p g l \theta = 0
\end{cases}
$$
