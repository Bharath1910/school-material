<h1 align="center">Python In a Nutshell</h1>

# Contents
* Python Tokens
* Variables and Assignments
* Simple Input/Output
* Data Types
* Mutable and Immutable Types
* Expressions
* If conditions
* Loops
* More Loops Lol

---

# Python Tokens
The smallest unit in a program

## Different Types of Tokens
* keyword
* Identifiers
* Literals
* Operators
* Punctuators

### Keywords
Predefined words which has special meaning to the python interpreter. you can't use this to name your variables

**Example Keywords**
* False
* True
* None
* import
* pass
* break

there are more, but I am lazy to type it all :)

### Identifiers
The names given by you is an identifier! example? the name of the variables and name of the functions.. there are more.. but I am lazy :)

#### Thou shalt follow the rules

* Variables should be non keyword with no space in between

```py
# Invalid Variable
pass variable = "Hello"

# Valid Variable
variable = "World"
```

* made only with **Letters**, **Numbers** and **Underscore** (_)

```py
# Invalid Variable
var-3 = "Hello"

# Valid Variable
var3 = "World"
```

* variables cannot start with a number, but can contain numbers

```py
# Invalid Variable
3var = "Hello"

# Valid Variable
var3 = "World"
```
### Literals
Data items which has fixed/constant value.

#### String Literals
String, just imagine that its a word.

* Single line Strings
```py
var = "This is a string"
var1 = 'String with single quotes'
```
* Multiline Strings
```py
var = '''
         hello
         I am a multi line
         string
      '''
 ```
 
#### Numeric Literals
numeric literals? they are just numbers..

---
### Integers

``int`` they are just integers. 0, positive and negative numbers 

**Types**
* Decimal - Base 10
* Octal - Base 8
* Hexadecimal - Base 16
---
### Float

``float`` they are numbers with decimal points
``3.14159``,``10.32``, etc

---
### Boolean Literals
its just ``True`` and ``False``
nothing much tosay to be honest 

---
### None
``None``. its just none. if you asked something to python and python cannot find it, it returns ``None``

---


 
