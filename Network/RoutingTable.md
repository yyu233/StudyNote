```
For each entry in the routing table, five items of information are listed:

The destination IP address Actually, this is the address of the destination subnet, and must be interpreted in the context of the subnet mask.
The subnet mask that must be applied to the destination address to determine the destination subnet
The IP address of the gateway to which traffic intended for the destination subnet will be sent
The IP address of the interface through which the traffic will be sent to the destination subnet
The metric, which indicates the number of hops required to reach destinations via the gateway
```

Each packet that's processed by the computer is evaluated against the rules in the routing table. If the packet's destination address matches the destination subnet for the rule, the packet is sent to the specified gateway via the specified network interface. If not, the next rule is applied.
