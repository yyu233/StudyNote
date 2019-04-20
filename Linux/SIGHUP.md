Signals have always been a convenient method of inter-process communication (IPC), but in early implementations there were no user-definable signals (such as the later additions of SIGUSR1 and SIGUSR2) that programs could intercept and interpret for their own purposes. For this reason, applications that did not require a controlling terminal, such as daemons, would re-purpose SIGHUP as a signal to re-read configuration files, or reinitialize.   

The shell exits by default upon receipt of a SIGHUP. Before exiting, an interactive shell resends the SIGHUP to all jobs, running or stopped. Stopped jobs are sent SIGCONT to ensure that they receive the SIGHUP. To prevent the shell from sending the signal to a particular job, it should be removed from the jobs table with the disown builtin (see SHELL BUILTIN COMMANDS below) or marked to not receive SIGHUP using disown -h.   

If the huponexit shell option has been set with shopt, bash sends a SIGHUP to all jobs when an interactive login shell exits.    

The value of SIGHUP can be varied across different platforms.    
