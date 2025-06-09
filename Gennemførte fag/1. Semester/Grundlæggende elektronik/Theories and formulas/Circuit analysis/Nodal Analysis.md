[[Nodal Analysis]] is a method used in circuit analysis to determine the [[Voltage]] at each node relative to a reference node (usually called the ground). It is based on **Kirchhoff’s Current Law ([[KCL]])** and is particularly useful for circuits with many components. The main idea is to write [[KCL]] equations at each node, expressing the sum of currents entering and leaving the node in terms of the node voltages, and then solve for those voltages.

### Steps in [[Nodal Analysis]]

1. **Label Nodes**: Identify all the nodes in the circuit and select a reference node (ground) with [[Voltage]] $V_{\text{ref}} = 0$. Label the remaining nodes with unknown voltages, such as $V_1$, $V_2$, etc.

2. **Apply KCL**: At each node, apply Kirchhoff’s Current Law ([[KCL]]), which states that the sum of currents entering a node must equal zero. Express the currents in terms of node voltages using [[Ohm's law]]: 
   $$ I = \frac{V_{\text{node}} - V_{\text{neighbor}}}{R} $$

3. **Set up Equations**: For each node, write an equation for the sum of currents based on [[KCL]]. This will result in a system of linear equations involving the node voltages.

4. **Solve the System**: Solve the system of equations for the node voltages using methods such as substitution, elimination, or matrix techniques (e.g., Gaussian elimination).

### Example

Consider a simple circuit with a [[Voltage]] source $V_s$, two resistors $R_1$ and $R_2$, and a node at which we need to find the [[Voltage]] $V_1$.

- Apply [[KCL]] at node $V_1$:
  $$ \frac{V_1 - V_s}{R_1} + \frac{V_1}{R_2} = 0 $$

- Rearranging, we get:
  $$ V_1 \left( \frac{1}{R_1} + \frac{1}{R_2} \right) = \frac{V_s}{R_1} $$

- Solving for $V_1$:
  $$ V_1 = \frac{V_s}{R_1} \cdot \frac{R_2}{R_1 + R_2} $$

This gives the [[Voltage]] at node $V_1$ relative to the reference node.

### Practical Application of [[Nodal Analysis]]

- **Multi-Node Circuits**: Nodal analysis is highly effective for circuits with multiple nodes and components, as it can be applied to complex networks without needing to analyze every current path individually.
- **Automated Solution**: Nodal analysis can be easily implemented in software tools like MATLAB or Python to solve large-scale systems of equations.