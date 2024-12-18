I²C (Inter-Integrated Circuit) is a two-wire, serial communication protocol developed by Philips in the 1980s.

It allows multiple "master" and "slave" devices to communicate, making it suitable for systems where multiple peripherals (e.g., sensors, displays, EEPROMs) need to share a common communication bus.
- Synchronous
- Master-Slave communication bus
- Half-duplex
- 100 Kpbs -> standard mode
- 400 kbps up to 3.4 Mbps -> fast mode

## Connection
I2C is master slave communication
``` markdown
  +3.3v / VCC
      |
	 [R] Pull-up resistor (4.7kΩ)
	  |
SCL --+-------------+-------------+------
SDL --+-------------+-------------+------
      |             |             |
  +--------+     +---------+   +---------+
  | Master |     | Slave 1 |   | Slave 2 |
  +--------+     +---------+   +---------+
      |             |             |
GND --+-------------+-------------+-------
```

- **SCL and SDA lines:** Connect the SCL and SDA pins of the master (e.g., microcontroller) to the corresponding pins on the slave device.
- **Pull-up resistors:** Both SCL and SDA lines need pull-up resistors (e.g., 4.7 kΩ) to ensure proper signal levels.
- **Common ground:** Ensure all devices share a common ground connection.
- Every device has an I2C address (check the datasheet)

## Protocol
I2C using a frame based communication with sequence of sending and receiving to select the slave.
### Step 1: Start Condition
Master pulls SDA low while SCL is high.

``` markdown
SCL: -------|^^^^^^^^^^|-------- 
SDA: -------|___       |--------
```
Communication starts when the master pulls the SDA line low while SCL remains high.
This indicates the beginning of a transmission.
### Step 2 : Address Transmission
Master sends 7-bit slave address + 1 R/W bit.

``` markdown
SCL: _|^|_|^|_|^|_|^|_|^|_|^|_|^|_ 
SDA: --A0--A1--A2--A3--A4--A5--A6--R/W-
```
The master sends a 7-bit address followed by a Read (1) or Write (0) bit. 
The slave whose address matches responds to the master.
### Step 3: Acknowledgment (ACK)
Slave responds by pulling SDA low.

``` markdown
SCL: _|^|_|^|_ 
SDA: -------------|__|
```
After receiving the address, the addressed slave pulls SDA low during the acknowledgment clock pulse.
### Step 4: Data Transfer (8 bits)
Master sends or receives 8 bits of data.

``` markdown
SCL: _|^|_|^|_|^|_|^|_|^|_|^|_|^|_
SDA: --D0--D1--D2--D3--D4--D5--D6--D7--
```
Data is sent in 8-bit packets (bytes) by either the master or slave, depending on the read/write mode. 
Each bit is synchronized with the clock on the SCL line.
### Step 5: Acknowledgment (ACK)
Receiver (master or slave) acknowledges receipt by pulling SDA low.

``` markdown
SCL: _|^|_|^|_ 
SDA: -------------|__|
```
The receiver (master or slave) pulls SDA low to acknowledge successful receipt of a byte.
### Step 6: Stop Condition
Master releases SDA (High) while SCL is high.

``` markdown
SCL: -------|^^^^^^^^^^|-------- 
SDA: -------|       ___|--------
```
The master stops communication by releasing the SDA line while SCL is high, indicating the end of transmission.

> Data changes on the rising edge of SCL.
> Pull-up resistors are necessary to maintain proper voltage levels on the bus.
> Every byte (address or data) is followed by an acknowledgment.

This step-by-step process is repeated for each data exchange, allowing seamless communication between the master and slave devices on the I2C bus.