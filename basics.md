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
## Keyword arguments
Keyword arguments must follow positional arguments. The order is not important as long as this criterion is fulfilled.
## Wrap-up
A function:
```
def foo(*arg, **kwarg):
    do stuff
```
*arg = positional arguments, **kwarg = keyword arguments. These are arbitrary argument lists, meaning that arbitrary number of parameters can be passed to the function. Any argumnets after `*args` must be keyword arguments.  
For example:
```
def foo(sep, *args):
    print(args)
    print(sep.join(args))
```
Now call the function:
```
>>> foo('hello', 'goodbye', 'good night')
['hello', 'goodbye', 'good night']
'hello/goodbye/good night'
``` 
Note that the number of arguments is not specified, we only know that *args is a list of arguments of arbitrary length.
## Unpacking arguments list
Conversely, if we unpack a list of arguments passed to a function, we get seperated individual arguments. For example:
```
>>> args = [1, 4]
>>> list(range(args)) // Wont work
>>> list(range(*args)) // Arguments unpacked
[1, 2, 3]
```
## Lambda Expressions
Small, light-weight functions can be defined using lambdas. The syntax is
```
lambda *args, **args: do stuff
```
For example:
``` 
>>> f = lambda a, b: a + b
>>> print(f(1, 2))
3
```
Lambdas are often used when small functions are passed as arguments.

