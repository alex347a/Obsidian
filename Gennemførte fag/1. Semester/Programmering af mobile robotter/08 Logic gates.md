
![[08 Logic gates Slide.pdf]]

| Slide: | Concept:                                                                                                                                |
| ------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| 13     | Buffer: input er output<br>NOT gate: output er det modsatte af input                                                                    |
| 14     | AND gate. Svarer til at gange.                                                                                                          |
| 15     | OR gate. Svarer til at plusse                                                                                                           |
| 17     | NAND gate. Det er en NOT AND gate, så det modsatte.                                                                                     |
| 18     | NOR gate. Det er en NOT OR gate, så det modsatte.                                                                                       |
| 20     | XOR gate. Exclusive OR gate, hvor den kun viser 1, når de to input er forskellige og 0, når de er ens.                                  |
| 21     | XNOR gate. Exclusive NOR gate, hvor den kun viser 1, når de to input er ens og 0 når de er forskellige, så det modsatte af en XOR gate. |
| 22-38  | Boolean algebra                                                                                                                         |
| 39-40  | Multiplexer                                                                                                                             |
| 41-45  | Encoder/decoder                                                                                                                         |
| 47-49  | Full adder                                                                                                                              |
| 50-58  | CPU, memory, Gated D-latch                                                                                                              |
| 59-86  | Laws of boolean algebra (regler for boolean algebra)                                                                                    |

Buffer og NOT gate:
![[Pasted image 20241104084054.png]]
AND gate: 
![[Pasted image 20241104084122.png]]
OR gate:
![[Pasted image 20241104084147.png]]
NAND gate:
![[Pasted image 20241104084211.png]]
NOR gate:
![[Pasted image 20241104084227.png]]
XOR gate:
![[Pasted image 20241104084413.png]]
XNOR gate:
![[Pasted image 20241104084426.png]]
2 Bit Adder:
![[Pasted image 20241104100020.png]]

**Boolean Algebra**

- A mathematical system for binary variables, used to simplify and analyze digital circuits.

**Multiplexer**

- A device that selects one of several input signals to send to the output, based on control signals.

**Encoder/Decoder**

- Encoder: Converts information from one format to another, typically from multiple inputs to a binary output.
- Decoder: Performs the reverse, converting a binary input to a specific output.

**Full Adder**

- A digital circuit that adds three binary bits (two inputs and a carry-in) and outputs a sum and carry-out.

**CPU, Memory, Gated D-Latch**

- CPU: Central Processing Unit, the brain of a computer that performs instructions.
- Memory: Stores data and instructions for processing.
- Gated D-Latch: A memory device that stores a bit of data, controlled by an enable signal.

**Laws of Boolean Algebra**

- Rules governing Boolean operations, such as the identity, null, complement, and distributive laws, used to simplify digital logic:
1. **Identity Laws**
    
    - $A + 0 = A$: Adding 0 to a variable doesn’t change its value.
    - $A \cdot 1 = A$: Multiplying a variable by 1 doesn’t change its value.
2. **Null Laws**
    
    - $A + 1 = 1$: Adding 1 to any variable results in 1.
    - $A \cdot 0 = 0$: Multiplying any variable by 0 results in 0.
3. **Idempotent Laws**
    
    - $A + A = A$: Adding a variable to itself does not change its value.
    - $A \cdot A = A$: Multiplying a variable by itself does not change its value.
4. **Complement Laws**
    
    - $A + \overline{A} = 1$: A variable OR’ed with its complement (NOT) is always 1.
    - $A \cdot \overline{A} = 0$: A variable AND’ed with its complement is always 0.
5. **Involution Law**
    
    - $\overline{\overline{A}} = A$: Double negation of a variable returns the original variable.
6. **Distributive Laws**
    
    - $A \cdot (B + C) = (A \cdot B) + (A \cdot C)$: AND distributes over OR.
    - $A + (B \cdot C) = (A + B) \cdot (A + C)$: OR distributes over AND.
7. **Absorption Laws**
    
    - $A + (A \cdot B) = A$: Adding a term that’s already part of a product simplifies to the term itself.
    - $A \cdot (A + B) = A$: Multiplying a term that’s already part of a sum simplifies to the term itself.
8. **De Morgan’s Theorems**
    
    - $\overline{A \cdot B} = \overline{A} + \overline{B}$: The complement of an AND operation equals the OR of the complements.
    - $\overline{A + B} = \overline{A} \cdot \overline{B}$: The complement of an OR operation equals the AND of the complements.

These laws allow Boolean expressions to be simplified, making circuits more efficient by reducing the number of logic gates required.