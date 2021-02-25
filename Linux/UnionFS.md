Unionfs is a filesystem service for Linux, FreeBSD and NetBSD which implements a union mount for other file systems. It allows files and directories of separate file systems, known as branches, to be transparently overlaid, forming a single coherent file system. Contents of directories which have the same path within the merged branches will be seen together in a single merged directory, within the new, virtual filesystem.

When mounting branches, the priority of one branch over the other is specified. So when both branches contain a file with the same name, one gets priority over the other.

The different branches may be either read-only or read/write file systems, so that writes to the virtual, merged copy are directed to a specific real file system. This allows a file system to appear as writable, but without actually allowing writes to change the file system, also known as copy-on-write. This may be desirable when the media is physically read-only, such as in the case of Live CDs.
