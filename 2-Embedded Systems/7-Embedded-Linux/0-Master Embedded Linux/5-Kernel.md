Kernel is responsible for:
- Manage Resources
- Interface with Hardware
	- Access to all memory addresses
	- Access to all CPU registers
- Provides an API for user space programs.

Linux interaction has two ways:
- From the User space by system calls
- From the hardware by interrupt for the device driver.

Linux Kernel Development:
- Linus Torvalds' Kernel tree:
> https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git

Linux Kernel is GPLv2 license, so if you use the kernel you have to make the source code available.

You may need to share the source code for custom kernel module. (Probably)

## Kernel Directories
- **Arch**: architecture specific files
- **Documentation**
- **drivers**: Hardware support, loadable modules
- **fs**: filesystem
- **include**: `#include` from user/kernel space
- **init**: system initialisation
- **kernel**: core functions - scheduling, locking, timers
- **mm**: Memory Management
- **net**: Network protocols
- **scripts**
- **tools**

## Building Kernel
To build the linux kernel you can use the KConfig
### KConfig
it is a text formated file to control the kernel configuration.
you can find it in `drivers/char/Kconfig`
``` 
menu "Character devices"
[...]
config DEVMEM
	bool "dev/mem virtual device support"
	defautl y
	help
		Say Y here if you want to support the /dev/mem device/
[...]
endmenu
```
There are multiple graphical tool to modify kernel configuration using KConfig files, one of them `make menuconfig`
 you can run it at kernel tree.
 The changes from KConfig are saved in `.config` file in flag format like `CONFIG_DEVMEM=y`

#### KConfig Options
KConfig/menuconfig allows you to specify 3 modes of most drivers:
- Off ` `: not built/included
- On `*`: built in to the kernel
- Module `M`: loadable at runtime

