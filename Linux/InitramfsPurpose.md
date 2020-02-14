There are only four primary reasons to have an initramfs in the LFS environment: loading the rootfs from a network, loading it from an LVM logical volume, having an encrypted rootfs where a password is required, or for the convenience of specifying the rootfs as a LABEL or UUID.

Many Linux distributions ship a single, generic kernel image that is intended to boot as wide a variety of hardware as possible. The device drivers for this generic kernel image are included as loadable modules, as it is not possible to statically compile them all into the one kernel without making it too large to boot from computers with limited memory or from lower-capacity media like floppy disks.

This then raises the problem of detecting and loading the modules necessary to mount the root file system at boot time (or, for that matter, deducing where or what the root file system is).

To further complicate matters, the root file system may be on a software RAID volume, LVM, NFS (on diskless workstations), or on an encrypted partition. All of these require special preparations to mount.

Another complication is kernel support for hibernation, which suspends the computer to disk by dumping an image of the entire system to a swap partition or a regular file, then powering off. On next boot, this image has to be made accessible before it can be loaded back into memory.

To avoid having to hardcode handling for so many special cases into the kernel, an initial boot stage with a temporary root file system —now dubbed early user space— is used. This root file system would contain user-space helpers that would do the hardware detection, module loading and device discovery necessary to get the real root file system mounted.
