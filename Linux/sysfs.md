The sysfs filesystem is a pseudo-filesystem which provides an
       interface to kernel data structures.  (More precisely, the files
       and directories in sysfs provide a view of the kobject structures
       defined internally within the kernel.)  The files under sysfs
       provide information about devices, kernel modules, filesystems,
       and other kernel components.

       The sysfs filesystem is commonly mounted at /sys.  Typically, it
       is mounted automatically by the system, but it can also be
       mounted manually using a command such as:

           mount -t sysfs sysfs /sys

       Many of the files in the sysfs filesystem are read-only, but some
       files are writable, allowing kernel variables to be changed.  To
       avoid redundancy, symbolic links are heavily used to connect
       entries across the filesystem tree.
