 Hook: cmdline
       The cmdline hook is a place to insert scripts to parse the kernel
       command line and prepare the later actions, like setting up udev
       rules and configuration files.

       In this hook the most important environment variable is defined:
       root. The second one is rootok, which indicates, that a module
       claimed to be able to parse the root defined. So for example,
       root=iscsi:.... will be claimed by the iscsi dracut module, which
       then sets rootok.

   Hook: pre-udev
       This hook is executed right after the cmdline hook and a check if
       root and rootok were set. Here modules can take action with the
       final root, and before udev has been run.

   Start Udev
       Now udev is started and the logging for udev is setup.

   Hook: pre-trigger
       In this hook, you can set udev environment variables with udevadm
       control --property=KEY=value or control the further execution of
       udev with udevadm.

   Trigger Udev
       udev is triggered by calling udevadm trigger, which sends add
       events for all devices and subsystems.

   Main Loop
       In the main loop of dracut loops until udev has settled and all
       scripts in initqueue/finished returned true. In this loop there
       are three hooks, where scripts can be inserted by calling
       /sbin/initqueue.

       Initqueue
           This hook gets executed every time a script is inserted here,
           regardless of the udev state.

       Initqueue settled
           This hook (initqueue/settled) gets executed every time udev
           has settled.

       Initqueue timeout
           This hook (initqueue/timeout) gets executed, when the main
           loop counter becomes half of the rd.retry counter.

       Initqueue online
           This hook (initqueue/online) gets executed whenever a network
           interface comes online (that is, once it is up and configured
           by the configured network module).

       Initqueue finished
           This hook (initqueue/finished) is called after udev has
           settled and if all scripts herein return 0 the main loop will
           be ended. Arbitrary scripts can be added here, to loop in the
           initqueue until something happens, which a dracut module
           wants to wait for.

   Hook: pre-mount
       Before the root device is mounted all scripts in the hook
       pre-mount are executed. In some cases (e.g. NFS) the real root
       device is already mounted, though.

   Hook: mount
       This hook is mainly to mount the real root device.

   Hook: pre-pivot
       This hook is called before cleanup hook, This is a good place for
       actions other than cleanups which need to be called before pivot.

   Hook: cleanup
       This hook is the last hook and is called before init finally
       switches root to the real root device. This is a good place to
       clean up and kill processes not needed anymore.

   Cleanup and switch_root
       Init (or systemd) kills all udev processes, cleans up the
       environment, sets up the arguments for the real init process and
       finally calls switch_root. switch_root removes the whole
       filesystem hierarchy of the initramfs, chroot()s to the real root
       device and calls /sbin/init with the specified arguments.

       To ensure all files in the initramfs hierarchy can be removed,
       all processes still running from the initramfs should not have
       any open file descriptors left.
