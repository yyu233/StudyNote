## PCI ## 

[Reference 1](https://www.oreilly.com/library/view/linux-device-drivers/0596005903/ch12.html)   
[Reference 2](https://docs.oracle.com/cd/E19120-01/open.solaris/819-3196/hwovr-25/index.html)    
[Reference 3](https://diego.assencio.com/?index=649b7a71b35fc7ad41e03b6d0e825f07)

PCI: both software layer and hardware layer    

Although many computer users think of PCI as a way of laying out electrical wires, it is actually a complete set of specifications defining how different parts of a computer should interact.

PCI bus has higher clock rate than ISA. Support 32-bit and 64-bit data bus. PCI drivers are jumperless and automatically configured at boot time.    

PCI peripheral is identified by: bus number, device number, function number.     

The PCI address domain consists of three distinct address spaces: configuration, memory, and I/O space. 

PCI defines 3 types of transaction: configuration, memory and I/O.    

CPU doesn't generate PCI transactions natively. Host bridge lets CPU perform PCI transactions.     

Each host bridge establishes a PCI domain (isolation): a set of bus segments. Transaction is not routable between domains. 

Cascade PCI busess with bridges.    

 PCI was a parallel interface, which means that it dealt with large amounts of data by splitting them up and sending them at a low speed. PCI Express, in contrast, is a serial interface, which means that it sends them one at a time, really fast.














