Memory management services in Linux are built on a programming foundation that includes a peripheral device called Memory Management Unit (MMU). MMU translates physical memory addresses to linear addresses used by the operating system, and requests a page fault interrupt, when the CPU tries to access memory that it is not entitled to.

Not all processors have MMUs. Therefore, the uClinux distribution (Linux for microcontrollers) supports a single address space of operation. This architecture lacks the protection provided by MMU but makes it possible for Linux to run on another class of processors.

**Buddy Allocator**: The Buddy Allocator is responsible for the management of the page allocations in the entire system.

**Zone Allocator**: The Zone Allocator is used to allocate pages in the specified zone. Today Linux kernel is supporting three memory zones:
* DMA — This zone consists of memory accessible for direct memory operations of the legacy devices
* NORMAL — This zone includes memory addresses used by the kernel for internal data structures as well as other system and user space allocations.
* HIGHMEM — This zone includes all memory used exclusively for system allocations (file system buffers, user space allocations, etc).
