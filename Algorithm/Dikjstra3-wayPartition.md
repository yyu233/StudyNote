## Dirkjstra 3-way Partition ##

Let v be the partitioning item a[lo]
Scan i from left to right: 
  * if (a[i] < v) swap a[lt] with a[i], increment lt and i
  * if (a[i] > v) swap a[gt] with a[i], derement gt
  * if (a[i] = v) increment i
  
### Java Implementation ###

```
public void swap (int[] nums, int i, int j) {
   int tmp = nums[i];
   nums[i] = nums[j];
   nums[j] = tmp;
}
public void sort (int[] nums, int low, int high) {
   int i = low;
   int lt = low;
   int gt = high;
   int pivot = nums[low];
   while (i < gt) {
      if (nums[i] < pivot) {
          swap(nums, lt++, i++); 
      } else if (nums[i] > pivot) {
          swap(nums, gt--, i);
      } else {
          i++;
      }
   }
   sort(nums, low, lt - 1);
   sort(nums, gt + 1, high);
}
```
