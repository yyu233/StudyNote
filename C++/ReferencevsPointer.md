A reference is the same object, just with a different name and a reference must refer to an object. Since references can’t be NULL, they are safer to use. 

A pointer can be re-assigned while a reference cannot, and must be assigned at initialization only.
The pointer can be assigned NULL directly, whereas the reference cannot.
Pointers can iterate over an array, we can use increment/decrement operators to go to the next/previous item that a pointer is pointing to.
A pointer is a variable that holds a memory address. A reference has the same memory address as the item it references.
A pointer to a class/struct uses ‘->’ (arrow operator) to access its members whereas a reference uses a ‘.’ (dot operator)
A pointer needs to be dereferenced with * to access the memory location it points to, whereas a reference can be used directly.
