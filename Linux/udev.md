[Reference](https://wiki.debian.org/udev)    

Udev is the mechanism used to create and name /dev device nodes corresponding to the devices that are present in the system. Udev uses matching information provided by sysfs with rules provided by the user to dynamically add the required device nodes.

udev is a replacement for the Device File System (DevFS) starting with the Linux 2.6 kernel series. It allows you to identify devices based on their properties, like vendor ID and device ID, **dynamically**. **udev runs in userspace (as opposed to devfs which was executed in kernel space).**

udev allows for rules that specify what name is given to a device, regardless of which port it is plugged into. For example, a rule to always mount a hard drive with manufacturer "iRiver" and device code "ABC" as /dev/iriver is possible. This consistent naming of devices guarantees that scripts dependent on a specific device's existence will not be broken

The udev system is composed of some kernel services and the udevd daemon. The kernel informs the udevd daemon when certain events happen. The udevd daemon is configured to respond to events with corresponding actions. The event information comes from the kernel - the actions happen in userspace. The responses to the events are configurable in "rules".   

* udev provides low-level access to the linux device tree. Allows programs to enumerate devices and their properties and get notifications when devices come and go.    
* dbus is a framework to allow programs to communicate with each other, securely, reliably, and with a high-level object-oriented programming interface.   
* udisks (formerly known as DeviceKit-disks) is a daemon that sits on top of libudev and other kernel interfaces and provides a high-level interface to storage devices and is accessible via dbus to applications.   
* upower (formerly known as DeviceKit-power) is a daemon that sits on top of libudev and other kernel interfaces and provides a high-level interface to power management and is accessible via dbus to applications.   
* NetworkManager is a daemon that sits on top of libudev and other kernel interfaces (and a couple of other daemons) and provides a high-level interface to network configuration and setup and is accessible via dbus to apps.    
