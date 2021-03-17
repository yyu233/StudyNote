Now let’s consider the use of extern with variables. To begin with, how would you declare a variable without defining it? You would do something like this:
```
extern int var;
```
Here, an integer type variable called var has been declared (it hasn’t been defined yet, so no memory allocation for var so far). And we can do this declaration as many times as we want. So far so good. 🙂
Now, how would you define var? You would do this:
```
int var;
```
In this line, an integer type variable called var has been both declared and defined (remember that definition is the superset of declaration). Since this is a definition, the memory for var is also allocated. Now here comes the surprise. When we declared/defined a function, we saw that the extern keyword was present implicitly. But this isn’t the case with variables. If it were, memory would never be allocated for them. Therefore, we need to include the extern keyword explicitly when we want to declare variables without defining them. Also, as the extern keyword extends the visibility to the whole program, by using the extern keyword with a variable, we can use the variable anywhere in the program provided we include its declaration the variable is defined somewhere.

