In Domain sockets, actual communication (the data exchange) does not use the file system, but buffers in kernel memory. By default, it is full-duplex mode.

Named pipes are identified by their access point, a file kept on the file system for handling the data. A named pipe by default supports blocked read and write operations. However, it is possible to make named pipes support non-blocking operations by specifying the O_NONBLOCK flag while opening them. A named pipe must be opened either read-only or write-only. It must not be opened for read-write because it is half-duplex,a one-way channel.

Of these two, named pipes are simpler to work with, but much less flexible than UNIX-domain sockets. For example, if you potentially expect more than one reading process for each writing process, then UNIX-domain sockets are a must; if you expect the reading process to stop and start during the execution of the writing process, then you'll need UNIX-domain sockets.
