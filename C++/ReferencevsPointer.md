A reference is the same object, just with a different name and a reference must refer to an object. Since references can’t be NULL, they are safer to use. 

A pointer can be re-assigned while a reference cannot, and must be assigned at initialization only.
The pointer can be assigned NULL directly, whereas the reference cannot.
Pointers can iterate over an array, we can use increment/decrement operators to go to the next/previous item that a pointer is pointing to.
A pointer is a variable that holds a memory address. A reference has the same memory address as the item it references.
A pointer to a class/struct uses ‘->’ (arrow operator) to access its members whereas a reference uses a ‘.’ (dot operator)
A pointer needs to be dereferenced with * to access the memory location it points to, whereas a reference can be used directly.

* Use references 
In function parameters and return types.
* Use pointers: 
Use pointers if pointer arithmetic or passing NULL-pointer is needed. For example for arrays (Note that array access is implemented using pointer arithmetic).
To implement data structures like linked list, tree, etc and their algorithms because to point different cell, we have to use the concept of pointers.


Apart from syntactic sugar, a reference is a const pointer (not pointer to a const). You must establish what it refers to when you declare the reference variable, and you cannot change it later.

Update: now that I think about it some more, there is an important difference.

A const pointer's target can be replaced by taking its address and using a const cast.

A reference's target cannot be replaced in any way short of UB.

This should permit the compiler to do more optimization on a reference.
