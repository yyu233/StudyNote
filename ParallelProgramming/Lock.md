```
Lock num_mutex

Thread 1:

mutex_lock(&num_mutex)

# Critical Section
num++
# End

mutext_unlock(&num_mutex)

Thread2:

mutex_lock(&num_mutex)

# Critical Section
num++
#End

mutext_unlock(&num_mutex)
```

