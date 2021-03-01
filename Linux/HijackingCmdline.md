There are three ways to pass options to the kernel and thus control its behaviour:

When building the kernel—in the kernel's config file. See Kernel#Compilation for details.
When starting the kernel—using command line parameters (usually through a boot loader).
At runtime—through the files in /proc/sys/ (see sysctl) and /sys/.

First create a file containing the desired kernel parameters
```
/root/cmdline
root=UUID=0a3407de-014b-458b-b5c1-848e92a327a3 ro console=tty1 logo.nologo debug
```
Then use a bind mount to overwrite the parameters
```
# mount -n --bind -o ro /root/cmdline /proc/cmdline
```
The -n option skips adding the mount to /etc/mtab, so it will work even if root is mounted read-only. You can cat /proc/cmdline to confirm that your change was successful.
