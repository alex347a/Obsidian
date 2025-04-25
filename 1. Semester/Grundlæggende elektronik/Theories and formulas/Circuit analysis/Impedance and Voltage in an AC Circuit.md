### **Impedance Overview**
Impedance ($Z$) is a measure of the opposition to the flow of alternating current (AC) in a circuit. It is a combination of **resistance** ($R$) and **reactance** ($X$), where reactance is caused by capacitors and inductors. This means impedance accounts for the effects of capacitors and inductors in AC circuits.

- Impedance is a **complex quantity**:
$$
Z = R + jX
$$
Where:
- $R$ is the **resistance** (real part).
- $X$ is the **reactance** (imaginary part).
- $j$ is the imaginary unit ($j^2 = -1$).

The **total impedance** can be calculated by combining the effects of the resistor and the capacitor (in a series configuration, for example).

#### **Impedance in a series RC circuit example**
In a series circuit with a **resistor** ($R$) and a **capacitor** ($C$), the total impedance is:
$$
Z = R + jX_C
$$
Where $X_C$ is the capacitive reactance:
$$
X_C = \frac{1}{2 \pi f C}
$$
(The reason for the fraction is because when a capacitor is in series it uses the formula for parallel resistors and inductors)
Where:
- $f$ is the frequency of the AC signal.
- $C$ is the capacitance of the capacitor. Which is given by:
$$ C = \varepsilon \cdot \frac{A}{d} $$
where:
- $C$ is the capacitance in farads (F),
- $\varepsilon$ is the permittivity of the dielectric material, which is the product of the dielectric constant ($\kappa$) and the permittivity of free space ($\varepsilon_0$),
- $A$ is the area of one of the plates in square meters (m²),
- $d$ is the distance between the plates in meters (m).

#### **Calculation of Current and Voltage**

- **Given values**:
  - Resistor: $R = 10 \, \Omega$
  - Capacitor: $C = 100 \, \mu\text{F}$
  - Frequency: $f = 50 \, \text{Hz}$
  - AC voltage source: $V_{\text{source}} = 10 \, \text{V}$

- **Calculate Capacitive Reactance ($X_C$)**:
$$
X_C = \frac{1}{2 \pi (50)(100 \times 10^{-6})} \approx 31.83 \, \Omega
$$

- **Total Impedance ($Z$)**:
$$
Z = 10 - j31.83 \, \Omega
$$

- **Magnitude of Impedance ($|Z|$)**:
$$
|Z| = \sqrt{10^2 + (-31.83)^2} \approx 33.37 \, \Omega
$$

- **Phase Angle ($\phi$)**:
$$
\phi = \arctan\left(\frac{-31.83}{10}\right) \approx -72.9^\circ
$$

#### **Current in the Circuit**

Using Ohm's Law for AC circuits:
$$
I = \frac{V_{\text{source}}}{Z}
$$
Substitute the values:
$$
|I| = \frac{10}{33.37} \approx 0.299 \, \text{A}
$$
So, the magnitude of the current is approximately $0.299 \, \text{A}$.

#### **Voltage Across Resistor and Capacitor**

- Voltage across the resistor ($V_R$):
$$
V_R = I \cdot R = 0.299 \cdot 10 = 2.99 \, \text{V}
$$

- Voltage across the capacitor ($V_C$):
$$
V_C = I \cdot |X_C| = 0.299 \cdot 31.83 \approx 9.51 \, \text{V}
$$

#### **Total Voltage in the Circuit**

Since the voltages across the resistor and capacitor are **90° out of phase**, the total voltage ($V_{\text{total}}$) is the vector sum:
$$
V_{\text{total}} = \sqrt{V_R^2 + V_C^2}
$$
Substitute the values:
$$
V_{\text{total}} = \sqrt{(2.99)^2 + (9.51)^2} \approx 9.96 \, \text{V}
$$
This is very close to the applied voltage of $10 \, \text{V}$.

#### **Phase Shift and Voltage-Current Relationship**

The phase angle $\phi \approx -72.9^\circ$ means that the **current lags the voltage** by **72.9°** in this capacitive circuit. The lag is due to the capacitive reactance, which causes the voltage and current to not peak at the same time.

#### **Impedance in a series RL circuit example**
In an RL circuit, the total impedance is the sum of the **resistor** ($R$) and the **inductive reactance** ($X_L$):
$$
Z = R + jX_L
$$
Where:
- $R$ is the resistance (real part).
- $X_L$ is the inductive reactance (imaginary part).

The **inductive reactance** $X_L$ is given by:
$$
X_L = 2 \pi f L
$$
Where:
- $f$ is the frequency of the AC source.
- $L$ is the inductance of the inductor. Which is calculated by:
It depends on the shape of the inductor, but if its a coil around a wire it is given by:
$$
L=\frac{\mu N^{2} A}{l}
$$
Where $\mu$ is the permeability of the material (in Henry pr. Meter)
N is the number of Windings
A is the cross-sectional area of the coil (in square Meters)
l is the length of the coil in Meters.

The **magnitude** of the impedance $|Z|$ is:
$$
|Z| = \sqrt{R^2 + X_L^2}
$$

And the **phase angle** $\phi$ between the voltage and current is:
$$
\phi = \arctan\left(\frac{X_L}{R}\right)
$$

#### **Example Calculation for an RL Circuit**

- **Given values**:
  - Resistor: $R = 10 \, \Omega$
  - Inductor: $L = 100 \, \text{mH} = 0.1 \, \text{H}$
  - Frequency: $f = 50 \, \text{Hz}$
  - Voltage source: $V_{\text{source}} = 10 \, \text{V}$

#### **Calculate the Inductive Reactance ($X_L$)**
$$
X_L = 2 \pi (50) (0.1) = 31.42 \, \Omega
$$

#### **Total Impedance ($Z$)**
$$
Z = 10 + j31.42 \, \Omega
$$

#### **Magnitude of Impedance ($|Z|$)**
$$
|Z| = \sqrt{10^2 + 31.42^2} \approx 32.87 \, \Omega
$$

#### **Phase Angle ($\phi$)**
$$
\phi = \arctan\left(\frac{31.42}{10}\right) \approx 72.3^\circ
$$

#### **Current in the RL Circuit**

Using Ohm’s Law for AC circuits:
$$
I = \frac{V_{\text{source}}}{Z}
$$
Substitute the values:
$$
|I| = \frac{10}{32.87} \approx 0.304 \, \text{A}
$$
Thus, the magnitude of the current is approximately $0.304 \, \text{A}$.

#### **Voltage Across the Resistor and Inductor**

- Voltage across the resistor ($V_R$):
$$
V_R = I \cdot R = 0.304 \cdot 10 = 3.04 \, \text{V}
$$

- Voltage across the inductor ($V_L$):
$$
V_L = I \cdot X_L = 0.304 \cdot 31.42 \approx 9.56 \, \text{V}
$$

#### **Total Voltage in the Circuit**

Since the voltages across the resistor and inductor are **90° out of phase**, the total voltage ($V_{\text{total}}$) is the vector sum:
$$
V_{\text{total}} = \sqrt{V_R^2 + V_L^2}
$$
Substitute the values:
$$
V_{\text{total}} = \sqrt{(3.04)^2 + (9.56)^2} \approx 10 \, \text{V}
$$
The total voltage across the series RL circuit is approximately equal to the applied voltage ($10 \, \text{V}$).

#### **Phase Shift and Voltage-Current Relationship**

The phase angle $\phi \approx 72.3^\circ$ means that the **current lags the voltage** by **72.3°** in this inductive circuit. The lag is due to the inductive reactance, which causes the voltage and current to not peak at the same time.
