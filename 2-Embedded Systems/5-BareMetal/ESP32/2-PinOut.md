
The ESP32 microcontroller has a versatile and complex pin layout that varies slightly depending on the specific model or board type, but the core pin functionality is similar across most versions.

Here’s a general overview of the most important ESP32 pins and their typical functions.
## **ESP32 Pinout Overview**
ESP32 boards usually have between 30 to 40 pins. Here are the primary pin groups you’ll use in projects:

|Pin|Function|Description|
|---|---|---|
|**3V3**|Power|Provides a 3.3V output (for powering sensors and peripherals).|
|**GND**|Ground|Ground pin (connect to the ground of other components).|
|**EN**|Enable|Used to enable or reset the ESP32.|
|**GPIO0**|Boot Mode|Used to put the ESP32 into boot mode (important for programming).|
|**GPIO Pins**|Digital I/O|General-purpose input/output pins; can be used as digital input/output.|
|**Analog Pins (ADC)**|Analog Input|The ESP32 has 18 ADC-enabled pins for reading analog signals (values from 0-3.3V).|
|**DAC Pins**|Digital-to-Analog|ESP32 has two DAC channels (GPIO25, GPIO26) that convert digital values to analog voltages.|
|**PWM Pins**|Pulse Width Modulation|Almost all GPIOs can generate PWM signals, used to control LEDs, motors, etc.|
|**SPI Pins**|Serial Peripheral Interface|GPIO12, GPIO13, GPIO14, GPIO15, and GPIO2 are often used for SPI communication.|
|**I2C Pins**|Inter-Integrated Circuit|Typically, GPIO21 (SDA) and GPIO22 (SCL) are used for I2C communication.|
|**UART Pins**|Serial Communication|Supports multiple UART interfaces; GPIO1 (TX) and GPIO3 (RX) are common for UART0.|
|**Touch Pins**|Capacitive Sensing|The ESP32 has 10 capacitive sensing GPIOs used for touch-sensitive applications.|
|**RTC GPIO Pins**|Real-Time Clock|GPIOs that can be used to wake up the ESP32 from deep sleep (GPIOs 0, 2, 4, 12-15, 25-27, 32-39).|


### **1. ESP32-WROOM Pinout**

``` md                                 
							     ESP-WROOM-32
                                 +----------+
                            EN ---|EN     D23|-~- IO23 (SPI_MOSI/VSPI_MOSI)
          (SensVP/ADC1_0)  I36 ---|VP     D22|-~- IO22 (I2C_SCL)
          (SensVP/ADC1_3)  I39 ---|VIN    TX0|-~- IO01 (U0_TXD/CLK3)
                 (ADC1_6)  I34 ---|D34    RX0|-~- IO03 (U0_RXD/CLK2)
                 (ADC1_7)  I35 ---|D35    D21|-~- IO21 (I2C_SDA)
   (XTAL32/Touch9/ADC1_4) IO32 -~-|D32    D19|-~- IO19 (SPI_MISO/VSPI_MISO)
   (XTAL32/Touch8/ADC1_5) IO33 -~-|D33    D18|-~- IO18 (SPI_SCK/VSPI_CLK)
            (DAC1/ADC2_8) IO25 -~-|D25     D5|-~- IO05 (VSPI_CS)
            (DAC2/ADC2_9) IO26 -~-|D26    TX2|-~- IO17 (U2_TXD)
          (Touch7/ADC2_7) IO27 -~-|D27    RX2|-~- IO16 (U2_RXD)
 (HSPI_CLK/Touch6/ADC2_6) IO14 -~-|D14     D4|-~- IO04 (ADC2_0/Touch0)
(HSPI_MISO/Touch5/ADC2_5) IO12 -~-|D12     D2|-~- IO02 (ADC2_2/Touch2/CS) (LED)
(HSPI_MOSI/Touch4/ADC2_4) IO13 -~-|D13    D15|-~- IO15 (ADC2_3/Touch3/HSPI_CS)
                           GND ---|GND    GND|--- GND
                           VIN ---|VIN    3V3|--- 3.3V
                                 +----------+
								  EN     BOOT
```