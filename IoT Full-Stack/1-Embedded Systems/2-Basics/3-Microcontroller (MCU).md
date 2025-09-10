Microcontroller is the workhorse of industrial electronic and Embedded systems, which is designed for standalone operation.

A self-contained integrated circuit that includes a CPU core, memory (RAM, ROM/Flash), and peripherals (timers, serial communication, analog-to-digital converters, etc.) all on a single chip.

MCUs are ideal for simpler, cost-sensitive embedded applications. Examples: ARM Cortex-M series, AVR, PIC.

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
## 