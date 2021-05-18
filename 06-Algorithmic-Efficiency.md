<h1 align='center'> Idea of algorithmic efficiency </h1>

Efficient programming is a manner of programming that,
when the program is executed, it uses a low amount of
overall resources pertaining to specially computer
hardware. A program is designed by a human being, and
different human beings may use different algorithms, or
sequences of codes, to perform particular tasks, so the
efficiency of such different programs/algorithm varies,
depend upon the number of resources being used.
Practicing to create a low size(number of line of
codes/number of operations) and low resource
algorithm results in an efficient program.

## Performance defined as inversely proportional to the wall clock time

* **Wall clock time/elapsed time** - time to complete
a task as seen by the user. In wall clock timing all
kind of time is included ,e.g. operating system
overhead or potentially interfering other
applications etc

* **CPU Time** - does not include time slices
introduced by external sources (e.g. running
other applications).

* **To maximize performance, minimize execution time**

   `Performance(x) / Performance(y) = ExecutionTime(x) / ExecutionTime(y) = n`
   
### Example

**If a particular desktop runs a program in 60 seconds and a laptop
runs the same program in 90 seconds, how much faster is the
desktop than the laptop?**

`= PerformanceDesktop / PerformanceLaptop`

`= (1/60)/(1/90) = 1.5`

So, the desktop is 1.5 times faster than laptop

## Performance of algorithm depends on many internal and external factors.

* **Internal factors** - time required to run and memory required to run

* **External factors** – size of input to the algorithm, speed of computer External factors are controllable, so many internal factors are studied an measured for algorithms efficiency
We will determine efficiency of algorithm in terms of computational complexity

* **Computational complexity** – computation+complexity
Computation involves the problems to be solve and algorithm to solve
them.Complexity involves study of factors to determine how much
resource(time to run+memory) is necessary for algo to run efficiently.

* **Big o notation** - allow us to measure the time and space Complexity of
our code.

## performance measurement in terms of the number of operations

To compute the number of operations in a piece of code,then simply count the number of
arithmetic operations+other operation that code is performing. All operations (addition,
subtraction, multiplication, and division) are usually counted to be the same, which is not
exactly true, since multiplication includes several additions and division includes several
multiplications when actually executed by a computer. However, we are looking for an
estimate here, so it is reasonable to assume that on average, all operations count in the
same manner.

**Here is an example (just for illustration):**
```py
r = 0
for i in range(4):
    for i in range(4):
        r = r + (i*n)
        
print(r)
```

For each r there is 1 multiplications, 1 addition and 1 assignment resulting in 3 operations.
This loop is executed 4X4 times, so there are (4X4)r operations. This is the the order of the
code. In this example, its is O(4^2 r).





