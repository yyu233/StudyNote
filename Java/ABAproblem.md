## CAS ABA problem ##
```
Thread 1: A ------> work

Thread 2: A ->B-->A 

```
Problem:   
Thread 2 change A, swap to B and then back to A. Thread 1 thinks A does not change and do the work. 

Solution:  
```
Thread 1: 1A -----> work

Thread 2: 1A ->2B->3A

```
