Kernel modules interact with the kernel by the means of exported symbols, in a way similar to how user space binaries use shared libraries. The /proc/kallsyms file lists all symbols currently known to the kernel.

If the configuration option CONFIG_KALLSYMS is enabled, the kallsyms feature shall be enabled. However, note that the it is a proc file and the /proc/kallsyms shall be created when the kernel boots up. The /proc/kallsyms shall contain all functions of the kernel.

start_kernel() takes care most of the Linux kernel initializations. This in turn uses the routines like setup_arch which is an architecture based set-up function that performs CPU specific initialization.
