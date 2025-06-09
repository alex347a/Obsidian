**The total current entering a node (or junction) in an electrical circuit is equal to the total current leaving the node.**

This law is based on the principle of conservation of charge, which implies that charge cannot accumulate at any point in a circuit—whatever current flows into a node must flow out. Mathematically, for a node with $n$ branches, KCL can be expressed as:

$$
\sum_{i=1}^{n} I_i = 0
$$

where $I_i$ represents the current in each branch connected to the node. Currents entering the node are considered positive, while currents leaving the node are considered negative (or vice versa, as long as consistency is maintained).

### Practical Application of [[KCL]]

1. **Node [[Voltage]] Analysis**: KCL is commonly used in [[Nodal Analysis]], a technique for finding unknown voltages in circuits. By applying [[KCL]] at each node and setting up equations based on the sum of currents, we can solve for the unknowns.
   
2. **Current Flow Analysis**: KCL is helpful in understanding and predicting the behaviour of complex circuits where multiple current paths converge, like in parallel circuits or networks with multiple sources.

### Example

Consider a node where three currents meet: $I_1$, $I_2$, and $I_3$. According to [[KCL]]:

$$
I_1 + I_2 = I_3
$$

This indicates that the sum of currents entering the node (e.g., $I_1$ and $I_2$) equals the sum of currents leaving it (e.g., $I_3$).