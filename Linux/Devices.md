## Device Files ## 
In Unix-like operating systems, a device file or special file is an interface to a device driver that appears in a file system as if it were an ordinary file. There are also special files in MS-DOS, OS/2, and Microsoft Windows. These special files allow an application program to interact with a device by using its device driver via standard input/output system calls. **Using standard system calls simplifies many programming tasks, and leads to consistent user-space I/O mechanisms regardless of device features and functions.**

Device files usually provide simple interfaces to standard devices (such as printers and serial ports), but can also be used to access specific unique resources on those devices, such as disk partitions. Additionally, device files are useful for accessing system resources that have no connection with any actual device such as data sinks and random number generators.
## Type of Devices ## 

Devices are divided into 2 types: character devices (only serial stream of input/output such as mouse, keyboard) and block devices (accessible randomly such as hard disk, floppy device). 

Block devices has a buffer for requests so that they can choose the best order in which to respond to the requests. This is important in the case of storage devices where it's faster to read or write sectors which are close to each other, rather than those which are further apart. 

Block devices can only accept input and return output in blocks, whereas character devices are allowed to use as many bytes as possible. 

## Registering A Device ##   
eg:   
``` brw-rw----  1 root  disk  3, 1 Jul  5  2000 /dev/hda1 ```    
   
The number 3 is a major number. The major number tells whcih driver handles which device file. The number 1 is a minor number. The minor number is uded only by the driver itself to differentiate which device it's operating on, just in case the driver handles more than one device.    

Registering a device means registering it with the kernel.    

## Unregistering A Device ## 

Check the number of processes that are using the kernel module by looking at the 3rd field of ``` /proc/modules ```. If this number is zero, rmmod will fail. 

## Pseudo Devices ## 

Device nodes on Unix-like systems do not necessarily have to correspond to physical devices. Nodes that lack this correspondence form the group of pseudo-devices. They provide various functions handled by the operating system. Some of the most commonly used (character-based) pseudo-devices include:

/dev/null – accepts and discards all input written to it; provides an end-of-file indication when read from    
/dev/zero – accepts and discards all input written to it; produces a continuous stream of Null characters (zero-value bytes) as output when read from    
/dev/full – produces a continuous stream of Null characters (zero-value bytes) as output when read from, and generates a "disk full" error when attempting to write to it  
/dev/random – when read, it produces as output a variable-length stream of numbers from the kernel's cryptographically secure pseudorandom number generator. Its exact behavior varies by implementation, and sometimes variants such as /dev/urandom or dev/arandom are also provided.    

## Commone Name Convention ##

1. lp:  line printer
2. pt: pseudo terminal
3. fb: frame buffer
4. fd: floppy device
5. hda: master device on the 1st ATA channel
6. hdb: slave device on the 1st ATA channel
7. hdc: master device on the 2nd ATA channel
8. hdd: slave device on the 2nd ATA channel
