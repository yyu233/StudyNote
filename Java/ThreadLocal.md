1. Each Thread holds a threadlocal map.
2. ThreadLocal.get()  -> identify which thread, then get the value from the threadlocal map. 
