Real Mode is a simplistic 16-bit mode that is present on all x86 processors. Real Mode was the first x86 mode design and was used by many early operating systems before the birth of Protected Mode. For compatibility purposes, all x86 processors begin execution in Real Mode.
    
Cons  
* Less than 1 MB of RAM is available for use.
* There is no hardware-based memory protection (GDT), nor virtual memory.
* There is no built in security mechanisms to protect against buggy or malicious applications.
* The default CPU operand length is only 16 bits.
* The memory addressing modes provided are more restrictive than other CPU modes.
* Accessing more than 64k requires the use of segment register that are difficult to work with.

Pros   
* The BIOS installs device drivers to control devices and handle interrupt.
* BIOS functions provide operating systems with a advanced collection of low level API functions.
* Memory access is faster due to the lack of descriptor tables to check and smaller registers.
