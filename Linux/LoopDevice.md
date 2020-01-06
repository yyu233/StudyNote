In Unix-like operating systems, a loop device, vnd (vnode disk), or lofi (loop file interface) is a pseudo-device that makes a file accessible as a block device.

Before use, a loop device must be connected to an existing file in the filesystem. The association provides the user with an API that allows the file to be used in place of a block special file (cf. device file system). Thus, if the file contains an entire file system, the file may then be mounted as if it were a disk device.

Files of this kind are often used for CD ISO images and floppy disk images. Mounting a file containing a filesystem via such a loop mount makes the files within that filesystem accessible. They appear in the mount point directory.

A loop device may allow some kind of data elaboration during this redirection. For example, the device may be the unencrypted version of an encrypted file. In such a case, the file associated with a loop device may be another pseudo-device. This is mostly useful when this device contains an encrypted file system. If supported, the loop device is in this case the decrypted version of the original encrypted file and can therefore be mounted as if it were a normal filesystem
