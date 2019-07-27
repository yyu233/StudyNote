1. Classic Load Balancer
2. Application Load Balancer
3. Network Load Balancer
4. Listener: a process that checks for connection requests using the protocal and port you configured.  The rule that you defined determine how the load balancer routes requests to the targets in one or more target groups
5. Target: a target is a destination for traffic based on the established listener rules
6. Target Group: each target group routes requests to one or more registered targets using the protocal and port number specified. A target can be registered with multiple target groups. Health check can be configured on per target group basis. 
7. Path and Host-based routing: path-based provides rules that forward requests to different target groups. Host-based can be used to define rules that forward requests to different target groups based on host name
8. Request tracing: track HTTP requests from clients to target
9. Dynamic ports utilized by scheduled containers.   
