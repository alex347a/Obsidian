Stores [[Energy]] in a magnetic field when current flows through it

## Inductance
Opposes changes in current. [[Voltage]] across an [[Inductor]] is:
$$V_{L}=L\cdot \frac{dI}{dt}$$
The unit is Henries (H). Acts as a short circuit to DC current in steady state.

The inductance is calculated in a coil with a wire around it by:
$$
L=\frac{\mu N^{2} A}{l}
$$
Where $\mu$ is the permeability of the material (in Henry pr. Meter)
N is the number of Windings
A is the cross-sectional area of the coil (in square Meters)
l is the length of the coil in Meters.

## [[Energy]] stored in an [[Inductor]]
$$W=\frac{1}{2}LI^2$$
Where W is [[Energy]] in joules, L is inductance and I is current.

## Inductors in circuits
#### Inductors in series
Total inductance: $L{eq}=L_1+L_2+\ldots$ (similar to resistors)
#### Inductors in parallel
$\frac{1}{L_{eq}}=\frac{1}{L_1}+\frac{1}{L_2}+\ldots$

## Initial conditions for [[Inductor]]
Current through an [[Inductor]] just before and after a switch operation remains continuous.

## [[transient behaviour]] ([[Inductor]])
**Inductors** cause current to change gradually and oppose sudden changes in current. This is while capacitors cause [[Voltage]] to change gradually and oppose sudden changes in [[Voltage]].

- **Inductors** resist changes in current because they store [[Energy]] in a magnetic field. When the current through an [[Inductor]] is suddenly changed (for example, when a switch is closed or opened), the [[Inductor]] generates a [[Voltage]] to oppose the change in current.
- The transient behaviour is characterized by an exponential rise or decay of current, depending on the circuit configuration. For an [[RL circuit]] ([[Resistor]]-[[Inductor]]), the current through the [[Inductor]] follows:
$$I(t)=I_{0}\left(1-e^{-\frac{R}{L}\cdot t}\right)$$
where:
- $I_{0}$ is the initial current.
- $R$ is the resistance,
- $L$ is the inductance,
- $t$ is the time.

The [[Voltage]] across the [[Inductor]] during this transition is given by:
$$V_{L}(t)=L\frac{dI}{dt}$$
## 74 HCT 04 Logic gate
Inverts input; if input is true, output is false, and vice versa.