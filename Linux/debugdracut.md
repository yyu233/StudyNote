      If you are dropped to an emergency shell, the file
       /run/initramfs/rdsosreport.txt is created, which can be safed to a (to
       be mounted by hand) partition (usually /boot) or a USB stick.
       Additional debugging info can be produced by adding rd.debug to the
       kernel command line. /run/initramfs/rdsosreport.txt contains all logs
       and the output of some tools. It should be attached to any report about
       dracut problems.
