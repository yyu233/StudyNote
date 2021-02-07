Average case analysis makes assumptions about the input that may not be met in certain cases. Therefore, if your input is not random, in the worst case the actual performace of an algorithm may be much slower than the average case.

Amortized analysis makes no such assumptions, but it considers the total performance of a sequence of operations instead of just one operation.

Dynamic array insertion provides a simple example of amortized analysis. One algorithm is to allocate a fixed size array, and as new elements are inserted, allocate a fixed size array of double the old length when necessary. In the worst case a insertion can require time proportional to the length of the entire list, so in the worst case insertion is an O(n) operation. However, you can guarantee that such a worst case is infrequent, so insertion is an O(1) operation using amortized analysis. Amortized analysis holds no matter what the input is.
