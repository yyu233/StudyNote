## Mounting File System Automatically ## 

When a Red Hat Enterprise Linux system is newly-installed, all the disk partitions defined and/or created during the installation are configured to be automatically mounted whenever the system boots. However, what happens when additional disk drives are added to a system after the installation is done? The answer is "nothing" because the system was not configured to mount them automatically. However, this is easily changed.
The answer lies in the /etc/fstab file. This file is used to control what file systems are mounted when the system boots, as well as to supply default values for other file systems that may be mounted manually from time to time. Here is a sample /etc/fstab file.

* File system specifier -- For disk-based file systems, either a device file name (/dev/sda1), a file system label specification (LABEL=/), or a devlabel-managed symbolic link (/dev/homedisk)
* Mount point -- Except for swap partitions, this field specifies the mount point to be used when the file system is mounted (/boot)
* File system type -- The type of file system present on the specified device (note that auto may be specified to select automatic detection of the file system to be mounted, which is handy for removable media units such as diskette drives)
* Mount options -- A comma-separated list of options that can be used to control mount's behavior (noauto,owner,kudzu)
* Dump frequency -- If the dump backup utility is used, the number in this field controls dump's handling of the specified file system
* File system check order -- Controls the order in which the file system checker fsck checks the integrity of the file systems
