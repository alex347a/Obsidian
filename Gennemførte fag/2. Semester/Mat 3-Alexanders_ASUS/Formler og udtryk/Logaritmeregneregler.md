# Logaritmeregneregler

#### 1. Definition af logaritme
$$
\log_b(x) = y \iff b^y = x
$$
#### 2. Naturlogaritme (ln)
$$
\ln(x) = \log_e(x)
$$
#### 3. Produktregel
$$
\log_b(xy) = \log_b(x) + \log_b(y)
$$
Eksempel: $\ln(2 \cdot 3) = \ln(2) + \ln(3)$
#### 4. Kvotientregel
$$
\log_b\left(\frac{x}{y}\right) = \log_b(x) - \log_b(y)
$$
Eksempel: $\ln\left(\frac{5}{2}\right) = \ln(5) - \ln(2)$
#### 5. Potensregel
$$
\log_b(x^a) = a \cdot \log_b(x)
$$
Eksempel: $\ln(x^3) = 3 \ln(x)$
#### 6. Rødder
$$
\log_b(\sqrt[n]{x}) = \frac{1}{n} \log_b(x)
$$
Eksempel: $\ln(\sqrt{x}) = \frac{1}{2} \ln(x)$
#### 7. Logaritme af 1
$$
\log_b(1) = 0
$$
Eksempel: $\ln(1) = 0$
#### 8. Logaritme af b (basen)
$$
\log_b(b) = 1
$$
Eksempel: $\log_2(2) = 1$
#### 9. Ændring af logaritmebase (basisskift)
$$
\log_b(x) = \frac{\log_k(x)}{\log_k(b)}
$$
Typisk bruges $k = 10$ eller $k = e$
#### 10. Eksponentialregler med logaritmer
Hvis $y = \ln(f(x))$, så er:
$$
\frac{d}{dx}[\ln(f(x))] = \frac{f'(x)}{f(x)}
$$
Eksempel: Hvis $f(x) = x^2 + 1$, så er:
$$
\frac{d}{dx}[\ln(x^2 + 1)] = \frac{2x}{x^2 + 1}
$$
