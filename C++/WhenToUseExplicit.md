Use it when the constructor has one and only one argument
It has meaning only when applied to constructor which can be called with exactly 1 argument provided. (Either it has 1 argument or has default values for all other)

Use it only on the default, copy, and move constructor.
It is actually useless for them: default constuctor does not have arguments, and move and copy constructors parameters already has the type of that class, so no implicit conversion could happen even in theory.

Gold rule is to use explicit keyword for all constructors which can be called with one argument provided unless you want to enable implicit conversion from argument type.
