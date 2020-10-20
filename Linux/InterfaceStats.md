```
interface stats
RX packets is a total number of packets received.

RX errors shows a total number of packets received with error. This includes too-long-frames errors, ring-buffer overflow errors, CRC errors, frame alignment errors, fifo overruns, and missed packets.

RX dropped is a number of dropped packets due to unintended VLAN tags or receiving IPv6 frames when interface is not configured for IPv6.

RX overruns is a number of received packets that experienced fifo overruns, caused by rate at which a buffer gets full and kernel isn’t able to empty it.

RX frame is a number of misaligned frames, i.e. frames with length not divisible by 8.

TX packets is total number of packets transmitted.

TX errors, TX dropped and TX overruns are similar to RX equivalents.

TX carriers is a number of packets that experienced loss of carriers. This usually happens when link is flapping.

TX collisions is a number of transmitted packets that experienced Ethernet collisions.

TX txqueuelen is length of transmission queue.

RX bytes is a total number of bytes received over interface.

TX bytes is a total number of bytes transmitted over interface.
```
