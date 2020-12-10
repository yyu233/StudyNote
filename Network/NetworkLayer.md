TCP/IP network model

5. Application layer: Message This layer consists of the connection protocols required for various network applications to communicate, such as HTTP, DHCP, SSH, FTP, SMTP, IMAP, and others. When you request a web page from a remote web site, a connection request is sent to the web server and the response is sent back to your host at this layer and then your browser displays the web page in its window.

4. Transport layer: TCP segment. The transport layer provides end-to-end data transport and flow management services that are independent of the data and types of protocols being transported. It uses ports such as 80 for HTTP and 25 for SMTP to make connections between the sending host and the remote host.

3. Internet layer: Packet. Packet routing is performed on the Internet layer. This layer is responsible for routing packets across two or more different networks in order to reach their final destination. This layer uses IP Addresses and the routing table to determine which device to send the packets to next. If sent to a router, each router is responsible for sending the data packets only to the next router in the series and not for mapping out the entire route from the local host to the target host. The Internet layer is mostly about routers talking to routers in order to determine the next router in the chain.

2. Data Link layer: Frame. The Link layer manages the direct connections between hardware hosts on a single, local, logical, physical network. This layer uses the Media Access Control (MAC) addresses embedded in the Network Interface Cards (NICs) to identify the physical devices attached to the local network. This layer cannot access hosts that are not on the local network.

1. Physical layer: Bits. This is the hardware layer and consists of the NICs and the physical Ethernet cable as well as the hardware level protocols used to transmit individual bits that make up the data frames between any two hosts or other network nodes that are locally connected.
