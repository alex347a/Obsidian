### Summary:
An [[RC circuit]] is a simple circuit that demonstrates transient behaviour due to the interaction between the [[Resistor]] and the [[Capacitor]]. It is used in various applications such as filtering, timing, and signal processing. The [[Voltage]] and current change over time in an exponential fashion, characterized by the time constant $\tau$.


An **[[RC circuit]]** is an electrical circuit consisting of a **[[Resistor]]** ($R$) and a **[[Capacitor]]** ($C$) connected in series or parallel. It is a type of linear electrical circuit that exhibits [[Capacitor#Transient behaviour (capacitor)|transient behaviour]] when a [[Voltage]] is applied or removed, typically involving the charging or discharging of the [[Capacitor]].

### Components of an [[RC circuit]]:
- **[[Resistor]]** ($R$): Resists the flow of electric current and dissipates [[Energy]] as heat.
- **[[Capacitor]]** ($C$): Stores [[Energy]] in an [[Electric field]] and resists changes in [[Voltage]] across its terminals.

### Basic Configurations of RC Circuits:
1. **Series [[RC circuit]]**:
   - The [[Resistor]] and [[Capacitor]] are connected in a single path, one after the other.
   - This is the most common [[RC circuit]], where the input [[Voltage]] is applied across the series combination of the [[Resistor]] and [[Capacitor]].
   
2. **Parallel [[RC circuit]]**:
   - The [[Resistor]] and [[Capacitor]] are connected in parallel across the same [[Voltage]] source.
   - This configuration can also exhibit unique transient behaviour, but is less common in simple applications.

### Behaviour of an [[RC circuit]]:
The behaviour of an [[RC circuit]] primarily involves the **charging** and **discharging** of the [[Capacitor]] through the [[Resistor]].

- **Charging**: When a [[Voltage]] is applied to a [[Capacitor]] through a [[Resistor]], the [[Capacitor]] gradually charges up, with the [[Voltage]] across the [[Capacitor]] increasing over time. The current decreases exponentially as the [[Capacitor]] charges.
- **Discharging**: When the [[Voltage]] source is removed, the [[Capacitor]] discharges through the [[Resistor]], with the [[Voltage]] across the [[Capacitor]] decreasing over time.

### Mathematical Equations:
For a **series [[RC circuit]]** with a DC [[Voltage]] source $V_0$, the charging and discharging behaviour can be described by the following equations:

1. **Charging the [[Capacitor]]**:
   The [[Voltage]] across the [[Capacitor]] $V_C(t)$ during charging is given by:

   $$
   V_C(t) = V_0 \left( 1 - e^{-\frac{t}{RC}} \right)
   $$

   where:
   - $V_0$ is the applied [[Voltage]],
   - $R$ is the resistance,
   - $C$ is the capacitance,
   - $t$ is time.

   The current $I(t)$ during the charging process is:

   $$
   I(t) = \frac{V_0}{R} e^{-\frac{t}{RC}}
   $$

2. **Discharging the [[Capacitor]]**:
   When the [[Voltage]] source is removed, the [[Capacitor]] discharges through the [[Resistor]], and the [[Voltage]] across the [[Capacitor]] $V_C(t)$ follows:

   $$
   V_C(t) = V_0 e^{-\frac{t}{RC}}
   $$

   The current $I(t)$ during the discharging process is:

   $$
   I(t) = - \frac{V_0}{R} e^{-\frac{t}{RC}}
   $$

   where the negative sign indicates the direction of current flow.

### Time Constant ($\tau$):
The **time constant** $\tau$ of an [[RC circuit]] is the time it takes for the [[Voltage]] across the [[Capacitor]] to reach approximately 63.2% of its final value during charging, or to decrease to about 36.8% during discharging. It is defined as:

$$
\tau = RC
$$

The time constant controls the speed at which the [[Capacitor]] charges or discharges. A larger $R$ or $C$ leads to a slower charging/discharging process.