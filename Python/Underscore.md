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

** Single Trailing Underscore**

```
Tkinter.Toplevel(master, class_='ClassName') # Avoid conflict with 'class' keyword
list_ = List.objects.get(1) # Avoid conflict with 'list' built-in type
```

[Reference](https://hackernoon.com/understanding-the-underscore-of-python-309d1a029edc)
