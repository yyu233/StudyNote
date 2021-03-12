The null block device (/dev/nullb*) is used for benchmarking the various block-layer implementations. It emulates a block device of X gigabytes in size. It does not execute any read/write operation, just mark them as complete in the request queue. The following instances are possible:
* Multi-queue block-layer
   * Request-based.
   * Configurable submission queues per device
*  No block-layer (Known as bio-based)
   * Bio-based. IO requests are submitted directly to the device driver.
   * Directly accepts bio data structure and returns them.

