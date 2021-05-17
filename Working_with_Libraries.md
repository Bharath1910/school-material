# Using Python Libraries

## Index
* [**Modularization of python program**](#Modularization-of-python-program)

* [**Using Python Libraries**](#Using-Python-Libraries)

  * [**Using Module**](#Using-Module)

    * [Import statement](#Python-Import-statement)
    * [Import with renaming](#)
    * [python ``from`` import statement](#)
    * [import all names](#)

  * [**Using Package**](#)

  * [**Using Library**](#)

  * [**Using Framwork**](#)


## Modularization of python program
![Imgur](https://i.imgur.com/R91uEwv.png) 

- Framework = Multiple Libraries 

- Library = Multiple Package

- Package = Multiple Modules

- Module = Multiple Functions/Class


---

## Using Python Libraries

Following terms must be clear while developing any python
project/program.

1. Module
2. Package
3. Library
4. Framework

---

## Using Module

It is a file which contains python functions / global
variables / clases etc.

It is just ``.py`` file which has python executable code / statement.

For example: Let’s create a file ``usermodule.py``

```py
def hello_world(user_name):
	return "Hello" + user_name
```

Now we can import `usermodule.py` module either in python interpreter another `py` file.

```py
import usermodule
print(usermodule.hello_message("India"))
```
---

## How to import modules in Python? Python module can be accessed in any of following way.

### Python Import statement
```py
import math
print("2 to the power 3 is", math.pow(2,3))
```
Just similar to math ,user defined module can be accessed using import statement


---
### Import with renaming
```py
import math as mt 
print("2 to the power 3 is", mt.pow(2,3))

```
You can use `as` keyword to change the name of the module

---

### Python ``From`` Import statement

```py
from math import pow
print("2 to the power 3 is", pow(2,3))
```
**Note -** You don't need to provide the Module's name when import a specific function. That is, you don't need to provide `math.pow()` but instead, you can use `pow()` directly

---

### Import all names

```py
from math import *
print("2 to the power 3 is", pow(2,3))
```
Similar to importing a specific function, Importing all functions does not requires to specify the module's name

---

## Using Package

- It is namespace that contains multiple package or modules. 
- It is a directory which contains a special file ``__init__.py``.
- Let’s create a directory `geometry`. 
- Now this package contains multiple packages / modules to handle user related requests.

![Packages](https://i.imgur.com/MoKCtEM.png)

#### Where,
1. Geometry is the top Package
2. Rectangle is first sub Package
2. Circle is second sub Package


**Now we can import it in following way in other `.py` file**

```py
from Geometry.Rectangle import area_rect
from Geometry.Circle import perimeter_circ
```
---

## Using Library

_working on it :)_

## Using Framework

Framework is like a collection of various libraries which architects
some more component.
For e.g. [Django](https://www.djangoproject.com/ "Django") which has various in-built libraries like Auth, user,
database connector etc.
