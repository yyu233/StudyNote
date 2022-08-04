In simple words, bank conflict is a case when any memory access pattern fails to distribute IO across banks available in the memory system. The following examples elaborates the concept:-

Let us suppose we have two dimensional 512x512 array of integers and our DRAM or memory system has 512 banks in it. By default the array data will be layout in a way that arr[0][0] goes to bank 0, arr[0][1] goes to bank 1, arr[0][2] to bank 2 ....arr[0][511] goes to bank 511. To generalize arr[x][y] occupies bank number y. Now some code (as shown below) start accessing data in column major fashion ie. changing x while keeping y constant, then the end result will be that all consecutive memory access will hit the same bank--hence bank conflict.
```
int arr[512][512];
  for ( j = 0; j < 512; j++ ) // outer loop
    for ( i = 0; i < 512; i++ ) // inner loop
       arr[i][j] = 2 * arr[i][j]; // column major processing
```
Such problems, usually, are avoided by compilers by buffering the array or using prime number of elements in the array.
