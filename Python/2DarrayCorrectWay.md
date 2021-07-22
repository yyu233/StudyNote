```
Method 2a
rows, cols = (5, 5)
arr = [[0]*cols]*rows
```
```
Method 2b
rows, cols = (5, 5)
arr = [[0 for i in range(cols)] for j in range(rows)]
```
```
# lets change the first element of the
# first row to 1 and print the array
arr[0][0] = 1
 
for row in arr:
    print(row)
# outputs the following
#[1, 0, 0, 0, 0]
#[1, 0, 0, 0, 0]
#[1, 0, 0, 0, 0]
#[1, 0, 0, 0, 0]
#[1, 0, 0, 0, 0]

```
We expect only the first element of first row to change to 1 but the first element of every row gets changed to 1 in method 2a. This peculiar functioning is because Python uses shallow lists which we will try to understand.
In method 1a, Python doesn’t create 5 integer objects but creates only one integer object and all the indices of the array arr point to the same int object as shown. 
