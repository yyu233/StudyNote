If you’re dealing with an I/O bound operation, multithreading is a good option so that you can benefit from reducing I/O wait time.

If you’re dealing with CPU-bound tasks, multiprocessing is a good option so that we can get benefit from multiple CPUs.

Since we’re focussing on I/O bound operation, multithreading would outperform multiprocessing because of the below reasons-

i. For CPU bound programs, multiprocessing would be the best option and not multithreading because of Global Interpreter Lock (GIL).        
ii. For I/O bound programs, multiprocessing would improve performance, but the overhead tends to be higher than when using multithreading.
