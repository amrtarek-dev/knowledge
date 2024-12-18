Computer Architecture is a set of rules and methods that describe **the functionality, organization, and implementation** of computer systems.

It is mainly concerned with the interactions between CPU, memory and I/O devices.

### Von Neumann Architecture

```markdown
+-------------------------------------------------------------+
|                     Input / Output Devices                  |
|           [Keyboard]    [Monitor]    [Printer]              |
+-------------------------------------------------------------+
|                      +-------------------+                  |
|                      |     Memory        |                  |
|                      +-------------------+                  |
|       +---------------------------------------------+       |
|       |  Data Bus  |  Address Bus  |  Control Bus   |       |
|       +---------------------------------------------+       |
|                      +-------------------+                  |
|                      |       CPU         |                  |
|                      | +---------------+ |                  |
|                      | | Control Unit  | |                  |
|                      | +---------------+ |                  |
|                      | |     ALU       | |                  |
|                      | +---------------+ |                  |
+-------------------------------------------------------------+
```

It is one of the famous computer architectures.
- Only one memory holds data and program
> Von Neumann bottleneck:
> 	- Instructions can only be done one at a time and can only be carried out sequentially, which will make enhancing performance is very hard.


### Harvard Architecture

```markdown
+-------------------------------------------------------------+
|                     Input / Output Devices                  |
|           [Keyboard]    [Monitor]    [Printer]              |
+-------------------------------------------------------------+
|       +-------------------+     +-------------------+       |
|       | Instruction Memory|     |     Data Memory   |       |
|       +-------------------+     +-------------------+       |
|        +--------------------------------------------+       |
|        |  Data Bus  |  Address Bus  |  Control Bus  |       |
|        +--------------------------------------------+       |
|                      +-------------------+                  |
|                      |       CPU         |                  |
|                      | +---------------+ |                  |
|                      | | Control Unit  | |                  |
|                      | +---------------+ |                  |
|                      | |     ALU       | |                  |
|                      | +---------------+ |                  |
+-------------------------------------------------------------+
```

It is the computer architecture that contains **separate storage and separate buses** for instructions and data.
it is mainly developed to **overcome VonNeumann** bottleneck.
The main advantage that the CPU can access instructions and read/write data at the same time.

## Instruction Set Architecture (ISA)
It describes the **design of a computer** in terms of the basic **Operations** it must support.
It defines:
- The types of instructions to be supported by the processor.
	- (Arithmetic/Logic, Data Transfer, and Branch and Jump Instructions)
- The Maximum length of each type of instruction.
- The Instruction Format of each type of instruction.

An instruction set is a group of commands for a central processing unit (CPU) in machine language.

The term can refer to all possible instructions for a CPU or a subset of instructions to enhance its performance in certain situations.

ISA is classified into:
- RISC: Reduced Instruction Set Computing
- CISC: Complex Instruction Set Computing
- MISC: Minimal Instruction Set Computers
- VLIW: Very long instruction word
- EPIC: Explicitly parallel instruction computing
- OISC: One instruction set computer
- ZISC: Zero instruction set computer

### Reduced Instruction Set Computer (RISC)
Reduced Instruction Set Computer (RISC) is an instruction set architecture (ISA) which has fewer cycles per instruction (CPI) than complex instruction set computer (CISC).

RISC processors are also used in supercomputers such as Summit, which, as of November 2018, is the world's fastest supercomputer as ranked by the TOP500 project.

#### Advanced Virtual RISC (AVR)
AVR microcontroller is manufactured by Atmel corporation in the year 1996. It is based on RISC Instruction set Architecture (ISA) and is also called Advanced Virtual RISC.
AT90S8515 was the initial microcontroller belonging to the AVR family. AVR microcontroller is the most popular category of controller and it is cheap. It is used in many robotic applications.

#### Advanced RISC Micro-controller
ARM micro-controller was introduced by Acorn computer organization and is manufactured by Apple, Nvidia, Qualcomm, Motorola, ST Microelectronics, Samsung Electronics, TI etc.
It is the most popular microcontroller and most industries use it for embedded systems as it provides a large set of features and is good to produce devices with excellent appearances.

### Complex Instruction Set Computer (CISC)
Complex Instruction Set Computer (CISC) is an instruction set architecture (ISA) which has fewer instructions per program than a Reduced instruction set computer (RISC).

### Minimal instruction set computers (MISC)
Minimal instruction set computers (MISC) is a processor architecture with a very small number of basic instruction operations and corresponding opcodes.
As a result of this is a smaller instruction set, a smaller and faster instruction set decode unit, and faster operation of individual instructions. The disadvantage is that smaller instruction set always have more sequential dependencies, reducing instruction-level parallelism.

### Very long instruction word (VLIW)
Very long instruction word (VLIW) is an instruction set architecture designed to exploit instruction level parallelism (ILP).
Central processing units (CPU, processor) mostly allow programs to specify instructions to execute in sequence only, a VLIW processor allows programs to explicitly specify instructions to execute in parallel.
This design is intended to allow higher performance without the complexity inherent in some other designs.

### Explicitly parallel instruction computing (EPIC)
Explicitly parallel instruction computing (EPIC) is an instruction set that permits microprocessors to execute software instructions in parallel by using the compiler, rather than complex on-die circuitry, to control parallel instruction execution.
This was intended to allow simple performance scaling without resorting to higher clock frequencies.


### One instruction set computer (OISC)
One instruction set computer (OISC) is an abstract machine that uses only one instruction obviating the need for a machine language opcode.
OISCs have been recommended as guides in teaching computer architecture and have been used as computational models in structural computing research.

### Zero instruction set computer (ZISC)
Zero instruction set computer (ZISC) is a computer architecture based on pattern matching and the absence of (micro-)instructions in the classical sense.
These chips are known for being thought of as comparable to the neural networks being marketed for the number of "synapses" and "neurons"