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

```
x = "x in module"
class A():
    print "A: "  + x                    #x in module
    x = "x in class A"
    print locals()
    class B():
        print "B: " + x                 #x in module
        x = "x in class B"
        print locals()
        def f(self):
            print "f: " + x             #x in module
            self.x = "self.x in f"
            print x, self.x
            print locals()

>>>A.B().f()
A: x in module
{'x': 'x in class A', '__module__': '__main__'}
B: x in module
{'x': 'x in class B', '__module__': '__main__'}
f: x in module
x in module self.x in f
{'self': <__main__.B instance at 0x00000000026FC9C8>}
```

[GOOD EXAMPLES](https://stackoverflow.com/questions/20246523/how-references-to-variables-are-resolved-in-python)
