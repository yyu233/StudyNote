
When you set a watchpoint on anything larger than 8 bytes on x86 processor, GDB can not set a hardware watchpoint (because x86 hardware doesn't support such watchpoints). GDB sets a software watchpoint instead. Software watchpoints are implemented as follows:

single-step the program
did values change? No -> go to step 1. Yes: stop.
Software watchpoints are really slow. If you watch your system with top, you'll likely discover that GDB is consuming 100% CPU.
