Address-space layout randomization (ASLR) is a well-known technique to make exploits harder by placing various objects at random, rather than fixed, addresses.
      
These kinds of attacks rely on knowing where symbols of interest live in the kernel's address space. Those locations change between kernel versions and distribution builds, but are known (or can be figured out) for a particular kernel. ASLR disrupts that process and adds another layer of difficulty to an attack.

ASLR in user space randomizes the location of various parts of an executable: stack, mmap region, heap, and the program text itself. Attacks have to rely on information leaks to get around ASLR. By exploiting some other bug (the leak), the attack can find where the code of interest has been loaded.
