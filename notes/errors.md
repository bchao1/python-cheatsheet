# Errors and Exceptions
## Exceptions
Error occured during program execution are called **exceptions**.
## Exception Blocks
```python
try:
    x = int(input("Enter an integer value: "))
except ValueError:
    print("ValueError!")
```
Run this script:
```python
>>> Enter an integer value: hello
ValueError!
```
