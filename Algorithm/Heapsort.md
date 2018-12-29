## Heapsort ##

1. First pass: build heap by bottom-up method
2. Second pass: sort down

### Java Implementation ###

```
  public void heapsort(Comparable[] a) {
    int n = a.length;
    for (int k = n / 2; k >= 1; k--) {
        sink(a, k, n);
    }
    while (n > 1) {
        exchange(a, 1, n);
        sink(a, 1, --n);
    }
  }
```
