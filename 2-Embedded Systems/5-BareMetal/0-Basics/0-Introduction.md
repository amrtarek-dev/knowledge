**Bare metal development** involves writing software that runs directly on a microcontroller or processor without an operating system (OS). This approach offers full control over hardware resources but requires manual management of tasks typically handled by an OS, such as memory, I/O, and peripherals. Bare metal programming is common in embedded systems, real-time applications, and IoT devices where performance and resource efficiency are critical.

## What is Bare Metal Development?

Bare metal programming involves working directly with hardware, bypassing any OS. It gives developers low-level access to the microcontroller's resources, allowing for efficient, real-time operations, but requires handling tasks like interrupts, memory management, and hardware control manually.

### Key Features:

- **No OS**: The software interacts directly with hardware.
- **Direct Hardware Access**: You manage peripherals like GPIOs, timers, and communication interfaces.
- **Manual Resource Management**: Everything from interrupts to memory allocation must be handled by the developer.

## Steps to Write Bare Metal Software

### 1. Choose the Hardware

Select a microcontroller like ARM Cortex-M, AVR (Arduino), or ESP32 for your project.

### 2. Set Up the Toolchain

- **Compiler**: Use a cross-compiler like GCC.
- **Debugger**: Tools like GDB or platform-specific options (ST-Link, J-Link) help you debug in real-time.
- **Linker**: A linker script arranges the memory layout.

### 3. Write Startup Code

Startup code initializes the system (stack, interrupts, clocks) before jumping to the `main()` function. For ARM, this includes setting up interrupt vectors and system clocks.

### 4. Initialize Hardware Peripherals

Configure peripherals like GPIOs, timers, and communication interfaces by writing directly to hardware registers.

Example (STM32 - ARM Cortex-M):

``` c
RCC->AHB1ENR |= (1 << 0);  // Enable GPIOA clock
GPIOA->MODER |= (1 << 10); // Set PA5 as output
```

### 5. Write Application Logic

Develop the main logic for your project, managing hardware directly. For example, blinking an LED on an STM32:

``` cpp
#include "stm32f4xx.h"  // Device-specific header

void initLED(void) {
    RCC->AHB1ENR |= (1 << 0);  // Enable GPIOA clock
    GPIOA->MODER |= (1 << 10); // Set PA5 as output
}

void delay(volatile uint32_t count) {
    while (count--) {}
}

int main(void) {
    initLED();  // Initialize LED (on PA5)

    while (1) {
        GPIOA->ODR ^= (1 << 5); // Toggle LED
        delay(1000000);
    }
}

```
### 6. Linker Script

The linker script defines where program sections (code, data) reside in memory (Flash, RAM).

### 7. Flash the Program

Firmware flashing is a fundamental process in embedded systems development, enabling you to load new or updated firmware onto microcontrollers and other programmable devices.
The most common methods include **JTAG**, **SWD**, **UART**
- **JTAG** (Joint Test Action Group) is a standard that was originally developed for boundary-scan testing of digital circuits, JTAG typically uses a set of pins such as **TDI** (data input), **TDO** (data output), **TMS** (test mode select), **TCK** (clock), and **TRST** (reset). It provides full access to the microcontroller's internal resources and allows for sophisticated debugging, you typically need a JTAG programmer (such as a J-Link or ST-Link) connected to your development system and the target device. The programmer allows you to access the microcontroller’s memory and load the firmware using appropriate software tools, such as OpenOCD or SEGGER J-Link tools.
- **SWD** (Serial Wire Debug) is an ARM-specific two-wire debugging protocol used to interact with ARM Cortex-M microcontrollers, SWD uses just two main data lines—**SWDIO** (data input/output) and **SWCLK** (clock)—along with optional **RESET** and **GND** lines. Flashing with **SWD** is similar to JTAG but requires an SWD-compatible debug probe. For ARM Cortex-M devices, tools like ST-Link, J-Link, or CMSIS-DAP can be used to interact with the SWD interface. Most IDEs, such as **Keil**, **Eclipse**, or **Visual Studio Code** (with extensions like PlatformIO), support SWD for programming and debugging.
- **UART** (Universal Asynchronous Receiver-Transmitter) is a serial communication protocol primarily used for data transfer between devices, UART is useful for bootloader communication (where a bootloader over UART allows you to flash firmware) and for sending debug information from the MCU to an external terminal. **UART-based flashing** is often performed using a bootloader that listens for a firmware file via a serial connection. Many microcontrollers, particularly those from the ESP32 or STM32 families, support bootloaders that facilitate flashing over **UART**. Tools like **esptool.py** for ESP32 and STM32CubeProgrammer for STM32 devices allow you to send a firmware image over a serial port and write it to flash. For devices like the **ESP32**, the flashing process involves putting the device into bootloader mode by manipulating the **IO0** or **GPIO0** pins, after which you can use a UART-to-USB adapter to send the firmware.

| Feature        | **JTAG**                                          | **SWD**                                             | **UART**                                           |
| -------------- | ------------------------------------------------- | --------------------------------------------------- | -------------------------------------------------- |
| **Purpose**    | Debugging, testing, programming                   | Debugging, programming ARM Cortex-M                 | Serial communication between devices               |
| **Pins**       | 10-20 pins                                        | 4 pins (SWDIO, SWCLK, GND, RESET)                   | 2 main pins (TX, RX), optional GND/VCC             |
| **Speed**      | High speed, but more complex                      | Faster than UART, simpler than JTAG                 | Lower speed, best for basic data transfer          |
| **Complexity** | High (requires specific hardware and setup)       | Low to moderate (designed for ARM Cortex-M)         | Very low, simple communication                     |
| **Use Case**   | Low-level access to MCU for debugging and testing | Efficient debugging and programming for ARM devices | Communication for peripherals, logging, or control |
### 8. Debug and Optimize

Use a hardware debugger (e.g., JTAG) for troubleshooting, and optimize for power efficiency or performance as needed.