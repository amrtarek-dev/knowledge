**USB (Universal Serial Bus)** is a widely-used standard for connecting, communicating with, and supplying power to devices.

Originally developed in the mid-1990s, USB has become the primary interface for connecting peripherals such as keyboards, mice, printers, storage devices, and more to computers and other digital systems.

- **Plug and play**: Devices connected via USB are typically recognized automatically by the operating system, making setup easy without needing complex configurations. 
- **Hot-Swappable**: USB devices can be connected and disconnected without shutting down the host computer.
- **Power Delivery**: USB cables can provide power to devices, often eliminating the need for separate power adapters. This is especially beneficial for portable devices.

## Operation
**USB (Universal Serial Bus)** operates on a **polling mechanism** to communicate with connected devices, rather than relying on devices to initiate communication.
### Host-Centric Communication
USB uses a **host-controller** model, where the **host** (typically a computer or a main controller in embedded systems) manages all communication.
USB devices (e.g., keyboard, printer, storage device) are **peripherals** that cannot initiate data transfer by themselves. They rely on the host to request data or send commands.

## USB Data Transfer Types
Depending on the type of data a device transmits, USB uses different **transfer types**, each with specific polling intervals:
### Control Transfers
Used for device setup and configuration, these transfers are used to establish and maintain communication between the host and device, and it is usually short and high priority

### Interrupt Transfers
Used for devices requiring low-latency response, such as keyboards and mice.
The host polls interrupt transfer devices at regular intervals to detect any changes (like a key press).

### Bulk Transfers
Used for large data transfers, often found in storage devices like USB flash drives.
Bulk transfers are polled less frequently than interrupt transfers and are handled when the bus is less busy.

### Isochronous Transfers
Used for real-time data, like audio or video streams, where timing is critical, but occasional data loss is acceptable.
The host sets a fixed data rate for polling isochronous devices, but it doesn’t wait for confirmation from the device, as real-time data streaming requires constant flow.

## Communication Workflow
### 1. Device Connection and Enumeration:
   When a USB device is connected, the host detects it and assigns it a unique address.
   The host then queries the device’s descriptors, which provide details like device type, manufacturer, power needs, and supported data transfer types.
### 2. Data Transfer Based on Polling
The host controller schedules polling based on the device type and transfer type. For instance, a keyboard (using interrupt transfers) will be polled very frequently, while a flash drive (using bulk transfers) may be polled only as needed.
If the device has data to send, it responds with data packets. If not, it simply indicates it has no data.
### 3. Power and Bandwidth Management
USB manages power and bandwidth allocation across devices, optimizing the communication to prevent data loss or delays.
USB hubs can further extend this polling, distributing polling signals and power to devices in a hub-and-spoke architecture.

## Versions
### USB 1.0/1.1
Basic speeds for peripherals like keyboards and mice, Up to 12 Mbps (Megabits per second)

### USB 2.0
Improved speeds, allowing connections with higher data needs, like external hard drives, Up to 480 Mbps

### USB 3.0/3.1/3.2
Increased data transfer rates, suitable for high-speed devices, Up to 5 Gbps (Gigabits per second), 10 Gbps, and 20 Gbps, respectively

### USB4
Builds upon Thunderbolt 3, supporting up to 40 Gbps and improving power delivery and data throughput, Up to 40 Gbps

| **USB Version**         | **Communication Type** | **Mode**    | **Description**                                                                                   |
| ----------------------- | ---------------------- | ----------- | ------------------------------------------------------------------------------------------------- |
| **USB 1.0 / 1.1**       | Serial                 | Half-Duplex | Basic USB standard; data flows in one direction at a time.                                        |
| **USB 2.0**             | Serial                 | Half-Duplex | Improved speed, but data still flows in only one direction at a time.                             |
| **USB 3.0 / 3.1 / 3.2** | Serial                 | Full-Duplex | Allows simultaneous two-way communication, increasing data rate and efficiency.                   |
| **USB4**                | Serial                 | Full-Duplex | Uses Thunderbolt 3 technology; supports higher data rates and advanced features like DisplayPort. |
## Connector Type
There are several types of USB connectors, each suited to specific purposes or devices:

### USB-A
The standard rectangular port found on most computers.
### USB-B
Typically used for larger devices like printers.

### Mini-USB
Older mobile devices and small electronics.

### Micro-USB
Widely used for mobile devices before USB-C.

### USB-C
A newer, reversible connector found on most modern devices, supporting higher speeds and power delivery.


## Wiring Diagrams
wiring diagrams for different USB versions and types, showing the evolution of wire configurations from USB 1.0 to USB-C with USB4.

### USB 1.0 / USB 2.0 (Standard-A Connector)
**Type:** USB-A  
**Version:** USB 1.0 / 2.0  
**Wires:** 4 (VCC, D-, D+, GND)
``` markdown
  USB 1.0 / 2.0 Wiring Diagram

  +----------+----------+----------+----------+
  |  Red     |  White   |  Green   |  Black   |
  |  (VCC)   |   (D-)   |   (D+)   |  (GND)   |
  +----------+----------+----------+----------+
```
- **VCC (Red)**: Supplies 5V power to the device.
- **D- (White)** and **D+ (Green)**: Differential data lines for half-duplex communication.
- **GND (Black)**: Ground wire.
### USB 3.0 / USB 3.1 (Standard-A Connector)
**Type:** USB-A  
**Version:** USB 3.0 / 3.1  
**Wires:** 9 (VCC, D-, D+, GND, SSRX+, SSRX-, SSTX+, SSTX-, GND)
``` markdown
  USB 3.0 / 3.1 Wiring Diagram

  +-----------+------------+------------+-------------+
  | Red/(VCC) | White/(D-) | Green/(D+) | Black/(GND) |
  +-----------+------------+------------+-------------+
  +--------------+----------------+
  | Blue/(SSRX-) | Yellow/(SSRX+) |
  +--------------+----------------+
  +----------------+----------------+-------------+
  | Purple/(SSTX-) | Orange (SSTX+) | Black/(GND) |
  +----------------+----------------+-------------+
```
- **SSRX- (Blue)** and **SSRX+ (Yellow)**: SuperSpeed receive data lines.
- **SSTX- (Purple)** and **SSTX+ (Orange)**: SuperSpeed transmit data lines.
- **Additional GND (Black)**: An additional ground pin to support the SuperSpeed lanes.
The **D-** and **D+** lines maintain compatibility with USB 2.0 devices, while the **SuperSpeed** lanes enable full-duplex data transfer.

### USB-C (Supports USB 3.2 and USB4)
**Type:** USB-C  
**Version:** USB 3.2 / USB4  
**Wires:** 12+ (VCC, GND, D-, D+, SSRX+, SSRX-, SSTX+, SSTX-, CC1, CC2, SBU1, SBU2)
``` markdown
  USB-C Wiring Diagram
+----------+----------+----------+----------+
|  VCC     |  D-      |  D+      |  GND     |
+----------+----------+----------+----------+
+----------+----------+----------+----------+
|  SSTX+   |  SSTX-   |  SSRX+   |  SSRX-   |
+----------+----------+----------+----------+
+----------+----------+----------+----------+
|  CC1     |  CC2     |  SBU1    |  SBU2    |
+----------+----------+----------+----------+
```
- **SSTX+ / SSTX-** and **SSRX+ / SSRX-**: SuperSpeed transmit and receive lanes for full-duplex communication.
- **CC1** and **CC2**: Configuration channels for detecting cable orientation, power negotiation, and USB mode selection.
- **SBU1** and **SBU2**: Sideband use channels, used for alternate modes like video output (e.g., DisplayPort).
The **USB-C** connector supports **USB4** with additional capabilities for **higher data rates** (up to 40 Gbps), **video output**, and **power delivery** up to 100W.