- An op-amp amplifies the difference between two input voltages with a _VERY_ high gain factor.
    
- We can use this property as a basic component in circuits with many different purposes by:
    
    a) Sending part of $U_{\text{out}}$ back to $U_{\text{in}-}$. This is called negative feedback and is used to create analog circuits.
    
    b) Sending part of $U_{\text{out}}$ back to $U_{\text{in}+}$. This is called positive feedback and is used for digital/binary circuits.
    
    c) Sending nothing back. This setup can be used to check if $U_{\text{in}-}$ is greater than  $U_{\text{in}+}$.
    

When using negative feedback, a voltage divider (two resistors) determines the fraction of $U_{\text{out}}$ that is sent back to $U_{\text{in}-}$, as shown in Figure 13.4. By feeding a fraction back as negative feedback, the overall gain of the circuit is reduced, and we can achieve the desired amplification by selecting appropriate resistors.

Connecting a signal to the positive input results in a non-inverting amplifier, while connecting a signal to the negative input (backwards through the voltage divider) results in an inverting amplifier.

Forstærkere / udgangstrin

"Loads" i robotter -> elektromotorer/motorer ->elektromagnetisme

Selvinduktion.
$$L\approx 1,5 \frac{nH}{m}$$
Man bruger kun induktorer, når der ikke er en anden vej, fordi det er billigere bare at lave en induktor med en kapacitor med følgende kredsløb:

Fourier rækker:
Enhver periodisk funktion af tiden: f(t) kan ses som en sum af sinusformede funktioner.  
I diverse formelsamlinger (og internettet) kan man finde tabeller over populære periodiske funktioner med angivelse af hvilke sinusoider de svarer til. Disse "opskrifter" kaldes Fourier rækker.  
  
Firkantfunktionen, der går mellem -1 og +1 med frekvens: f har fx følgende Fourierrække:  
$$\frac {4}{pi}\cdot \frac{(sin(1\cdot w\cdot t)}{1} + \frac {sin(3\cdot w\cdot t)}{3} + \frac {sin(5\cdot w\cdot t)}{5} + \frac {sin(7\cdot w\cdot t)}{7} .....)$$
hvor $w=2\cdot pi\cdot f$
![[Pasted image 20241106091716.png]]
Switched mode strømforsyning (Google det)



Op-amp

Feedback