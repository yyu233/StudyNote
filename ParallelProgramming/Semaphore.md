val = max number of threads for sharing resources, if <= 0: wait 
ops: wait, signal

```
# Producer
Semaphore emptyCount = N

# Critical
Semaphore mutex = 1

# Consumer
Semaphore fullCount = 0

Producer Thread:

sem_wait(&emptyCount)

sem_wait(&mutex)

# Critical
produce()
# End

sem_signal(&mutex)

sem_signal(&fullCount)
```

```
Consumer Thread:

sem_wait(&fullCount)

sem_wait(&mutex)

# Critcal
consume()
# End

sem_signal(&mutex)

sem_signal(&emptyCount)

```
