# Python Basics Review

## Functions
### Default function arguments 
The default function value will only be evaluated once. Be careful when using mutable objects as default arguments.
```
def foo(L = []):
    L.append(1)
    return L
```
After calling function three times:
```
>>> print(foo())
[1]
>>> print(foo())
[1, 1]
>>> print(foo())
[1, 1, 1]
```
