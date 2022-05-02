move constructor is called:

* when an object initializer is std::move(something)
* when an object initializer is std::forward<T>(something) and T is not an lvalue reference type (useful in template programming for "perfect forwarding")
* when an object initializer is a temporary and the compiler doesn't eliminate the copy/move entirely
* when returning a function-local class object by value and the compiler doesn't eliminate the copy/move entirely
* when throwing a function-local class object and the compiler doesn't eliminate the copy/move entirely
