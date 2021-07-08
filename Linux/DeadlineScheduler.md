The Deadline scheduler works by creating two queues: a read queue and a write queue. Each I/O request has a time stamp associated that is used by the kernel for an expiration time.

While this scheduler also attempts to service the queues based on the most efficient ordering possible, the timeout acts as a "deadline" for each I/O request. When an I/O request reaches its deadline, it is pushed to the highest priority.

While tunable, the default "deadline" values are 500 ms for Read operations and 5,000 ms for Write operations. Based on these values, we can see why the Deadline scheduler is considered an optimal scheduler for read-heavy workloads. With these timeout values, the Deadline scheduler may prioritize reads more than writes.
