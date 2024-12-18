
## Load filesystem

there are 2 options to do so:
- initramfs
- block device

### initramfs
It will extract the files into RAM, which could be used to setup your real root filesystem, or load modules to support hardware which is needed to access the root filesystem.

Block device
Which is specify a block device (HDD) which is already supported by the kernel.
Kernel command line with a root = parameter.

## Root filesystem contents
- init: starts the system - usually scripts
- shell: runs shell scripts, handles command prompt.
- deamons: background programs that provide services.
- shared libraries
- configuration files (/etc)
- devices nodes (/dev)
- /proc and /sys pseudo filesystems
- kernel modules (/lib/modules/[kernel version])


> kernel does not know any thing about the root filesystem, only expects the init program, specified in command line.
> It is a design decision to decouple root file system and Kernel

The programs are in the Filesystem Hierarchy Standard (FHS)

## Filesystem Hierarchy Standard
It defines the content of all the different directories in the root filesystem, and how they should be used.
- /bin - programs for all users, used at boot
- /dev - device nodes and other files
- /etc - system configuration files
- /lib - shared libraries
- /proc, /sys - proc and sysfs filesystem
- /sbin - programs for the system administrator, used at boot
- /tmp - temporary files - can be deleted on boot
- /usr, /usr/bin, /usr/sbin - additional programs, libraries, utilities
- /var - files modified at runtime (/var/log) which need to be retained after boot.

## BusyBox
It is a single application (binary application) that implements essential Linux programs, and rather than having multiple executable for linux.
BusyBox is a single executable that does all Linux essential binaries, and in order to under stand which command it should run it uses Symbolic links to tell which program is being requested.

To make it run on the target device, you have to get the shared libraries from the toolchain sysroot by grep on the `program interpreter` flag and `Shared library`
```bash
aarch64-none-linux-gnu-readelf -a /bin/busybox | grep "program interpreter"
aarch64-none-linux-gnu-readelf -a /bin/busybox | grep "Shared library"
```


## Use rootfs with target
there are 3 ways to use the rootfs with a targe:
- Ramdisk: which us a disk image loaded in RAM by the boot loader.
- Disk image: for use with memory (like SD card).
- Network: by Network file system (NFS)