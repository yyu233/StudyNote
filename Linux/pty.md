A pty is created by a process through posix_openpt() (which usually opens the special device /dev/ptmx), and is constituted by a pair of bidirectional character devices:

    The master part, which is the file descriptor obtained by this process through this call, is used to emulate a terminal. After some initialization, the second part can be unlocked with unlockpt(), and the master is used to receive or send characters to this second part (slave).

    The slave part, which is anchored in the filesystem as /dev/pts/x (the real name can be obtained by the master through ptsname() ) behaves like a native terminal device (/dev/ttyx). In most cases, a shell is started that uses it as a controlling terminal
