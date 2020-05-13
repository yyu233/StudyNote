## The proc filesystem ##

The Linux kernel has two primary functions:     
1. Control access to physical devices     
2. shedule when and how processes interact with the devices     

```/proc/``` directory contains system hardware and running processes information.     
```/proc/``` contains virtual type of file.    

The virtual files are listed as 0 bytes in size. They are constantly updated.    

```/proc/cmdline``` contains parameter information for kernel at start time     
```/proc/devices``` displays the various character and block devices currently configured (not including devices whose modules are not loaded)   
```/proc/ioports``` provides a list of currently registered port regions used for input or output communication with a device    
```/proc/kcore``` this file represents the physical memory of the system and is stored in the core file format. Unlike most /proc/ files, kcore displays a size. This value is given in bytes and is equal to the size of the physical memory (RAM) used plus 4 KB.
The contents of this file are designed to be examined by a debugger, such as gdb, and is not human readable.    
```/proc/locks``` each lock has its own line which starts with a unique number. The second column refers to the class of lock used, with FLOCK signifying the older-style UNIX file locks from a flock system call and POSIX representing the newer POSIX locks from the lockf system call. The third column can have two values: ADVISORY or MANDATORY. ADVISORY means that the lock does not prevent other people from accessing the data; it only prevents other attempts to lock it. MANDATORY means that no other access to the data is permitted while the lock is held. The fourth column reveals whether the lock is allowing the holder READ or WRITE access to the file. The fifth column shows the ID of the process holding the lock. The sixth column shows the ID of the file being locked, in the format of MAJOR-DEVICE:MINOR-DEVICE:INODE-NUMBER . The seventh and eighth column shows the start and end of the file's locked region.    
```/proc/self/``` a link to the currently running process. This allows a process to look at itself without having to know its process ID.

### Why proc filesystem ###

The proc filesystem (procfs) is a special filesystem in Unix-like operating systems that presents information about processes and other system information in a hierarchical file-like structure, providing a more convenient and standardized method for dynamically accessing process data held in the kernel than traditional tracing methods or direct access to kernel memory. 

Details of this process can be obtained by looking at the associated files in the directory for this process, /proc/460. You might wonder how you can see details of a process that has a file size of 0. It makes more sense if you think of it as a window into the kernel. The file doesn't actually contain any data; it just acts as a pointer to where the actual process information resides. 
