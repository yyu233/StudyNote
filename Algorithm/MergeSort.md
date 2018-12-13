## Merge Sort ##

1. Find middle point of the array 
2. Divide into halves
3. Recursivley divide the two halves
4. Merge the two sorted halves 

### Time Complexity ###

*T(n) = 2T(n/2) + &theta;(n)*

### Space Complexity ###

*O(n)*

### Application of Merge Sort ###

Merge sort is good for linked list. No extra space needed. Sequential access. 

### Java Implementation ###

**Top Down Approach**
```
public void merge(int[] nums, int low, int mid, int high) {
    int n = nums.length;
    int[] aux = new int[n];
    int j = low;
    int k = mid + 1;
    for (int i = low; i <= high; i++) {
        aux[i] = nums[i];
    }
    for (int i = low; i <= high; i++) {
        if (j > mid) {
            nums[i] = aux[k++];
        } else if (k > high) {
            nums[i] = aux[j++];
        } else if (aux[j] >= aux[k]) {
            nums[i] = aux[k++];
        } else {
            nums[i] = aux[j++];
        }
    }
}
public void sort(int[] nums, int low , int high) {
    if (low == high) return;
    int mid = low + (high - low) /2; // (high + low) / 2 may cause overflow and produce incorrect result
    sort(nums, low , mid);
    sort(nums, mid + 1, high);
    merge(nums, low, mid, high);
}
public void mergesort(int[] nums) {
    sort(nums, 0, nums.length - 1);
}
```
Use insertion for small subarrays since merge sort has too much overhead for small subarrays. 

**Bottom Up Approach**
```
    public void mergesort(int[] nums) {
        int len = nums.length;
        for (int size = 1; i < len; size += size) {
            for (int low = 0; i < len - size; low += size) {
                merge(nums, low, low + size - 1, Math.min(low + size + size - 1, len - 1);
            }
        }
    }
```
