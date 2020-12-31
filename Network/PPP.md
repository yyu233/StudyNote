In computer networking, Point-to-Point Protocol (PPP) is a Data link layer (layer 2) communications protocol between two routers directly without any host or any other networking in between. It can provide connection authentication, transmission encryption,[1] and compression.

PPP is used over many types of physical networks, including serial cable, phone line, trunk line, cellular telephone, specialized radio links, and fiber optic links, such as SONET. Internet service providers (ISPs) have used PPP for customer dial-up access to the Internet, since IP packets cannot be transmitted over a modem line on their own without some data link protocol that can identify where the transmitted frame starts and where it ends.

Two derivatives of PPP, Point-to-Point Protocol over Ethernet (PPPoE) and Point-to-Point Protocol over ATM (PPPoA), are used most commonly by ISPs to establish a digital subscriber line (DSL) Internet service connection with customers

```
Application	FTP	SMTP	HTTP	…	DNS	…
Transport	TCP	UDP
Network	IP
Data Link	PPP
Application	SSH
Transport	TCP
Network	IP
Data Link	Ethernet	ATM
Physical	Cables, Hubs, and so on
```
