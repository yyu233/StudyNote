When you say threads are faster, it is a different “fast” that it is. Process creation is a resource intensive operation, in terms of memory allocation and also inter process communication is also pretty much expensive when they need to share data. So a program which spawns multiple processes, need to have some complexity to share the common data that they are using.

Hence, the advent of threads, which are lightweight version of a process. Other than some resource being spent in spawning them, there are no additional resources allocated like memory, etc. Also guarantees that the OS provides regarding data integrity during multiprocessing environment are also relaxed.

Threads share the memory that is allocated to the process and have signalling and lock based approaches to maintain data integrity. Hence it appears as threads to be faster than processes.

However, with use of threads, to ensure data is accessed and modified consistently and atomically, it is upto programmers to deal with locking and use of thread signalling. A tradeoff that we need to deal with for performance.
