KNX defines **how devices talk to each other**—from the structure of a data telegram to the secure transport of information over IP.

## 1. Telegram Structure

Every piece of communication on a KNX network happens through a **telegram**—a data packet exchanged between devices.
A typical KNX telegram consists of the following parts:
1. **Frame**
    - Defines the start and end of the telegram.
    - Ensures the receiver can recognize when a valid message begins and ends.

2. **Control Field**
    - Indicates priority (system vs user messages).
    - Defines if the telegram is standard, extended, or repeated.
    - Contains flags like “repeat” (for retransmission) or “acknowledge.”

3. **Address Field**
    - Contains both **source address** (who sent it) and **destination address** (who should receive it).
    - Destination can be **individual (point-to-point)** or **group (multicast)**.

4. **Data Field**
    - Holds the payload, e.g., “switch light ON” or “set temperature to 22 °C.”
    - KNX uses standardized **Datapoint Types (DPTs)** for interoperability.

5. **Checksum**
    - A small value at the end used for **error detection**.
    - Ensures the telegram wasn’t corrupted during transmission.

> Example: When a wall switch sends “Turn ON light,” the telegram includes control info, the source (switch), the destination (lamp group), the ON command (payload), and a checksum.


## 2. Group Communication vs Point-to-Point

One of KNX’s strengths is its flexible communication model.
- **Group Communication (Multicast)**
    - The most common in KNX.
    - One telegram can be sent to multiple devices at once.
    - Example: A switch sends “Turn ON” to group address `1/0/1`. All lights in that group respond simultaneously.
    - Efficient for building-wide automation.

- **Point-to-Point (Unicast)**
    - Direct communication between two devices.
    - Example: A presence sensor sends its status only to one specific controller.
    - Used for system messages, device programming, and diagnostics.

## 3. Physical vs Logical Addressing
KNX distinguishes between two types of addressing:
- **Physical Address (Individual Address)**
    - Unique ID of each device (like an IP address).
    - Format: `Area.Line.Device` (e.g., `1.1.25`).
    - Used for commissioning, configuration, and direct communication.
        
- **Logical Address (Group Address)**
    - Represents a function rather than a device.
    - Example: Group address `1/0/1` = “Living Room Lights.”
    - Multiple devices can share the same group address for synchronized behavior.


> Think of **physical address** as a **device’s home address** and **logical address** as a **WhatsApp group** where multiple participants exchange the same message.

## 4. KNX/IP Tunneling vs Routing
As modern installations grow, KNX often integrates with IP networks (Ethernet, Wi-Fi). KNX/IP provides two key modes:

- **KNX/IP Tunneling**
    - Works like a virtual serial cable over IP.
    - Each connection is point-to-point between a PC/ETS software and one KNX/IP interface.
    - Ideal for commissioning, debugging, or single connections.
    - Limitation: Multiple clients need multiple tunnels.
        
- **KNX/IP Routing**
    - Uses **multicast** to forward telegrams between KNX TP lines and IP backbones.
    - More efficient in large projects.
    - Example: A building backbone connects different KNX lines via IP routers.
    - Supports multiple clients without separate tunnels.

## 5. KNX Secure (Data Encryption)
As buildings become smarter and more connected, security is critical. KNX Secure was introduced to protect installations against cyber threats.

It defines two complementary security layers:

- **KNX IP Secure**
    - Encrypts KNX telegrams when transmitted over IP networks.
    - Protects against eavesdropping and unauthorized access.
        
- **KNX Data Secure**
    - Encrypts and authenticates telegrams at the application level.
    - Ensures only authorized devices can interpret or act on messages.
    - Example: A command “Unlock Door” is signed and encrypted so it cannot be forged.
        
Benefits of KNX Secure:
- Prevents replay attacks and data manipulation.
- Guarantees device authentication.
- Ensures integrity and confidentiality.