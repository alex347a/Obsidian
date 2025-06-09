**Thevenin's Theorem** simplifies a complex linear circuit into a simple equivalent circuit consisting of a single [[Voltage]] source $V_T$ in series with a resistance $R_T$. This theorem is useful for analyzing [[Power]] systems and circuits by reducing the number of components, making it easier to understand the behavior of the circuit at specific load points.

### [[Thevenin's Theorem]] Steps

1. **Identify the Portion of the Circuit**: Select the part of the circuit for which you want to find the Thevenin equivalent. Remove the load [[Resistor]] if one exists.

2. **Find the Thevenin [[Voltage]] $V_T$**: 
   - Thevenin [[Voltage]] $V_T$ is the open-circuit [[Voltage]] across the terminals where the load [[Resistor]] was removed.
   - To find $V_T$, calculate the [[Voltage]] using any appropriate method (e.g., voltage division, mesh analysis, or [[Nodal Analysis]]) based on the remaining circuit.

3. **Find the Thevenin Resistance $R_T$**: 
   - To find $R_T$, deactivate all independent [[Voltage]] and current sources in the circuit (replace [[Voltage]] sources with short circuits and current sources with open circuits).
   - Calculate the equivalent resistance seen from the terminals where the load [[Resistor]] was connected.

4. **Reconstruct the Thevenin Equivalent Circuit**: After finding $V_T$ and $R_T$, the Thevenin equivalent circuit consists of $V_T$ in series with $R_T$. You can now reconnect the load [[Resistor]] to this simplified circuit.

### Thevenin Equivalent Circuit

The Thevenin equivalent circuit is represented as:
$$
\text{Thevenin Equivalent Circuit} = V_T \text{ (in series with) } R_T
$$

### Example

Consider a circuit with a [[Voltage]] source $V_s$, resistors $R_1$ and $R_2$, and a load [[Resistor]] $R_L$.

- **Step 1: Find $V_T$**: Thevenin [[Voltage]] $V_T$ is the open-circuit [[Voltage]] across the terminals where $R_L$ was connected. Using [[Voltage]] division:
  $$ V_T = V_s \cdot \frac{R_2}{R_1 + R_2} $$

- **Step 2: Find $R_T$**: Deactivate $V_s$ (replace with a short circuit), and find the equivalent resistance seen from the terminals:
  $$ R_T = R_1 \parallel R_2 $$

- **Step 3: Reconstruct the Thevenin Equivalent**: The simplified circuit consists of a [[Voltage]] source $V_T$ in series with $R_T$, with $R_L$ reconnected as the load.

### Practical Application of [[Thevenin's Theorem]]

- **Simplification**: Thevenin’s Theorem reduces complex circuits into simpler ones, making it easier to analyze the effect of varying load resistances on [[Power]] delivery.
- **[[Power]] Transfer**: Thevenin’s Theorem is used to determine the optimal load resistance for [[Maximum Power Transfer]], where the load resistance should equal the Thevenin resistance $R_T$ for maximum [[Power]].