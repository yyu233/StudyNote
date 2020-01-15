After the kernel boots, udevd is used to create device nodes for all detected devices. That is a relatively time consuming task that has to be completed for the boot process to continue, otherwise there is a risk of services failing due to missing device nodes.

udevadm settle waits for udevd to process the device creation events for all hardware devices, thus ensuring that any device nodes have been created successfully before proceeding.
