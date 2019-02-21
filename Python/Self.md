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

[Reference](https://stackoverflow.com/questions/625083/python-init-and-self-what-do-they-do)
