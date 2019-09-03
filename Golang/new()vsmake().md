The builtin new(T) function allocates “zeroed” storage for a new item of type T and returns its address, a value of type *T. In Go terminology, it returns a pointer to a newly allocated zero value of type T    

The make() function, on the other hand, is a special built-in function that is used to initialize slices, maps, and channels. Note that make() can only be used to initialize slices, maps, and channels, and that, unlike the new() function, make() does not return a pointer.
