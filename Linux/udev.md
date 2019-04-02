Udev is the mechanism used to create and name /dev device nodes corresponding to the devices that are present in the system. Udev uses matching information provided by sysfs with rules provided by the user to dynamically add the required device nodes.

udev is a replacement for the Device File System (DevFS) starting with the Linux 2.6 kernel series. It allows you to identify devices based on their properties, like vendor ID and device ID, dynamically. udev runs in userspace (as opposed to devfs which was executed in kernel space).

udev allows for rules that specify what name is given to a device, regardless of which port it is plugged into. For example, a rule to always mount a hard drive with manufacturer "iRiver" and device code "ABC" as /dev/iriver is possible. This consistent naming of devices guarantees that scripts dependent on a specific device's existence will not be broken
