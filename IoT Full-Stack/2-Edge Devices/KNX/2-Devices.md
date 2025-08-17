# Devices & Functions

KNX is not only about how devices communicate—it’s about **what those devices do**. The ecosystem covers a wide range of components that enable control, automation, and optimization in buildings. From simple wall switches to advanced logic controllers, every KNX device plays a role in making smart buildings efficient, comfortable, and secure.

This section breaks down KNX devices and their functions.

---

## 1. Input Devices

Input devices are the **senses** of a KNX installation. They collect data from users or the environment and send corresponding telegrams onto the bus.

- **Sensors**
    
    - Measure environmental values such as temperature, humidity, CO₂, or brightness.
        
    - Example: A temperature sensor reports 22.5 °C to the HVAC controller.
        
- **Switches / Push-buttons**
    
    - Classic input method for lights, blinds, and scenes.
        
    - Each button can be assigned to one or multiple group addresses.
        
- **Motion & Presence Detectors**
    
    - Trigger automation when movement is detected.
        
    - Used for lighting control, HVAC optimization, and security.
        
    - Presence detectors go further by detecting occupancy even with minimal motion.
        
- **Weather Stations**
    
    - Provide wind speed, rainfall, brightness, and outdoor temperature.
        
    - Critical for functions like automatic shutter control in strong winds or sunlight tracking.
        

> In essence, **input devices** answer the question: _“What is happening, or what does the user want?”_

---

## 2. Output Devices

Output devices are the **muscles** of the KNX system. They act on commands and directly influence the physical world.

- **Switch Actuators (Relays)**
    
    - Control binary loads such as lights, sockets, or pumps.
        
    - Example: A relay closes its contact when it receives “Switch ON.”
        
- **Dimmers**
    
    - Regulate light intensity.
        
    - Support different dimming technologies (leading-edge, trailing-edge, DALI gateway).
        
    - Example: Smoothly dim LED lights from 100% to 20% brightness.
        
- **HVAC Controllers**
    
    - Manage heating, ventilation, and air conditioning systems.
        
    - Interface with valves, fan coils, floor heating circuits, or thermostats.
        
    - Example: Maintain target temperature based on room sensor input.
        
- **Shutter / Blind Actuators**
    
    - Control motors for blinds, shutters, awnings, or curtains.
        
    - Allow not only “up/down” but also **slat angle control** for daylight management.
        

> Output devices transform telegrams into **real-world actions**.

---

## 3. Advanced Logic Modules

Beyond basic control, KNX allows complex automation via **logic modules** or **logic functions integrated in actuators/controllers**.

- **Scenes**
    
    - Combine multiple commands into one action.
        
    - Example: “Movie Scene” dims lights, closes blinds, and turns on TV.
        
- **Timers & Schedulers**
    
    - Automate events based on time or date.
        
    - Example: Heating reduces at night and resumes in the morning automatically.
        
- **Conditional Logic**
    
    - Executes actions based on “if/then” rules.
        
    - Example: _If presence is detected AND brightness < 200 lux, THEN turn on lights._
        

These modules allow KNX systems to behave **intelligently**, not just reactively.

---

## 4. Energy Management & Metering Integration

With sustainability becoming a priority, KNX supports **energy monitoring and optimization**.

- **Energy Meters**
    
    - Measure electricity, gas, water, or heat consumption.
        
    - Provide real-time data for dashboards or billing.
        
- **Load Management**
    
    - Prioritizes or sheds non-critical loads to avoid peak demand.
        
    - Example: When electric vehicle charging starts, reduce heating temporarily to balance consumption.
        
- **Integration with Renewable Sources**
    
    - KNX can integrate with PV (solar) inverters, battery storage, or smart grid signals.
        
    - Enables intelligent use of self-generated energy.
        

> Energy management transforms KNX from a **comfort system** into a **sustainability tool**.