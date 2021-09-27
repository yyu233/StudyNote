```
Choose an element from the array as pivot, exchange the position of pivot and number at the end of the array.
The pivot can either be the end element or a random chosen element. A random chosen pivot can make the algorithm much possibly run in average case time.
Partition the array into 2 parts in which the numbers in left subarray is less than (or equal to) the pivot and the numbers in right subarray is greater than (or equal to) the pivot.
Exchange pivot (at the end of the array now) with the first element in the right part.
Compare k with length of the left subarray, say, len.
if k == len + 1， then pivot is the target.
if k <= len, repeat from step 1 on the left subarray.
if k > len, k = k - len, repeat from step 1 on the right subarray.
```
