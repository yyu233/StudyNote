var and let are both used for variable declaration in javascript but the difference between them is that var is function scoped and let is block scoped. It can be said that a variable declared with var is defined throughout the program as compared to let.

```
Input:
console.log(x);
var x=5;
console.log(x);
Output:
undefined
5
```

```
Input:
console.log(x);
let x=5;
console.log(x);
Output:
Error

```
