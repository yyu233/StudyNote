When installing a DICE machine, at least two methods are possible:
installation from customised CD, and
installation over the network via a network boot environment (normally PXE)
Each of these methods uses an appropriate version of a boot-loader from the Linux suite of boot-loaders collectively known as SYSLINUX (relevant versions are ISOLINUX in the case of CD installation, and PXELINUX for network installation via PXE).
Both methods involve an initial BIOS utility to select the boot method, followed by the loading of the relevant type of SYSLINUX boot-loader - which then prompts for installation method or version, and goes on to load the kernel image and hand control over to it.

Once the kernel is loaded and run, it starts the installroot process - which prompts for the type of installation required (source media or OS version), and the machine configuration and installation begins.

During the DICE install phase, GRUB is not used - instead, a SYSLINUX image is loaded (the isolinux boot loader, isolinux.bin, directly from the CD - or the pxelinux boot-loader, pxelinux.0, over the network). The version of isolinux.bin on CD is copied from /usr/lib/syslinux/isolinux.bin (provided by the Redhat RPM syslinux-3.10), and is part of the CD image created by the BuildInstallRoot process.
