In embedded systems, **communication** refers to the transfer of data between different components, such as between microcontrollers, sensors, and external devices.

Communication allows an embedded system to collect, process, and exchange information, either internally (within the system) or externally (with other systems or networks).

## Communication Types
Depend on the physical layer communication categories:
- Wired
- Wireless
And every physical types has 2 main categories:
- Serial communication
- Parallel communication
And every category has communication mode:
- Simplex
- Half-Duplex
- Full-Duplex

### Wired Communication
It involves a physical medium, such as cables or wires, to transmit data between devices. Common examples include copper wires, fiber optic cables, and connectors like USB or Ethernet cables.

### Wireless Communication
It uses electromagnetic waves, such as radio or infrared, to transmit data without physical connections. This enables data exchange over long distances and in applications where mobility and flexibility are essential.

## Communication Protocol
A **communication protocol** is a set of rules that define how data is exchanged between devices in a network. 

In embedded systems and electronics, communication protocols are essential for coordinating the transfer of data between microcontrollers, sensors, actuators, and other devices. 

They establish guidelines for timing, data format, error detection, and data integrity, enabling devices with different architectures and functions to communicate reliably.

Communication protocols fall broadly into two categories: **serial** and **parallel**.
### Serial Communication
In **serial communication**, data is transmitted one bit at a time over a single line or channel, allowing long-distance communication with minimal wiring. Serial communication is slower than parallel but more efficient in terms of wiring and space, making it ideal for many embedded systems.
Examples:
- **UART (Universal Asynchronous Receiver-Transmitter)**: An asynchronous protocol used in serial communication where data is transferred without a shared clock signal. Start and stop bits define each data frame, making it popular in devices where low data transfer rates are acceptable.
    
- **I2C (Inter-Integrated Circuit)**: A synchronous protocol used for short-range communication between devices. It requires two lines: a data line (SDA) and a clock line (SCL). I2C supports multiple devices on the same bus and is widely used in sensors and low-speed devices.
    
- **SPI (Serial Peripheral Interface)**: A synchronous protocol ideal for fast data transfer between a master device and one or more slave devices. It uses multiple lines (MOSI, MISO, SCK, and SS) and is known for its simplicity and high data transfer speed in short-range applications.
### Parallel Communication
In **parallel communication**, multiple bits are sent simultaneously over multiple wires or lines. This type of communication is generally faster than serial but requires more wiring and is usually limited to shorter distances.
Parallel protocols are typically used for high-speed data transfer over short distances, such as within a computer system.
Example:
- **PCI (Peripheral Component Interconnect)** and **Parallel ATA (Advanced Technology Attachment)** are examples of parallel protocols used for connecting peripherals within computers.

### Simplex Communication
It is one-way communication from fixed sender to fixed receiver, like car radio.

### Half-Duplex Communication
It is a Two-way communication, but only one direction is working at a time, like Walkie-talkie

### Full-Duplex Communication
it is a type of data transmission where two devices can send and receive data simultaneously. Unlike **half-duplex** (where devices take turns to communicate) or **simplex** (one-way communication), full-duplex allows for continuous, bidirectional data flow, making it ideal for applications that require real-time or high-speed communication.

| **Type**        | **Description**                                                                        | **Characteristics**                                             | **Common Protocols**                          | **Use Cases**                                                             |
| --------------- | -------------------------------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------- | ------------------------------------------------------------------------- |
| **Wired**       | Communication through physical cables or wires.                                        | Reliable, high data rates, secure, limited mobility.            | UART, SPI, I2C, CAN, Ethernet, RS-232, USB    | Industrial automation, automotive systems, IoT gateways, embedded sensors |
| **Wireless**    | Communication through electromagnetic waves (radio, infrared).                         | Flexible, mobile, can suffer interference, variable data rates. | Wi-Fi, Bluetooth, Zigbee, LoRa, NFC, Cellular | IoT devices, wearable tech, remote monitoring, mobile communication       |
| **Serial**      | Data transmitted bit-by-bit in a sequence over a single data line.                     | Slower than parallel, simple wiring, lower data transfer rate.  | UART, SPI, I2C, RS-232, CAN                   | Long-distance, sensor communication, microcontroller interfacing          |
| **Parallel**    | Multiple bits transmitted simultaneously across multiple data lines.                   | High speed, requires more lines, limited by cable length.       | GPIO, Memory Bus Communication, PATA          | Data transfer within devices, high-speed internal communication           |
| **Full-Duplex** | Data can flow in both directions simultaneously, allowing concurrent send and receive. | Low latency, higher data throughput.                            | UART, SPI, USB, Ethernet, Mobile Phones       | Real-time monitoring, telecommunication, high-speed networks              |
| **Half-Duplex** | Data can flow in both directions but not simultaneously, devices take turns.           | Moderate speed, reduced latency compared to simplex.            | RS-485, CAN                                   | Walkie-talkies, shared communication lines, IoT applications              |
| **Simplex**     | Data flows in only one direction, from sender to receiver.                             | High reliability for unidirectional data flow.                  | Radio Broadcast, Sensors                      | Broadcasting, one-way sensor data, simple controls                        |

