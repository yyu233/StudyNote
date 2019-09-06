```
Node {
  boolean pred
  boolean locked
}
```

when thread A acquires lock, it create Node A, set locked to be true, set tail pointer to node.    
when thread B tries to acquire lock, it creates Node B, set pred to Node A's locked, insert between node and tail, Node B pred is in while loop to wait for the pred to become false which indicates thread A releases the lock. 

