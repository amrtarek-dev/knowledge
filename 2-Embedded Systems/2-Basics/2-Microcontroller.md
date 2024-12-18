Microcontroller is the workhorse of industrial electronic and Embedded systems, which is designed for standalone operation.

Microcontrollers are often referred to as **single chip** devices or **single chip computers**

- Microcontroller is consisted of:
	- CPU (8-bit, 16-bit, 32-bit, 64-bit)
	- Memory (RAM, ROM, EEPROM, and Flash)
	- Peripherals (i/o, UART, SPI, I2C, CAN, LIN, ... ) 
	- Buses

``` mermaid
flowchart TD
    A(Microcontroller)
    A --> B(Microprocessor)
    A --> C(Clock Generator)
    A --> D(Memory)
    A --> E(Interrupt Controller)
    A --> F(Peripherals)
    
    B --> B1(ALU)
    B --> B2(Control Unit)
    B --> B3(Register File)

    D --> D1(ROM)
    D --> D2(RAM)
    
    F --> F1(Timers)
    F --> F2(GPIO)
    F --> F3(Serial Communication)
    F --> F4(ADC)
    F --> F5(PWM)
```
## Microprocessor
It is a general purpose CPU, its function is to fetch the instructions from the memory, decode and execute them, so the microprocessor alone is useless.

|     Instruction     | OP-Code             |
| :-----------------: | ------------------- |
| LDI Rd, k (0<K<255) | 1110-kkkk-dddd-kkkk |
|    LDI R10, 255     | 1110-1111-1010-1111 |
- CPU is consisted of:
	- ALU
	- Registers
	- Control unit
	- Interconnections
		- Data bus: data carrying wires
		- Address bus: address carrying.
		- Control bus: read/write control signals carrying wires

### ALU
Arithmetic Logic Unit, is an integrated circuit within a CPU or GPU (Graphics Processing Unit) that performs **arithmetic** and **logic** operations.
- Arithmetic:
	- Addition
	- Subtraction
	- Shifting
- Logic:
	- NOT
	- AND
	- OR
	- XOR

### Registers
Register are the fastest types of memories, it is used to facilitate CPU operations
The are 2 types:
- General Purpose Register (GPR) (R0, R1, .... , R31)
- Special purpose registers:
	- Program counter (PC)
	- Instruction Register (IR)
	- Instruction decoder (ID)
	- Status Register (SREG)
	- Accumulator Register (ACC)
	- Stack Pointer (SP)
	- Index Register (X, Y)

#### General Purpose Register (GPR)
They are available to store any transient data required by the program.
> In general the more registers a CPU has, the faster it can work.
#### Program Counter (PC)
It is the most important CPU register, which holds the **address of the next instruction** in program memory space.

The size of the program counter register is related to the size of the microcontroller program memory.

#### Instruction Register (IR)
It contains the next instruction (Op-Code) to be decoded by the Instruction Decoder

#### Instruction Decoder (ID)
It takes the Op-Code stored in the instruction register and decodes it then tells the CPU what to do for it and enable the components for this operation.

#### Status Register (SREG)
It contains flags represent the status of the last operation to control the following instructions:
- Overflow Flag: it means that the result is too large to fit in the register width.
- Negative flag: the result is negative
- Zero flag: the result is zero
- Carry flag: indicates a carry in the last arithmetic or logical operation.
- Half-carry flag: indicates that a bit carry was produced between the 4-bit halves of the byte operand as a result of the last arithmetic operation.
- Global Interrupt Mask: (Global interrupt status and enabler)

#### Accumulator Register (ACC)
It is a register where saves the intermediate arithmetic and logic results.
it is faster to save the result in this register rather than write it to main memory especially to use it in the next operation.
#### Stack Pointer (SP)
It is a register which holds the memory address of the last location on the stack where the data are stored, 
or the memory of the next available location on the stack to store data.
> It will point to next instruction in case of the POP call and to the next available location (Empty) after push call.

#### Index Registers (X, Y)
It is used in case of the indirect memory access mode.
> accessed address = index register + offset mentioned in the code
 
### Control Unit
The control unit is the circuitry that controls the flow of data through the processor, and coordinates the activities of the other units within it.
In other words it is in charge of the entire instructions (machine) cycle.

#### Instruction lifecycle

``` mermaid
graph TD
    B(Fetch Instruction) --> C(Decode Instruction)
    C --> D(Execute Instruction)
    D --> F(Write Back)
    F --> B
```

Program counter register points to the instruction to be executed.
- Fetching: Fetch the instruction from the memory and store it in the Instruction Register.
- Decoding: decode the instruction into commands
- Executing: ALU execute the instructions.
- Store: Writing the result to the memory.

 Every instruction has:
 - operator code ( which determines what will be done).
 - operands  (which define the data to be used in the operation)
 To access the data the ALU needs to access the memory by one of the addressing mode. 

##### Addressing mode
- **Direct**: The CPU read from the address of the memory in the instruction.
- **Indirect**: The CPU read from the address inside the register you pass in the instruction.
- **Base**: The CPU will read from the address = index register + offset (Passed in the instruction).

#### Pipelining
The instruction lifecycle is sequential, which is a bit slow.
if we supposed that fetch, decode, and execute take **1 clock cycle each**, then to perform **3 instructions we need 9 clock cycles**.

Pipelining is a process of **Arrangement of hardware** elements of the CPU such that its **Overall performance is increased** by making the same clock cycle execute, decode, and fetch.

>Cycle 1: F1
>Cycle 2: ID1, IF2
>Cycle 3: EX1, ID2, IF3
>Cycle 4: STORE1, EX2, ID3, IF4
>Cycle 5: STORE2, EX3, ID4, IF5
....

Pipelining will:
- **Increased Throughput**: Multiple instructions are processed simultaneously, increasing overall instruction throughput.
- **Reduced Latency**: Each stage processes a part of the instruction, reducing the time it takes for each instruction to be completed.
##### Pipelining Hazards
- Structural hazards: it is a resource conflict situation, when more than one instruction tries to access the same resource in the same cycle.
- Data hazards: when instruction depends on result of prior instruction which still in the pipeline.
- Control hazards: Caused by delay between the fetching of instructions and decisions about changes in control flow (branches and jumps).
>Solution to these hazards is by adding delays.
