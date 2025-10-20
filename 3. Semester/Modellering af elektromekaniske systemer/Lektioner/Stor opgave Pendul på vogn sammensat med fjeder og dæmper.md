# 2 Fritlegeme analyse

Vi betragter systemet bestående af en vogn med masse $m_c$ og et pendul med masse $m_p$ og længde $l$, som er fastgjort til vognen.  
Vognen påvirkes af:

- En ydre kraft $F(t)$  
- En fjeder med stivhed $k$  
- En dæmper med konstant $b$  
- Pendulets vandrette kraftkomponent  
- Tyngdekraft via pendulet  

Pendulet påvirkes af:

- Tyngdekraften $m_p g$  
- En reaktionskraft i pivotpunktet (fra vognen)  
- Dens egen inerti  

---

### Fritlegemediagrammer

**For vognen (masse $m_c$):**

Vandret akse (positiv mod højre):

$F(t) - b\dot{x}_c - k x_c - H = m_c \ddot{x}_c$

hvor $H$ er den vandrette reaktionskraft fra pendulet på vognen.

---

**For pendulet (masse $m_p$):**

Krafter på massen i enden af pendulet:

- Tyngde: $m_p g$  
- Reaktionskræfter fra stangen i pivotpunktet: $H$ (vandret) og $V$ (lodret)  

Vi skriver bevægelsesligninger for pendulets massepunkt:

$$
\begin{cases}
m_p(\ddot{x}_c + l\ddot{\theta}\cos\theta - l\dot{\theta}^2\sin\theta) = H \\
m_p(l\ddot{\theta}\sin\theta + l\dot{\theta}^2\cos\theta) = V - m_p g
\end{cases}
$$

---

# 3 Bevægelsesligninger for systemet

Vi eliminerer de ukendte reaktionskræfter $H$ og $V$ ved at kombinere vognens og pendulets ligninger.

Fra vognens ligning:

$m_c \ddot{x}_c = F(t) - b\dot{x}_c - kx_c - H$

Fra pendulets vandrette ligning:

$H = m_p(\ddot{x}_c + l\ddot{\theta}\cos\theta - l\dot{\theta}^2\sin\theta)$

Indsæt dette $H$ i vognens ligning:

$(m_c + m_p)\ddot{x}_c + m_p l \cos\theta\,\ddot{\theta} - m_p l \sin\theta\,\dot{\theta}^2 + kx_c + b\dot{x}_c = F(t)$

Dette er **bevægelsesligning (1)**.

---

For pendulets rotation om pivotpunktet bruges $\sum M = I\alpha$:

Træk moment omkring pivot (positiv mod uret):

$m_p g l \sin\theta = m_p l^2 \ddot{\theta} + m_p l \cos\theta\,\ddot{x}_c$

eller omskrevet:

$m_p l^2 \ddot{\theta} + m_p l \cos\theta\,\ddot{x}_c + m_p g l \sin\theta = 0$

Dette er **bevægelsesligning (2)**.

---

**Opsummering:**

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

Et system er **konservativt**, hvis summen af potentiel og kinetisk energi er konstant over tid, dvs. ingen energi tabes gennem friktion, dæmpning eller ydre arbejde.

I dette system indgår:

- Fjeder (konservativ)  
- Tyngdekraft (konservativ)  
- Dæmper $b$ (ikke-konservativ)  
- Ekstern kraft $F(t)$ (ikke-konservativ)  

Systemet **er derfor ikke konservativt**, fordi dæmpningen $b\dot{x}_c$ dissipaterer energi og $F(t)$ kan tilføre energi.

---

# 5 Potentiel og kinetisk energi

Den potentielle og kinetiske energi findes som:

$E_{\text{kin}} = \tfrac{1}{2}(m_c+m_p)\dot{x}_c^2 + m_p l \cos\theta\,\dot{x}_c\,\dot{\theta} + \tfrac{1}{2}m_p l^2\dot{\theta}^2$

$E_{\text{pot}} = \tfrac{1}{2}k x_c^2 + m_p g l(1 - \cos\theta)$

Summen $E_{\text{tot}} = E_{\text{kin}} + E_{\text{pot}}$ er konstant, hvis $b=0$ og $F(t)=0$.

---

# (Valgfrit) Linearisering for små vinkler

For små $\theta$ ($\sin\theta \approx \theta$, $\cos\theta \approx 1$) reduceres systemet til:

$$
\begin{cases}
(m_c + m_p)\ddot{x}_c + m_p l \ddot{\theta} + kx_c + b\dot{x}_c = F(t) \\
m_p l^2 \ddot{\theta} + m_p l \ddot{x}_c + m_p g l \theta = 0
\end{cases}
$$
