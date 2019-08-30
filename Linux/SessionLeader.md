Linux, every process has several IDs associated with it, including:

* Process ID (PID)

This is an arbitrary number identifying the process. Every process has a unique ID, but after the process exits and the parent process has retrieved the exit status, the process ID is freed to be reused by a new process.

* Parent Process ID (PPID)

This is just the PID of the process that started the process in question.

* Process Group ID (PGID)

This is just the PID of the process group leader. If PID == PGID, then this process is a process group leader.

* Session ID (SID)

This is just the PID of the session leader. If PID == SID, then this process is a session leader.

Sessions and process groups are just ways to treat a number of related processes as a unit. All the members of a process group always belong to the same session, but a session may have multiple process groups.

Normally, a shell will be a session leader, and every pipeline executed by that shell will be a process group. This is to make it easy to kill the children of a shell when it exits. (See exit(3) for the gory details.)
