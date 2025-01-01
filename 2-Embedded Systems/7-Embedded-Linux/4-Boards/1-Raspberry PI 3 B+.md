
To get started, you need a Raspberry Pi 3 Model B, a [5V USB power supply](https://www.jameco.com/z/KSA29A0500300D5-Jameco-ReliaPro-5V-3A-3000mA-Compact-Wall-Adapter-Power-Supply-with-USB-Port-Output-Foldable-Terminals-Charger_2318551.html) of at least 2 amps with a [micro USB cable,](https://www.jameco.com/z/10U2-20126-03-Jameco-Valuepro-3-Foot-micro-USB-Data-Sync-and-Power-Charge-Cable_2135064.html) any standard USB keyboard and mouse, an [HDMI cable](https://www.jameco.com/z/BC-DH006F-JVP-Jameco-ValuePro-DisplayPort-Male-to-HDMI-Male-Cable-4K-with-Latch_2357551.html) and monitor/TV for display, and a micro SD card with the operating system pre-installed. The NOOBS (New Out Of the Box Software) OS is recommended for beginners, and you may choose one of several from the [download page](http://www.raspberrypi.org/downloads/).

This Raspberry Pi 3B pinout diagram will help you become familiar with the layout of the board and get started immersing yourself in your own passion projects.

``` md

+----------------------------------------------------------------------+
| 02 04 06 08 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 |USB-A   |
| 01 03 05 07 09 11 13 15 17 19 21 23 25 27 29 31 33 35 37 39 |2-Ports |
|-------+                                                     +--------+
|DSI.   |         Broadcom                                    |USB-A   |
|Display|         BCM2835                                     |2-Ports |
|-------+                                                     +--------+
|                                                             |Ethernet|
| USB        HDMI OutPort                                     |        |
+----------------------------------------------------------------------+
```

| Pin | Name   | Function            | Pin | Name   | Function                 |
| --- | ------ | ------------------- | --- | ------ | ------------------------ |
| 1   | 3.3V   | Power               | 2   | 5V     | Power                    |
| 3   | GPIO2  | SDA1 (I2C)          | 4   | 5V     | Power                    |
| 5   | GPIO3  | SCL1 (I2C)          | 6   | GND    | Ground                   |
| 7   | GPIO4  | GPCLK0              | 8   | GPIO14 | TXD0 (UART)              |
| 9   | GND    | Ground              | 10  | GPIO15 | RXD0 (UART)              |
| 11  | GPIO17 | General-purpose I/O | 12  | GPIO18 | PCM_CLK, General-purpose |
| 13  | GPIO27 | General-purpose I/O | 14  | GND    | Ground                   |
| 15  | GPIO22 | General-purpose I/O | 16  | GPIO23 | General-purpose I/O      |
| 17  | 3.3V   | Power               | 18  | GPIO24 | General-purpose I/O      |
| 19  | GPIO10 | SPI0_MOSI           | 20  | GND    | Ground                   |
| 21  | GPIO9  | SPI0_MISO           | 22  | GPIO25 | General-purpose I/O      |
| 23  | GPIO11 | SPI0_SCLK           | 24  | GPIO8  | SPI0_CE0_N               |
| 25  | GND    | Ground              | 26  | GPIO7  | SPI0_CE1_N               |
| 27  | ID_SD  | ID EEPROM           | 28  | ID_SC  | ID EEPROM                |
| 29  | GPIO5  | General-purpose I/O | 30  | GND    | Ground                   |
| 31  | GPIO6  | General-purpose I/O | 32  | GPIO12 | PWM0                     |
| 33  | GPIO13 | PWM1                | 34  | GND    | Ground                   |
| 35  | GPIO19 | PCM_FS              | 36  | GPIO16 | General-purpose I/O      |
| 37  | GPIO26 | General-purpose I/O | 38  | GPIO20 | PCM_DIN                  |
| 39  | GND    | Ground              | 40  | GPIO21 | PCM_DOUT                 |