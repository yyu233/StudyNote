The kernel parses parameters from the kernel command line up to “–”; if it doesn’t recognize a parameter and it doesn’t contain a ‘.’, the parameter gets passed to init: parameters with ‘=’ go into init’s environment, others are passed as command line arguments to init. Everything after “–” is passed as an argument to init.

|parameter|	Description|
|----|----|
|init=|	Run specified binary instead of /sbin/init as init process. The systemd-sysvcompat package symlinks /sbin/init to /usr/lib/systemd/systemd to use systemd.|
|init=/bin/sh	|Boot to shell.|
|initrd=|	Specify the location of the initial ramdisk. For UEFI boot managers and EFISTUB, the path must be specified using backslashes (\) as path separators.|
|debug|	Enable kernel debugging (events log level).|
|maxcpus=|	Maximum number of processors that an SMP kernel will bring up during bootup.|
|mem=	|Force usage of a specific amount of memory to be used.|
|netdev=|	Network devices parameters.|
|nomodeset|	Disable Kernel mode setting.|
|nvidia-drm.modeset=|	Enables the proprietary NVIDIA Direct Rendering Manager.|
|panic=|	Time before automatic reboot on kernel panic.|
|resume=|	Specify a swap device to use when waking from hibernation.|
|ro	|Mount root device read-only on boot (default1).|
|root=|	Root filesystem. See init/do_mounts.c for kernel's supported device name formats. Note that an initramfs with udev supports more name formats.|
|rootflags=|	Root filesystem mount options. Useful for setting options that cannot be applied by remounting (i.e. by systemd-remount-fs.service(8)). For example, the discard option of an XFS root volume.|
|rw	|Mount root device read-write on boot.|
|systemd.unit=	|Boot to a specified target.|
|video=	|Override framebuffer video defaults.|
|zswap.enabled|	Enable Zswap.|
