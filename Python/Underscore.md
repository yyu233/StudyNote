## Underscore ##

**Single Leading Underscore**

Private class, variable, method

```
_internal_name = 'one_nodule' # private variable
_internal_version = '1.0' # private variable

class _Base: # private class
    _hidden_factor = 2 # private variable
    def __init__(self, price):
        self._price = price
    def _double_price(self): # private method
        return self._price * self._hidden_factor
    def get_double_price(self):
        return self._double_price()
```
You can still call the method using its mangled name, so this feature doesn’t provide much protection.

You should know the following for accessing private members and private functions:

1. When you write to an attribute of an object, that does not exist, the python system will normally not complain, but just create a new attribute.
2. Private attributes are not protected by the Python system. That is by design decision.
3. Private attributes will be masked. The reason is, that there should be no clashes in the inheritance chain. The masking is done by some implicit renaming. Private attributes will have the real name "__<className>_<attributeName>"   With that name, it can be accessed from outside. When accessed from inside the class, the name will be automatically changed correctly. 
 
[Reference](https://medium.com/@manjuladube/encapsulation-abstraction-35999b0a3911)

** Single Trailing Underscore**

```
Tkinter.Toplevel(master, class_='ClassName') # Avoid conflict with 'class' keyword
list_ = List.objects.get(1) # Avoid conflict with 'list' built-in type
```

[Reference](https://hackernoon.com/understanding-the-underscore-of-python-309d1a029edc)
