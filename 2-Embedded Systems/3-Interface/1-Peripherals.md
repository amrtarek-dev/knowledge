Embedded system peripherals are hardware components that interact with a central processing unit (CPU) or microcontroller (MCU) to extend the functionality by providing additional functions. 
These peripherals interface with the main system to perform specific tasks, such as input, output, communication, or control.

They can be either:
- **internal** (on-chip, integrated within the MCU)
- **external** (connected externally via buses or interfaces like I2C, SPI, UART, etc.).

## Types of Peripherals
### Input / Output peripherals
#### GPIO
General Purpose Input/Output, it is basically peripheral that controls microcontroller **pins**.
- They are grouped into **PORTS**
- Its input and output may be **digital** or **analog**
It is programming using specific registers to enable the microcontroller to interface with external devices like sensors, LEDs, switches, and motors.
**Input:**
- **Buttons/Switches:** Simple components that allow user input, such as starting or stopping a process.
- **Keypads:** Provide multi-key input, often used in security systems or devices requiring numerical entry.
- **Sensors:** Devices that detect and convert physical conditions into electrical signals. Types include:
    - **Temperature Sensors** (e.g., LM35, DHT11)
    - **Pressure Sensors** (e.g., BMP180)
    - **Motion Sensors** (e.g., PIR sensors)
    - **Proximity Sensors** (e.g., ultrasonic sensors)
    - **Light Sensors** (e.g., LDRs, photodiodes)
**Output:**
- **LEDs and Displays:** Visual output devices, such as LEDs for indicators, LCDs for text, and OLEDs for graphical displays.
- **Buzzers/Speakers:** Provide audio feedback or alerts, commonly used for alarms and notifications.
- **Motors:** Mechanical outputs for motion control, including:
    - **DC Motors**
    - **Stepper Motors**
    - **Servo Motors**
### Timers and Counters
Timers are a **special types of registers** that is **incremented** automatically according to the feeding **clock signal**.
It can be used to:
- Generate delays
- Generating Pulse Width Modulation (PWM) signals.
- Counting external events.
- Generate system tick for RTOS.
**Watchdog** timer is one of the timers in the microcontroller that is used to reset the controller if it is **stuck in an unknown state**.
Timers may be 8-bit, 16-bit, or 32-bit size, the more size the more accurate timer is.

**Counters:** Count events or pulses, often used in frequency measurement or digital tachometers.

### ADC (Analog-to-Digital Converter)
Converts analog signals (like voltage from a sensor) to digital values for processing by the MCU.

### DAC (Digital-to-Analog Converter)
Converts digital values to analog signals, can be used to generate analog signals like audio waveforms or controlling motor speed with an analog output.

### PWM (Pulse Width Modulation)
Produces a modulated pulse signal with a varying duty cycle, commonly used for controlling devices like motors and LEDs.

### Communication Peripherals
- **UART (Universal Asynchronous Receiver-Transmitter):** Enables serial communication, often used for debugging and interfacing with other microcontrollers or PCs.
- **SPI (Serial Peripheral Interface):** A high-speed synchronous protocol for communication between microcontrollers and peripheral devices like sensors, displays, and memory chips.
- **I2C (Inter-Integrated Circuit):** A multi-master, multi-slave synchronous communication protocol ideal for connecting multiple devices with different addresses on the same two-wire bus.
- **CAN (Controller Area Network):** Used primarily in automotive and industrial systems for reliable, long-distance communication.
- **USB (Universal Serial Bus):** Common for interfacing with PCs and supporting various data transmission and power functionalities.
- **Ethernet:** Enables networking capabilities, allowing the embedded system to connect to a local network or the internet.
- **Wireless Communication:** Includes Wi-Fi, Bluetooth, Zigbee, LoRa, and other RF communication modules for wireless data transmission.

