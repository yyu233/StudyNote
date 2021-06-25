Process ID (PID)

This is an arbitrary number identifying the process. Every process has a unique ID, but after the process exits and the parent process has retrieved the exit status, the process ID is freed to be reused by a new process.

Parent Process ID (PPID)

This is just the PID of the process that started the process in question. If the parent process exits before the child does, the child's PPID is changed to another process (usually PID 1).

Process Group ID (PGID)

This is just the PID of the process group leader. If PID == PGID, then this process is a process group leader.

Session ID (SID)

This is just the PID of the session leader. If PID == SID, then this process is a session leader.
