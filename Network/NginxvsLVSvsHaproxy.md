Three major software load balancer comparisons (LVS VS Nginx VS Haproxy)
LVS：
1. Strong anti-loading ability. Strong anti-loading capability, high performance, can reach 60% of F5 hardware; low consumption of memory and cpu resources
2, work in the network layer 4, through the vrrp protocol forwarding (for distribution purposes only), the specific traffic is handled by the Linux kernel, so no traffic is generated.
2, stability, reliability, and have a perfect hot standby solution; (such as: LVS + Keepalived)
3, a wide range of applications, can load balance all applications;
4, does not support regular processing, can not do dynamic separation.
5, support load balancing algorithm: rr (round robin), wrr (weighted round robin), lc (minimum connection), wlc (weight minimum connection)
6, the configuration is complex, the network dependence is relatively large, the stability is very high.
Ngnix：
1. Working on the 7th layer of the network, you can do some shunting strategies for http applications, such as domain name and directory structure;
2. Nginx's dependence on the network is relatively small. In theory, the load function can be performed by pinging.
3, Nginx installation and configuration is relatively simple, the test is more convenient;
4, can also bear high load pressure and stability, generally can support more than 10,000 times of concurrent;
5, the health check of the back-end server, only supports detection through the port, does not support detection by url.
6, Nginx asynchronous processing of requests can help the node server to reduce the load;
7, Nginx can only support http, https and Email protocols, so it is less applicable.
8, does not support the direct maintenance of the Session, but can be solved by ip_hash. Support for the Big request header is not very good.
9. Support load balancing algorithms: Round-robin, Weight-round-robin, Ip-hash (Ip hash)
10, Nginx can also do the Web server Cache function.
 
The characteristics of HAProxy are:
1. Support two proxy modes: TCP (four layers) and HTTP (seven layers), supporting virtual hosts;
2, can supplement some of Nginx's shortcomings such as the maintenance of Session, the guidance of cookies, etc.
3, support url detection back-end server problem detection will be very helpful.
4. More load balancing strategies such as Dynamic Round Robin, Weighted Source Hash, Weighted URL Hash, and Weighted Parameter Hash have been implemented.
5, purely in terms of efficiency, HAProxy will have better load balancing speed than Nginx.
6, HAProxy can load balance Mysql, detect and load balance the DB node at the back end.
9. Support load balancing algorithms: Round-robin, Weight-round-robin, source (original address hold), RI (request URL),Rdp-cookie (according to cookies)
10, can not be a web server that is Cache.
 
 
 
The three major software load balancers are suitable for business scenarios:
1. In the initial stage of website construction, Nigix/HAproxy can be selected as the reverse proxy load balancing (or load balancing can be omitted if the traffic is not large), because its configuration is simple and the performance can meet the general business scenarios. If you consider that the load balancer has a single point problem, you can use Nginx+Keepalived/HAproxy+Keepalived avoids a single point problem with the load balancer itself.
2. After the website reaches a certain level of concurrency, in order to improve stability and forwarding efficiency, LVS can be used. After all, LVS is more stable than Nginx/HAproxy, and the forwarding efficiency is higher. However, the maintenance of LVS will also require higher maintenance personnel and higher input costs.

Note: Niginx compares with Haproxy: Niginx supports seven layers, the largest number of users, and relatively stable stability. Haproxy supports four layers and seven layers, supports more load balancing algorithms, supports session saving, and so on. The specific selection depends on the usage scenario. At present, Haproxy has been making up for the disadvantages of some Niginx users.

[Reference](http://www.programmersought.com/article/5753215316/)
