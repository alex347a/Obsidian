**[[Resistors in parallel]]** are connected across the same two points, providing multiple paths for the current to flow. In a parallel connection, the total resistance is less than the resistance of any individual [[Resistor]] in the circuit. The [[Voltage]] across each [[Resistor]] in parallel is the same, but the current through each [[Resistor]] depends on its resistance.

### Total Resistance in Parallel

The total resistance $R_{\text{total}}$ for [[Resistors in parallel]] is found using the reciprocal formula:
$$
\frac{1}{R_{\text{total}}} = \frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3} + \dots + \frac{1}{R_n}
$$
where $R_1, R_2, R_3, \dots, R_n$ are the individual resistances. For two resistors, the formula simplifies to:
$$
R_{\text{total}} = \frac{R_1 R_2}{R_1 + R_2}
$$
For three resistors, the formula becomes:
$$
\frac{1}{R_{\text{total}}} = \frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3}
$$

### [[Current Division]] in Parallel

In a parallel circuit, the total current $I_{\text{total}}$ is the sum of the currents through each [[Resistor]]. The current through each [[Resistor]] $I_i$ can be found using [[Ohm's law]]:
$$
I_i = \frac{V}{R_i}
$$
where $V$ is the [[Voltage]] across the resistors, and $R_i$ is the resistance of the individual [[Resistor]].

The total current is:
$$
I_{\text{total}} = I_1 + I_2 + I_3 + \dots + I_n
$$
which can be expressed as:
$$
I_{\text{total}} = \frac{V}{R_1} + \frac{V}{R_2} + \frac{V}{R_3} + \dots
$$

### [[Voltage]] in Parallel

The [[Voltage]] across each [[Resistor]] in a parallel circuit is the same and equal to the total [[Voltage]] $V_{\text{total}}$. This is because the resistors are connected across the same two points.

### Example of [[Resistors in parallel]]

Consider a circuit with three [[Resistors in parallel]]:
- $R_1 = 4 \, \Omega$
- $R_2 = 6 \, \Omega$
- $R_3 = 12 \, \Omega$

The total resistance is:
$$
\frac{1}{R_{\text{total}}} = \frac{1}{4} + \frac{1}{6} + \frac{1}{12} = \frac{3}{12} + \frac{2}{12} + \frac{1}{12} = \frac{6}{12} = \frac{1}{2}
$$
Thus, 
$$
R_{\text{total}} = 2 \, \Omega
$$

If the total [[Voltage]] applied is $V_{\text{total}} = 12 \, \text{V}$, the current through each [[Resistor]] is:
- Current through $R_1$: 
  $$ I_1 = \frac{V_{\text{total}}}{R_1} = \frac{12}{4} = 3 \, \text{A} $$
- Current through $R_2$: 
  $$ I_2 = \frac{V_{\text{total}}}{R_2} = \frac{12}{6} = 2 \, \text{A} $$
- Current through $R_3$: 
  $$ I_3 = \frac{V_{\text{total}}}{R_3} = \frac{12}{12} = 1 \, \text{A} $$

The total current is:
$$
I_{\text{total}} = I_1 + I_2 + I_3 = 3 \, \text{A} + 2 \, \text{A} + 1 \, \text{A} = 6 \, \text{A}
$$

### Key Points about [[Resistors in parallel]]
- **Same [[Voltage]]**: The [[Voltage]] across each [[Resistor]] is the same.
- **Total Resistance**: The total resistance is always less than the smallest individual resistance.
- **[[Current Division]]**: The current is divided among the parallel resistors inversely proportional to their resistances.
- **Application**: Parallel resistors are used in applications where the goal is to decrease the total resistance or share the current among multiple paths.

