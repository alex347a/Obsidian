$$
\sideset{^{i-1}_{i}}{}{T} = 
\begin{bmatrix}
\cos(\theta_{i})  & - \sin(\theta_{i})  &  0  & a_{i-1} \\ 
\sin(\theta_{i}) \cos(\alpha_{i-1})  &  \cos(\theta_{i}) \cos(\alpha_{i-1})  &  - \sin(\alpha_{i-1})  &  -\sin(\alpha_{i-1}) d_{i} \\ 
\sin(\theta_{i}) \sin(\alpha_{i-1})  &  \cos(\theta_{i}) \sin(\alpha_{-1})  &  \cos(\alpha_{i-1})  &  \cos(\alpha_{i-1}) d_{i} \\ 
0  &  0  & 0  & 1
\end{bmatrix}
$$

Og så bare husk at:
$$
\begin{align*}
\cos(0) &= 1\\
\cos\left(\frac{\pi}{6}\right) &= \frac{\sqrt{3}}{2}\\
\cos\left(\frac{\pi}{4}\right) &= \frac{\sqrt{2}}{2}\\
\cos\left(\frac{\pi}{3}\right) &= \frac{1}{2}\\
\cos\left(\frac{\pi}{2}\right) &= 0\\
\cos(\pi) &= - 1\\
\cos\left(\frac{3 \pi}{2}\right) &= 0\\
\cos(2\pi) &= 1\\
\sin(0) &= 0\\
\sin\left(\frac{\pi}{6}\right) &= \frac{1}{2}\\
\sin\left(\frac{\pi}{4}\right) &= \frac{\sqrt{2}}{2}\\
\sin\left(\frac{\pi}{3}\right) &= \frac{\sqrt{3}}{2}\\
\sin\left(\frac{\pi}{2}\right) &= 1\\
\sin(\pi) &= 0\\
\sin\left(\frac{3\pi}{2}\right) &= -1\\
\sin(2\pi) &= 0
\end{align*}
$$

Hvis du skal bruge standard DH (highly doubt)
$$
T_{i} = 
\begin{bmatrix}
\cos(\theta_{i})  & - \sin(\theta_{i}) \cos(\alpha_{i-1})  &  \sin(\theta_{i}) \sin(\alpha_{i-1})  & a_{i-1} \cos(\theta_{i}) \\ 
\sin(\theta_{i})  &  \cos(\theta_{i}) \cos(\alpha_{i-1})  &  - \cos(\theta_{i})\sin(\alpha_{i-1})  &  \alpha_{i-1} \sin(\theta_{i}) \\ 
0  &  \sin(\alpha_{-1})  &  \cos(\alpha_{i-1})  &  d_{i} \\ 
0  &  0  & 0  & 1
\end{bmatrix}
$$
Og så ganger du bare $T_{i}$ med $T_{i+1}$ 