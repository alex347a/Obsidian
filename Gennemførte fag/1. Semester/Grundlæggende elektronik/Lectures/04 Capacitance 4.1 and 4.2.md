The transient part of the response for a circuit containing sources, resistances, and a single energy-storage element (L or C) is of the form $Ke^{-t/\tau}$. The time constant is given by $\tau = RC$ or by $\tau = L/R$, where $R$ is the Thevenin resistance seen looking back into the circuit from the terminals of the energy-storage element. 

In DC steady-state conditions, inductors behave as short circuits and capacitors behave as open circuits. We can find the steady-state (forced) response for DC sources by analysing the DC equivalent circuit.

Discharge of a capacitance through a resistance: Before $t=0$ there is a [[Voltage]] $V_i$ charged in the circuit. Then, at $t=0$, the switch closes and current flows through the [[Resistor]] and discharges the [[Capacitor]]:
$$
C \frac{dv_C(t)}{dt} + \frac{v_C(t)}{R} = 0
$$

With the resistance multiplied:
$$
RC \frac{dv_C(t)}{dt} + v_C(t) = 0
$$

We get a differential equation, where the solution for $v_C(t)$ must be a function that has the same form as the derivative, therefore an exponential function:
$$
v_C(t) = Ke^{st}
$$

Where $K$ and $s$ are constants. If we substitute the equations above we get:
$$
RCKse^{st} + Ke^{st} = 0
$$

Solving for $s$:
$$
s = \frac{-1}{RC}
$$

The solution is therefore:
$$
v_C(t) = Ke^{-t/RC}
$$

The [[Voltage]] across the [[Capacitor]] cannot change instantaneously when the switch closes because the current through the [[Capacitor]] is: $i_C(t) = C \frac{dv_C}{dt}$; otherwise, the current would have to be infinite. It must therefore be continuous:
$$
v_C(0+) = V_i
$$

Where $v_C(0+)$ represents the [[Voltage]] immediately after the switch closes.
$$
v_C(0+) = V_i = Ke^{0} = K
$$

We see that the constant $K$ is the initial [[Voltage]] across the [[Capacitor]].
$$
v_C(t) = V_i e^{-t/RC}
$$

The time constant $\tau = RC$. In one time constant, the [[Voltage]] decreases by $e^{-1} = 0.368$, where it will decrease slower and slower as the [[Voltage]] goes towards 0. For charging, it is almost the same, although here $V_s$ is subtracted from the [[Voltage]], and therefore we end up with another constant:
$$
RC \frac{dv_C(t)}{dt} + v_C(t) = V_s
$$

$$
v_C(t) = K_1 + K_2 e^{st}
$$

Where $K_1$, $K_2$, and $s$ are constants. If we substitute into the equation 2 equations above we get:
$$
V_s = (1 + RCs) K_2 e^{st} + K_1
$$

For equality, the coefficient of $e^{st}$ must be zero:
$$
s = \frac{-1}{RC}
$$

And:
$$
K_1 = V_s
$$

If we use those two equations in the original formula:
$$
v_C(t) = V_s + K_2 e^{-t/RC}
$$

Now if:
$$
v_C(0+) = 0 = V_s + K_2 e^{0} = V_s + K_2
$$

Where we can identify that $K_2 = -V_s$:
$$
v_C(t) = V_s - V_s e^{-t/RC}
$$

$-V_s e^{-t/RC}$ is called the transient response, which eventually decays to negligible values, while $V_s$ is called the steady-state response or forced response. Which persists after the transient has decayed. Since $RC = \tau$, it can also be written as:
$$
v_C(t) = V_s - V_s e^{-t/\tau}
$$

Look at the graph:
![[Pasted image 20241029180318.png]]

$v_C(t)$ starts at 0 and reaches 63.2% after one time constant. For practical purposes, $v_C(t)$ is equal to its final value after five time constants. Then the circuit has reached steady-state.

## 4.2 DC Steady-state.

The transient terms in the expression for currents and voltages in RLC circuits decay to zero with time, but an exception is LC circuits that have no resistance. For DC sources, the steady-state currents and voltages are also constant.

Current through a capacitance:
$$
i_C(t) = C \frac{dv_C(t)}{dt}
$$

If the [[Voltage]] is constant, then the current is zero. Therefore, the capacitance behaves as an open circuit for steady-state conditions with DC sources. Similarly for inductance:
$$
v_L(t) = L \frac{di_L(t)}{dt}
$$

When the current is constant, the [[Voltage]] is zero. Therefore, inductances behave as short circuits for steady-state conditions with DC sources.

### Section 4.1 notes: Capacitors in [[DC Steady State]]

This section discusses the behavior of capacitors in DC circuits once the system has reached steady state. In the context of [[DC Steady State]]:
- A steady state occurs after any transient effects (such as charging or discharging) have subsided, and the [[Voltage]] and current in the circuit no longer change with time.
- In steady state, a [[Capacitor]] behaves like an open circuit in a DC system because once it is fully charged, no current flows through it:
    - Current through the [[Capacitor]] in steady state is zero: $i(t) = 0$.
- The [[Voltage]] across the [[Capacitor]] remains constant at the value determined by the circuit's initial conditions.
- Since no current flows in steady state, the [[Voltage]] across a [[Capacitor]] depends on the charge stored on the plates, which does not change once steady state is achieved.

### Section 4.2 notes: Capacitor [[Voltage]] in [[DC Steady State]]

The [[Voltage]] across a [[Capacitor]] depends on the initial conditions and the charging process. Once the system reaches steady state in a DC circuit:
$$
v(t) = v(t_0)
$$
where $v(t_0)$ is the [[Voltage]] when the system first entered steady state.
- [[Capacitor]] Charge and [[Voltage]]: The amount of charge stored on a capacitor’s plates is related to the [[Voltage]] across it, and in [[DC Steady State]], this charge remains constant:
$$
Q = CV
$$
where:
- $Q$ is the charge on the [[Capacitor]],
- $C$ is the capacitance,
- $V$ is the [[Voltage]] across the [[Capacitor]].

Therefore, once the [[Capacitor]] reaches steady state, the [[Voltage]] across it will remain at a fixed value determined by how much charge it accumulated during the charging phase. In [[DC Steady State]], you can think of the [[Capacitor]] as "holding" the [[Voltage]], which cannot change unless a new external force is applied (like opening or closing a switch).

## Key Concepts for Capacitance in [[DC Steady State]]:
- Capacitors behave like open circuits in [[DC Steady State]], meaning no current flows through them after they are fully charged.
- The [[Voltage]] across a [[Capacitor]] remains constant in steady state and is determined by the initial charging process.
- Capacitance ($C$) governs how much charge a [[Capacitor]] can hold for a given [[Voltage]], and this relationship is fixed in [[DC Steady State]].

## Inductors:
Inductors are passive electrical components consisting of coils of wire that generate a magnetic field when current flows through them. The inductance $L$ measures the strength of this opposition to current changes and is measured in henries ($H$).
Inductance ($L$) is defined as the ratio of the magnetic flux linkage to the current:
$$
L = \frac{\lambda}{I}
$$
where:
- $\lambda$ is the magnetic flux linkage (in weber-turns),
- $I$ is the current through the [[Inductor]] (in amperes),
- $L$ is the inductance (in henries).

The relationship between the [[Voltage]] across an [[Inductor]] and the current through it is given by:
$$
v(t) = L \frac{d}{dt} i(t)
$$

This shows that the [[Voltage]] across an [[Inductor]] is proportional to the rate of change of current through it. If the current is constant, the [[Voltage]] across the [[Inductor]] is zero.

### [[Energy]] Stored in an [[Inductor]]:
Like capacitors store [[Energy]] in an [[Electric field]], inductors store [[Energy]] in a magnetic field. The [[Energy]] stored in an [[Inductor]] is:
$$
W = \frac{1}{2} LI^2
$$
where $W$ is the [[Energy]] in joules, $L$ is the inductance, and $I$ is the current.

### Section 4.2: Inductors in Series and Parallel
Just like resistors and capacitors, inductors can be connected in series or parallel to achieve different total inductances.

- Inductors in Series: When inductors are connected end-to-end, the total inductance is the sum of the individual inductances, similar to [[Resistors in series]]:
$$
L_{eq} = L_1 + L_2 + L_3 + \cdots
$$

This is because each [[Inductor]] contributes to the total magnetic field generated by the current flowing through the entire series circuit.

- Inductors in Parallel: When inductors are connected in parallel, the reciprocal of the total inductance is the sum of the reciprocals of the individual inductances, similar to [[Resistors in parallel]]:

$$
\frac{1}{L_{eq}} = \frac{1}{L_1} + \frac{1}{L_2} + \cdots
$$

Inductors in parallel behave like a single [[Inductor]] with a smaller inductance.

## Key Concepts:

- Inductance opposes changes in current by generating a [[Voltage]] proportional to the rate of change of the current.
  
- The [[Energy]] stored in an [[Inductor]] depends on the square of the current and the inductance.
  
- Inductors in series add their inductances, while inductors in parallel reduce the overall inductance.