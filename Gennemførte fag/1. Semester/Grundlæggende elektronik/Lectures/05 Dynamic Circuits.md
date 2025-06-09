## Chapter 3.4: 

![[Pasted image 20241029180548.png]]

If a switch is opened, normally the current would fall to zero. However, with an inductor, there is an infinitely high voltage instantaneously, which can destroy a switch if repeated too many times because it will create an arc over the switch (elektrisk udeladning (gnist)).

![[Pasted image 20241029180556.png]]
### Root Mean Square

![[Pasted image 20241029180612.png]]
![[Pasted image 20241029180618.png]]
![[Pasted image 20241029180625.png]]![[Pasted image 20241029180631.png]]
The same applies to capacitors:
$$
V_C = Z_C I_C
$$

For resistors:
$$
V_R = RI_R
$$
![[Pasted image 20241029180643.png]]![[Pasted image 20241029180645.png]]

## Chapter 5: Dynamic Circuits

### Section 5.1: The Inductor
This section introduces the inductor, which stores energy in a magnetic field when current flows through it.
- Inductance ($L$) is the property of an inductor that opposes changes in current. The voltage across an inductor is proportional to the rate of change of current through it:
$$
v(t) = L \frac{d}{dt} i(t)
$$
- **Unit of Inductance**: The unit of inductance is the henry (H). An inductor resists changes in current and acts as a short circuit to DC current once steady state is reached.
- **Energy Stored**: The energy stored in the magnetic field of an inductor is given by:
$$
W = \frac{1}{2} LI^2
$$
where $W$ is the energy (in joules), $L$ is the inductance, and $I$ is the current.

### Section 5.2: The Inductor in a Circuit
This section explains the behavior of an inductor when connected in a circuit, particularly focusing on its transient and steady-state behavior.
- In an initial condition, the current through an inductor cannot change instantaneously because a sudden change would require an infinite voltage, which is physically impossible. Thus, inductors exhibit transient behavior when the current changes.
- In DC steady state, the current through the inductor becomes constant, and the voltage across the inductor is zero. In this state, the inductor acts as a short circuit (since a constant current produces no changing magnetic field).

### Section 5.3: The Capacitor
This section revisits capacitors, reinforcing their dynamic behavior in circuits.
- A capacitor stores energy in an electric field when a voltage is applied across its plates.
- The current through a capacitor is proportional to the rate of change of voltage across it:
$$
i(t) = C \frac{d}{dt} v(t)
$$
where $C$ is the capacitance, $i(t)$ is the current, and $v(t)$ is the voltage.
- In DC steady state, a capacitor behaves as an open circuit because no current flows through it once it’s fully charged.
- **Energy Stored in a Capacitor**: The energy stored in the electric field of a capacitor is given by:
$$
E = \frac{1}{2} CU^2
$$
where $E$ is the energy in joules, $C$ is the capacitance, and $U$ is the voltage across the capacitor.

### Section 5.4: Capacitors and Inductors in Series and Parallel
This section extends the concepts of combining capacitors and inductors in series and parallel circuits.
- **Inductors in Series**: When inductors are connected in series, the total inductance is the sum of the individual inductances:
$$
L_{eq} = L_1 + L_2 + \cdots
$$
This is similar to resistors in series.
- **Inductors in Parallel**: When inductors are connected in parallel, the reciprocal of the total inductance is the sum of the reciprocals of the individual inductances:
$$
\frac{1}{L_{eq}} = \frac{1}{L_1} + \frac{1}{L_2} 
$$
For capacitors it is the opposite of resistors and inductors.
- **Capacitors in Parallel**: The equivalent capacitance of capacitors in parallel is the sum of the individual capacitances:
$$
C_{eq} = C_1 + C_2 + \cdots
$$
So it is like resistors and inductors in series. Capacitors in parallel add up, allowing the circuit to store more charge.
- **Capacitors in Series**: When capacitors are connected in series, the reciprocal of the total capacitance is the sum of the reciprocals of the individual capacitances:
$$
\frac{1}{C_{eq}} = \frac{1}{C_1} + \frac{1}{C_2} + \cdots
$$
So that is like resistors and inductors in parallel.
### Section 5.5: Initial Conditions in a Circuit
This section focuses on the importance of initial conditions in dynamic circuits involving capacitors and inductors. These initial conditions must be considered when solving circuits with energy-storing elements (capacitors and inductors).
- **Inductor Initial Condition**: The current through an inductor just before and just after a switch operation remains continuous. This means the initial current through an inductor is the same as its value immediately after the switch.
- **Capacitor Initial Condition**: The voltage across a capacitor cannot change instantaneously because this would require infinite current, which is impossible. Therefore, the voltage across the capacitor just before and just after a switching operation is the same.
- In practical terms, these initial conditions are critical when analyzing transient responses in circuits, as they help determine how the circuit evolves over time after a switch is flipped or a power source is applied.

---

### Key Concepts:
- Inductors and capacitors store energy in magnetic and electric fields, respectively, and their behaviour in circuits is time-dependent.
  
- In steady state, inductors behave like short circuits, while capacitors behave like open circuits.
  
- Combining inductors and capacitors in series and parallel allows for equivalent simplifications similar to resistors.
  
- Initial conditions for current through inductors and voltage across capacitors are crucial when analyzing circuits with dynamic (transient) responses.