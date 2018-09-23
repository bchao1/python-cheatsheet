# Classes
## Objects 
In Python, passing objects to functions are like passing pointers in C++. All modifications in the function scope will also be visible to the caller.  
For example, we define a class and a function `foo` that takes an `MyClass` object as argument:
```python
class MyClass:
    def __init__(self)
        self.content = 10
def foo(obj):
    obj.content = 100
```
Now we call `foo` on a `MyClass` object:
```python
>>> x = MyClass()
>>> x.content
10
>>> foo(x)
>>> x
100
```
We can see that the content of the object passed to the function has changed.
## Scopes and Namespaces
### `nonlocal` and `global`
## Classes
### Class and Instance Variables
**Class variables** are shared by all class objects. When class variables are mutable objects, we need to be very careful.
```python
class MyClass:
    var = []
    def __init__(self):
        ...
    def add(self, num):
        self.var.append(num)
```
Now consider the following:
```python
>>> x = MyClass()
>>> y = MyClass()
>>> x.add(1)
>>> x.var
[1]
>>> y.add(2)
>>> x.var
[1, 2]
```
Be **VERY** careful when manipulating shared data. Use class variables when you won't change its value.