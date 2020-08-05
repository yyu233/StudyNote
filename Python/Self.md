__init__ is the constructor for a class. The self parameter refers to the instance of the object (like this in C++).

class Point:
    def __init__(self, x, y):
        self._x = x
        self._y = y
The __init__ method gets called when memory for the object is allocated:

x = Point(1,2)
It is important to use the self parameter inside an object's method if you want to persist the value with the object. If, for instance, you implement the __init__ method like this:

class Point:
    def __init__(self, x, y):
        _x = x
        _y = y
Your x and y parameters would be stored in variables on the stack and would be discarded when the init method goes out of scope. Setting those variables as self._x and self._y sets those variables as members of the Point object (accessible for the lifetime of the object).

The self is used to represent the instance of the class. With this keyword, you can access the attributes and methods of the class in python. It binds the attributes with the given arguments. The reason why we use self is that Python does not use the ‘@’ syntax to refer to instance attributes. 

Is self a Keyword?
self is used in different places and often thought to be a keyword. But unlike in C++, self is not a keyword in Python.

[Reference](https://stackoverflow.com/questions/625083/python-init-and-self-what-do-they-do)
