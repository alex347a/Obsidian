Fourierrækken for en given funktion $f(x)$ er generelt givet ved formlen
$$
f(x) = \frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{2 \pi n x}{p}\right)+ b_{n} \sin\left(\frac{2 \pi n x}{p}\right)\right]
$$
Identificer perioden p og HUSK at $p = 2L$
Dernæst skal jeg beregne $a_{0}, a_{n} \text{ og } b_{n}$:
$$
\begin{align*}
a_{0} &=  \frac{1}{L} \int_{-L}^{L} f(x) \, dx\\
a_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx\\
b_{n} &=  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx
\end{align*}
$$
Hvor $2L = p$
Jeg starter med at beregne $a_{0}$:

Nu beregner jeg $a_{n}$: 
$$
a_{n} =  \frac{1}{L} \int_{-L}^{L} f(x) \cos\left(\frac{n \pi x}{L}\right) \, dx
$$

Nu skal jeg trække den nedre grænse fra den øvre grænse:


Nu skal jeg regne hvordan funktionen ser ud for lige og ulige n-værdier:

Derfor bliver $a_{n}$:
$$
a_{n} = \cases{0, \quad \quad \quad \space \text{ hvis n er lige} \\
- \frac{4}{n^{2} \pi^{2}}, \quad \text{ hvis n er ulige}}
$$
Nu beregner jeg $b_{n}$:
$$
b_{n} =  \frac{1}{L} \int_{-L}^{L} f(x) \sin\left(\frac{n \pi x}{L}\right) \, dx\\
$$
Indsætter i formlen for $b_{n}$

Nu skal jeg trække den nedre grænse fra den øvre grænse:

Nu skal jeg regne hvordan funktionen ser ud for lige og ulige n-værdier:

Derfor bliver $b_{n}$:
$$
b_{n} = \cases{-\frac{2}{n \pi}, \quad  \text{ hvis n er lige} \\
0, \quad \quad \space \space  \text{ hvis n er ulige}}
$$
Nu hvor jeg har beregnet $a_{0}, a_{n}$ og $b_{n}$ kan jeg indsætte det i formlen for fourierrækken:
$$
\frac{a_{0}}{2} + \sum_{n=1}^{\infty} \left[a_{n} \cos\left(\frac{ \pi n x}{2}\right)+ b_{n} \sin\left(\frac{\pi n x}{2}\right)\right] 
$$