

A pool is used to avoid constantly creating and destroying resources that are costly to create. A resource from a pool can be used by only one client at a time. Available resources are stored in the pool. When you need one, you get it from the pool and thus make it unavailable to other clients. When you're done with the resource, you put it back to the pool. Pools are used for database connections and threads, typically. Another advantage is that it allows maintaining the number of resources (connections, threads) to a reasonable maximum.

A cluster is a collection of nodes (computers, virtual machines) which allows serving a larger number of concurrent clients (scalability) and avoiding a single point of failure (failover, redundancy). Also note that load balancers are not necessarily random. In many cases, the load balancer uses sticky sessions: once a client has been assigned to a node of the cluster, all his subsequent requests go to the same node.

The goals are thus not the same between a pool and a cluster. And the resources stored in a pool are not the same kind as the resources of a cluster.
