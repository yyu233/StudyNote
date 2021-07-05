Setting up cgroup is somehow distribution specific as it may already be mounted or even used somewhere. Here's general idea, however (assuming you have proper kernel configuration):

mount -t tmpfs cgroup_root /sys/fs/cgroup
mkdir -p /sys/fs/cgroup/blkio
mount -t cgroup -o blkio none /sys/fs/cgroup/blkio
Now that you have blkio controller set, you can use it:

mkdir -p /sys/fs/cgroup/blkio/limit1M/
echo "X:Y  1048576" > /sys/fs/cgroup/blkio/limit1M/blkio.throttle.write_bps_device 
Now you have a cgroup limit1M that limits write speed on device with major/minor numbers X:Y to 1MB/s. As you can see, this limit is per device. All you have to do now is to put some process inside of that group and it should be limited:

echo $PID > /sys/fs/cgroup/blkio/limit1M/tasks


The following command invokes the updatedb(8) tool, but lowers the block IO weight for it to 10. See systemd.resource-control(5) for more information on the BlockIOWeight= property.
systemd-run -p BlockIOWeight=10 updatedb
Consider using the --scope option to make systemd-run run the program in the foreground.
