It is the interface between the computer hardware and the user.

Hardware refers to the physical components of a computer.

OS enables computer:
- Run multiple applications at once
- Access external devices like (Printer, Keyboard, mice)
- It helps humans and computers communicate, by providing interface.

OS security:
- Securing files
- Data access
- User authentication
Against:
- Viruses
- Worms
- Malware

**Windows** introduced in 1985 and it is closed source

**macOS** introduced in 1984 and partially open-source 
(macOS's kernel)

**Linux** introduced in 1991 it is open-source.

**ChromeOS** introduced in 2011 it is partially open-source and derived from Chromium OS which is open-source.

Android introduces on 2008 and it is open-source

iOS is introduced in 2007 and it is partially open-source.

## Vulnerabilities

A **legacy operating system** is an operating system that is outdated but still being used. so they’re no longer supported or updated.
and they are vulnerable to the new threats.

it is in industries that use a lot of equipment that requires embedded software—software that’s placed inside components of the equipment.

Up to data OS can be vulnerable:
- MSRC (Microsoft Security Response Center)
	- https://msrc.microsoft.com/update-guide/vulnerability
- Apple Security Updates
	- https://support.apple.com/en-us/HT201222
- Common Vulnerabilities and Exposures (CVE) Report for Ubuntu
	- https://ubuntu.com/security/cves
- Google Cloud Security Bulletin
	- https://cloud.google.com/support/bulletins

## Turn on the computer
- Press the power button
- Special microchip called BIOS is activated (after 2007) it has replaced by UEFI which contain the booting instructions which loading the bootloader.
- Bootloader is responsible for starting the operating system.

BIOS: Basic Input/Output System
UEFI: Unified Extensible Firmware Interface
To enhance the security of the BIOS

Communication from USER to APPLICATION to OS to HARDWARE.

The OS handles resource and memory management to ensure the limited capacity if the computer system is used where it's needed most

## Virtualization
is the process of using software to create virtual representations of various physical machines. The term “virtual” refers to machines that don’t exist physically, but operate like they do because their software simulates physical hardware.

Virtual systems don’t use dedicated physical hardware. Instead, they use software-defined versions of the physical hardware.

This means that a single virtual machine has a virtual CPU, virtual storage, and other virtual hardware. Virtual systems are just code.

- A **virtual machine (VM)** is a virtual version of a physical computer. Virtual machines are one example of virtualization.


One benefit is that virtualization can provide an isolated environment, or a sandbox, on the physical host machine.

> Although using virtual machines is useful when investigating potentially infected machines or running malware in a constrained environment, there are still some risks. For example, a malicious program can escape virtualization and access the host machine. This is why you should never completely trust virtualized systems.

### Hypervisors
Hypervisors help users manage multiple virtual machines and connect the virtual and physical hardware.
Also help with allocating the shared resources of the physical host machine to one or more virtual machines.

## User Interface
A user interface is a program that allows a user to control the functions of the operating system.
- GUI - Graphical User Interface.
- CLI - Command Line interface.

**GUI** is a user interface that uses icons on the screen to manage different tasks on the computer.

**CLI** is a text-based user interface that uses commands to interact with the computer.

CLI is more flexible and more powerful than GUI