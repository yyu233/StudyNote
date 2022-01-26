* Use CamelCase for all names. Start types (such as classes, structs, and typedefs) with a capital letter, other names (functions, variables) with a lowercase letter. You may use an all-lowercase name with underscores if your class closely resembles an external construct (e.g., a standard library construct) named that way.
* C++ interfaces are named with a Interface suffix, and abstract base classes with an Abstract prefix.
* Member variables are named with a trailing underscore.
* Accessors for a variable foo_ are named foo() and setFoo().
* Global variables are named with a g_ prefix.
* Static class variables are named with a s_ prefix.
* Global constants are often named with a c_ prefix.
* If the main responsibility of a file is to implement a particular class, then the name of the file should match that class, except for possible abbreviations to avoid repetition in file names (e.g., if all classes within a module start with the module name, omitting or abbreviating the module name is OK). Currently, all source file names are lowercase, but this casing difference should be the only difference.
