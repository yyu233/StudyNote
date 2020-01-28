File systems expect to read from and write to block devices, but image files aren’t block devices. Loop devices provide a block device on top of a file (or another block device, optionally with remapping).

There’s no need to consider loop devices when mounting images in many cases because mount takes care of everything for you; but loop devices are still involved. losetup -l -a will show them.
