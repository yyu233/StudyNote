Fair Discpline: thread waiting longest is granted the lock first

Non-fair Discpline: thread waiting longest may not be granted the lock first  

Non-fair lock is more efficient than fair lock. Context switch for thread from blocked to unblocked. For unfair lock, some thread can get the lock first and finish its task while the other thread is waiting for context switch (interval overlapping).
