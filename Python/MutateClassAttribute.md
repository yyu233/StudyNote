## Mutate Class Attribute to Instance Attribute ## 

```
if __name__ = '__main__':
 foo = ExampleClass(1)
    bar = ExampleClass(2)
    #print the class attribute as a porperty of a foo
    print foo.class_attr
    #0
    #modify the class attribute as a foo property
    foo.class_attr = 5
    print foo.class_attr
    #5
    #print the class attribute as a porperty of a bar
    print bar.class_attr
    # 0 
    #oups !!!!

```

The affectation added a new instance attribute to the object foo and only to that object which is why in the previous example the object bar kept printing the class attribute.

With immutable objects, this behavior is always the same. However, with mutable objects like lists, for example, it is not always the case, depending on how you modify your class attribute.

```
class ExampleClass(object):
  class_attr = []
  def __init__(self, instance_attr):
    self.instance_attr = instance_attr

```

```
if __name__ = '__main__':
 foo = ExampleClass(1)
    bar = ExampleClass(2)
    #print the class attribute as a porperty of a foo
    print foo.class_attr
    # []
    #modify the class attribute as a foo property
    foo.class_attr.append(0)
    print foo.class_attr
    #[0]
    #print the class attribute as a porperty of a bar
    print bar.class_attr
    # [0]
```

When a mutable class attribute is modified by an object, it does not mutateto turn into an instance attribute for that object. It stays shared between all the objects of the class with the new elements appended to it.

However, if you attach a new list to that attribute ( foo.class_attr = list("foo")) you will get the same behavior as the immutable objects.

```
if __name__ = '__main__':
 foo = ExampleClass(1)
    bar = ExampleClass(2)
    #print the class attribute as a porperty of a foo
    print foo.class_attr
    # []
    #modify the class attribute as a foo property
    foo.class_attr = list("example") 
    print foo.class_attr
    #[e,x,a,m,p,l,e]
    #print the class attribute as a porperty of a bar
    print bar.class_attr
    # []

```

[Reference](https://dzone.com/articles/python-class-attributes-vs-instance-attributes)
