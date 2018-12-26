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

## Java Implementation ##

```
  void swim(int k) {
      while (k > 1 && less(k / 2, k)) {
        swap(k, k / 2);
        k = k / 2;
      }
  }
  void insert(Key k) {
      pq[++n] = k;
      swim(n);
  }
```

