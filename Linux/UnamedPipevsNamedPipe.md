Like un-named/anonymous pipes, named pipes provide a form of IPC (Inter-Process Communication). With anonymous pipes, there's one reader and one writer, but that's not required with named pipes—any number of readers and writers may use the pipe.

PIPE:
* They are un-named IPC Object.
* FIFO is capable of communicating across different computers and network.
* PIPE does not exist in the file system.
* In PIPE, data transfer takes place between the child process and parent process.
* PIPE is created by pipe () function.
* In PIPE, reader and writer operation is done at same time.
* PIPE vanishes as soon as it is closed, or one of the processes (parent or child) completes execution.
* PIPE has no control over ownership and permissions.
* PIPE is unidirectional.
* PIPE provides simplex data flow.
* In PIPE, communication is among the process having a common ancestor (related process)

FIFO:
* They are named IPC Object.
* PIPE is local to the system and cannot be used for communication across the network.
* FIFO exists in the files system.
* FIFO have multiple processes communicating through it, like multiple client-server application.
* FIFO is created by mkfifo () function.
* In FIFO, it does not require that both read and write operation to occur at the same time.
* FIFO exists even when calling process exit. They remain till system reboots.
* Given that FIFO is a file, you can control ownership and permissions.
* FIFO is bi-directional. The same FIFO can be used for reading and writing.
* FIFO provides half duplex data flow.
* In FIFO, it is not necessary for the process having a common ancestor for communication (unrelated process)
