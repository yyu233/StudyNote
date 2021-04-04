The most common usage of an alternate signal stack is to handle the SIGSEGV signal that is generated if the space available for the normal process stack is exhausted: in this case, a signal handler for SIGSEGV cannot be invoked on the process stack; if we wish to handle it, we must use an alternate signal stack.

Establishing an alternate signal stack is useful if a process expects that it may exhaust its standard stack. This may occur, for example, because the stack grows so large that it encounters the upwardly growing heap, or it reaches a limit established by a call to setrlimit(RLIMIT_STACK, &rlim). If the standard stack is exhausted, the kernel sends the process a SIGSEGV signal. In these circumstances the only way to catch this signal is on an alternate signal stack.

On most hardware architectures supported by Linux, stacks grow downward. sigaltstack() automatically takes account of the direction of stack growth. 
