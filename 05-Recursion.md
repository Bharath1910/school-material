# <h1 align="center"> Recursion </h1>

# Index
* [Recursion](#recursion)
* [2 Laws of Recursion](#2-laws-of-recursion)
* [Simple algorithms with recursion](#simple-algorithms-with-recursion)
	* [Print Message forever](#print-message-forever)
		* [Program](#program)
		* [Program Explanation](#program-explanation)
	* [Sum of Natural Numbers Using Recursive Function](#sum-of-natural-numbers-using-recursive-function)
		* [Algorithm](#algorithm-2)
		* [Program](#program-2)
		* [Program Explanation](#program-explanation-2)
	* [Factorial of a Number Using Recursion](#factorial-of-a-number-using-recursion)
		* [Algorithm](#algorithm-3)
		* [Program](#program-3)
	* [Fibonacci numbers Using Recursion](#fibonacci-numbers-using-recursion)
		* [Algorithm](#algorithm-4)
		* [Program](#program-4)


## Recursion

**It is a way of programming or coding technique, in which a
function calls itself for one or more times in its body. Usually, it is
returning the return value of this function call procedure. If a
function definition fulfils such conditions, we can call this
function a recursive function.**

![Recursion](https://i.imgur.com/WmK3Hi2.gif)

## 2 Laws of Recursion

* **Must have a base case** - There must be at least one base criteria/condition, when such condition is met the function stops calling itself.
* **Must move toward the base case** - The recursive calls should moves in such a way that each time it comes closer to the base criteria.

---
## Simple algorithms with recursion 
---

### Print Message forever

### Program
```py
def hellomessage():
    print("Hello")
	hellomessage()

hellomessage()
```

### Program Explanation

Run this program.it will display ``hello`` message forever ,because there is nobase case to exit.It call hellomessage() function & Display ``hello`` And again call ``hellomessage()``
function. This will call ``hellomessage()`` function forever and will display `hello` continuously 

To exit press ``ctrl + c``

---

### Sum of Natural Numbers Using Recursive Function

### Algorithm

* Test if n equal to base case return 1.
* If not, then call the algorithm with n – 1 **(so as to move towards base case)**

### Program
```py
def sum(n):
    if n <= 1:
        return n
    else:
        return n + sum(n-1)
        num = int(input("Enter a number: "))
        print("The sum is: ", sum(num))
```

### Program Explanation

The `input()` function takes input from the user and `int()` function converts its type to an integer as `input()` return string. Here we call `sum()`
function and pass the entered number, which is assigned to `n`. The base condition for recursion is defined and if the input number is less than or equals
to 1, the number is returned, else we return the same function call with number decremented by 1. In this way, the recursive function works in Python 
that can calculate the sum of natural numbers.It works like suppose we pass 5 in input `5 + sum(4) + sum(3) + sum(3) + 1`

---

### Factorial of a Number Using Recursion

### Algorithm

* Test if `n <= 0`. If so, return 1
* If not, then call the factorial algorithm with `n – 1` and multiply the result by n and return that value.

### Program
```py
def factorial(x):
    if x == 1:
        return 1
    else:
        return x * factorial(x-1)

f = factorial(5)
print("factorial of 5 is: ",f)
```

---

### Fibonacci numbers Using Recursion

### Algorithm

``Fib(n)``
* If n = 1 or n = 2, then return 1
* else
* a = Fib(n-1)
* b = Fib(n-2)
* return a + b

### Program

```py
def fib(n):
    if n <= 1:
        return n
    else:
        return(fib(n-1) + fib(n-2))
	
nterms = int(input("enter a number"))

if nterms <= 0:
    print("Plese enter a positive integer")
    
else:
    print("Fibonacci sequence:")
    for i in range(nterms):
        print(fib(i))
```







