
There are two ways to use slices to create a matrix. Let's take a look at the differences between them.

First method:
```
matrix := make([][]int, n)
for i := 0; i < n; i++ {
    matrix[i] = make([]int, m)
}

```
Second method:
```
matrix := make([][]int, n)
rows := make([]int, n*m)
for i := 0; i < n; i++ {
    matrix[i] = rows[i*m : (i+1)*m]
}
```
In regards to the first method, making successive make calls doesn't ensure that you will end up with a contiguous matrix, so you may have the matrix divided in memory. Let's think of an example with two Go routines that could cause this:

The routine #0 runs make([][]int, n) to get allocated memory for matrix, getting a piece of memory from 0x000 to 0x07F.
Then, it starts the loop and does the first row make([]int, m), getting from 0x080 to 0x0FF.
In the second iteration it gets preempted by the scheduler.
The scheduler gives the processor to routine #1 and it starts running. This one also uses make (for its own purposes) and gets from 0x100 to 0x17F (right next to the first row of routine #0).
After a while, it gets preempted and routine #0 starts running again.
It does the make([]int, m) corresponding to the second loop iteration and gets from 0x180 to 0x1FF for the second row. At this point, we already got two divided rows.
With the second method, the routine does make([]int, n*m) to get all the matrix allocated in a single slice, ensuring contiguity. After that, a loop is needed to update the matrix pointers to the subslices corresponding to each row.
