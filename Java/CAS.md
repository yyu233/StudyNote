## Compare and Swap ## 

CAS(memory addres, A, B) ->  while(get A): A is expected value, swap A with B. 

CAS volatile variable

```
public final int getAndIncrement() {
            for (;;) {
                  int current = get();
                int next = current + 1;
                if (compareAndSet(current, next))
                    return current;
            }
        }

```
