The toolchain is the set of tools that compiles source code into executables that can run on your target device, and includes a compiler, a linker, and run-time libraries.

- Compiler
- Linker
- Run-time libraries
- GCC or Clang are the most likely toolchain options
## GCC Toolchain components
`Binutils` is a binary utilities including assembler and linker ( the components which compile the applications).

`GCC (Gnu Compiler Collection)` which is the compiler it self for our case for C language.

`C library` API based on POSIX definition

## Setting up a toolchain
- Do it manually: download/build/install the component yourself
- Use build system: like Buildroot or Yocto

## Types of Toolchains
- Native Toolchain: Runs on the same system as the target system.
- Cross Toolchain: Runs on a different architecture than the host (cross compiling)

Why cross toolchain? because your host is probably more powerful than the target (faster), or you do not want to include a development tools in your target image (maybe for Image size)

## Gnu toolchain targets
To specify toolchain targets for GNU it prefix the toolchain.
ex:
for QEMU:
- aarch64-none-linux-gnu-gcc
which means
- CPU is arm 64 bit
- Vendor is `none` (support a common set of ARM CPUs)
- Kernel is "linux"
- Operating system is GNU GCC

``` bash
aarch64-none-linux-gnu-gcc -g -Wall -c -o writer.o writer.c
```

## Sysroot
it is the root filesystem of your cross toolchain, it consists of files specific to the target type (Mirrors files on your host root filesystem).
Some files are needed to compile programs, other are needed on the target at runtime.

``` bash
aarch64-none-linux-gnu-gcc -print-sysroot
/usr/local/arm-cross-compiler/install/gcc-arm-10.2.2020.11-x86_64-aarch64-nonw-linux-gnu/bin/../aarch64-none-linux-gnu/libc
```

### Sysroot fs
directories:
- lib: shared objects for C library (on target)
- usr/lib: static library archive files for the C library
- usr/include: Headers for libraries (for instance `<stdio.h>`)
- usr/(s)bin: Utility programs for the cross toolchain.

# Other tools in toolchain
Use all cross toolchain components with the same prefix referenced for gcc
- aarch64-none-linux-gnu-XXXX
	- gcc, g++ (comiler)
	- gdb  (debugger)
	- ld (linker)
- addr2line: Converts program addresses into filenames/numbers for debug.
- objdump: Disassemble object files.
- strip: remove debug tables to make the binary files smaller.
- readelf: Additional information about executables (Object code, location memory, etc.)

## Static vs Dynamic Linking
gcc or g++ always links with glibc, the C library.
- Static linking
	- All library functions and dependencies are pulled from archive and placed in your executable.
		- use it when you have a single application (Busybox)
		- or if you need to run application before the root filesystem is available (driver for example)
- Dynamic linking
	- Linking is done dynamically at runtime, it means that the libraries has to be already in the target platform.
		- use it when you know that the library you are using is already at the target (libc for example)
	- Shared library will be checked by linker in :
		- /lib, /lib64
		- /usr/lib, /usr/lib64
		- content of LD_LIBRARY_PATH environment variables

## Logging and Debugging
Syslog is a deamon (syslogd) that uses configuration file (`/etc/rsyslog.d/*.default`) to configure logging
- Usually writing to files in /var/log
To handle log messages from applications using `syslog()` api calls.

Usage of this utility splitting the log messages into:
- Facilities
	- LOG_USER
	- LOG_DAEMON
	- LOG_LOCAL0 ... LOG_LOCAL7
- Priorities
	- LOG_ERR
	- LOG_WARNING
	- LOG_INFO
	- LOG_DEBUG

To use it 
``` c
# openlog with a facility
openlog(NULL, 0, LOG_USER)

# To log
syslog(LOG_ERR, "Invalid Number of arguments: %d", argc);
```

Result will be in /var/log/syslog