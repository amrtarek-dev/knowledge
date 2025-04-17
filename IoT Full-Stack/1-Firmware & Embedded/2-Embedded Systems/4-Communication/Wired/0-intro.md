Wired communication in embedded systems involves using physical cables to transmit data between devices or components. It is typically chosen for applications requiring reliable, fast, and secure data transfer in close proximity.

It has 2 types:
- Synchronized Communication
- Unsynchronized Communication

## Synchronized Communication
Synchronized communication requires both the sender and receiver to follow a shared timing signal, often referred to as a clock signal. This clock ensures data is transmitted and received in sync, allowing for higher precision and predictable data transfer rates. Here are some characteristics:

- **Clock Dependency**: Both devices rely on the same clock signal, often provided by a master device. This ensures data integrity as the timing is consistent.
- **Data Rate**: Because of the clock, the data transfer rate can be higher and more reliable, making this approach suitable for real-time systems.
- **Examples**: Protocols such as I2C (Inter-Integrated Circuit) and SPI (Serial Peripheral Interface) are synchronous, using clock lines to synchronize data transmission between devices.

## Unsynchronized Communication

In unsynchronized communication, also known as asynchronous communication, the sender and receiver operate independently without a shared clock signal. Each transmission usually starts with a specific start bit, followed by data bits, and ends with a stop bit. Key features include:

- **Independent Timing**: Devices operate on separate clocks, so they do not need to be in sync continuously. The use of start and stop bits helps establish data boundaries.
- **Data Rate Variability**: Since there’s no shared clock, the data rate is typically lower than synchronized communication and may vary slightly, though it can be quite efficient over longer distances.
- **Examples**: UART (Universal Asynchronous Receiver/Transmitter) communication is asynchronous, commonly used in serial communication where data is transmitted over long distances, such as in RS232 and RS485 standards.

Common wired communication protocols in embedded systems include: