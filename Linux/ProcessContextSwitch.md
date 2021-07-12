runs from one process to another, and the following changes occur during this process:
1. Save the processor context, including the program counter and other registers.
2. Update the PCB information.
3. Move the process's PCB into the appropriate queue, such as ready, blocked in an event, and so on.
4. Select another process to execute and update its PCB.
5. Update the data structure of memory management.
6. Restore the processor context.
