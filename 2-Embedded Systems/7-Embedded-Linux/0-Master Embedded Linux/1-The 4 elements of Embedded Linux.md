Every embedded linux project target is obtaining, customising and deploying these four elements:
- Toolchain
- Bootloader
- Kernel
- Root filesystem

## Toolchain
This consists of the compiler and other tools needed to create code for your target device, every thing else depends on the toolchain.

## Bootloader
This is necessary to initialise the board and to load the Linux Kernel.

## Kernel
This is the heart of the system, managing system resources and interfacing with hardware.

## Root filesystem
This contains the libraries and programs that are run once the kernel has completed its initialisation.
