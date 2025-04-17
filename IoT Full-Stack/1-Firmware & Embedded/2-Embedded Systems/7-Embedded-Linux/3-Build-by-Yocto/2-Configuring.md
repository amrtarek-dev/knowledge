the configuration in Yocto start form sourcing the `oe-init-build-env` script which is OpenEmbedded-Initializaing-build-environment
which be default creates a build director called `build`.

## Build directory
All of the configuration, intermediate, and deployable files will be put in this directory.
So its status will be changed before the building process and after the building process.
### Before Building
Initially it contains only one subdirectory named `conf`, which contains the configuration files for the project.
- local.conf: specification for the machine (device)
- bblayers.conf: has a list of directories that contain the layers you use.
- templateconf.cfg: it contains the name of a directory which contains various `conf` files

You should always be sure that you configured the `local.conf` file to have the target machine like `MACHINE ?= "qemuarm"`

### After Building
When it is completed you will have a new directories like:
- **build/download**: contains all sources downloaded for build
- **build/tmp**: contains most of the build artifacts
- **build/tmp/work**: Contains the build directory and the staging area for all components.
- **build/tmp/deploy**: Contains the final binaries to be deployed on the target
	- **deploy/image**"machine name": Contains the bootloader, kernel, and RFS.
	- **deploy/rpm**: contains the RPM packages that went to make up the images.
	- **deploy/licences**: Contains the license files extracted form each package.


## Running
by default Yocto builds QEMU target for the generated image.
To run it make sure you have sourced the `oe-init-build-env` script in the current terminal, and then:
``` bash
runqemu qemuarm
```
Or without graphics
``` bash
runqemu qemuarm nographic
```