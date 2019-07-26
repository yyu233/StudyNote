## Scope and Variable Binding ##

 There is no new scope introduced by using try except clause

There are three scopes in Python for all code blocks, but the functions:
* Local
* Global
* Builtin

There are four blocks in Python for the functions only (according to PEP 227):
* Local
* Enclosing functions
* Global
* Builtin

The rule for a variable to bind it to and find it in a block is quite simple:
* any binding of a variable to an object in a block makes this variable local to this block, unless the variable is declared global (in that case the variable belongs to the global scope)
* a reference to a variable is looked up using the rule LGB (local, global, builtin) for all blocks, but the functions
* a reference to a variable is looked up using the rule LEGB (local, enclosing, global, builtin) for the functions only.
