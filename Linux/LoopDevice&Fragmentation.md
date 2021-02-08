0

Vaguely described, a loop mount redirects the mount as a "loop device".

A "loop device" is effectively representative of a physical partition (which typically represents sequential device blocks) but must be interpreted through the filesystem on which the image resides in a potentially fragmented state.

Unlike a physical partition, the underlying filesystem must be consulted for each block read. It's less efficient, though more convenient, and allows for nested filesystems of varying filesystem types.

A mount -o loop is not technically identical to a mount operation any more than using swapon for a swap file is identical to using swapon for a swap partition.

On an actual partition, reads and writes are restricted to physical partition/cylinder boundaries. Fragmentation is obfuscated by the partition's filesystem.

In a looped image, fragmentation is hidden behind an apparently sequential mount. The underlying filesystem handles file fragmentation and presents a sequential "partition".

This becomes more apparent in the case of encrypted or compressed disk images like squashfs. In such cases, said image blocks are accessed via the underlying filesystem and then processed through the applicable compression (or encryption) API to present an apparently sequential set of device blocks.

In short, a "block device" is expected to be a sequential list of "device blocks". The special device created by a loop mount pretends that potentially non-sequential device blocks of varying sizes are sequential device blocks of a predetermined size.
