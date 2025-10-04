Build system will make:
- Download source for common packages from upstream
- Apply patches for cross compilation, arch dependent bugs, etc.
- Build Linux components ( Bootloader, kernel, device tree)
- Assemble rootfs in staging area
- Create image files


## Build systems projects
- BuildRoot
	- Easy to use
	- Limited configuration settings
	- Requires full image rebuild
- OpenWrt
	- Focused on networking gear (e.g routers)
	- Package-based updates
- Yocto
	- Steep learning curve
	- Customizable
	- Active community