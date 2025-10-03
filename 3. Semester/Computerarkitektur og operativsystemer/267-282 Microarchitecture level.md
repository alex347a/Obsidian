## Complete Mic-1 Microarchitecture Abbreviations Table

|Abbreviation|Stands For|Description / Function|
|---|---|---|
|**MAL**|Micro Assembly Language|High-level language used to write microcode for the Mic-1 microarchitecture|
|**SP**|Stack Pointer|Points to the top of the stack in memory|
|**PC**|Program Counter|Holds address of next byte to fetch from instruction stream|
|**LV**|Local Variables|Pointer to the local variable frame in memory|
|**CPP**|Constant Pool Pointer|Points to the constant pool area in memory|
|**TOS**|Top Of Stack|Register that caches the top word on the stack for faster access|
|**OPC**|OPCode (temporary)|Scratch register used for temporary storage during instruction execution|
|**MAR**|Memory Address Register|Holds memory address for 4-byte data word reads/writes|
|**MDR**|Memory Data Register|Holds data for 4-byte memory reads/writes|
|**MBR**|Memory Buffer Register|1-byte register that holds bytes from the instruction stream (sign-extended)|
|**MBRU**|Memory Buffer Register Unsigned|Unsigned version of MBR (zero-extended)|
|**H**|H register|Temporary holding register for ALU operations|
|**ALU**|Arithmetic Logic Unit|Performs arithmetic and logical operations|
|**MPC**|MicroProgram Counter|Controls sequencing through microinstructions|
|**JAMN**|JAM if Negative|Conditional microcode branch based on negative ALU result|
|**JAMZ**|JAM if Zero|Conditional microcode branch based on zero ALU result|
|**JMPC**|JuMP on Condition|Microcode branch control using MBR|
|**IJVM**|Integer Java Virtual Machine|The Java VM subset implemented by the Mic-1|
|**rd**|Read|Initiates a 4-byte memory read operation|
|**wr**|Write|Initiates a 4-byte memory write operation|
|**fetch**|Fetch|Initiates a 1-byte opcode fetch from instruction stream|
|**OBJREF**|OBJect REFerence|Reference to an object in object-oriented programming|
|**IADD**|Integer ADD|Adds top two integers on stack|
|**ISUB**|Integer SUBtract|Subtracts top two integers on stack|
|**IAND**|Integer AND|Bitwise AND of top two integers on stack|
|**IOR**|Integer OR|Bitwise OR of top two integers on stack|
|**BIPUSH**|Byte Integer PUSH|Pushes a byte onto the stack as an integer|
|**ILOAD**|Integer LOAD|Loads integer from local variable onto stack|
|**ISTORE**|Integer STORE|Stores integer from stack into local variable|
|**WIDE**|WIDE prefix|Modifies following instruction to use 16-bit index instead of 8-bit|
|**LDC_W**|LoaD Constant Wide|Loads constant from constant pool using 16-bit index|
|**IINC**|Integer INCrement|Increments a local variable by a constant value|
|**GOTO**|GOTO instruction|Unconditional branch instruction|
|**IFLT**|IF Less Than|Branches if top of stack is less than zero|
|**IFEQ**|IF EQual|Branches if top of stack equals zero|
|**IF_ICMPEQ**|IF Integer CoMPare EQual|Branches if top two integers on stack are equal|
|**INVOKEVIRTUAL**|INVOKE VIRTUAL method|Invokes a method in object-oriented programming|
|**IRETURN**|Integer RETURN|Returns from method with integer value|
## Key Implementation Notes:
- **MBR vs MBRU**: MBR is sign-extended (used for signed values like in BIPUSH), while MBRU is zero-extended (used for unsigned values like array indices)
- **WIDE prefix**: Modifies ILOAD/ISTORE to use 16-bit indices instead of 8-bit, allowing access to more local variables
- **TOS optimization**: Caches the top stack value to avoid memory reads
- **Main1 loop**: Single microinstruction that handles opcode dispatch and prefetching
- **Conditional branching**: Uses JAMN/JAMZ based on ALU N and Z flags

### Tricks
- **Non-sequential Control Store:** This is a major point. Microinstructions are **not stored consecutively** in memory. The address of the first microinstruction for an opcode (e.g., `POP` at `0x57`) is fixed, but the subsequent instructions in its sequence are stuffed into "holes" between other reserved starting addresses. This is why the `goto` mechanism is so essential and not just a convenience.
- **The Data Path Bottleneck:** The ALU operations are highly constrained. The text explicitly states:
    - `MDR = SP + MDR` is **illegal**.
    - `H = H - MDR` is **illegal**.  
        This is because one operand for addition/subtraction (other than +1/-1) **must** be the H register. The micro assembler must catch these errors.
- **Overlapping Operations for Speed:** The design heavily relies on doing multiple things in a single cycle to avoid wasting time. For example:
    - In `iadd1 (MAR = SP = SP - 1; rd)`, it decrements the stack pointer, writes the new address to MAR, _and_ starts a memory read, all at once.
    - The `Main1` loop (`PC = PC + 1; fetch; goto (MBR)`) increments the PC, starts the fetch of the _next_ opcode, _and_ dispatches to the _current_ opcode's handler, all in one cycle.
### Key Concepts in the Notation (MAL)
The MAL notation is designed to abstract away the painful details of the 36-bit microinstruction word.
- **Imaginary Registers `N` and `Z`:** Writing `Z = TOS` doesn't store a value in a register. It runs `TOS` through the ALU to set the `Z` and `N` condition code flip-flops, which are then used for conditional branching (`if (Z) goto L1`).
- **The `goto (MBR)` Mechanism:** This is the heart of the main dispatch loop. It uses the `JMPC` control bit to OR the value in the `MBR` (the opcode) into the `MPC`, performing a multi-way branch to the start of the corresponding instruction's microcode.
- **Memory Ports:** The distinction between `rd`/`wr` (for the 4-byte data port using `MAR`/`MDR`) and `fetch` (for the 1-byte instruction stream port using `PC`/`MBR`) is critical. They can operate in parallel.
### Specific Instruction Highlights
- **WIDE Prefix Handling:** This is a clever two-level dispatch. The `WIDE` opcode goes to `wide1`, which then does a second multi-way branch by using `goto (MBR OR 0x100)`. This sends `WIDE ILOAD` to address `0x115` instead of `0x15`, where a different code sequence handles the 16-bit index.
- **GOTO's Use of OPC:** The `GOTO` instruction needs the offset to be relative to the address of its _opcode_. Since `PC` has already been incremented by `Main1`, the microcode must save the original `PC` in `OPC` (`goto1: OPC = PC - 1`) to use as the base for the branch calculation.
- **INVOKEVIRTUAL Complexity:** This instruction is the most complex because it builds a new stack frame. It reads two 16-bit header fields from the method (parameter count and local variable count) and uses them to calculate where to store the old `LV` and `PC` (the linkage information) before setting up the new `LV` and `PC`.