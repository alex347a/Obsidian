[[Phasors]] are a complex representation of sinusoidal functions, used extensively in AC circuit analysis to simplify calculations involving sinusoidal voltages and currents.

## 1. Definition of Phasor
A phasor is a complex number that represents the magnitude and phase of a sinusoidal function, such as:
$$ V(t) = V_m \cos(\omega t + \phi) $$
where $V_m$ is the peak [[Voltage]], $\omega$ is the angular frequency, and $\phi$ is the phase angle. In phasor form, this is represented as a complex number in polar form:
$$ V = V_m \angle \phi $$

## 2. Phasor Notation
[[Phasors]] convert sinusoidal functions into a single complex expression:
$$ V = V_m e^{j\phi} $$
The phasor notation simplifies sinusoidal voltages and currents, making it easier to perform operations such as addition, subtraction, multiplication, and division.

## 3. Advantages of Using [[Phasors]]
- **Simplifies Calculations**: Allows complex sinusoidal equations to be represented as simpler algebraic forms.
- **Linear Analysis**: Phasors make it easy to apply [[Ohm's law]], Kirchhoff’s laws, and impedance analysis to AC circuits.
- **Ease with AC Analysis**: Phasors provide an efficient way to analyze circuits with AC sources and determine relationships between voltages and currents.

## 4. Conversion Between Time Domain and Phasor Domain
- **Time to Phasor**: A sinusoidal function in time, $V(t) = V_m \cos(\omega t + \phi)$, can be converted to a phasor by expressing it in terms of its magnitude and phase:
  $$ V = V_m \angle \phi $$
- **Phasor to Time**: To convert back, use the real part of the complex exponential:
  $$ V(t) = \operatorname{Re} \{ V_m e^{j(\omega t + \phi)} \} $$

## 5. Phasors in Circuit Analysis
- **Impedance and Admittance**: Phasors enable the use of complex impedance ($Z = R + jX$) and admittance ($Y = G + jB$) in AC circuits, making it easier to analyze the frequency response of resistors, capacitors, and inductors.
- **[[Voltage]] and Current Relationships**: Using [[Phasors]], we apply Ohm’s law in AC as $V = IZ$, where $V$ and $I$ are [[Phasors]], and $Z$ is the complex impedance.

## 6. Example of Phasor Calculation in AC Circuits
For a circuit with a [[Resistor]] $R$ and [[Inductor]] $L$ in series, with an applied AC source $V_s(t) = V_m \cos(\omega t)$:
- Phasor form of the source: $V_s = V_m \angle 0$
- Impedance of the [[Resistor]]: $Z_R = R$
- Impedance of the [[Inductor]]: $Z_L = j\omega L$
- Total impedance: $Z = R + j\omega L$

Using [[Ohm's law]] in phasor form:
$$ I = \frac{V_s}{Z} = \frac{V_m}{R + j\omega L} $$

## 7. Phasor Diagrams
Phasor diagrams visually represent the relative magnitudes and phase angles of voltages and currents. Typically, they use arrows in a 2D plane where the angle corresponds to the phase angle, and the length represents the magnitude.
![[Phasor diagram.png]]