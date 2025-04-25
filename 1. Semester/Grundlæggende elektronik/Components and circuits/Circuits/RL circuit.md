### Summary:
An [[RL circuit]] demonstrates transient behavior due to the interaction between the [[Resistor]] and the [[Inductor]]. The current through the [[Inductor]] increases or decreases exponentially over time, depending on whether the [[Voltage]] source is applied or removed. The [[Voltage]] across the [[Inductor]] is proportional to the rate of change of current. The time constant $\tau = \frac{L}{R}$ determines the speed of this change.


An **[[RL circuit]]** is an electrical circuit that consists of a **[[Resistor]]** ($R$) and an **[[Inductor]]** ($L$) connected in series or parallel. It is a type of linear electrical circuit that exhibits [[[[inductor]]#Transient behaviour ([[Inductor]])|transient behaviour]] when the current through the [[Inductor]] changes, such as when a [[Voltage]] is suddenly applied or removed.

### Components of an [[RL circuit]]:
- **[[Resistor]]** ($R$): Resists the flow of electric current and dissipates [[Energy]] as heat.
- **[[Inductor]]** ($L$): Stores [[Energy]] in a magnetic field and resists changes in current.

### Basic Configurations of RL Circuits:
1. **Series [[RL circuit]]**:
   - The [[Resistor]] and [[Inductor]] are connected in a single path, one after the other.
   - This is the most common [[RL circuit]], where the input [[Voltage]] is applied across the series combination of the [[Resistor]] and [[Inductor]].
   
2. **Parallel [[RL circuit]]**:
   - The [[Resistor]] and [[Inductor]] are connected in parallel across the same [[Voltage]] source.
   - This configuration also exhibits transient behavior but is less common in simple applications.

### Behavior of an [[RL circuit]]:
The behavior of an [[RL circuit]] primarily involves the **charging** and **discharging** of the [[Inductor]]'s magnetic field through the [[Resistor]].

- **Charging (Current Increase)**: When a [[Voltage]] is applied to the [[RL circuit]], the current through the [[Inductor]] gradually increases, and the [[Inductor]] generates a [[Voltage]] opposing the increase in current. The current reaches a steady-state value over time.
- **Discharging (Current Decrease)**: When the [[Voltage]] source is removed, the [[Inductor]] resists the sudden decrease in current and releases [[Energy]] stored in its magnetic field. The current decays over time.

### Mathematical Equations:
For a **series [[RL circuit]]** with a DC [[Voltage]] source $V_0$, the transient behavior can be described by the following equations:

1. **Current through the [[Inductor]] during Charging**:
   The current $I(t)$ through the [[Inductor]] during the charging process is given by:

   $$
   I(t) = I_0 \left(1 - e^{-\frac{R}{L}t}\right)
   $$

   where:
   - $I_0$ is the initial current (at $t = 0$),
   - $R$ is the resistance,
   - $L$ is the inductance,
   - $t$ is time.

   The [[Voltage]] across the [[Inductor]] $V_L(t)$ during this process is:

   $$
   V_L(t) = L \frac{dI}{dt}
   $$

2. **Current through the [[Inductor]] during Discharging**:
   When the [[Voltage]] source is removed, the current through the [[Inductor]] decays, and is given by:

   $$
   I(t) = I_0 e^{-\frac{t}{\tau}}
   $$

   where:
   - $I_0$ is the initial current,
   - $\tau = \frac{L}{R}$ is the time constant,
   - $t$ is time.

   The [[Voltage]] across the [[Inductor]] during the discharging process is:

   $$
   V_L(t) = - L \frac{dI}{dt}
   $$

### Time Constant ($\tau$):
The **time constant** $\tau$ of an [[RL circuit]] is the time it takes for the current through the [[Inductor]] to reach approximately 63.2% of its final value during a transient process. It is defined as:

$$
\tau = \frac{L}{R}
$$

The time constant controls the speed at which the current increases or decreases in the [[Inductor]]. A larger $L$ or smaller $R$ results in a slower transient response.