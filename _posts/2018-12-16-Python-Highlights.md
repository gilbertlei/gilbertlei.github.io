---
layout: post
title: Python Highlights
---

Python is undoubtedly one of the most popular computer programming languages in today's world. I learned about it before and during my MDS program. This post is to summarize some fundamentals of Python programming.

### Data types  
Python has data types listed in below table:   

|  Data Type  |  Keyword  |  Example  |
| ----------  |  -------  |  -------  |
| integer  | int  |  42  |
| floating point number  | float  |  42.22222  |
| complex number  | complex  |  1+2j  |
| boolean  | bool  |  True  |
| string  | str  |  "Hello World"  |
| list  | list  |  ['Apple', 'Orange', 'Pear']  |
| tuple  | tuple  |  (42, 99, 'Apple', 'Orange')  |
| dictionary  | dict  |  {'name': 'Gilbert Lei', 'grade': 'A+'}  |
| range object  | range  |  range(0, 20, 2)  |
| none  | NoneType  |  Noe  |

*Notes:*  
*1. strings, tuples and ranges are immutable types. lists are mutable.*  
*2. The major difference between lists and tuples is that a list is used as a homogeneous sequence, but a tuple is used as a heterogeneous sequence.*

Each data type has some methods. Take string data type as an example:  
- str_greeting = "How are you?"  
- str_greeting.split()  
- str_greeting.lower()  
- len(str_greeting)  

Take list as another example:  
- age_list = [18, 19, 20, 18]  
- age_list.append(22)  
- age_list.count(18)  
- len(age_list)  
- type(age_list)  
- age_list[0]  
- age_list[0:2]

Here is a list of commonly used built-in functions:
- print(x)  
- type(x)  
- range(a, b, n)  
- len(seq)  
- abs(x)  
- sum(seq)  
- max(seq)  
- min(seq)  
- sorted(seq)  
- list(seq)  

### Operators
Python has below arithmetic operators:  
- \+  # plus  
- \-  # minus  
- \*  # multiply  
- /   # divide  
- \** # 幂/次方，exponentiation   
- //  # 取整，integer division   
- %   # 取余

Python has below comparison operators:  
- x == y  
- x != y  
- x > y  
- x >= y  
- x < y  
- x <= y  


### Control Flow
The most common types of control flow:
- if-elif-else
- while
- for


### Functions
This is how to define functions in Python:
```
def square(n):
  square = n**2
  return(square)
```

### Docstrings
A Docstrings is a string that follows immediately the `def` statement. It can be viewed using `?` in Jupyter Notebook.  
```
def square(n):
  "Compute the square of n."  
  square = n**2
  return(square)
```

### Python Testing  
Best practices: writing tests before you write code!!!   
```
assert square(8) == 64, "The output of square(8) should be 64."  
print("Test passed. Success!")
```


### Python class  
```
class people():  
  def __init__(self, first_name, last_name):  
    self.first_name = first_name
    self.last_name = last_name  

  def __repr__(self):
    return '{} {}'.format(self.first_name, self.last_name)

  def greeting(self):
    print("Hello! My name is {} {}. Very nice to meet you!".format(self.first_name, self.last_name))
```


### Python Modules and Packages
A Python module is a text file containing Python code that has a `.py` extension.
```
import samples      # import the module to current environment
type(samples)       # check the data type of 'samples'
dir(samples )       # list all the methods and attributes in 'samples'  
```

A Python Package is a collection of Python modules. We can think of Python modules as files and Python packages as directories. We can use `import` to import a package.  
