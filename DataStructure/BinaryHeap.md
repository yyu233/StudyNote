## Binary Heap ##

**Definition**  
Array representation of a heap ordered complete binary tree. 

Heap Ordered complete binary tree: 
Keys in node and parent key is no smaller than the children's key.

Largest key is at array[1], which is the root of the binary tree.

Parent of node at k is k/2
Children of node at k is 2k and 2k + 1

Insert node at the end and swim up.
Pop maximum: exchange root with the node at the end, and sink it down.

## Time Complexity ##

Insert: O(log(n))
DelMax: O(log(n))

## Java Implementation ##

```
  void swim(int k) {
      while (k > 1 && less(k / 2, k)) {
        swap(k, k / 2);
        k = k / 2;
      }
  }
  void sink(int k) {
    while ( 2 * k <= n) {
      int j = 2 * k;
      if (j < n && less(j, j + 1) {
          j++;
      }
      if (!less(k, j)) {
          break;
      }
      exchang(k, j);
      k = j;
    }
  }
  Key delMax() {
    Key max = pq[1];
    exchange(1, n--);
    sink(1);
    pq[n+1] = null;
    return max;
  }
  void insert(Key k) {
      pq[++n] = k;
      swim(n);
  }
```

