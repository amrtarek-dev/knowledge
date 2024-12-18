**BitBake** is the build engine and task scheduler that automates the process of compiling, assembling, and creating software packages.

There are 4 components bitbake dealing with:
1. **Images:** End products of the build, such as complete Linux images or packages, which are defined by special recipe types (e.g., `core-image-minimal`).
2. **Layers:** Collections of recipes, configuration files, and other metadata. Layers organize the build metadata by functionality, like board support, applications, or configuration.
3. **Recipes (.bb files):** Define instructions on how to build a specific software component, including where to fetch the source, dependencies, build steps, and packaging.
4. **Tasks and Dependencies:** BitBake breaks down the build process into tasks, such as fetching, configuring, compiling, and installing. It then schedules and runs tasks based on dependencies.

## Images
it is the end products of the build, such as complete linux or packages, there are 4 common images in yocto:
- **core-image-minimal**: a small console-based system which is useful for test and as the basis for custom images.
- **core-image-minimal-initramfs**: the same, but built as a ramdisk image.
- **core-image-x11**: it support graphics through an X11 server and xterminal terminal app.
- core-image-sato: a full graphical system based on Sato, which is a mobile graphical environment built on X11, and GNOME, and it is including several apps like terminal, editor and file manager.

## Layers
The metadata for the Yocto Project is structured into layers, by convention, each with a name beginning with `meta`.
The core layers of the Yocto Project are:
- meta: The OpenEmbedded
- meta-yocto: Metadata specific to the Yocto project (Poky distribution)
- meta-yocto-bsp: The board-support-package for the reference machines that Yocto project supports.

There is a useful list of layers at http://layers.openembedded.org. Here are some examples:
- **meta-angstrom**: The Ångström distribution
- **meta-qt5**: Qt5 libraries and utilities
- **meta-fsl-arm**: BSPs for Freescale ARM-based SoCs
- **meta-fsl-ppc**: BSPs for Freescale PowerPC-based SoCs
- **meta-intel**: BSPs for Intel CPUs and SoCs
- **meta-ti**: BSPs for TI ARM-based SoCs
### Create Layer
Each meta layer has to have at least one configuration file `conf/layer.conf` , 
and should also have a `README` file and a `license`.
to create layer you can use the `yocto-layer` script to create one:
``` bash
cd poky
scripts/yocto-layer create nova

# Please enter the layer priority you'd like to use for the layer: [default: 6]
# Would you like to have an example recipe created? (y/n) [default: n]
# Would you like to have an example bbappend file created? (y/n) [default: n]
# New layer created in meta-nova.
# Don't forget to add it to your BBLAYERS (for details see meta-nova\README).
```
Where `nova` is the layer name, so this will create a new directory with `meta-nova` name, with MIT license in `COPYING.MIT`, and `conf/layer.conf` which looks like:
``` bash
# We have a conf and classes directory, add to BBPATH
BBPATH .= ":${LAYERDIR}"

# We have recipes-* directories, add to BBFILES
BBFILES += "${LAYERDIR}/recipes-*/*/*.bb \
${LAYERDIR}/recipes-*/*/*.bbappend"

BBFILE_COLLECTIONS += "nova"
BBFILE_PATTERN_nova = "^${LAYERDIR}/"
BBFILE_PRIORITY_nova = "6"
```
The last step you need is to add the layer to the image that you want to build by editing the `build/conf/bblayers.conf`
``` bash
LCONF_VERSION = "6"

BBPATH = "${TOPDIR}"
BBFILES ?= ""

BBLAYERS ?= " \
	/home/amr/poky/meta \
	/home/amr/poky/meta-yocto \
	/home/amr/poky/meta-yocto-bsp \
	/home/amr/poky/meta-nova \
	"

BBLAYERS_NON_REMOVABLE ?= " \
	/home/amr/poky/meta \
	/home/amr/poky/meta-yocto \
	"
```

You can list all added layers by running command:
``` bash
bitbake-layers show-layers
```

## Recipes & Tasks
Recipe is a collection of tasks written in a combination of Python and shell code.
which are in the layer directory `/recipes-*/*/*.bb` or `/recipes-*/*/*.bbappend`.
These tasks have names like: 
- do_fetch
- do_unpack
- do_patch
- do_configure
- do_compile
- do_install
- do_build (default)
You can list the recipes tasks by:
``` bash
bitbake -c listtasks core-image-minimal
```
And you can execute specific task by call it without `do_` part
``` bash
bitbake -c fetch busybox
```
Or 
``` bash
bitbake -c fetchall core-image-minimal
```
And to clean a built recipe:
``` bash
bitbake -c cleanall busybox
```
### Recipes files
there are 5 types of recipes files:
1. recipes: `.bb` which contains information about building a unit of software (it include the tasks).
2. append: `.bbappend` it appends its instructions to the end of a recipe `.bb` file.
3. include: `.inc` it has the common to several recipes. they using `include`, or `require` which will produce error if the file is not exist.
4. classes: `.bbclass` it has the common but can be inherited and extended by other classes using `inherit` key word (by default all recipes inherited `classes/base.bbclass`)
5. configuration: `.conf` it is for the configuration variables which govern the project's build process. 

For example to make a `Hello world` in the `meta-nova` layer you would create a directory structure like this:
``` bash
meta-nova/recipes-local/helloworld
|-files
| |_ helloworld.c
|_ helloworld_1.0.bb
```
Usually the recipe files are named `<package-name>_version.bb` ,like we can see here in `helloworld_1.0.bb` which contains:
``` bash
DESCRIPTION = "A friendly program that prints Hello World!"
PRIORITY = "optional"
SECTION = "examples"

LICENSE = "GPLv2"
LIC_FILES_CHKSUM = "file://${COMMON_LICENSE_DIR}/GPL-
2.0;md5=801f80980d171dd6425610833a22dbe6"

SRC_URI = "file://helloworld.c"
S = "${WORKDIR}"

do_compile() {
	${CC} ${CFLAGS} -o helloworld helloworld.c
}

do_install() {
	install -d ${D}${bindir}
	install -m 0755 helloworld ${D}${bindir}
}
```
The location of source code is set by `SRC_URI`, and the `do_compile` and `do_install` tasks will compile and install the binaries because `${D}` expands to the staging area of the target device and `${bindir}` to the default binary directory `/usr/bin/` in the image.

### Recipe license
Every recipe has a license defined by `LICENSE` in the `*.bb` file, it has the license and its checksum in `LIC_FILES_CHKSUM`.

The license file may be part of the package or you can use the standard license text in `meta/files/common-license` like `LICENSE = "GPLv2"`.

Commercial licenses are disallowed, but you can enable them by:
`LICENSE_FLAGS = "commercial"`
and in your `conf/local.conf`
`LICENSE_FLAGS_ACCEPTED = "commercial"`

### Build Recipe
To build the recipe only you can use
``` bash
# bitbake <recipe_name>
bitbake helloworld
```
You will found the binaries in `tmp/work/cortexa8hf-vfp-neon-poky-linux-gnueabi/helloworld/`, and an installing package `rpm` in `cortexa8hf_vfp_neon/helloworld-1.0-r0.cortexa8hf_vfp_neon.rpm`

To add the recipe (package) to the image you have to add it to the `conf/local.conf` file by
``` bash
IMAGE_INSTALL_append = " helloworld"
```
> the space before the recipe name is mandatory here, because bitbake will append it to the IMAGE_INSTALL variable.

Then build the image by
``` bash
bitbake core-image-minimal
```
You will find it in `tmp/deploy/images/beaglebone/core-image-minimal-beaglebone.tar.bz2` and it is installed in `usr/bin/helloworld`.