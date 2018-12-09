## Insertion Sort ##

Traverse the array from left to right, compare and swap the element with each larger element to its left. 

### Java Application ###
```
  void insertionSort(int[] nums) {
    for (int i = 1; i < nums.length; i++) {
        if (nums[i] < nums[i - 1]) {
          for (int j = i; j > 0; j--) {
              if (nums[i] <= nums[j] && nums[i] >= nums[j - 1]) {
                  insert(nums[i], j);
              }
          }
        }
    }
  }
```

### Run Time ##
*0 + 1 + 2 + ... + (n-1) = (n^2)/2*
