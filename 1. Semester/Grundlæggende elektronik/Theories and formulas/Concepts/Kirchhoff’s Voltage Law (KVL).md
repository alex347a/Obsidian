**The sum of all voltages around any closed loop in a circuit is equal to zero.**

This law is derived from the conservation of [[Energy]], which implies that as we move around a closed loop, the total [[Energy]] gained and lost by the charges should balance out to zero. In other words, the sum of all [[Voltage]] drops and rises around a loop is zero. Mathematically, for a closed loop with $n$ elements, KVL can be expressed as:

$$
\sum_{i=1}^{n} V_i = 0
$$

where $V_i$ represents the [[Voltage]] across each element in the loop. Voltages are assigned positive or negative signs depending on their direction with respect to the chosen loop traversal.

### Practical Application of [[KVL]]

1. **Loop or Mesh Analysis**: KVL is used in [[Mesh Analysis]], a method for finding unknown currents in circuits. By applying [[KVL]] to each loop in the circuit and setting up equations based on [[Voltage]] drops, we can solve for the unknowns.
   
2. **[[Voltage]] Distribution**: KVL helps in analyzing how voltages are distributed across elements in series, making it useful for circuits involving multiple resistors, capacitors, or inductors.

### Example

Consider a simple loop with a [[Voltage]] source $V$ and two resistors $R_1$ and $R_2$, with currents flowing in the same direction. According to [[KVL]]:

$$
V - (I \cdot R_1) - (I \cdot R_2) = 0
$$

or rearranged:

$$
V = I \cdot (R_1 + R_2)
$$

This shows that the [[Voltage]] supplied by the source is equal to the sum of the [[Voltage]] drops across the resistors, validating [[KVL]] in the loop.