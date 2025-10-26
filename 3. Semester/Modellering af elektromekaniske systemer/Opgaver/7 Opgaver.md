![[Pasted image 20251026135629.png]]
![[Pasted image 20251026135637.png]]
1. Opstil differentialligninger, der beskriver dynamikken for systemet.
Ligesom ved en translatorisk bevægelse for en kasse der rykkes hen ad jorden.
$$
f_{d} = -b_{m} v
$$
$$
J_{m} \ddot{\theta}_{m} = - b_{m} \dot{\theta}_{m}
$$
Hvor $b_{m}$ er friktionskraften.
På samme side:
$$
J_{m} \ddot{\theta}_{m} + b_{m} \dot{\theta}_{m}
$$
Denne er så koblet med fjederen med stivhed $k_{s}$, som roterer med både motorsidens $\theta_{m}$ og linkets side $\theta_{l}$. Siden det er motoren der roterer så er det motorens side minus linkets side
$$k(\theta_{m} - \theta_{l})$$
Koblet bliver det:
$$
J_{m} \ddot{\theta}_{m} + b_{m} \dot{\theta}_{m} + k_{s}(\theta_{m} - \theta_{l}) = \tau_{m}(t)
$$
Linkets momentbalance er når der ingen friktion er på linkets side (kun på fjederen):
$$
J_{l} \ddot{\theta}_{l} = k_{s}(\theta_{m} - \theta_{l})
$$
$$
J_{l} \ddot{\theta}_{l} - k_{s}(\theta_{m} - \theta_{l}) = 0
$$
Hvilket også kan skrives som:
$$
J_{l} \ddot{\theta}_{l} + k_{s}(\theta_{l} - \theta_{m}) = 0
$$
2. Omskriv differentialligningerne til et system af 1. ordens differentialligninger.






3. Simuler systemet med to forskellige input (og parametrene fra Tabel 1)
(a) $\tau_{m}(t) = 1$

(b) $\tau_{m}(t) = \sin(t)$