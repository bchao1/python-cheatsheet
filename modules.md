# Modules
## Basics
```python
>>> import foo
>>> foo.__name__
foo
```
When you import a module, you might not want some irrelevant testing code to be executed.
```python
# In a module
if __name__ == "__main__":
    do stuff
```
## `dir()`
Returns a list of names a module defines.
```python
# In a module
def foo()
    ...
def bar()
    ...
```
Now we import `foo` and check `dir(foo)`
```python
>>> import foo
>>> dir(foo)
['__name__', 'foo', 'bar']
```