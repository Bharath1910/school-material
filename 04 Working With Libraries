<h1 align='center'> Using Python Libraries <h1>

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

It is a collection of various packages. Conceptually, _**There is no difference between
package and python library**_.In Python, a library is used loosely to describe a
collection of the core modules.

`standard library` of Python language comes bundled with the core Python
distribution are collection of exact syntax, token and semantics of the Python
language. The python standard library lists down approx more than 200 such core
modules that form the core of Python.

`Additional libraries` refer to those optional components that are commonly
included in Python distributions. The Python installers automatically adds the standard library and some additional
libraries. The additional library is generally provided as a collection of packages. To use such
additional library we have to use packaging tools like [`easyinstall`](https://wiki.python.org/moin/EasyInstall "Easy Install") or [`pip`](https://github.com/pypa/pip#pip---the-python-package-installer "Pip") to install such
additional libraries.

![Library](https://i.imgur.com/X1CWe4V.png)

Define a function `moduletest2()` in [`module2.py`](#module2py) file and call this
function in [`mylibcall.py`](#mylibcallpy) file as a part of library1 library. Now run `mylibcall.py` file
It will call `moduletest2()` method and display-`from module2` message.
Please make sure that a blank file with `__init__.py` is created.

### Module2.py
```py
def moduletest2():
    print("From Module 2")
```

### Mylibcall.py
```py
from library1.package1 import module2
print(module2.moduletest2())
```

## Using Framework

Framework is like a collection of various libraries which architects
some more component.
For e.g. [Django](https://www.djangoproject.com/ "Django") which has various in-built libraries like Auth, user,
database connector etc.
