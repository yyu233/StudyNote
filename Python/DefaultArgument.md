## Default Argument ##

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
