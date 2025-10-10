
| Abbreviation      | Stands For                    | Description / Function                                                      |
| ----------------- | ----------------------------- | --------------------------------------------------------------------------- |
| **MAL**           | Micro Assembly Language       | High-level language used to write microcode for the Mic-1 microarchitecture |
| **SP**            | Stack Pointer                 | Points to the top of the stack in memory                                    |
| **PC**            | Program Counter               | Holds address of next byte to fetch from instruction stream                 |
| **LV**            | Local Variables               | Pointer to the local variable frame in memory                               |
| **CPP**           | Constant Pool Pointer         | Points to the constant pool area in memory                                  |
| **TOS**           | Top Of Stack                  | Register that caches the top word on the stack for faster access            |
| **OPC**           | OPCode (temporary)            | Scratch register used for temporary storage during instruction execution    |
| **MAR**           | Memory Address Register       | Holds memory address for 4-byte data word reads/writes                      |
| **MDR**           | Memory Data Register          | Holds data for 4-byte memory reads/writes                                   |
| **MBR**           | Memory Byte Register          | 8-bit register that holds bytes from the instruction stream (sign-extended) |
| **MBRU**          | Memory Byte Register Unsigned | Unsigned version of MBR (zero-extended) 32-bit.                             |
| **H**             | H register                    | Temporary holding register for ALU operations                               |
| **ALU**           | Arithmetic Logic Unit         | Performs arithmetic and logical operations                                  |
| **MPC**           | MicroProgram Counter          | Controls sequencing through microinstructions                               |
| **JAMN**          | JAM if Negative               | Conditional microcode branch based on negative ALU result                   |
| **JAMZ**          | JAM if Zero                   | Conditional microcode branch based on zero ALU result                       |
| **JMPC**          | JuMP on Condition             | Microcode branch control using MBR                                          |
| **IJVM**          | Integer Java Virtual Machine  | The Java VM subset implemented by the Mic-1                                 |
| **rd**            | Read                          | Initiates a 4-byte memory read operation                                    |
| **wr**            | Write                         | Initiates a 4-byte memory write operation                                   |
| **fetch**         | Fetch                         | Initiates a 1-byte opcode fetch from instruction stream                     |
| **OBJREF**        | OBJect REFerence              | Reference to an object in object-oriented programming                       |
| **IADD**          | Integer ADD                   | Adds top two integers on stack                                              |
| **ISUB**          | Integer SUBtract              | Subtracts top two integers on stack                                         |
| **IAND**          | Integer AND                   | Bitwise AND of top two integers on stack                                    |
| **IOR**           | Integer OR                    | Bitwise OR of top two integers on stack                                     |
| **BIPUSH**        | Byte Integer PUSH             | Pushes a byte onto the stack as an integer                                  |
| **ILOAD**         | Integer LOAD                  | Loads integer from local variable onto stack                                |
| **ISTORE**        | Integer STORE                 | Stores integer from stack into local variable                               |
| **WIDE**          | WIDE prefix                   | Modifies following instruction to use 16-bit index instead of 8-bit         |
| **LDC_W**         | LoaD Constant Wide            | Loads constant from constant pool using 16-bit index                        |
| **IINC**          | Integer INCrement             | Increments a local variable by a constant value                             |
| **GOTO**          | GOTO instruction              | Unconditional branch instruction                                            |
| **IFLT**          | IF Less Than                  | Branches if top of stack is less than zero                                  |
| **IFEQ**          | IF EQual                      | Branches if top of stack equals zero                                        |
| **IF_ICMPEQ**     | IF Integer CoMPare EQual      | Branches if top two integers on stack are equal                             |
| **INVOKEVIRTUAL** | INVOKE VIRTUAL method         | Invokes a method in object-oriented programming                             |
| **IRETURN**       | Integer RETURN                | Returns from method with integer value                                      |
