### Von Neumann Architecture
The von Neumann architecture is the fundamental concept of computer design based on the ability to store program instructions and the data they operate on in the same memory. This replaced earlier machines that were built for a single purpose and required manual rewiring to program. The architecture consists of three main components: the central processing unit (CPU), memory, and input/output (I/O) interfaces.
![[2.1.png]]

### Central Processing Unit (CPU)
The CPU is the heart of the computing system and contains three main parts:
1. **Control Unit (CU):** Determines the order of instruction execution, controls operand retrieval, interprets instructions, and governs information flow by issuing control signals. Each operation from a control signal is a microoperation (MO).
    
2. **Arithmetic Logic Unit (ALU):** Performs all mathematical and Boolean operations.
    
3. **Registers:** Temporary storage locations for fast access to data and instructions being used. They are faster than memory because they are on the same chip as the CU. A CPU on a single chip is a microprocessor.

### Memory
The computer's memory stores program instructions and data. Two common types are:

1. **RAM (Random-Access Memory):** Stores data and general-purpose programs. It is temporary; its contents can be changed and are erased when power is off.
    
2. **ROM (Read-Only Memory):** Permanent memory used to store the initial boot-up instructions.
### Input/Output (I/O) Interfaces
I/O interfaces allow the computer's memory to receive information from input devices and send data to output devices. They also enable communication with the user and secondary storage devices like disk and tape drives.
### Buses
The components are connected by a collection of signal lines called a bus. The main buses are:

1. **Address Bus:** Identifies a memory location or an I/O device.
    
2. **Data Bus:** Bidirectional; sends data to or from a component.
    
3. **Control Bus:** Consists of signals that allow the CPU to communicate with memory and I/O devices. Each bus contains multiple wires for parallel transmission.

### Program Execution
Program execution involves the operating system controlling the three main components:

1. The program is loaded from secondary storage (like a disk) into memory via I/O interfaces.
    
2. The operating system schedules the CPU to execute the program.
    
3. The CPU fetches each instruction from memory into the Instruction Register (IR).
    
4. The instruction is decoded in the IR.
    
5. If needed, operands are fetched from memory or registers.
    
6. The instruction is executed.
    
7. Results are stored back in memory or registers.  
    This fetch-decode-execute cycle repeats for all instructions.

### Simple Microcomputer Design
A microcomputer is a computer whose CPU is a microprocessor. It is small and inexpensive, like a personal computer. The main components of a simple microcomputer are a CPU, a clock generator, a decoder, and memory modules.
![[2.2.png]]
### Memory Addressing
The example microcomputer has two memory modules (M0, M1), each containing 8 words of 8 bits each, for a total of sixteen 8-bit words. The 4-bit address bus can address all 16 locations. The three least significant address bits connect directly to the memory modules. The most significant bit (MSB) connects to the decoder's select line (S). When the MSB is 0, M0 is selected (addresses 0-7); when it is 1, M1 is selected (addresses 8-15).

### VHDL Structural View
The system's structure is described in VHDL, which declares components and connects them with signals.
For a simple microcomputer:
![[Noter/Pasted Images/3. Semester/Computerarkitektur og operativsystemer/2/2.3.png]]

- The **declaration part** (before `begin`) defines the input/output ports for each component (CPU, RAM, DEC, CLK) and declares signals (like `M`) for interconnecting them.
    
- The **design part** (after `begin`) uses component instantiation statements to create instances of components and connect their ports to each other or to the declared signals via a `portmap`.
    

### RAM Behavioral View
The behavioral view of the RAM describes its function.
For an 8-by-8 RAM
![[2.4.png]]
- An array variable `memory` represents the 8x8 bit storage.
    
- A `while` loop checks if the RAM is selected (when `CS0` and `CS1` are both '1').
    
- A `case` statement handles read (`RW=0`) and write (`RW=1`) operations. A read copies data from the addressed memory location to the data bus. A write copies data from the data bus into the addressed memory location.
    
- A `process` with a `wait` statement suspends operation until a change on `CS0`, `CS1`, `DATA`, `ADDR`, or `RW` is detected.
    

### CPU Components
The main components of the CPU are:
1. **Datapath:** Contains the Arithmetic Logic Unit (ALU) and various registers.
    
2. **Control Unit:** Governs the operation of the CPU.
    
3. **Register File:** A set of registers.  
    The CPU communicates with memory via the Memory Data Register (MDR) and Memory Address Register (MAR). The Program Counter (PC) holds the address of the next instruction to execute. The Instruction Register (IR) holds an instruction while it is being decoded and executed.
A simple CPU:
![[2.5.png]]

### Instruction Set
The example microcomputer uses a simple instruction set with a 2-bit opcode and operand fields. 
![[operand.png]]
- **LOAD:** Loads a memory word into a register.
    
- **STORE:** Stores a register into a memory word.
    
- **ADDR:** Adds two registers and stores the result in a third register.
    
- **ADDM:** Adds a register and a memory word and stores the result in the register.

![[2.6.png]]

### Instruction Execution Phases
Instruction execution is divided into three main phases:
1. **Instruction Fetch:** Retrieves an instruction from memory and stores it in the IR. The PC is incremented to point to the next instruction.
    
2. **Decode & Operand Fetch (decode_opfetch):** Decodes the instruction in the IR and fetches any required operands from memory or registers.
    
3. **Execute & Write Back (execute_opwrite):** Performs the operation and writes the result to the specified location (register or memory). Some instructions (like LOAD) complete after the decode_opfetch phase.

![[2.8.png]]

### Phase Control
A control process manages the sequence of these phases (inst_fetch -> decode_opfetch -> execute_opwrite -> inst_fetch...) using a state variable (`next_state`) triggered on the clock. 
![[2.9.png]]

### VHDL Process Descriptions
- **Fetch Phase:** Transfers PC to MAR and then to the address bus, requests a memory read, increments the PC, transfers the read data from the bus to MDR, and then from MDR to the IR.
![[2.10.png]]
    
- **Decode/Operand Fetch Phase:** Uses a `case` statement on the opcode (bits 7-6 of IR) to execute the specific routine for each instruction (e.g., initiating memory reads for LOAD/ADDM, memory writes for STORE, or setting up register operands for ADDR).
![[2.11.png]]
    
- **Execute/Write Phase:** Performs the core operation (e.g., addition via the `ADD` function when `add_op` is true) and writes the result to the destination register in the register file.
![[2.12.png]]
### Control Unit
There are two main approaches for realizing a control unit: the hardwired circuit and microprogram design:
#### Hardwired Control Unit
The hardwired approach implements the control unit as a sequential circuit based on different machine states; it issues a series of control signals at each state to govern the computer's operation. For example, the LOAD instruction uses control signals like:
- RW (read/write memory)
- MR (enable memory chip select)
- LD (load data bus to MDR)
- AD (load MAR to address bus)
- LA (load rightmost 4 bits of IR to MAR)
- WR (read/write register file)
- SR0/SR1 (select register address from IR).
![[2.13.png]]

The operation uses a state diagram (e.g., S0 to S5 for LOAD) where transitions between states occur based on inputs (like opcode bits and the decode_opfetch signal), and each state activates specific control outputs.
![[2.14.png]]
This state diagram can be implemented using a Programmable Logic Array (PLA). If the PLA becomes too large, it can be decomposed into smaller PLAs to save chip space.
![[2.15.png]]
A main drawback of the hardwired approach is its lack of flexibility, as changes require circuit modifications. However, due to the short lifetime of modern microprocessors, flexibility is less critical, and most modern microprocessors use hardwired control.

#### Microprogrammed Control Unit
Microprogramming, invented by Wilkes in 1951, solves the inflexibility problem of hardwired design. It resembles a "computer within a computer," using a special memory (microcode storage) to store and execute control information (microinstructions) that trigger the machine's control signals.
![[2.16.png]]
Each machine instruction translates into a sequence of microinstructions. The Microprogram Counter (MPC) points to the next microinstruction. A control circuit can map connections from microcode storage to reduce its size. This approach is more flexible, allowing instructions to be added or changed without circuit modification, but it is potentially slower due to the need to access microcode storage.

### Microinstruction Word Design
Designing a microinstruction format involves balancing four criteria: minimizing microcode storage word size (microword), minimizing microprogram size, maximizing flexibility for changes, and maximizing concurrency of microoperations.  
A microword typically contains a microoperation field and a next address field. There are two extreme design approaches for the microoperation field:

1. **Horizontal Design:** Assigns one bit to each control signal, resulting in a wide microword. This allows any combination of control signals to be invoked simultaneously (maximizing concurrency).
    
2. **Vertical Design:** Uses a few highly encoded subfields (e.g., 2-bit subfields), resulting in a narrower microword. Each subfield can only invoke one control signal from a group at a time, reducing concurrency but saving space.
    

### Horizontal vs. Vertical Microprogramming

A horizontal microprogram for the LOAD instruction uses a bit for each signal (e.g., ST, LA, AD, MR, RW, LD, SR0, SR1, WR, DO), allowing multiple signals to be activated in parallel. 
![[2.17.png]]
A vertical microprogram uses encoded subfields (e.g., a 2-bit F1 field for signals SR0/WR/MR and a 3-bit F2 field for signals SR1/AD/LD/RW/DO/LA/ST), resulting in shorter microwords but requiring decoding and preventing simultaneous activation of signals within the same group.
![[2.18.png]]
**Advantages of Horizontal Microprogramming (HM):**
 - Allows simultaneous execution of any combination of control signals.
    
- Has shorter microinstruction execution time (no decoding delay).  

**Advantages of Vertical Microprogramming (VM):**
- Uses shorter microinstructions, reducing hardware cost and microcode storage size.
    
- Results in a smaller microprogram size.  
    In practice, a mix of both approaches is often chosen. HM is preferred when maximum parallelism is required, while VM is suitable for minimizing hardware cost.

### Instruction Set Design
Instruction set design is a critical aspect of processor design, defining CPU functions and affecting the entire system. Each instruction contains an opcode field and 0 to 3 operand fields. 
Key design questions include: 
1. How many instructions to provide.
2. What types of operations to include.
3. How many and what type of operands to allow.
### Size of Opcode
The number of instructions is directly related to the opcode size. More instructions (a larger opcode) can reduce program size, storage needs, and execution time by replacing sequences of basic instructions with single, more complex ones (e.g., a MULTIPLY instruction instead of ADD/SHIFT sequences). However, increasing opcode size has trade-offs: it can eventually increase overall program storage space, add complexity to processor design (requiring a more extensive control unit), and potentially prevent a single-chip CPU implementation due to the increased number of gates needed. This leads to two competing design philosophies:

- **CISC (Complex Instruction Set Computer):** Emphasizes a large instruction set to reduce the number of instructions per program, aiming to increase overall performance.
    
- **RISC (Reduced Instruction Set Computer):** Emphasizes a small, simple instruction set to reduce the average number of clock cycles per instruction, based on the observation that complex instructions are seldom used. Most RISC instructions execute in a single cycle.
    

### Type of Operation
Maintaining compatibility with previous processors is crucial, leading to a tendency to support existing instructions and add new ones. Most instruction sets include these general operation types:

- **Data Transfer:** Instructions like load, store, and move for copying data between memory and registers.
    
- **Arithmetic:** Instructions for operations like increment, decrement, add, subtract, multiply, and divide.
    
- **Logical:** Instructions for Boolean operations (NOT, AND, OR, XOR) that operate on bits.
    
- **Control:** Instructions like jump, branch, skip, call, return, and halt that control instruction execution flow.
    
- **System:** Privileged instructions reserved for the operating system, such as system calls and memory management instructions.
    
- **Input/Output (I/O):** Instructions like input (read) and output (write) for data transfer between memory and external devices.
    

### Type of Operand Fields
Operand fields provide the address of data or the data itself. Due to limited field size, various addressing modes are used to reference a large memory range:

- **Immediate Addressing:** The operand field contains the actual operand. 
	- Advantage: operand is immediately available (no memory reference). 
	- Disadvantage: operand value is limited by field size.
    
- **Direct Addressing:** The operand field contains the memory or register address of the operand.
	- Advantage: only one memory/register reference is needed. 
	- Disadvantage: address space is limited by operand field size.
    
- **Indirect Addressing:** The operand field contains a pointer to the address of the operand (in memory or a register). 
	- Advantage: large address space (limited by word length, not field size). 
	- Disadvantage: requires two memory references to fetch the operand.
    
- **Displacement Addressing:** Combines direct and register indirect addressing. A register's content is added to a displacement value to produce the operand's address. Common types:
    
    - **Relative Addressing:** The Program Counter (PC) is added to the displacement.
        
    - **Base Register Addressing:** A base register (containing a memory address) is added to the displacement.
        
    - **Indexed Addressing:** A memory address is added to an index register (containing a displacement).
        
- **Stack Addressing:** An implied form of register indirect addressing where a stack register always points to the top of the stack. Instructions operate on the top stack elements without needing explicit operand fields.
### Number of Operands per Operation
The number of operands per instruction significantly impacts machine design:
1. **Zero Operands (Stack Machine):** Operands are implicitly on a stack. Instructions are short but performance can suffer due to lack of general registers and frequent memory accesses (only PUSH/POP access memory).
    
2. **One Operand (Accumulator Machine):** One operand is explicit; the other is implicit in the accumulator register. Instructions are short but performance degrades due to frequent memory access and having only one register.
    
3. **Two or Three Operands:** Machines have multiple registers. They are divided into two types:
    - **Load-Store Design:** Only load and store instructions access memory; all others operate on registers. 
	    - Advantages: fewer memory accesses, short/fixed-length instructions, consistent clock cycles, simple compiler model. 
	    - Disadvantage: inefficient instruction encoding can require more instructions for simple operations.
        
    - **Memory-Register Design:** One operand can be in memory while others are in registers. 
	    - Advantages: data can be accessed directly from memory, fewer instructions needed per program due to more addressing modes. 
	    - Disadvantages: variable-length instructions, more memory accesses, fewer registers.
        
4. **Multiple Memory Addresses:** Instructions can have two or more memory operands.
	- Advantage: avoids using registers for temporary storage. 
	- Disadvantage: results in complex instructions with many memory accesses.