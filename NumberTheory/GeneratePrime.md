## Generate Prime ## 

```
int size = Integer.MAX_VALUE;
int[] buf = new int[size];

for (int i = 0; i < size; i++) {
    buf[i] = 0;
}

for (int i = 2; i < size; i++) {
    if (buf[i] == 0) {
        for (int j = 2; i * j < size; j++) {
            buf[i * j] = 1;    
        }
    }
}
```

Time Complexity: O(nloglogn) 
