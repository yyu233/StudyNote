## Class Attribute vs Instance Attribute ## 

An instance attribute is a Python variable belonging to one, and only one, object. This variable is only accessible in the scope of this object and it is defined inside the constructor function, __init__(self,..) of the class.

A class attribute is a Python variable that belongs to a class rather than a particular object. It is shared between all the objects of this class and it is defined outside the constructor function, __init__(self,...), of the class.

The below ExampleClass is a basic Python class with two attributes: class_attr and instance_attr. 

```
class ExampleClass(object):
  class_attr = 0
  def __init__(self, instance_attr):
    self.instance_attr = instance_attr
```
instance_attr is an instance attribute defined inside the constructor.     

class_attr  is a class attribute defined outside the constructor.    

When you access an attribute (instance or class attribute) as a property of an object using the dot convention, it searches first in the namespace of that object for that attribute name. If it is found, it returns the value, otherwise, it searches in the namespace of the class. If nothing is found there as well, it raises an  AttributeError. The object namespace is before the class namespace.
