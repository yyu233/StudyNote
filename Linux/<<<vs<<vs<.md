```

Here document

<< is known as here-document structure. You let the program know what will be the ending text, and whenever that delimiter is seen, the program will read all the stuff you've given to the program as input and perform a task upon it.

Here's what I mean:

$ wc << EOF
> one two three
> four five
> EOF
 2  5 24
In this example we tell wc program to wait for EOF string, then type in five words, and then type in EOF to signal that we're done giving input. In effect, it's similar to running wc by itself, typing in words, then pressing CtrlD

In bash these are implemented via temp files, usually in the form /tmp/sh-thd.<random string>, while in dash they are implemented as anonymous pipes. This can be observed via tracing system calls with strace command. Replace bash with sh to see how /bin/sh performs this redirection.

$ strace -e open,dup2,pipe,write -f bash -c 'cat <<EOF
> test
> EOF'
Here string

<<< is known as here-string . Instead of typing in text, you give a pre-made string of text to a program. For example, with such program as bc we can do bc <<< 5*4 to just get output for that specific case, no need to run bc interactively.

Here-strings in bash are implemented via temporary files, usually in the format /tmp/sh-thd.<random string>, which are later unlinked, thus making them occupy some memory space temporarily but not show up in the list of /tmp directory entries, and effectively exist as anonymous files, which may still be referenced via file descriptor by the shell itself, and that file descriptor being inherited by the command and later duplicated onto file descriptor 0 (stdin) via dup2() function. This can be observed via

$ ls -l /proc/self/fd/ <<< "TEST"
total 0
lr-x------ 1 user1 user1 64 Aug 20 13:43 0 -> /tmp/sh-thd.761Lj9 (deleted)
lrwx------ 1 user1 user1 64 Aug 20 13:43 1 -> /dev/pts/4
lrwx------ 1 user1 user1 64 Aug 20 13:43 2 -> /dev/pts/4
lr-x------ 1 user1 user1 64 Aug 20 13:43 3 -> /proc/10068/fd
And via tracing syscalls (output shortened for readability; notice how temp file is opened as fd 3, data written to it, then it is re-opened with O_RDONLY flag as fd 4 and later unlinked, then dup2() onto fd 0, which is inherited by cat later ):

$ strace -f -e open,read,write,dup2,unlink,execve bash -c 'cat <<< "TEST"'
execve("/bin/bash", ["bash", "-c", "cat <<< \"TEST\""], [/* 47 vars */]) = 0
...
strace: Process 10229 attached
[pid 10229] open("/tmp/sh-thd.uhpSrD", O_RDWR|O_CREAT|O_EXCL, 0600) = 3
[pid 10229] write(3, "TEST", 4)         = 4
[pid 10229] write(3, "\n", 1)           = 1
[pid 10229] open("/tmp/sh-thd.uhpSrD", O_RDONLY) = 4
[pid 10229] unlink("/tmp/sh-thd.uhpSrD") = 0
[pid 10229] dup2(4, 0)                  = 0
[pid 10229] execve("/bin/cat", ["cat"], [/* 47 vars */]) = 0
...
[pid 10229] read(0, "TEST\n", 131072)   = 5
[pid 10229] write(1, "TEST\n", 5TEST
)       = 5
[pid 10229] read(0, "", 131072)         = 0
[pid 10229] +++ exited with 0 +++
--- SIGCHLD {si_signo=SIGCHLD, si_code=CLD_EXITED, si_pid=10229, si_uid=1000, si_status=0, si_utime=0, si_stime=0} ---
+++ exited with 0 +++
Opinion: potentially because here strings make use of temporary text files, it is the possible reason why here-strings always insert a trailing newline, since text file by POSIX definition has to have lines that end in newline character.
```
