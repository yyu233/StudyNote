## Useful Signals to User ## 

1. SIGHUP 1 – sent to a process when its controlling terminal is closed
2. SIGINT 2 – sent to a process by its controlling terminal when a user interrupts the process by pressing  [Ctrl+C].
3. SIGQUIT 3 – sent to a process if the user sends a quit signal [Ctrl+D].
4. SIGKILL 9 – this signal immediately terminates (kills) a process and the process will not perform any clean-up operations.
5. SIGTERM 15 – this a program termination signal (kill will send this by default).
6. SIGTSTP 20 – sent to a process by its controlling terminal to request it to stop (terminal stop); initiated by the user pressing [Ctrl+Z].

```
Ctrl+Z: pause a process.

Ctrl+C: politely ask the process to shut down now.

Ctrl+\: mercilessly kill the process that is currently in the foreground

```
