There are no general principles for the ISA (Intruction Set Archiecture). A microprogram has a state, which is a set of variables that can be accessed by all the functions. For example the PC (Program Counter) is part of the state as it indicates the memory location that contains the next function to be executed. During execution of each instruction the PC is advanced to point to the next instruction that has to be executed. The first field of every instruction is the opcode (operation code) which identifies the instruction. Many also have a field for the operand which tells if a variable has to be accessed which variable it is. This execution model is usually called the fetch-decode-execute-cycle. 

### Data path
the part of the CPU containing the ALU and its inputs and outputs.
![[4.1.png]]
![[4.2.png]]
Nået til side 247