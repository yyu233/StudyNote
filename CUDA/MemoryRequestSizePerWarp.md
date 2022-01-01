Fermi and newer GPUs have at least 32 thread processors per SM. Therefore a memory transaction is immediately visible across a full warp. As a result, memory requests are issued at the per-warp level, rather than per-half-warp. However, a full memory request can only retrieve 128 bytes at a time. Therefore, for data sizes larger than 32 bits per thread per transaction, the memory controller may still break the request down into a half-warp size.