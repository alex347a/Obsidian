**[[Voltage]] Division** refers to the distribution of the total [[Voltage]] across resistors in a series circuit. The [[Voltage]] is divided among the resistors in proportion to their resistances. This concept is particularly useful for determining the [[Voltage]] drop across each [[Resistor]] when multiple resistors are connected in series.

### [[Voltage]] Division Formula

For a series circuit with resistors $R_1, R_2, R_3, \dots, R_n$ connected across a total [[Voltage]] $V_{\text{total}}$, the [[Voltage]] across a specific [[Resistor]] $R_x$ is given by the [[Voltage]] divider rule:
$$
V_x = V_{\text{total}} \cdot \frac{R_x}{R_{\text{total}}}
$$
where:
- $V_x$ is the [[Voltage]] across [[Resistor]] $R_x$,
- $V_{\text{total}}$ is the total [[Voltage]] applied across the series combination of resistors,
- $R_x$ is the resistance of the individual [[Resistor]], and
- $R_{\text{total}}$ is the total resistance of the series circuit, calculated as:
  $$ 
  R_{\text{total}} = R_1 + R_2 + R_3 + \dots + R_n
  $$

### Example of [[Voltage]] Division

Consider a series circuit with three resistors:
- $R_1 = 4 \, \Omega$
- $R_2 = 6 \, \Omega$
- $R_3 = 10 \, \Omega$

The total resistance is:
$$
R_{\text{total}} = R_1 + R_2 + R_3 = 4 \, \Omega + 6 \, \Omega + 10 \, \Omega = 20 \, \Omega
$$

If the total [[Voltage]] is $V_{\text{total}} = 12 \, \text{V}$, the [[Voltage]] across each [[Resistor]] can be calculated:
- [[Voltage]] across $R_1$:
  $$ 
  V_1 = 12 \, \text{V} \cdot \frac{4 \, \Omega}{20 \, \Omega} = 2.4 \, \text{V}
  $$
- [[Voltage]] across $R_2$:
  $$ 
  V_2 = 12 \, \text{V} \cdot \frac{6 \, \Omega}{20 \, \Omega} = 3.6 \, \text{V}
  $$
- [[Voltage]] across $R_3$:
  $$ 
  V_3 = 12 \, \text{V} \cdot \frac{10 \, \Omega}{20 \, \Omega} = 6 \, \text{V}
  $$

### Key Points about [[Voltage]] Division
- **Proportional to Resistance**: The [[Voltage]] across each [[Resistor]] is proportional to its resistance.
- **Sum of Voltages**: The sum of the voltages across all resistors equals the total [[Voltage]] applied to the series circuit.
- **Application**: Voltage division is used to design circuits that require specific [[Voltage]] levels across individual components.