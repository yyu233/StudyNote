On Linux, the Docker daemon has support for several different image layer storage drivers: aufs, devicemapper, btrfs, zfs, overlay, overlay2, and fuse-overlayfs.

The aufs driver is the oldest, but is based on a Linux kernel patch-set that is unlikely to be merged into the main kernel. These are also known to cause some serious kernel crashes. However aufs allows containers to share executable and shared library memory, so is a useful choice when running thousands of containers with the same program or libraries.

The devicemapper driver uses thin provisioning and Copy on Write (CoW) snapshots. For each devicemapper graph location – typically /var/lib/docker/devicemapper – a thin pool is created based on two block devices, one for data and one for metadata. By default, these block devices are created automatically by using loopback mounts of automatically created sparse files. Refer to Devicemapper options below for a way how to customize this setup. ~jpetazzo/Resizing Docker containers with the Device Mapper plugin article explains how to tune your existing setup without the use of options.

The btrfs driver is very fast for docker build - but like devicemapper does not share executable memory between devices. Use dockerd -s btrfs -g /mnt/btrfs_partition.

The zfs driver is probably not as fast as btrfs but has a longer track record on stability. Thanks to Single Copy ARC shared blocks between clones will be cached only once. Use dockerd -s zfs. To select a different zfs filesystem set zfs.fsname option as described in ZFS options.

The overlay is a very fast union filesystem. It is now merged in the main Linux kernel as of 3.18.0. overlay also supports page cache sharing, this means multiple containers accessing the same file can share a single page cache entry (or entries), it makes overlay as efficient with memory as aufs driver. Call dockerd -s overlay to use it.

The overlay2 uses the same fast union filesystem but takes advantage of additional features added in Linux kernel 4.0 to avoid excessive inode consumption. Call dockerd -s overlay2 to use it.
