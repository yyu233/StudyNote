## Inter Process Communication ##

* Pipe
* FIFO
* Message Queue
* Shared Memory

|Pipe | FIFO|
| ---| ---|
|They are un-named IPC object | They are named IPC object|
|Pipe doesn't exist in the filesystem | FIFO exists in the filesystem|
|Pipe is created by pipe() | FIFO is created by mkfifo() |
|In Pipe, communication is among the process having a common ancestor| In FIFO, it is not necessary for the process having a common ancestor for communication |
|Pipe provides simplex data flow| FIFO provides half duplex data flow|
|Pipe is unidirectional | FIFO is bi-directional same FIFO can be used for reading and writing|
|Pipe is local to the system and cannot be used for communication across the network | FIFO is capable of communicating across different computers and network|
|In Pipe, reader and writer operation is done at same time | In FIFO, it doesn't require that both read and write operation occurs at the same time. |
|In Pipe, data transfer takes place between the child process and parent process | FIFO have multiple processes communicating throught it, like multiple client-server application |
|Pipe has no control over ownership and permissions | FIFO is a file and you cna control ownership and permissions|
|Pipe vanishes as soon as it is closed or one of the processes (parent or child) completes execution| FIFO exists even when calling process exit. They remain till system reboots| 

[Reference](http://www.embhack.com/pipe-and-fifo/)
