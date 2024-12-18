Start with embedded rust for ARM bare-metal intro and needed tools, and implement it on qemu for ARM.

## Embedded Rust intro
We are going to cover the embedded rust programming basics by covering the embedded basic programming by rust rather than C/C++ by these steps:
- Getting the Rust embedded tools
- Microcontroller configuration and control.
- Microcontroller peripherals functionality (I/O, PWM, ADC).
- Microcontroller communication protocols (UART, SPI, I2C).
- Multitasking concepts: (cooperative vs preemptive, interrupt, schedulers).
- Control systems concepts: Open-loop control, closed-loop control, sensors, actuators.

## Embedded Rust tools
We are using Linux (Ubuntu) as the host developing environment, so these are the tools required for the development:

- Rust  -V >= 1.51
- itmdump (tool to parse and dump ITM packets)  -v >= 0.3.1 
- cargo-binutils  -v >= 0.1.4
- arm-none-eabi-gdb (Arm GNU debugger) -v >= 7.12
- OpenOCD (Open On-Chip Debugger) -v >= 0.8
- minicom  -v >= 2.7

### Rust
You can install Rust by this instructions [Rust intro](/blog/coding/rust/what-is-rust), or by Rust website
```bash
https://www.rust-lang.org/tools/install
```

### itmdump
Rust itmdump is a tool to parse and dump ARM **ITM** packets, ARM ITM stands for Instrumentation Trace Macrocell, which support **printf** style debugging, and trace OS and application events, for more abour ITM you can find it on [ARM website](https://developer.arm.com/documentation/ddi0314/h/Instrumentation-Trace-Macrocell) 

When you installed Rust you will have a cargo package manager, use it to install itmdump by:
```bash
cargo install itm
itmdump -V
itmdump 0.3.1
```

### cargo-binutils

install **llvm-tools-preview** component first, it provides GNU binutils alternatives like: llvm-nm, llvm-objcopy, llvm-objdump, llvm-size. 
```bash
rustup component add llvm-tools-preview
```
then install **cargo-binutils**
```bash
cargo install cargo-binutils
```

### arm-none-eabi-gdb
for ubuntu -v >= 18.04
```bash
sudo apt install gdb-multiarch
```

### OpenOCD
To install open on-chip debugger on ubuntu -v >= 18.04
```bash
sudo apt install openocd
```

### minicom
To install minicom to communicate with the target throuw UART/USART on ubuntu -v >= 18.04
```bash
sudo apt install minicom
```

## Hello world

We will use cargo to manage the project because we are going to use multiple dependencies and it will be easier to make cargo grape it from crates.io and compile it for us.

run this command to build a project from scratch
```bash
cargo new hello-embedded-rust
```
this will make directory with name hello-embedded-rust.

let's start coding for embedded rust by a simple program to just say hello, inside the **hello-embedded-rust** directory there is another directory called **src**, edit the **main.rs** file and replace it with the next crate.

```rust
#![no_main]
#![no_std]

#[allow(unused)]
use panic_halt as _;

use cortex_m_rt::entry;
use cortex_m_semihosting::{debug, hprintln};

#[entry]
fn main() -> ! {
    hprintln!("Hello, world!").unwrap();

    // exit QEMU
    // NOTE do not run this on hardware; it can corrupt OpenOCD state
    debug::exit(debug::EXIT_SUCCESS);

    loop {}
}
```
As you can see, this crate depends on **panic_halt**, **cortex_m_rt**, and **cortex_m_semihosting**

### Cargo.toml
So to add them to the cargo build, you have to edit the **Cargo.toml** file to add this code, you will find it in the root directory of the project:

```rust
[dependencies]
cortex-m = "0.6.0"
cortex-m-rt = "0.6.10"
cortex-m-semihosting = "0.3.3"
panic-halt = "0.2.0" 
```
This will make **cargo** build know that these packages are dependencies packages and it will automatically download, and compile them for us from [crates.io](https://crates.io/)

### memory.x
memory.x is a file to provide the memory layout of the target device via a linker script named memory.x. which is used during linking by the **Tlink.x**
so you have to make a new file called **memory.x** and add this content to it.
```bash
MEMORY
{
  /* NOTE 1 K = 1 KiBi = 1024 bytes */
  /* TODO Adjust these memory regions to match your device memory layout */
  /* These values correspond to the LM3S6965, one of the few devices QEMU can emulate */
  FLASH : ORIGIN = 0x00000000, LENGTH = 256K
  RAM : ORIGIN = 0x20000000, LENGTH = 64K
}
```

## Cross compile
Now try to cross compile it to Arm architecture, rust has supported Arm developing by provide mutible target:
- **thumbv6m-none-eabi** for Cortex-M0, Cortex-M0+
- **thumbv7m-none-eabi** for Cortex-M3
- **thumbv7em-none-eabi** for Cortex-M4, Cortex-M7
- **thumbv7em-none-eabihf** for Cortex-M4F, Cortex-M7F (with float point unit)

To Cross compile you have to install the target library first, so let's start with Cortex-M0 by 
```bash
rustup target add thumbv6m-none-eabi
```

## Build
Now we are ready to build the project by specify the target, we are going to use **Cortex-M3** for this build, and we are going to export the linking variables for rust by:

```Bash
export RUSTFLAGS="-C link-arg=-Tlink.x"
cargo build --target thumbv7m-none-eabi
```
When it is finished it will make the executable on **target/thumbv7m-none-eabi/debug/hello-embedded-rust** directory.

## qemu-system-arm
To test your hello world you can use the qemu for arm by running this command

```bash
qemu-system-arm \
  -cpu cortex-m3 \
  -machine lm3s6965evb \
  -nographic \
  -semihosting-config enable=on,target=native \
  -kernel target/thumbv7m-none-eabi/debug/hello-embedded-rust
```

- **qemu-system-arm** This is the QEMU emulator. There are a few variants of these QEMU binaries; this one does full system emulation of ARM machines hence the name.

- **-cpu cortex-m3** This tells QEMU to emulate a Cortex-M3 CPU. Specifying the CPU model lets us catch some miscompilation errors: for example, running a program compiled for the Cortex-M4F, which has a hardware FPU, will make QEMU error during its execution.

- **-machine lm3s6965evb** This tells QEMU to emulate the LM3S6965EVB, a evaluation board that contains a LM3S6965 microcontroller.

- **-nographic** This tells QEMU to not launch its GUI.

- **-semihosting-config (..)** This tells QEMU to enable semihosting. Semihosting lets the emulated device, among other things, use the host stdout, stderr and stdin and create files on the host.

- **-kernel $file** This tells QEMU which binary to load and run on the emulated machine.

## Automate the config
There is a conventional way to make all this configuration run by cargo by making a **.cargo** dirctory, and inside it make a file call it **config** and add the configuration to it
```bash
mkdir .cargo
nano config
```

``` bash
[target.thumbv7m-none-eabi]
runner = "qemu-system-arm -cpu cortex-m3 -machine lm3s6965evb -nographic -semihosting-config enable=on,target=native -kernel"

rustflags = [
  # LLD (shipped with the Rust toolchain) is used as the default linker
  "-C", "link-arg=-Tlink.x",
]

[build]
target = "thumbv7m-none-eabi"        # Cortex-M3
```
After this you can just use
``` bash
cargo build
```
for building the project, and
```bash 
cargo run
```
to build the project and run it for qemu.
