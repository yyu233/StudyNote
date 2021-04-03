```
Kernel perspective:

I will try to answer from the kernel perspective, covering various OS's.

Memory segmentation is the old way of accessing memory regions. All major operating systems including OSX, Linux, (from version 0.1) and Windows (from NT) are now using paging which is a better way (IMHO) of accessing memory.

Intel, has always introduced backward compatibility in its processors (except IA-64, and we saw how it failed...) So, in its initial state (after reset) the processor starts in a mode called real mode, in this mode, segmentation is enabled by default to support legacy software. During the boot process of the operating system, the processor is changed into protected mode, and then in enabled paging.

Before paging, the segment registers were used like this

    In real mode each logical address points directly into physical memory location, every logical address consists of two 16 bit parts: The segment part of the logical address contains the base address of a segment with a granularity of 16 bytes, i.e. a segments may start at physical address 0, 16, 32, ..., 220-16. The offset part of the logical address contains an offset inside the segment, i.e. the physical address can be calculated as physical_address := segment_part × 16 + offset (if the address line A20 is enabled), respectively (segment_part × 16 + offset`) mod 220 (if A20 is off) Every segment has a size of 216 bytes. [Wikipedia]

Let's see some examples (286-386 era) :

The 286 architecture introduced 4 segments: CS (code segment) DS (data segment) SS (stack segment) ES (extra segment) the 386 architecture introduced two new general segment registers FS, GS.

typical assembly opcode (in Intel syntax) would look like:

mov dx, 850h
mov es, dx     ; Move 850h to es segment register
mov es:cx, 15h ; Move 15 to es:cx

Using paging (protected mode) the segment registers weren't used anymore for addressing memory locations.

    In protected mode the segment_part is replaced by a 16 bit selector, the 13 upper bits (bit 3 to bit 15) of the selector contains the index of an entry inside a descriptor table. The next bit (bit 2) specifies if the operation is used with the GDT or the LDT. The lowest two bits (bit 1 and bit 0) of the selector are combined to define the privilege of the request; where a value of 0 has the highest priority and value of 3 is the lowest. [wikipedia]

The segments however still used to enforce hardware security in the GDT

    The Global Descriptor Table or GDT is a data structure used by Intel x86-family processors starting with the 80286 in order to define the characteristics of the various memory areas used during program execution, including the base address, the size and access privileges like executability and writability. These memory areas are called segments in Intel terminology. [wikipedia]

So, in practice the segment registers in protected mode are used to store indexes to the GDT.

Several operating systems such as Windows and Linux, use some of the segments for internal usage. for instance Windows x64 uses the GS register to access the TLS (thread local storage) and in Linux it's for accessing cpu specific memory.

User perspective:

From the user perspective, in recent operating system that uses paging, the memory works in so called "flat mode". Every process access its own memory (4GB) in linear fashion, so basically the segment registers are not needed.

They are still registers, so they can of course be used for various other assembly operations.
```
