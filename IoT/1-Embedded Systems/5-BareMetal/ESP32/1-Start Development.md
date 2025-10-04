Each ESP32 board comes with core features that make them highly adaptable for a wide variety of use cases.
- **Wireless Communication**: Built-in Wi-Fi and Bluetooth.
- **Dual-Core Processor**: For multitasking and intensive computing.
- **Peripherals**: GPIO, ADC, DAC, UART, SPI, I2C, and PWM are supported.
- **Memory Options**: Varying RAM and flash memory configurations, including PSRAM in WROVER models.
- **Low Power Modes**: Multiple sleep modes to save power when idle, which is essential for battery-operated projects.

To start develop with ESP32, the first step is preparing the Development Environment

## ESP32 Setup and Development Environment
There are 3 development environment for ESP32:
1. **Arduino IDE**: Ideal for beginners with ESP32 libraries are available.
2. **PlatformIO**: An alternative IDE with broader library support and integration options, and you can combine it with VS code.
3. **ESP-IDF**: Espressif’s official development framework, offering the most advanced functionalities but with a steeper learning curve.

We will explain the 2nd option which is the VS code with PlatformIO because it is free and cross platform.

## ESP32 Development using PlatformIO and Visual Studio Code
This guide will walk you through installing and setting up PlatformIO with VS Code, writing and uploading a simple program, and addressing common challenges you might encounter along the way.

PlatformIO is a development ecosystem that simplifies working with microcontrollers, especially in VS Code. It provides:
- Easy management of libraries and dependencies
- Support for multiple platforms, including ESP32
- Tools for building, uploading, and debugging code in a single environment

### Prerequisites
To follow along with this guide, make sure you have the following:
1. **Visual Studio Code (VS Code)** – [Download here](https://code.visualstudio.com/).
2. **Python** – PlatformIO requires Python to run, so make sure it’s installed. [Get it here](https://www.python.org/downloads/).
Once these are set up, let’s dive into installing PlatformIO.

### Step 1: Installing PlatformIO in Visual Studio Code
1. **Open VS Code** and navigate to the **Extensions** panel (the square icon on the sidebar or press `Ctrl+Shift+X`).
2. In the search bar, type **PlatformIO IDE**. Click **Install** to add it to VS Code.
3. After installation, PlatformIO will add some new options to the status bar and a new icon on the sidebar.
PlatformIO is now ready to handle ESP32 projects!

### Step 2: Creating Your First Project
1. **Open PlatformIO** by clicking on the PlatformIO icon in the VS Code sidebar.
2. Click **New Project** and fill in the details:
    - **Name**: Choose a project name, such as "ESP32-Blink."
    - **Board**: Select your ESP32 model (e.g., "ESP32 Dev Module").
    - **Framework**: Choose **Arduino** for this project. (PlatformIO also supports ESP-IDF if you prefer more advanced development.)
3. Click **Finish**, and PlatformIO will create a project folder with the necessary setup.
Your new project will include a `src` folder for code, an `include` folder for headers, a `lib` folder for additional libraries, and a `platformio.ini` configuration file.

## Step 3: Writing Code – Making the ESP32 Blink
Let’s start with a simple program to blink the onboard LED. In the `src` folder, open the `main.cpp` file and replace the contents with this code:
``` cpp
#include <Arduino.h>

void setup() {
    pinMode(LED_BUILTIN, OUTPUT); // Set built-in LED as output
}

void loop() {
    digitalWrite(LED_BUILTIN, HIGH); // Turn the LED on
    delay(1000);                     // Wait for a second
    digitalWrite(LED_BUILTIN, LOW);  // Turn the LED off
    delay(1000);                     // Wait for a second
}
```
This program will blink the onboard LED every second. It’s a simple way to test if your development environment is correctly set up.

### Step 4: Building and Uploading Code
1. **Connect Your ESP32** to your computer via USB.
2. **Select the Serial Port**:
    - In the PlatformIO Toolbar at the bottom of VS Code, find the **PlatformIO: Select Serial Port** option, and choose the port for your ESP32 (usually something like COM3 on Windows or `/dev/ttyUSB0` on Linux).
3. **Build and Upload the Code**:
    - Click the checkmark (`✓`) in the PlatformIO Toolbar to **Build** your project.
    - Once it’s successfully built, click the right-facing arrow (`→`) to **Upload** the code to your ESP32.

You should see the onboard LED start to blink once the upload completes.

### Step 5: Using the Serial Monitor for Debugging (Optional)
The Serial Monitor is essential for debugging and monitoring your ESP32. Here’s how to set it up:
1. In the `setup()` function, initialise serial communication by adding `Serial.begin(115200);`.
2. Use `Serial.println("Your message");` to print information to the Serial Monitor.
3. Open the Serial Monitor by clicking the **plug icon** in the PlatformIO Toolbar or selecting **PlatformIO: Monitor**.
Try running this small addition to the blink code to see it in action:
``` cpp
#include <Arduino.h>

void setup() {
    Serial.begin(115200);             // Start serial communication
    pinMode(LED_BUILTIN, OUTPUT);      // Set built-in LED as output
}

void loop() {
    Serial.println("LED ON");          // Print to Serial Monitor
    digitalWrite(LED_BUILTIN, HIGH);   // Turn the LED on
    delay(1000);                       // Wait for a second
    Serial.println("LED OFF");         // Print to Serial Monitor
    digitalWrite(LED_BUILTIN, LOW);    // Turn the LED off
    delay(1000);                       // Wait for a second
}
```
Upload this code, open the Serial Monitor, and observe the messages.


## Customising the Project – Configuration in platformio.ini
PlatformIO’s configuration file, `platformio.ini`, allows you to tailor settings for your project. Here are a few handy tweaks:

- **Changing upload speed**: You can adjust `upload_speed` for faster uploads.
- **Adding libraries**: Specify libraries directly in the `platformio.ini` file or use the PlatformIO library manager to handle dependencies.

Example `platformio.ini` entry for the ESP32 board:
``` ini
[env:esp32dev]
platform = espressif32
board = esp32dev
framework = arduino
upload_speed = 921600
monitor_speed = 115200
```
This configuration sets the board type, upload speed, and monitor speed for faster development and smoother debugging.