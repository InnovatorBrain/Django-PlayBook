# Programming Concepts Cheat Sheet

A concise reference guide to fundamental programming concepts in python.

## Variables
```python
global x
```

## Numbers
```python
import random
print(random.randrange(1, 10))
```

## Strings
```python
"free" in txt
"expensive" not in txt
len
in
not in
#Slicing
upper()
lower()
strip()
replace()
split()
format()
...and more
```

## Operators
```python
and
or
not
is
is not
in
in not
& 	AND
|	OR
~	NOT
^	XOR
```

## Lists
```python
list()
Changing List Items
insert()
append()
extend()
remove()
pop()
del thislist[0]
clear()
List Comprehension
newlist = [x for x in fruits if "a" in x]
sort()
sort(reverse = True)
sort(key=str.lower)
reverse()
copy()
count()
index()
```

## Tuples
```python
tuple()
Modifying with Lists (`list()` or `tuple()`)
```
## Sets
Unordered, Unchangeable, Duplicates Not Allowed
```python
set()
add()
update()
remove()
discard()
clear()
union()
intersection_update()
intersection()
symmetric_difference_update()
symmetric_difference()
```
## Dictionaries
Changeable, Duplicates Not Allowed
```python
dict()
get()
keys()
values()
items()
update()
pop()
popitem()
del()
clear()
copy()
for x,y in thisdict.items():
  print(x,y)
```
## Conditional Statements
```
print() using Ternary Operators
pass
```
## Loops

### While Loop
- `break`
- `continue`

### For Loop
- `break`
- `continue`
- `range()`
- `range(2,30,3)`
- `pass`

## Functions
- `*args` and `**kwargs`
- Default Parameter Values
- `return` to pass values
- `print` for console output
- **Recursion** for problem-solving
- *...and more*

## Lambda Functions
- Ideal for compact operations
```
x = lambda a, b : a * b
print(x(5, 6))
```
## Classes and Inheritance
- `class` creation
- `__init__()` for initialization
- `__str__()` for string representation
The self parameter is a reference to the current instance of the class, and is used to access variables that belong to the class.
- `self`
- `del` for deletion
- `super()` for parent class access

## Iterators and Scope
- `iter()` and `next()`
```
myit = iter(mystr)
print(next(myit))
```
- `__iter__()` and `__next__()`
- Global and Local scope

## Modules and Math
- `import` with aliases
- `dir()` for module contents
- `from _ import _`
- `min()`, `max()`, `abs()`, `pow()`
- `math` module functions
- *...and more*

# JSON and Regular Expressions
- `import json`
- `json.load()` for JSON to Python
- `json.dumps()` for Python to JSON
```
json.dumps(x, indent=4, separators=(". ", " = "), sort_keys=True)
```
## RegEx
- `import re`
- `re.search()`, `re.findall()`, `re.split()`, `re.sub()`

## Package Management (PIP)
- `pip --version`
- `pip install package_name`
- `pip uninstall package_name`
- `pip list`

## Exception Handling (Try Except)
- `try`, `except`, `else`, `finally`

## File Handling (Try Except)
-  `with open("example.txt", "r") as file:`
- `read()` `readline()`
- `close()`
- `import os` , `os.remove(file.name)` 
