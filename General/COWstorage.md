COW may also be used as the underlying mechanism for snapshots, such as those provided by logical volume management, file systems such as Btrfs and ZFS,[9] and database servers such as Microsoft SQL Server. Typically, the snapshots store only the modified data, and are stored close to the main array, so they are only a weak form of incremental backup and cannot substitute for a full backup.[10] Some systems also use a COW technique to avoid the fuzzy backups, otherwise incurred when any file in the set of files being backed up changes during that backup.

When implementing snapshots, there are two techniques:

    Redirect-on-write or ROW: the original storage is never modified. When a write request is made, it is redirected away from the original data into a new storage area.
    Copy-on-write or COW: when a write request is made, the data are copied into a new storage area, and then the original data are modified.

Despite their names, copy-on-write usually refers to the first technique. COW does two data writes compared to ROW's one; it is difficult to implement efficiently and thus used infrequently.

The copy-on-write technique can be used to emulate a read-write storage on media that require wear leveling or are physically write once read many.

The qcow2 (QEMU copy on write) disk image format uses the copy-on-write technique to reduce disk image size.

Some live CDs (and live USBs) use copy-on-write techniques to give the impression of being able to add and delete files in any directory, without actually making any changes to the CD (or USB flash drive). 
