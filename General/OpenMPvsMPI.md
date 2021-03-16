OpenMP is a way to program on shared memory devices. This means that the parallelism occurs where every parallel thread has access to all of your data.

You can think of it as: parallelism can happen during execution of a specific for loop by splitting up the loop among the different threads.

MPI is a way to program on distributed memory devices. This means that the parallelism occurs where every parallel process is working in its own memory space in isolation from the others.

You can think of it as: every bit of code you've written is executed independently by every process. The parallelism occurs because you tell each process exactly which part of the global problem they should be working on based entirely on their process ID.


MPI stands for Message Passing Interface. It is a set of API declarations on message passing (such as send, receive, broadcast, etc.), and what behavior should be expected from the implementations.

The idea of "message passing" is rather abstract. It could mean passing message between local processes or processes distributed across networked hosts, etc. Modern implementations try very hard to be versatile and abstract away the multiple underlying mechanisms (shared memory access, network IO, etc.).

OpenMP is an API which is all about making it (presumably) easier to write shared-memory multi-processing programs. There is no notion of passing messages around. Instead, with a set of standard functions and compiler directives, you write programs that execute local threads in parallel, and you control the behavior of those threads (what resource they should have access to, how they are synchronized, etc.). OpenMP requires the support of the compiler, so you can also look at it as an extension of the supported languages.

