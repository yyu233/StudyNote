There are 2 files that are used as a kernel symbol table:

/proc/kallsyms
System.map
There. You now know what the System.map file is.

Every time you compile a new kernel, the addresses of various symbol names are bound to change.

/proc/kallsyms is a "proc file" that is created on the fly when a kernel boots up. Actually, it's not really a disk file; it's a representation of kernel data which is given the illusion of being a disk file. If you don't believe me, try finding the filesize of /proc/kallsyms. Therefore, it will always be correct for the kernel that is currently running.

However, System.map is an actual file on your filesystem. When you compile a new kernel, your old System.map has wrong symbol information. A new System.map is generated with each kernel compile and you need to replace the old copy with your new copy.
