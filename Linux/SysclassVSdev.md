On Unix and Unix-like systems, hardware devices are accessed through special files (also called device files or nodes) located in the /dev directory. These files are read from and written to just like normal files, but instead of writing and reading data on a disk, they communicate directly with a kernel driver which then communicates with the hardware. There are many online resources describing /dev files in more detail. Traditonally, these special files were created at install time by the distribution, using the mknod command. In recent years, Linux systems began using udev to manage these /dev files at runtime. For example, udev will create nodes when devices are detected and delete them when devices are removed (including hotplug devices at runtime). This way, the /dev directory contains (for the most part) only entries for devices which actually exist on the system at the current time, as opposed to devices which could exist.

The directories in Sysfs contain the heirarchy of devices, as they are attached to the computer. For example, on my computer, the hidraw0 device is located under:

/sys/devices/pci0000:00/0000:00:12.2/usb1/1-5/1-5.4/1-5.4:1.0/0003:04D8:003F.0001/hidraw/hidraw0     
Based on the path, the device is attached to (roughly, starting from the end) configuration 1 (:1.0) of the device attached to port number 4 of device 1-5, connected to USB controller 1 (usb1), connected to the PCI bus. While interesting, this directory path doesn't do us very much good, since it's dependent on how the hardware is physically connected to the computer.

Fortunately, Sysfs also provides a large number of symlinks, for easy access to devices without having to know which PCI and USB ports they are connected to. In /sys/class there is a directory for each different class of device.

The files in /dev are actual devices files which UDEV creates at run time. The directory /sys/class is exported by the kernel at run time, exposing the hierarchy of the hardware through sysfs.

The /sys filesystem (sysfs) contains files that provide information about devices: whether it's powered on, the vendor name and model, what bus the device is plugged into, etc. It's of interest to applications that manage devices.

The /dev filesystem contains files that allow programs to access the devices themselves: write data to a serial port, read a hard disk, etc. It's of interest to applications that access devices.
