There are three ways to pass options to the kernel and thus control its behaviour:

* When building the kernel—in the kernel's config file. See Kernel#Compilation for details.
* When starting the kernel—using command line parameters (usually through a boot loader).
* At runtime—through the files in /proc/sys/ (see sysctl) and /sys/.
