The kernel has currently 3 ways to mount the root filesystem:

a) all required device and filesystem drivers compiled into the kernel, no initrd. init/main.c:init() will call prepare_namespace() to mount the final root filesystem, based on the root= option and optional init= to run some other init binary than listed at the end of init/main.c:init().

b) some device and filesystem drivers built as modules and stored in an initrd. The initrd must contain a binary '/linuxrc' which is supposed to load these driver modules. It is also possible to mount the final root filesystem via linuxrc and use the pivot_root syscall. The initrd is mounted and executed via prepare_namespace().

c) using initramfs. The call to prepare_namespace() must be skipped. This means that a binary must do all the work. Said binary can be stored into initramfs either via modifying usr/gen_init_cpio.c or via the new initrd format, an cpio archive. It must be called "/init". This binary is responsible to do all the things prepare_namespace() would do.

To maintain backwards compatibility, the /init binary will only run if it comes via an initramfs cpio archive. If this is not the case, init/main.c:init() will run prepare_namespace() to mount the final root and exec one of the predefined init binaries.
