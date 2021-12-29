A high availability cluster also known as the fail-over cluster, contains a set of nodes running in conjunction with each other that ensures high availability of the service.

The nodes in the cluster are connected by a private network called the heartbeat network that continuously monitors the health and the status of each node in the cluster.

A single state across all the nodes in a cluster is achieved with the help of a shared distributed memory and a distributed coordination service like the Zookeeper.
