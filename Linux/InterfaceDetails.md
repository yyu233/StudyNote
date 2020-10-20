```
interface details
Let’s look closely at details of ifconfig output:

Link encap shows how packets are encapsulated for transmission. Most interfaces wrap packets in Ethernet frames.

HWaddr is hardware address of the ethernet interface (also known as MAC address).

inet addr is IPv4 address assigned to the interface.

Bcast is broadcast address for the interface.

Mask is network mask for the interface.

inet6 addr is IPv6 address assigned to the interface.

Scope is scope of IPv6 address. It can be link-local or global. Link-local address is used in local area network and is not routable. Global address is routable.

UP indicates that kernel modules related to the interface have been loaded and interface is activated.

BROADCAST indicates that interface is configured to handle broadcast packets, which is required for obtaining IP address via DHCP.

RUNNING indicates that interface is ready to accept data.

MULTICAST indicates that interface supports multicasting.

MTU is maximum transmission unit. IP datagrams larger than MTU bytes will be fragmented into multiple Ethernet frames.

Metric determines the cost of using the interface. Interfaces with lower cost have higher priority.
```
