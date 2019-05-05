## Kernel Module ##

Modules are pieces of code that can be loaded and unloaded into the kernel upon demand. They extend the functionality of the kernel without the need to reboot the system. For example, one type of module is the device driver, which allows the kernel to access hardware connected to the system. Without modules, we would have to build monolithic kernels and add new functionality directly into the kernel image. Besides having larger kernels, this has the disadvantage of requiring us to rebuild and reboot the kernel every time we want new functionality.

Kernel modules interact with the kernel by the means of exported symbols, in a way similar to how user space binaries use shared libraries. The /proc/kallsyms file lists all symbols currently known to the kernel.

If the configuration option CONFIG_KALLSYMS is enabled, the kallsyms feature shall be enabled. However, note that the it is a proc file and the /proc/kallsyms shall be created when the kernel boots up. The /proc/kallsyms shall contain all functions of the kernel.

start_kernel() takes care most of the Linux kernel initializations. This in turn uses the routines like setup_arch which is an architecture based set-up function that performs CPU specific initialization.

## Kernel Flavor ##
Each architecture has its own set of kernel flavor.  
