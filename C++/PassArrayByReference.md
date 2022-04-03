```
void Func(int (&myArray)[100])
^ Pass array of 100 int by reference the parameters name is myArray;

void Func(int* myArray)
^ Pass an array. Array decays to a pointer. Thus you lose size information.

void Func(int (*myFunc)(double))
^ Pass a function pointer. The function returns an int and takes a double. The parameter name is myFunc.
```
