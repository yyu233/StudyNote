```
Example:

#include <unistd.h>

int global_a;
int global_b;

int foo()
{
  global_a = 42;
  read(0, &global_b, 1);

  return global_a + global_b;
}

int main()
{
  return foo();
}

gcc -g -Wall t.c

gdb -q ./a.out
(gdb) start
Temporary breakpoint 1 at 0x400563: file t.c, line 16.
Starting program: /tmp/a.out

Temporary breakpoint 1, main () at t.c:16
16    return foo();
(gdb) watch global_a
Hardware watchpoint 2: global_a
(gdb) watch global_b
Hardware watchpoint 3: global_b
(gdb) c
Continuing.
Hardware watchpoint 2: global_a

Old value = 0
New value = 42
This is a modification of global_a in user-space (via direct assignment), and it triggers watchpoint 2 as expected

foo () at t.c:9
9     read(0, &global_b, 1);
(gdb) c
Continuing.
                    # Press Enter here
This read 0xA == 10 into global_b.

[Inferior 1 (process 126196) exited with code 064]
Note that the exit code is 064 == 52 == 42+10, but the watchpoint 3 did not fire.

any method to find when this variable changes its value

If you are sure that your "normal" watchpoints are working (e.g. by running above test yourself) and suspect that the variable is being changed via a system call, you can:

Print the address of the variable and
Run your program under strace and look for system calls that could change the value at variable's address.
Using the same example:

(gdb) p &global_b
$1 = (int *) 0x601044 <global_b>

strace -e raw=all ./a.out < /dev/zero

execve(0x7ffe1853e530, 0x7ffe1853f920, 0x7ffe1853f930) = 0
brk(0)                                  = 0x2253000
access(0x7fa66eee48c3, 0)               = -1 (errno 2)
mmap(0, 0x2000, 0x3, 0x22, 0xffffffff, 0) = 0x7fa66f0e8000
...
munmap(0x7f57ece26000, 0x203a2)         = 0
read(0, 0x601044, 0x1)                  = 0x1  ### &global_b is "covered" by the buffer being read into
exit_group(42)                          = ?
+++ exited with 42 +++
```
