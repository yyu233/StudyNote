2.9.7 Thread Interactions with Regular File Operations
All of the following functions shall be atomic with respect to each other in the effects specified in POSIX.1-2017 when they operate on regular files or symbolic links:


chmod()
chown()
close()
creat()
dup2()
fchmod()
fchmodat()
fchown()
 


fchownat()
fcntl()
fstat()
fstatat()
ftruncate()
lchown()
link()
linkat()
 


lseek()
lstat()
open()
openat()
pread()
read()
readlink()
readlinkat()
 


readv()
pwrite()
rename()
renameat()
stat()
symlink()
symlinkat()
truncate()
 


unlink()
unlinkat()
utime()
utimensat()
utimes()
write()
writev()
 

If two threads each call one of these functions, each call shall either see all of the specified effects of the other call, or none of them. The requirement on the close() function shall also apply whenever a file descriptor is successfully closed, however caused (for example, as a consequence of calling close(), calling dup2(), or of process termination).
