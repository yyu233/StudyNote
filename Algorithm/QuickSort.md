## Quick Sort
Step:
1. Find Pivot (Firts, last, random, median element)
2. Low pointer points at the first element of the remaining array, high pointer points at the last element
3. Low pointer points at a larger value than the pivot value, stops; high pointer points at at a smaller value than the pivot value; swap 
4. Repeat until low pointer and high pointer cross each other, swap the pivot with the low pointer. 
5. Divide the array into two parts from the pivot point.
6. Repeat from 1 to 5

### Time Complexity 

*T(n) = T(k) + T(n - k - 1) + &theta;(n)*

**Worst Case**: when the array is sorted in either increasing order or decreasing order, and pivot is the first element or last element. 

*k = 0,  T(n) = T(0) + T(n - 1) + &theta;(n)*

*O(n^2)*

**Best Case**: when pivot is the middle element 

*T(n) = T(n/2) + &theta;(n)* 

*O(nlog(n))*

### Java Implementation ###

```
  public int partition(int[] nums, int low, int high) {
      int i = low;
      int j = high + 1;
      while (true) {
        while (nums[++i] < nums[low]) {
            if (i == high) {
                break;
            }
        }
        while (nums[--j] > nums[low]) {
            if (j == low) {
                break;
            }
        }
        if (i > j) {
            break;
        } else {
            int tmp = nums[i];
            nums[i] = nums[j];
            nums[j] = tmp;
        }
      }
      int tmp = nums[low];
      nums[low] = nums[j];
      nums[j] = tmp;
      return j;
  }
  
  public void sort(int[] nums, int low , int high) {
    if (high < low) return;
    int j = partition(nums, 0, nums.length);
    sort(nums, 0, j);
    sort(nums, j + 1, high);
  }
  
  public void sort(int[] nums) {
      Collections.shuffle(nums); // stay tuned
      sort(nums, 0, nums.length - 1); 
  }
```

