A network interface is a software interface to networking hardware. Linux kernel distinguishes between two types of network interfaces: physical and virtual.

Physical network interface represents an actual network hardware device such as network interface controller (NIC). In practice, you’ll often find eth0 interface, which represents Ethernet network card.

Virtual network interface doesn’t represent any hardware device and is usually linked to one. There are different kinds of virtual interfaces: Loopback, bridges, VLANs, tunnel interfaces and so on. With proliferation of software defined networks, virtual interfaces become wildly used.

