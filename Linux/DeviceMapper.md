The Device Mapper is a kernel driver that provides a framework for volume management. It provides a generic way of creating mapped devices, which may be used as logical volumes. It does not specifically know about volume groups or metadata formats.
The Device Mapper provides the foundation for a number of higher-level technologies. In addition to LVM, Device-Mapper multipath and the dmraid command use the Device Mapper. The application interface to the Device Mapper is the ioctl system call. The user interface is the dmsetup command.
LVM logical volumes are activated using the Device Mapper. Each logical volume is translated into a mapped device. Each segment translates into a line in the mapping table that describes the device. The Device Mapper supports a variety of mapping targets, including linear mapping, striped mapping, and error mapping. So, for example, two disks may be concatenated into one logical volume with a pair of linear mappings, one for each disk. When LVM creates a volume, it creates an underlying device-mapper device that can be queried with the dmsetup command

Functions provided by the device mapper include linear, striped and error mappings, as well as crypt and multipath targets. For example, two disks may be concatenated into one logical volume with a pair of linear mappings, one for each disk. As another example, crypt target encrypts the data passing through the specified device, by using the Linux kernel's Crypto API.

The following mapping targets are available:

* cache – allows creation of hybrid volumes, by using solid-state drives (SSDs) as caches for hard disk drives (HDDs)
* clone – will permit usage before a transfer is complete.
* crypt – provides data encryption, by using the Linux kernel's Crypto API
* delay – delays reads and/or writes to different devices (used for testing)
* era – behaves in a way similar to the linear target, while it keeps track of blocks that were written to within a user-defined period of time
* error – simulates I/O errors for all mapped blocks (used for testing)
* flakey – simulates periodic unreliable behaviour (used for testing)
* linear – maps a continuous range of blocks onto another block device
* mirror – maps a mirrored logical device, while providing data redundancy
* multipath – supports the mapping of multipathed devices, through usage of their path groups
* raid – offers an interface to the Linux kernel's software RAID driver (md)
* snapshot and snapshot-origin – used for creation of LVM snapshots, as part of the underlying copy-on-write scheme
* striped – stripes the data across physical devices, with the number of stripes and the striping chunk size as parameters
* thin  – allows creation of devices larger than the underlying physical device, physical space is allocated only when written to
* zero – an equivalent of /dev/zero, all reads return blocks of zeros, and writes are discarded
