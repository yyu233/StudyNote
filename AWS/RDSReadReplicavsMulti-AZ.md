An RDS read replica instance is an asynchronous read-only replica of an upstream primary ("master") database instance. It can be used by your application for any query that does not require changing data, thus relieving load from the master. If the replica crashes or fails, it has no impact on the master but the replica itself can no longer handle any traffic.

Multi-AZ means the database instance has a standby spare server machine and spare hard drive in a different availability zone of the same region. This is a synchronous replica, but cannot be accessed by you. If the active server fails, the spare server takes over and starts handling traffic more quickly than would be possible without the spare.

Multi-AZ is a deployment strategy for higher reliability. It reduces the downtime required for version upgrades, and reduces the impact of backup snapshots and creation of replicas, since snapshots can be done from the spare (by the service). It doubles the cost of the instance because of the hot standby capacity it provides.

Multi-AZ typically used only on the master instance, for fast recovery.
