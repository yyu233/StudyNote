## The proc filesystem ##

The Linux kernel has two primary functions:     
1. Control access to physical devices     
2. shedule when and how processes interact with the devices     

```/proc/``` directory contains system hardware and running processes information.     
```/proc/``` contains virtual type of file.    

The virtual files are listed as 0 bytes in size. They are constantly updated.    

```/proc/cmdline``` contains parameter information for kernel at start time     
```/proc/devices``` displays the various character and block devices currently configured (not including devices whose modules are not loaded)   
