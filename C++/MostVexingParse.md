```
A a( A() );
This could be disambiguated either as

a variable definition of class [A], taking an anonymous instance of class [A] or
a function declaration for a function which returns an object of type [A] and takes a single (unnamed) argument which is a function returning type [A] (and taking no input).
Most programmers expect the first, but the C++ standard requires it to be interpreted as the second.
```
