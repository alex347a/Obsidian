**Current Division** refers to the way in which the total current is split among the parallel branches of a circuit. In a parallel circuit, the total current $I_{\text{total}}$ entering the node is divided among the branches, with each branch carrying a portion of the total current. The [[Current Division]] depends on the resistance of each branch, with more current flowing through branches with lower resistance.

### [[Current Division]] Formula

For two resistors $R_1$ and $R_2$ in parallel, the current through [[Resistor]] $R_1$ ($I_1$) is given by the following formula:
$$
I_1 = I_{\text{total}} \cdot \frac{R_2}{R_1 + R_2}
$$
Similarly, the current through [[Resistor]] $R_2$ ($I_2$) is:
$$
I_2 = I_{\text{total}} \cdot \frac{R_1}{R_1 + R_2}
$$

For a parallel network with more than two resistors, the current through each [[Resistor]] can be found using a similar approach, where the current through [[Resistor]] $R_x$ is:
$$
I_x = I_{\text{total}} \cdot \frac{R_{\text{total}}}{R_x}
$$
where $R_{\text{total}}$ is the total resistance of the parallel network.

### Example of [[Current Division]]

Consider a circuit with two [[Resistors in parallel]]:
- $R_1 = 4 \, \Omega$
- $R_2 = 6 \, \Omega$

The total current applied is $I_{\text{total}} = 10 \, \text{A}$.

The total resistance is:
$$
R_{\text{total}} = \frac{R_1 R_2}{R_1 + R_2} = \frac{4 \, \Omega \cdot 6 \, \Omega}{4 \, \Omega + 6 \, \Omega} = \frac{24}{10} = 2.4 \, \Omega
$$

Now, calculate the current through each [[Resistor]]:
- Current through $R_1$:
  $$ I_1 = 10 \, \text{A} \cdot \frac{6 \, \Omega}{4 \, \Omega + 6 \, \Omega} = 10 \, \text{A} \cdot \frac{6}{10} = 6 \, \text{A} $$
- Current through $R_2$:
  $$ I_2 = 10 \, \text{A} \cdot \frac{4 \, \Omega}{4 \, \Omega + 6 \, \Omega} = 10 \, \text{A} \cdot \frac{4}{10} = 4 \, \text{A} $$

Thus, the total current of $10 \, \text{A}$ is split between the two resistors with $6 \, \text{A}$ flowing through $R_1$ and $4 \, \text{A}$ flowing through $R_2$.

### Key Points about [[Current Division]]
- **Current Splits**: The current divides between branches in parallel based on their resistances.
- **Inverse Proportionality**: The current is inversely proportional to the resistance of each branch; higher resistance carries less current.
- **Application**: Current division is useful in analyzing parallel circuits and designing circuits where specific current levels are needed in different paths.