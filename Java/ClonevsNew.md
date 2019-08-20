If we need to use many object having the same data, then don't create objects using new keyword. use clone method to create that object, because operation of creating object with clone method is faster than using new keyword.   

Simply copy the values of all the properties into another instance of the same class. But what about the variables that are references to other objects? Copies of these reference values mean they will point to the same objects as the first class.

But maybe that is not what we want. Perhaps we want all the objects referenced by the copy to be independent copies as well.

These two types of object copies are called:

shallow copy - exact bit copy of all the attributes of the original object deep copy - primitives are copied exactly but objects referenced are copied rather than the references themselves. The Object class, which is inherited by all Java classes, includes the clone() method that will make exact bit copies of all the properties.

However, clone() is a protected method. So a given object can not be cloned by instances of any classes outside the package (unless they are subclasses of that object's class). This allows the class designer to specify explicitly what kind of clones (shallow or deep) to make.

Java requires classes that want to override the clone() method, to implement the cloneable interface. The clone() method must be made public as well so as to override the access restrictions.

For example, the HashTable class implements cloneable. Its clone() method makes a shallow copy so the keys and values of the copied HashTable will reference the same objects as the original.

Many core Java classes, however, do not implement cloneable. If the clone() method is invoked for such classes, a CloneNotSupportedException will result.
