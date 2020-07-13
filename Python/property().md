In Python, the main purpose of Property() function is to create property of a class.
```
Syntax: property(fget, fset, fdel, doc)

Parameters:
fget() – used to get the value of attribute
fset() – used to set the value of attribute
fdel() – used to delete the attribute value
doc() – string that contains the documentation (docstring) for the attribute

Return: Returns a property attribute from the given getter, setter and deleter.
```
Applications:
By using property() method, we can modify our class and implement the value constraint without any change required to the client code. So that the implementation is backward compatible.
