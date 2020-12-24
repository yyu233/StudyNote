PCI standardizes a certain procedure for discovery of devices on the bus. This procedure can be triggered at any time (not exclusively on boot) by hotplug controller or even manually, via /sys/bus/pci/rescan (see pci_rescan_bus).

The scan will proceed recursively, traversing the bridges as discovered and reading the configuration space data off each device encountered (see PCI configuration space).

For each device found, if not yet active, the kernel will look for an instance of pci_driver object with a matching pci_device_id. Then it will call the probe method of that object (the rest is driver implementation specific).

If appropriate pci_driver instance is not found, kernel will emit an event to an user space daemon (udev or hotpug or whatever), which may load an appropriate module and create the necessary pci_driver object.
