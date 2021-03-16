A process in S state is usually in a blocking system call, such as reading or writing to a file or the network, or waiting for another called program to finish.

You can use strace -p <pid> to find out which system call is currently happening. It will produce output like

write(1, "foobar"..., 4096

which means that the process is trying to write 4096 bytes starting with "foobar" to stdout (fd #1) but whatever it has been redirected into is busy and the output buffer is full.
