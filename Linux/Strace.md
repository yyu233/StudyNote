strace -p <PID> ----> To attach a process to strace. "-p" option is for PID of the process.

strace -e trace=read,write -p <PID> --> By this you can also trace a process/program for an event, like read and write (in this example). So here it will print all such events that include read and write system calls by the process.

Other such examples

-e trace= network  (Trace all the network related system calls.)

-e trace=signal    (Trace all signal related system calls.)

-e trace=ipc       (Trace all IPC related system calls.)

-e trace=desc      (Trace all file descriptor related system calls.)

-e trace=memory    (Trace all memory mapping related system calls.)
