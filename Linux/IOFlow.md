1. User space is where the applications will be running and the bottom level is where the devices would be available.
2. Now application on the User Space will be generating IO requests which will be sent to the kernel interface of VFS (Virtual File System)
3. VFS relates to filesystem like etx4, xfs etc. These are the underlying filesystem residing on the devices.
4. But before the IO reaches the device, it goes through Buffer Cache.
5. Next the IO request goes through IO scheduler.
6. And finally the IO request from IO scheduler goes to the device.
