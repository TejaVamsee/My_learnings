# ARM ARCHEITECTURE

## Defination
- ARM architecture refers to a family of processor architectures created and licensed by Arm Ltd.
- It follows the RISC (Reduced Instruction Set Computing).It is designed for high performance with minimal power usage.
- Applications like IOT devices, Smart phones and Embedded system.

## Keywords before going to understand the ARM Archtecture  
- Core
- Processor
- RISC AND CISC
- Arm consists like Registors,pipelining,Instruction set

## Core
- A core in ARM architecture is an individual processing element within a CPU that is capable of executing instructions and managing tasks independently.
- Each core contains its own components such as registers, an Arithmetic Logic Unit (ALU), a control unit, an instruction decoder.

## Processor
- A processor is also called as CPU (Central Processing Unit), is the primary part of a computer or device responsible for carrying out calculations, running instructions, and controlling the movement of data.
- The processor is the entire CPU unit, which may contain either a single core or multiple cores. Besides the cores, it also includes other components such as cache memory and control units.
- Multi-core CPUs: ARM processors often come with 2, 4, 6, or 8 cores (or more in high-end devices) to increase performance.

## ARM Architecture Components
- Registors
- Instruction Set
- Pipelining
- Memory Management Unit (MMU)
- Interupts and Exceptions

### Registors
- Registers are small, high-speed storage units within the CPU that temporarily store data while instructions are being executed.
- In ARM processors, there are usually 16 general-purpose registers labeled R0 through R15 and 4 special purpose registors.
- Special Registors are:
  
   - Program Counter (PC): Contains the address of the next instruction to be executed.
   - Link Register (LR): Holds the return address during function calls.
   - Stack Pointer (SP): Points to the current position in the stack.
   - Current Program Status Register (CPSR): Stores various status flags and control bits, such as the zero and carry flags.

### Instruction Set
- ARM uses a RISC (Reduced Instruction Set Computing) instruction set.Instructions are mostly fixed-length (32-bit), allowing simple and fast decoding.
- Instructions performs the operations like Data processing (arithmetic, logical), Data transfer (load/store),Branching (conditional/unconditional jumps) etc..

### Pipelining 
- ARM processors use pipeline architecture to improve instruction throughput.
- Pipelining splits instruction execution into multiple stages such as:
    - Fetch (get instruction from memory)
    - Decode (interpret the instruction)
    - Execute (perform the operation)
    - Memory access (read/write data if needed)
    - Write-back (store results in registers)
- This allows multiple instructions to be processed simultaneously executes multiple instructions in parallel at different stages(fetch, decode, execute), speeding up overall execution.

### Memory Mangement Unit
- ARM includes a Memory Management Unit (MMU) for virtual memory and memory protection.
- MMU is going to extract the page numbers from page table
- With the help of page no and offset gives the corresponding physical frame address.
