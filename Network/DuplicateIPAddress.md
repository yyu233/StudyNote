When two devices attempt to share a single IP, you see the dreaded "Address Already in Use" Kill — with no ability to access the network.

The Quick Fix: The blame for this often rests with your router's default DHCP configuration. DHCP is probably trying to assign your new device an address at the beginning of your subnet, and another device may already occupy these low-numbered addresses with static IPs. If you've just introduced a new device or server to your network, it may have its own DHCP server. Simply disable the DHCP server on that device to restore sanity to your network.
