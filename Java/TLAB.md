## Thread Local Allocation Buffer ## 

In Java, new objects are allocated in Eden. TLAB is a region inside Eden. It is exclusively assigned to a thread. Each thread has own TLAB. If TLAB gets full, thread will be allocated a new TLAB or allocated outside TLAB. If a thread allocates a large object that cannot fit into the TLAB, it will be allocated in the shared region of Eden. 
