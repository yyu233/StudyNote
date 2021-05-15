Processes can choose to:

* ignore the SIGINT signal usually sent upon pressing Ctrl-C (like with trap '' INT in a shell) or have their own handler for it that decides not to terminate (or fails to terminate in a timely fashion).
* tell the terminal device that the character that causes a SIGINT to be sent to the foreground job is something else (like with stty int '^K' in a shell)
* tell the terminal device not to send any signal (like with stty -isig in a shell).
* Or, they can be uninterruptible, like when in a middle of a system call that can't be interrupted.
