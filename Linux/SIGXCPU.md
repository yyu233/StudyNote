The SIGXCPU signal is sent each second to a process after it exceeds its limit on consumed processor time (RLIMIT_CPU), or, for realtime processes, its limit on running without sleeping. The problem here is with your recursive z function that does not stop and calls itself again and again (and causes a stack overflow).