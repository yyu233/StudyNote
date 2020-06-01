initrd is a fixed-size block device, which requires to be 'formatted' by a filesystem such as ext2. It sits on /dev/ram0 by default, and cannot be enlarged or shortened.

On the other hand, initramfs is a cpio archive which is simply unpacked during boot to ramfs memory. This memory is of dynamic size and thus can be shortened or enlarged as needed.
