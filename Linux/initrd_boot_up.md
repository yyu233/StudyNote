Boot-up operation
       When booting up with initrd, the system boots as follows:

       1. The boot loader loads the kernel program and /dev/initrd's
          contents into memory.

       2. On kernel startup, the kernel uncompresses and copies the
          contents of the device /dev/initrd onto device /dev/ram0 and
          then frees the memory used by /dev/initrd.

       3. The kernel then read-write mounts the device /dev/ram0 as the
          initial root filesystem.

       4. If the indicated normal root filesystem is also the initial
          root filesystem (e.g., /dev/ram0) then the kernel skips to the
          last step for the usual boot sequence.

       5. If the executable file /linuxrc is present in the initial root
          filesystem, /linuxrc is executed with UID 0.  (The file
          /linuxrc must have executable permission.  The file /linuxrc
          can be any valid executable, including a shell script.)

       6. If /linuxrc is not executed or when /linuxrc terminates, the
          normal root filesystem is mounted.  (If /linuxrc exits with
          any filesystems mounted on the initial root filesystem, then
          the behavior of the kernel is UNSPECIFIED.  See the NOTES
          section for the current kernel behavior.)

       7. If the normal root filesystem has a directory /initrd, the
          device /dev/ram0 is moved from / to /initrd.  Otherwise, if
          the directory /initrd does not exist, the device /dev/ram0 is
          unmounted.  (When moved from / to /initrd, /dev/ram0 is not
          unmounted and therefore processes can remain running from
          /dev/ram0.  If directory /initrd does not exist on the normal
          root filesystem and any processes remain running from
          /dev/ram0 when /linuxrc exits, the behavior of the kernel is
          UNSPECIFIED.  See the NOTES section for the current kernel
          behavior.)

       8. The usual boot sequence (e.g., invocation of /sbin/init) is
          performed on the normal root filesystem
