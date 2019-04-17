## PCI ## 

[Reference](https://www.oreilly.com/library/view/linux-device-drivers/0596005903/ch12.html)   
[Reference](https://docs.oracle.com/cd/E19120-01/open.solaris/819-3196/hwovr-25/index.html)

PCI: both software layer and hardware layer    

Although many computer users think of PCI as a way of laying out electrical wires, it is actually a complete set of specifications defining how different parts of a computer should interact.

PCI bus has higher clock rate than ISA. Support 32-bit and 64-bit data bus. PCI drivers are jumperless and automatically configured at boot time.    

PCI peripheral is identified by: bus number, device number, function number.     

The PCI address domain consists of three distinct address spaces: configuration, memory, and I/O space.

