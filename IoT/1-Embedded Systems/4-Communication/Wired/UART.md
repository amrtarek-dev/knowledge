The **Universal Asynchronous Receiver-Transmitter (UART)** is a hardware communication protocol used for asynchronous serial communication between devices. 
Unlike synchronous protocols such as SPI or I2C, UART does not require a clock signal, making it simpler and more flexible for point-to-point communication. 

## Connection
UART working in one-to-one communication
``` markdown
Device A            Device B 
  (TX)  ------------>  (RX) 
  (RX)  <------------  (TX) 
  (GND) ------------>  (GND)
```
- **TX (Transmit)**: Data is sent from Device A's TX pin to Device B's RX pin.
- **RX (Receive)**: Data is sent from Device B's TX pin to Device A's RX pin.
- **GND (Ground)**: Both devices share a common ground to complete the circuit.

## Protocol
UART functions by sending data bits serially, meaning one bit at a time, over a single wire. It relies on two main pins:

- **TX (Transmit)**: The pin used to send data.
- **RX (Receive)**: The pin used to receive data.

A UART data frame includes the following components:

1. **Start Bit** (1 bit): A low signal (0) indicates the beginning of the frame.
2. **Data Bits** (5-9 bits): The actual data being transmitted. Most commonly, this is 8 bits.
3. **Parity Bit** (1 bit, optional): Used to detect errors during transmission. The parity can be even, odd, or none.
4. **Stop Bits** (1, 1.5, or 2 bits): Signals the end of the frame.

The frame is transmitted in the order of start bit → data bits → optional parity bit → stop bits.

## Communication
**UART** typically operates at TTL levels (0V/3.3V/5V) and it is designed for two-way communication between two devices only, and it supports a wide range of baud rates.
### **Asynchronous Transmission**

- UART does not require a clock signal, both devices (transmitter and receiver) operate independently using the same baud rate to synchronize the data flow.
- Asynchronous communication allows UART to be simple to implement but requires that both sides agree on the timing parameters, such as **baud rate**, **data bits**, **parity**, and **stop bits**.

### **Baud Rate**

The baud rate defines the speed at which data is transmitted. Common baud rates are **9600**, **115200**, and **250000**, though others are also supported. Both transmitting and receiving devices must be set to the same baud rate for reliable communication.

### **Error Detection**

UART provides basic error detection through the optional **parity bit**. Additional error handling mechanisms, such as **checksums** or **protocols**, can be implemented depending on the system requirements.