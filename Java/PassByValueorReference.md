Like C/C++, Java creates a copy of the variable being passed in the method and then do the manipulations.

In Java, all primitives like int, char, etc are similar to C/C++, but all non-primitives (or objects of any class) are always references. So it gets tricky when we pass object references to methods. Java creates a copy of references and pass it to method, but they still point to same memory reference. Mean if set some other object to reference passed inside method, the object from calling method as well its reference will remain unaffected.
