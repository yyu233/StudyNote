The main difference between epoll and select is that in select() the list of file descriptors to wait on only exists for the duration of a single select() call, and the calling task only stays on the sockets' wait queues for the duration of a single call. In epoll, on the other hand, you create a single file descriptor that aggregates events from multiple other file descriptors you want to wait on, and so the list of monitored fd's is long-lasting, and tasks stay on socket wait queues across multiple system calls. Furthermore, since an epoll fd can be shared across multiple tasks, it is no longer a single task on the wait queue, but a structure that itself contains another wait queue, containing all processes currently waiting on the epoll fd. (In terms of implementation, this is abstracted over by the sockets' wait queues holding a function pointer and a void* data pointer to pass to that function).

So, to explain the mechanics a little more:

An epoll file descriptor has a private struct eventpoll that keeps track of which fd's are attached to this fd. struct eventpoll also has a wait queue that keeps track of all processes that are currently epoll_waiting on this fd. struct epoll also has a list of all file descriptors that are currently available for reading or writing.
When you add a file descriptor to an epoll fd using epoll_ctl(), epoll adds the struct eventpoll to that fd's wait queue. It also checks if the fd is currently ready for processing and adds it to the ready list, if so.
When you wait on an epoll fd using epoll_wait, the kernel first checks the ready list, and returns immediately if any file descriptors are already ready. If not, it adds itself to the single wait queue inside struct eventpoll, and goes to sleep.
When an event occurs on a socket that is being epoll()ed, it calls the epoll callback, which adds the file descriptor to the ready list, and also wakes up any waiters that are currently waiting on that struct eventpoll.
Obviously, a lot of careful locking is needed on struct eventpoll and the various lists and wait queues, but that's an implementation detail.

The important thing to note is that at no point above there did I describe a step that loops over all file descriptors of interest. By being entirely event-based and by using a long-lasting set of fd's and a ready list, epoll can avoid ever taking O(n) time for an operation, where n is the number of file descriptors being monitored.