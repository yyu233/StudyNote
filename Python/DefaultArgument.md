## Default Argument ##

Python 3   
Python 2 doesn't have a way to define keyword-only argument.    

Python does not support overloaded methods/functions and default arguments are an easy way of “faking” the overloading behavior.     

Ptyhon method variable will take the default value if no argument value is passed in during function call. 

```
  def _foobar(foo, bar = 'BAR')
```

The default value is evaluated only once. This makes a difference when the default is a mutable object such as a list, dictionary, or instances of most classes. 

```
def f(a, L=[]):
    L.append(a)
    return L

print(f(1))
print(f(2))
print(f(3))
```
output: 
```
[1]
[1, 2]
[1, 2, 3]

```
