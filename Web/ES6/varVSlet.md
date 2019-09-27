## Overwrite Variable ##
One of the biggest problems with declaring variables with the var keyword is that you can overwrite variable declarations without an error.    
In a small application, you might not run into this type of problem, but when your code becomes larger, you might accidentally overwrite a variable that you did not intend to overwrite.   

If you were to replace var with let in the variable declarations of the code above, the result would be an error. 

## Scope ##

When you declare a variable with the var keyword, it is declared globally, or locally if declared inside a function.

The let keyword behaves similarly, but with some extra features. When you declare a variable with the let keyword inside a block, statement, or expression, its scope is limited to that block, statement, or expression.

For example:
```
var numArray = [];
for (var i = 0; i < 3; i++) {
  numArray.push(i);
}
console.log(numArray);
// returns [0, 1, 2]
console.log(i);
// returns 3
With the var keyword, i is declared globally. So when i++ is executed, it updates the global variable.
```


