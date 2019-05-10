## Early Binding vs Late Binding ##
In OOP, a child class inherits from a base class. This child can be referenced by its actual type or its base class type. Some methods from the base class are overridden by this child class. The method can be resovled at the compilation time or at the runtime. If the function is virtual in the base class, invoking the function will call the child class implementation regardless of the reference type of the object. If the funciton is not virtual, the method is resolved at compilation time and the implementation of a function of the reference type of the object is called.

## Underlying Implemenation of Virtual: VPTR & VTABLE

At compilation time, compiler creates a virtual lookup table storing the address of each virtual function of the class. Compiler also creates a hidden pointer VPTR which points to the location of VTABLE. When a class inherits from a base class, the VPTR sets to the location of the VTABLE of the derived class. When a virtual function of the base class gets overriden by the derived class, the entry for the address of that virtual function in the VTABLE of the derived class gets updated. 
