Accessing the printk buffer after a silent hang on boot
Sometimes, if the kernel hangs early in the boot process, you get no messages on the console before the hang. However, there may still be messages in the printk buffer, which can give you an idea of where the problem is.

The kernel starts putting messages into the printk buffer as soon as it starts. They stay buffered there until the console code has a chance to initialize the console device (often the serial port for embedded devices). Even though these messages are not printed before the hang, it is still possible in some circumstances to dump the printk buffer and see the messages.

The tricky parts of doing this are:

using a warm reset (if possible) so the memory contents are not lost when transitioning from the stuck kernel to the bootloader. You can do a cold boot, but if the memory is left unpowered for very long, you will start to see memory corruption.
figuring out the address to use in the bootloader, based on the address of __log_buf in System.map. You will probably need to subtract the value of CONFIG_PAGE_OFFSET from the __log_buf address. However, there may be other offsets present as well (such as TEXT_OFFSET). Sometimes you can find the buffer by dumping the memory in a suspected area and locating the kernel messages visually in the dump. Note that the mapping offset between the kernel map of memory and the bootloader map of memory should not change. So once you figure it out you are set.
