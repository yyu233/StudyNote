initrd provides the capability to load a RAM disk by the boot loader. This RAM disk can then be mounted as the root file system and programs can be run from it. Afterwards, a new root file system can be mounted from a different device. The previous root (from initrd) is then moved to a directory and can be subsequently unmounted.

initrd is mainly designed to allow system startup to occur in two phases, where the kernel comes up with a minimum set of compiled-in drivers, and where additional modules are loaded from initrd.

When using initrd, the system typically boots as follows:

1. the boot loader loads the kernel and the initial RAM disk
2. the kernel converts initrd into a “normal” RAM disk and frees the memory used by initrd
3. if the root device is not /dev/ram0, the old (deprecated) change_root procedure is followed. see the “Obsolete root change mechanism” section below.
4. root device is mounted. if it is /dev/ram0, the initrd image is then mounted as root
5. /sbin/init is executed (this can be any valid executable, including shell scripts; it is run with uid 0 and can do basically everything init can do).
6. init mounts the “real” root file system
7. init places the root file system at the root directory using the pivot_root system call
8. init execs the /sbin/init on the new root filesystem, performing the usual boot sequence
9. the initrd file system is removed

Note that changing the root directory does not involve unmounting it. It is therefore possible to leave processes running on initrd during that procedure. Also note that file systems mounted under initrd continue to be accessible.

[Ref](https://man7.org/linux/man-pages/man4/initrd.4.html)
