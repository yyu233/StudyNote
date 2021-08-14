```
10.0.0.0        -   10.255.255.255  (10/8 prefix)
172.16.0.0      -   172.31.255.255  (172.16/12 prefix)
192.168.0.0     -   192.168.255.255 (192.168/16 prefix)
```

The three private address ranges, and many other address ranges, are not allowed to be routed on the Internet. IANA owns the private address ranges and has allowed anyone to use them as they wish, as long as they are not routed on the Internet. They are simply network addresses used the same way as public addresses, except that any Internet provider will drop any packets with a private address.

Your pings to private addresses on the Internet never made it to the Internet since your provider dropped them at the PE.
