```
Lock count_mutex;

int count = 0;

Producer Thread:

mutex_lock(&count_mutex);

# Busy waiting
while (count == MAX_SIZE):
  mutex_unlock(&count_mutex);
  Thread.sleep(3000);
  mutex_lock(&count_mutex);

# Critical Section
produce();
count++;
# End

mutex_unlock(&count_mutex);
```

```
Consumer Thread:

mutex_lock(&count_mutex);

# Busy waiting
while (count == 0):
  mutex_unlock(&count_mutex);
  Thread.sleep(3000);
  mutex_lock(&count_mutex);

# Critical Section
consume();
count--;
# End

mutex_unlock(&count_mutex);
```
