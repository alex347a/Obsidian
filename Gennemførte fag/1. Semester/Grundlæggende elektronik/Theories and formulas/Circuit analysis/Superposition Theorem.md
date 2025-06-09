**Superposition Theorem** states that in a linear circuit with multiple independent sources, the total response ([[Voltage]] or current) at any point in the circuit is the algebraic sum of the responses from each independent source acting alone, while all other independent sources are replaced by their internal resistances. This theorem is particularly useful for analyzing circuits with multiple sources.

### [[Superposition Theorem]] Steps

1. **Deactivate All but One Source**: 
   - For each independent source, deactivate all other sources.
   - [[Voltage]] sources are replaced by short circuits (i.e., replace the [[Voltage]] source with a wire).
   - Current sources are replaced by open circuits (i.e., remove the current source and leave a gap in the circuit).

2. **Solve for the Response**: 
   - With only one source active, solve for the desired quantity ([[Voltage]] or current) at the point of interest.

3. **Repeat for Each Source**: 
   - Repeat the process for each independent source, deactivating all other sources each time.

4. **Sum the Responses**: 
   - After solving for the responses from each source acting alone, sum all the individual responses algebraically to get the total response.

### Example

Consider a circuit with two [[Voltage]] sources, $V_1$ and $V_2$, and resistors $R_1$, $R_2$, and $R_3$. We want to find the total current through [[Resistor]] $R_3$.

1. **Deactivate $V_2$ (Replace with Short Circuit)**:
   - Solve the circuit with only $V_1$ active. Find the current $I_1$ through $R_3$.

2. **Deactivate $V_1$ (Replace with Short Circuit)**:
   - Solve the circuit with only $V_2$ active. Find the current $I_2$ through $R_3$.

3. **Total Current through $R_3$**:
   - The total current $I_{\text{total}}$ through $R_3$ is:
   $$ I_{\text{total}} = I_1 + I_2 $$

### Important Considerations

- **Superposition is applicable only to linear circuits**, where the relationship between [[Voltage]] and current is linear (i.e., Ohm's law holds).
- **Sign Convention**: The algebraic sum must account for the direction of currents and voltages. If the responses from the individual sources oppose each other, they will subtract from each other.
  
### Practical Use of Superposition

- **Simplification**: This theorem simplifies the analysis of complex circuits by breaking them down into simpler problems involving just one source at a time.
- **Flexibility**: Superposition is applicable to both AC and DC circuits and can be used to analyze [[Voltage]], current, and impedance in complex systems with multiple sources.