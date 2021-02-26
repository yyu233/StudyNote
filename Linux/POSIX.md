POSIX is the Portable Operating System Interface standard, IEEE Std 1003.1-1988 and related.  These standards, based on the Unix operating system, define a set of programming and command interfaces.  Programs and scripts following these standards are supposed to be easily portable between operating system platforms providing these interfaces.

The POSIX standards imply a model for file system organization: POSIX file systems are organized as directories (folders) containing files (documents).  The POSIX programming API defined a number of operations to work with files, directories, and entire file systems:

* mount, umount the file system
* open, close file descriptor
* write, read to/from file descriptor
* mkdir, rmdir, creat, unlink, link, symlink
* fcntl (byte range locks, etc.)
* stat, utimes, chmod, chown, chgrp
* Path names are case sensitive, components are separated with forward slash (/).

Essentially, this is the API that evolved for Unix and adopted by Linux.
