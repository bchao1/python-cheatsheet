# Python Data Structures Review 
## Lists
`list.count(x)` returns the number of times `x` apprears in a list. For example:
```python
>>> print([1, 2, 2, 2, 3, 4].count(2))
3
```
`list.copy()` returns a shallow copy of the list. Use `copy.deepcopy()` in the `copy` module instead.

`list.sort(key = None, reverse = False)` sorts the list by key (can be defined using a simply lambda) **inplace**. For example:
```python
>>> L = [(1, 'c'), (2, 'b'), (3, 'a')]
>>> L.sort(key = lambda x:x[1])  # Sort by second element in tuple
>>> print(L)
L = [(3, 'a'), (2, 'b'), (1, 'c')]
```
