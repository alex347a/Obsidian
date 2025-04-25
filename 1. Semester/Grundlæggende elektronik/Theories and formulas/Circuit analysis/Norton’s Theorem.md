**Norton’s Theorem** is similar to [[Thevenin's Theorem]], but instead of simplifying a circuit into a [[Voltage]] source in series with a [[Resistor]], it simplifies a complex linear circuit into a current source $I_N$ in parallel with a resistance $R_N$. This theorem is useful for analyzing circuits, especially when focusing on current delivery to the load.

### Norton’s Theorem Steps

1. **Identify the Portion of the Circuit**: Select the part of the circuit for which you want to find the Norton equivalent. Remove the load [[Resistor]] if one exists.

2. **Find the Norton Current $I_N$**: 
   - Norton current $I_N$ is the short-circuit current, which is the current flowing through the terminals where the load [[Resistor]] was removed, assuming the load is shorted (i.e., zero resistance across the terminals).
   - To find $I_N$, calculate the current using methods like mesh or [[Nodal Analysis]], considering the circuit with the load terminals shorted.

3. **Find the Norton Resistance $R_N$**: 
   - To find $R_N$, deactivate all independent [[Voltage]] and current sources in the circuit (replace [[Voltage]] sources with short circuits and current sources with open circuits).
   - Calculate the equivalent resistance seen from the terminals where the load [[Resistor]] was connected.

4. **Reconstruct the Norton Equivalent Circuit**: After finding $I_N$ and $R_N$, the Norton equivalent circuit consists of a current source $I_N$ in parallel with $R_N$. You can now reconnect the load [[Resistor]] to this simplified circuit.

### Norton Equivalent Circuit

The Norton equivalent circuit is represented as:
$$
\text{Norton Equivalent Circuit} = I_N \text{ (in parallel with) } R_N
$$

### Example

Consider a circuit with a [[Voltage]] source $V_s$, resistors $R_1$ and $R_2$, and a load [[Resistor]] $R_L$.

- **Step 1: Find $I_N$**: Norton current $I_N$ is the short-circuit current across the terminals where $R_L$ was connected. Using [[Current Division]] or [[Mesh Analysis]], find the current through the short-circuited terminals:
  $$ I_N = \frac{V_s}{R_1 + R_2} $$

- **Step 2: Find $R_N$**: Deactivate $V_s$ (replace with a short circuit), and find the equivalent resistance seen from the terminals:
  $$ R_N = R_1 \parallel R_2 $$

- **Step 3: Reconstruct the Norton Equivalent**: The simplified circuit consists of a current source $I_N$ in parallel with $R_N$, with $R_L$ reconnected as the load.

### Practical Application of Norton’s Theorem

- **Simplification**: Norton’s Theorem reduces complex circuits into simpler ones, making it easier to analyze the current delivered to the load [[Resistor]].
- **Maximum [[Power]] Transfer**: Just like Thevenin’s Theorem, Norton’s Theorem can be used to determine the optimal load resistance for [[Maximum Power Transfer]]. The load resistance should be equal to the Norton resistance $R_N$ for maximum [[Power]].
