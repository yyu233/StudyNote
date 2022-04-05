The benefit of not calling via the shell is that you are not invoking a 'mystery program.' On POSIX, the environment variable SHELL controls which binary is invoked as the "shell." On Windows, there is no bourne shell descendent, only cmd.exe.

So invoking the shell invokes a program of the user's choosing and is platform-dependent. Generally speaking, avoid invocations via the shell.

Invoking via the shell does allow you to expand environment variables and file globs according to the shell's usual mechanism. On POSIX systems, the shell expands file globs to a list of files. On Windows, a file glob (e.g., "*.*") is not expanded by the shell, anyway (but environment variables on a command line are expanded by cmd.exe).

If you think you want environment variable expansions and file globs, research the ILS attacks of 1992-ish on network services which performed subprogram invocations via the shell. Examples include the various sendmail backdoors involving ILS.

In summary, use shell=False.
