## Lock ## 

```
 lock.lock();
 //do my work
 lock.unlock();
```
problem: if do my work throws exception, lock is not unlocked.

correct way:
```
  lock.lock();
  try {
      //do my work
  } finally {
      lock.unlock();
  }
  
```
