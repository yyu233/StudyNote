## Kernel Module ##

Modules are pieces of code that can be loaded and unloaded into the kernel upon demand. They extend the functionality of the kernel without the need to reboot the system. For example, one type of module is the device driver, which allows the kernel to access hardware connected to the system. Without modules, we would have to build monolithic kernels and add new functionality directly into the kernel image. Besides having larger kernels, this has the disadvantage of requiring us to rebuild and reboot the kernel every time we want new functionality.

Kernel modules interact with the kernel by the means of exported symbols, in a way similar to how user space binaries use shared libraries. The /proc/kallsyms file lists all symbols currently known to the kernel.

If the configuration option CONFIG_KALLSYMS is enabled, the kallsyms feature shall be enabled. However, note that the it is a proc file and the /proc/kallsyms shall be created when the kernel boots up. The /proc/kallsyms shall contain all functions of the kernel.

start_kernel() takes care most of the Linux kernel initializations. This in turn uses the routines like setup_arch which is an architecture based set-up function that performs CPU specific initialization.

## Kernel Flavor ##
Each architecture has its own set of kernel flavor.  

## How to Load Kernel Module into Kernel ##
When a Kernel Module is new to Kernel, daemon kmod will execute modprobe. modprobe will check from /lib/modules/version/modules.dep to see if any dependencies need to loaded. modprobe will invoke insmod to load dependencies and the new Kernel Module into Kernel.   

## Where Binary Kernel Module Installed ##
Binary Kernel Modules are installed at: /lib/modules  
**Never replace modules from the kernel package by overwriting files: this would lead to inconsistencies between the file system and the RPM database.**   

## Kernel Module Packages ##
Kernel Module Package spec files define a main package, and a sub-package for each kernel flavor supported. The kernel-flavor-specific sub-packages are defined with the %kernel_module_package rpm macro. The macro automatically determines for which kernel flavors to generate sub-packages.    
BuildRequires tag in the spec file will pull the module-init-tools, kernel-source, kernel-syms and kernel-devel packages into the build root.   
