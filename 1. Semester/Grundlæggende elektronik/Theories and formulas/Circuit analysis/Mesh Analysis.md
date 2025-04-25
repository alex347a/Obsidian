[[Mesh Analysis]], also known as **loop analysis**, is a method used to determine the current in each independent loop of a circuit. It is based on **Kirchhoff’s [[Voltage]] Law ([[KVL]])**, which states that the sum of voltages around any closed loop is equal to zero. Mesh analysis is particularly useful for circuits with multiple loops and components, as it reduces the problem to a system of equations involving only the loop currents.

### Steps in [[Mesh Analysis]]

1. **Label Loops**: Identify all the independent loops in the circuit. Label each loop with a current, typically denoted as $I_1$, $I_2$, etc. The direction of the loop currents is assumed arbitrarily (clockwise or counterclockwise), but the choice is not crucial as the final current value will have a sign to indicate direction.

2. **Apply KVL**: For each loop, apply Kirchhoff’s [[Voltage]] Law ([[KVL]]), which states that the sum of the [[Voltage]] drops around the loop must be zero. Voltage drops are expressed in terms of the loop currents and the resistances in the loop.

   - For each element, use Ohm’s Law to relate [[Voltage]] and current: 
     $$ V = I \cdot R $$

3. **Set up Equations**: For each loop, write an equation based on [[KVL]], summing the [[Voltage]] drops for each [[Resistor]] and source. If two loops share a [[Resistor]], the [[Voltage]] drop across that [[Resistor]] depends on the difference in loop currents.

4. **Solve the System**: Solve the system of linear equations for the loop currents using methods such as substitution, elimination, or matrix techniques (e.g., Gaussian elimination).

### Example

Consider a simple circuit with two resistors $R_1$ and $R_2$, a [[Voltage]] source $V_s$, and two loops with currents $I_1$ and $I_2$.

- Apply [[KVL]] for the first loop:
  $$ -V_s + I_1 \cdot R_1 + (I_1 - I_2) \cdot R_2 = 0 $$

- Apply [[KVL]] for the second loop:
  $$ I_2 \cdot R_2 + (I_2 - I_1) \cdot R_2 = 0 $$

- Solve the system of equations to find $I_1$ and $I_2$.

### Practical Application of [[Mesh Analysis]]

- **Simplifies Circuit Analysis**: Mesh analysis is particularly useful for solving circuits with multiple [[Voltage]] sources and resistors. It allows for direct calculation of the currents in the loops, making it ideal for circuits with many components.
- **Linear Equations**: Mesh analysis results in a system of linear equations, which can be solved using various algebraic techniques or computational tools like MATLAB or Python.