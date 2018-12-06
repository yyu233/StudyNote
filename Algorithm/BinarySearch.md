## Binary Search ## 

Step:
1. Array is sorted.
2. Compare the search value with the median value.
3. If less than the median, recursively search the left half.
4. If greater than the median, recursivley search the right half.
5. If equal to the median, we foudn the value.

### Time Complexity ###

*T(n) = O(log(n))*

### Java Implementation ###

```
int binarySearch(int[] nums, int d) {
      int low = 0;
      int high = nums.length - 1;
      while (low <= high) {
          int mid = low + (high - low) / 2;
          if (d > mid) {
            low = mid + 1;  
          } else if (d < mid) {
            high = mid - 1;
          } else {
            return mid;
          }
      }
      return -1;
  }
```
