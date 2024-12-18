Yocto project is an umbrella organisation under the Linux foundation.
The Linux part of the project is based on OpenEmbedded Core.

## Yocto Framework
The Yocto project is a set of templates, tools, and methods that allow of build custom embedded Linux-based systems.

It is an Open Source project initiated by the Linux Foundation in 2010 and is still managed by one of the Founder: Richard Purdie.

## Yocto Background
In 2005 Richard Purdie forked the OpenEmbedded project which was porting Linux to various hand-held computers and he named it `Poky`.
OpenEmbedded and Poky continued to run alongside each other, sharing updates and keeping the architectures more or less in steps.
Until Intel brought out OpenedHand in 2008 (Richard's company) and transferred Poky Linux to the Linux Foundation in 2010, when they formed Yocto project.

Since 2010 the common components of OpenEmbedded and Poky have been combined into a project called OpenEmbedded Core, `oe-core`.

## Yocto Components
- Poky: The Linux distribution reference
- oe-core: The core metadata, which is shared with OpenEmbedded
- BitBake: the task scheduler.
- Hob: A graphical user interface to OpenEmbedded and BitBake.
- Toaster: A web-based interface to OpenEmbedded and BitBake.
- ADT Eclipse: A plug-in for Eclipse that makes it easier to build projects using Yocto Project SDK.
- Documentation: User manuals and developer's guides for each component.
## Releases
There is a release of the Yocto project every six months, in April and October.
They are known by the code name, but it is useful to know the version number of the Yocto project and Poky as well.
https://wiki.yoctoproject.org/wiki/Releases

## Start with Yocto
To know the compatible build system you can find it :
https://docs.yoctoproject.org/
by selecting the release that you need, at the supported Linux Distributions:
https://docs.yoctoproject.org/ref-manual/system-requirements.html#supported-linux-distributions

you can use the project documentation from:
https://docs.yoctoproject.org/brief-yoctoprojectqs/index.html

and you will find that the prerequisites for your build system is to install these packages on your Linux machine.
``` bash
sudo apt install gawk wget git diffstat unzip texinfo gcc build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 python3-subunit zstd liblz4-tool file locales libacl1
sudo locale-gen en_US.UTF-8
```

Then clone Poky
``` bash
git clone git://git.yoctoproject.org/poky
```

Then pick up a stable release and try to build the first image for it.
You can know the LTTS releases from here:
https://wiki.yoctoproject.org/wiki/Releases

``` bash
cd poky
git checkout -b scarthgap origin/scarthgap
```

`Scarthgap` is Yocto project April 2024 Long term support
Then you have to initialise the environment by 
``` bash
source oe-init-build-env
```
This will configure the environment variables and making a default build directory called `build`.

> It is good practice to specify a build directory to have multiple images build at the same time.


## Images
There are 4 common images in yocto:
- **core-image-minimal**: a small console-based system which is useful for test and as the basis for custom images.
- **core-image-minimal-initramfs**: the same, but built as a ramdisk image.
- **core-image-x11**: it support graphics through an X11 server and xterminal terminal app.
- core-image-sato: a full graphical system based on Sato, which is a mobile graphical environment built on X11, and GNOME, and it is including several apps like terminal, editor and file manager.