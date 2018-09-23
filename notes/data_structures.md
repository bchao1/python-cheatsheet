# Python Data Structures Review 
## Lists
`list.count(x)` returns the number of times `x` apprears in a list. For example:

```python
>>> [1, 2, 2, 2, 3, 4].count(2)
3
```

`list.copy()` returns a shallow copy of the list. Use `copy.deepcopy()` in the `copy` module instead.

`list.sort(key = None, reverse = False)` sorts the list by key (can be defined using a simply lambda) **inplace**. For example:

```python
>>> L = [(1, 'c'), (2, 'b'), (3, 'a')]
>>> L.sort(key = lambda x:x[1])  # Sort by second element in tuple
>>> L
L = [(3, 'a'), (2, 'b'), (1, 'c')]
```

## List Comprehensions
Write clean `list` expressions using compact one-liners.  
For example, the following code creates a list of integers and its square.

```python
>>> L = [(x, x**2) for x in range(1, 4)]s
>>> L
[(1, 1), (2, 4), (3, 9)]
```
***
## Tuples
Tuples are immutable objects.
### Tuple packing

```python
>>> x = 1, 2, 3
>>> x
(1, 2, 3)
```

### Singleton tuples
```python
>>> x = 1,  # Note the comma
>>> x
(1,)
>>> type(x)
<class 'tuple'>
```
***
## Sets 

Initialize sets using `set()` not `{}`.

```python
>>> x = {}
>>> type(x)
<class 'dict'>
>>> x = set()
>>> type(x)
<class 'set'>
```

`set` objects supports various set operations:
- union : `|`
- intersection : `&`
- complement : `-`
- disjunctive union : `^`
***
## Dictionaries
### Constructor
`dict()` constructor builds dictionaries from sequence of key-value pairs.

```python
>>> dict([(1, 'a'), (2, 'b'), (3, 'c')])
{1: 'a', 2: 'b', 3: 'c'}
```

We can also use keyword arguments (when keys are strings). 
```python
>>> dict(a = 1, b = 2, c = 3)
{'a': 1, 'b': 2, 'c': 3}
```
***
## Looping through sequences
### `item()` method
When looping through dictionaries, use `items()` to retrive key and value at the same time (usually we only access the key and then use `[]` to access the value).
```python
>>> d = {'a': 1, 'b': 2, 'c': 3}
>>> for k, v in d.items():
    ... print(k, v)
    ...
a 1
b 2 
c 3
```
### `zip()` method
To iterate through multiple sequences at the same time, use the built-in `zip()` method (Note: the length of `zip(x, y)` will be the length of the shorter sequence).
```python
>>> x = [1, 2, 3]
>>> y = ['a', 'b', 'c']
>>> for i, j in zip(x, y):
    ... print(i, j)
    ...
1 'a'
2 'b'
3 'c'
```
