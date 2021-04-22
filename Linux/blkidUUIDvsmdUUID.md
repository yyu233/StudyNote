

The first one reports the UUID of the ext4 filesystem on the md block device. It helps the system identify the file system uniquely among the filesystems available on the system. That is stored in the structure of the filesystem, that is in the data stored on the md device.

The second one is the UUID of the RAID device. It helps the md subsystem identify that particular RAID device uniquely. In particular, it helps identify all the block devices that belong to the RAID array. It is stored in the metadata of the array (on each member). Array members also have their own UUID (in the md system, they may also have partition UUIDs if they are GPT partitions (which itself would be stored in the GPT partition table), or LVM volumes...).

blkid is a bit misleading, as what it returns is the ID of the structure stored on the device (for those kind of structures it knows about like most filesystems, LVM members and swap devices). Also note that it's not uncommon to have block devices with structures with identical UUIDs (for instance LVM snapshots). And a block device can contain anything, including things whose structure doesn't include a UUID.

So, as an example, you could have a system with 3 drives, with GPT partitioning. Those drives could have a World Wide Name which identifies it uniquely. Let's say the 3 drives are partitioned with one partition each (/dev/sd[abc]1). Each partition will have a GPT UUID stored in the GPT partition table.

If those partitions make up a md RAID5 array. Each will get a md UUID as a RAID member, and the array will get a UUID as md RAID device.

That /dev/md0 can be further partitioned with MSDOS or GPT-type partitioning. For instance, we could have a /dev/md0p1 partition with a GPT UUID (stored in the GPT partition table that is stored in the data of /dev/md0).

That could in turn be a physical volume for LVM. As such it will get a PV UUID. The volume group will also have a VG UUID.

In that volume group, you would create logical volumes, each getting a LV UUID.

On one of those LVs (like /dev/VG/LV), you could make an ext4 filesystem. That filesystem would get an ext4 UUID.

blkid /dev/VG/LV would get you the (ext4) UUID of that filesystem. But as a partition inside the VG volume, it would also get a partition UUID (some partitioning scheme like MSDOS/MBR don't have UUIDs). That volume group is made of members PVs which are themselves other block devices. blkid /dev/md0p1 would give you the PV UUID. It also has a partition UUID in the GPT table on /dev/md0. /dev/md0 itself is made off other block devices. blkid /dev/sda1 will return the raid-member UUID. It also has a partition UUID in the GPT table on /dev/sda.
