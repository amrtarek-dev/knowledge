**GPIO** stands for **General-Purpose Input/Output**. It's a type of pin found on microcontrollers and other integrated circuits that can be configured as either an input or output, depending on the application's requirements.

GPIOs are called "general-purpose" because they are not limited to specific tasks; instead, they can serve a wide range of purposes, allowing for customization based on the embedded system’s requirements.

## Modes
### **Input Mode**:
In input mode, GPIO pins read digital signals from external sources, like button presses or sensor readings. 
For example, if you press a button connected to a GPIO input pin, the pin will detect the change in voltage, which the microcontroller interprets as a change in state.
#### Interrupt Capability
When GPIO is in input mode, Some GPIO pins support **interrupts**, which trigger the processor to respond immediately to certain events (e.g., a button press). When an interrupt occurs, the processor can pause its current task to handle the event, then resume where it left off. This feature is particularly useful for low-power applications where the system can sleep until an interrupt wakes it up to perform an action.

### **Output Mode**:
When set as an output, GPIO pins can send signals to other devices. 
For example, an output pin can send a high voltage signal to an LED to turn it on, or a low signal to turn it off.
#### Pull-up and Pull-down Resistors
Many microcontrollers offer internal **pull-up** and **pull-down** resistors that can be enabled on GPIO pins. These resistors help stabilize the pin state when no external device is connected, avoiding undefined or "floating" states that could cause unreliable readings.

- **Pull-up Resistor**: Sets the default state of the pin to high unless overridden.
- **Pull-down Resistor**: Sets the default state of the pin to low unless overridden.

## Uses
GPIO pins enable embedded systems to interact with their environment in versatile and efficient ways. Here are some common applications:

- **Reading Inputs from Buttons or Sensors**: GPIO pins configured as inputs can monitor button presses or sensor signals to gather data, respond to user interactions, or trigger certain actions.
    
- **Controlling LEDs or Motors**: GPIO outputs are often used to control LEDs, motors, relays, and other devices. For instance, you can program a GPIO pin to turn on an LED when a sensor detects a particular condition.