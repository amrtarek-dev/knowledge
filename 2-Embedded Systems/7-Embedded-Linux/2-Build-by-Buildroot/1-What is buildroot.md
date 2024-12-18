
Build root is a builder for root filesystem for embedded system devices.
- Collection of linux packages with build instructions (host and target packages)
- Started in 2001, focuses on simplicity.

## How to start
To start with Buildroot you have to use:
- [The Buildroot User Manual](https://buildroot.org/downloads/manual/manual.html)

Start with installing the Mandatory packages, then getting Buildroot.
You can get Buildroot by:

- git clone git://git.buildroot.net/buildroot
Once you have it change directory to Buildroot and list the `config` directory.
it includes all boards that is supported by default from Buildroot.

For example to build  `stm32mp157a` board default configuration `defconfig`
``` bash
make stm32mp157a_dk1_defconfig
```
This will create a `.config` file that can be build with `make menuconfig`
> note: you have to install ncurses or ncurses-dev to use the menuconfig UI.
```bash
make menuconfig
```

Once you are satisfy with the configuration for the kernel and the RootFileSystem, you can exit and just run
```bash
make
```

Once the build process is done the output is in `output/images`, you will find:
- rootfs.ext2
- sdcard.img
- stm32mp157a-dk1.dtb
- u-boot.stm32
- zImage

You can use `dd` command to make a bit by bit copying:
```bash
sudo dd if=ouput/images/sdcard.img of=/dev/mmcblk2 bs=1M
```
- if: input file
- of: output file
- bs: block size