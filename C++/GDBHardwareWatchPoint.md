```
GDB hardware watchpoints use special debug registers in hardware, and there is usually a limit on how such registers work. On x86, you can set up to 4 word-sized hardware watch points, so for example you gave you can set watchpoints on &data->a and &data->b, and that will "cover" entire memory of the data.

I am guessing that your actual data has many more members though, and so 4 word-sized watch points will not suffice.

If you are on platform which has Valgrind support, and if your program can execute under Valgrind, then you can use Valgrind's built-in gdbserver to set watchpoints on arbitrary regions of memory.

Update:

I looked through the page you linked to and couldn't find what I was looking for

I am not sure what you were looking for. Here is a sample session showing how it works:

#include <stdlib.h>

void foo(char *p)
{
  *p = 'a';
}

typedef struct {
  char buf[1024];
} data;

int main()
{
  data *d = calloc(1, sizeof(data));
  foo(d->buf + 999);
}

gcc -g main.c

valgrind --vgdb-error=0 ./a.out
...
==10345== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==10345==   /path/to/gdb ./a.out
==10345== and then give GDB the following command
==10345==   target remote | vgdb --pid=10345
... Valgrind now waits for debugger to attach.

In another window:

gdb ./a.out
GNU gdb (GDB) 7.4
...
(gdb) target remote | vgdb --pid=10345
relaying data between gdb and process 10345
[Switching to Thread 10345]
0x0000000004000af0 in _start () from /lib64/ld-linux-x86-64.so.2
(gdb) b main
Breakpoint 1 at 0x40053d: file main.c, line 14.
(gdb) c

Breakpoint 1, main () at main.c:14
14        data *d = calloc(1, sizeof(data));
(gdb) n
15        foo(d->buf + 999);
(gdb) watch *d
Hardware watchpoint 2: *d
Note that a "hardware" watchpoint has been set on entire *d. It's a hardware watchpoint only in the sense that Valgrind is the hardware.

(gdb) p d.buf[999]
$1 = 0 '\000'
(gdb) c
Hardware watchpoint 2: *d

Old value = {buf = '\000' <repeats 1023 times>}
New value = {buf = '\000' <repeats 999 times>, "a", '\000' <repeats 23 times>}
foo (p=0x51b6457 "a") at main.c:6
6       }
(gdb) q
Voila: the debugger stopped when 999th element was modified, proving that the watchpoint "covered" the entire structure.
```
