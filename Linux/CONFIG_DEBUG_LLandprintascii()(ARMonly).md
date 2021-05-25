If the kernel fails before the serial console is enabled, you can use CONFIG_DEBUG_LL to add extra debug output routines to the kernel. These are printascii, printch and printhex. These routines print directly to the serial port, bypassing the console code, and are available earlier in machine initialization.

To see printks earlier in the boot sequence (before the console is initialized), set CONFIG_DEBUG_LL=y and CONFIG_EARLY_PRINTK=y.

Alternatively, add your own calls to printascii, printch, and printhex where you believe the problems are located.
