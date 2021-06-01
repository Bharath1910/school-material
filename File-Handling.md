<h1 align="center"> File Handling </h1>

# Index
* [Need for a Data File]()
* [File Handling]()
    * [Types of File]()
    * [Opening and Closing Files]()
        * [open Function]()
        * [File opening modes]()
        * [Basic Text file operations]()
    * [Methods of os module]()
    * [Absolute Path vs Relative Path]()
    * [File object attributes]()
        * [open a text file]()
        * [Close a text file]()
        * [Read/write text file]()
        * [Getting & Resetting the Files Position]()
        * [Modify a Text file]()
        * [Append content to a Text file]() 
    * [Standard input, output, and error streams in python]()
    * [Write and read a Binary file]()
    * [Pickle Module]()
        * [Binary file Operation]()
        * [Binary file R/W Operation]()
        * [Iteration over Binary file]()
        * [Insert/append record in a Binary file]()
        * [Read records from a Binary file]()
        * [Search record in a Binary file]()
        * [Update record of a Binary file]()
        * [Delete record of a Binary file]()
    * [Binary Data Handler Program]()
    * [CSV File]()
        * [Write / Read CSV File]() 
    

## Need for a Data File
* To Store data in organized manner
* To store data permanently
* To access data faster
* To Search data faster
* To easily modify data later on

## File Handling
A file is a sequence of bytes on the disk/permanent storage where a group
of related data is stored. File is created for permanent storage of data.
In programming, Sometimes, it is not enough to only display the data on the
console. Those data are to be retrieved later on,then the concept of file
handling comes. It is impossible to recover the programmatically generated
data again and again. However, if we need to do so, we may store it onto
the file system which is not volatile and can be accessed every time. Here,
comes the need of file handling in Python.
File handling in Python enables us to create, update, read, and delete the
files stored on the file system through our python program. The following
operations can be performed on a file.

In Python, File Handling consists of following three steps:
* Open the file.
* Process file i.e perform read or write operation.
* Close the file.

## Types of Files

**Text Files -** A file whose contents can be viewed using a text editor is called a text file. A text
file is simply a sequence of ASCII or Unicode characters. Python programs, contents written
in text editors are some of the example of text files. e.g.`.txt`,`.rtf`,`.csv` etc.

**Binary Files -** A binary file stores the data in the same way as as stored in the memory. The
`.exe`,`.mp3` file, image files, word documents are some of the examples of binary files.we
can’t read a binary file using a text editor.e.g. `.bmp`, `.cdr` etc.

|Text Files|Binary FIles|
|---|---|
|Its Bits represent character.|Its Bits represent a custom data.|
|Less prone to get corrupt as change reflects as soon as made and can be undone.|Can easily get corrupted, corrupt on even single bit change|
|Store only plain text in a file.|Can store different types of data (audio,text,image) in a single file.|
|Widely used file format and can be opened in any text editor.|Developed for an application and can be opened in that application only.|
|Mostly .txt,.rtf are used as extensions to text files.|Can have any application defined extension.|

## Opening and Closing Files
To perform file operation ,it must be opened first then after reading, writing, editing operation can be performed. To create any new file
then too it must be opened. On opening of any file ,a file relevant structure is created in memory as well as memory space is created to store contents.
Once we are done working with the file, we should close the file. Closing a file releases valuable system resources. In case we forgot to close the file, 
Python automatically close the file when program ends or file object is no longer referenced in the program. However, if our program is large and we are reading 
or writing multiple files that can take significant amount of resource on the system. If we keep opening new files carelessly, we could run out of resources. So be a good
programmer , close the file as soon as all task are done with it

### Open Function
Before any reading or writing operation of any file,it must be opened first
of all.Python provide built in function ``open()`` for it. On calling of
this function creates file object for file operations.

**Syntax**

```py
file_object = open(<file_name>, <access_mode>,< buffering>)
```

|Parameters|Uses|
|---|---|
| file_name | name of the file ,enclosed in double quotes. |
| access_mode | Determines the what kind of operations can be performed with file,like read,write etc. |
| Buffering | for no buffering set it to 0.for line buffering set it to 1.if it is greater than 1, then it is buffer size.if it is negative then buffer size is system default.|

### File Opening Modes

|#|Mode|Description|
|---|---|---|
| 1 |`r`| Reading only. Sets file pointer at beginning of the file. This is the default mode. |
| 2 |`rb`| Same as r mode but with binary file. |
| 3 |`r+`| Both reading and writing. The file pointer placed at the beginning of the file. |
| 4 |`rb+`| same as r+ mode but with binary file. |
| 5 |`w`| writing only. Overwrites the file if the file exists. If not, creates a new file for writing. |
| 6 |`wb`| same as w mode but with binary file. |
| 7 |`w+`| both writing and reading. Overwrites . If no file exist, creates a new file for R&W. |
| 8 |`wb+`| same as w+ mode but with binary file. |
| 9 |`a`|for appending. Move file pointer at end of the file.Creates new file for writing,if not exist.|
| 10 |`ab`| same as a but with binary file. |
| 11 |`a+`| for both appending and reading. Move file pointer at end. If the file does not exist, it creates a newfile for reading and writing. |
| 12 |`ab+`| same as a+ mode but with binary mode. |

## Basic Text Files Operation

* Open (filename – absolute or relative path, mode)
* Close a text file
* Reading / Writing data
* Manipulation of data
* Appending data into a text file

## Methods of OS module

Before Starting file operation following methods must be learn by a programmer to perform file system related methods available in os module(standard module)
which can be used during file operations.
|Function|Description|Examples|
|---|---|---|
|`rename()`|Used to rename files|[Syntax](#rename)|
|`remove()`|method to delete file.|[Syntax](#remove)|
|`mkdir()`|method of the os module to create directories in the current directory.|[Syntax](#mkdir)|
|`chdir()`|method to change the current directory.|[Syntax](#chdir)|
|`getcwd()`|method displays the current directory.|[Syntax](#getcwd)|
|`rmdir()`|method deletes the directory.|[Syntax](#rmdir)|


### Examples

#### Rename()
```py
os.rename(current_file_name, new_file_name)
```

#### Remove()
```py
os.remove(file_name)
```

#### mkdir()
```py
os.mkdir("newdir")
```

#### chdir()
```py
os.chdir("newdir")
```

#### getcwd()
```py
os.getcwd()
```

#### rmdir()
```py
os.rmdir('dirname')
```


## Absolute and Relative Path

let's learn about relative and absolute path in python. wait, what's that? here's an example,

|Example Path|Path Name|
|---|---|
|``C:\Users\user01\python\example.py``| Absolute Path |
|``python\example.py``| Relative path |

Absolute path is like defining the exact location of the specific file, and relative path is like defining the location of the file with respect to another file, in this case a python file. Now let's see an example.
we have 2 files in ``C:\Users\user01\python\example.py`` and ``C:\Users\user01\python\test_text.txt``.

We gave the absolute path of the both files. but this is a tedious work if you have many such folders in your computer. 
when you realise `C:\Users\user01\python\` is common in both files, so if you need to open `test_text.txt` using python. you can either give `C:\Users\user01\python\test_text.txt` or `test_text.py`. because the python file is in``C:\Users\user01\python\`` the file knows it is there, you don't need to specify it again.

it is same like going to a person and telling your home is in `Number-100/st street/abc colony/chennai/tamil nadu/india/earth/solar system/milky way galaxy`.
you don't need that extra information of `earth/solar system/milky way galaxy`
because you both are in earth (unless you are talking with a alien :P).

it's the same thing with computers too.


## File Object attributes

* closed: It returns true if the file is closed and false when the file is open.
* encoding: Encoding used for byte string conversion
* mode: Returns file opening mode
* name: Returns the name of the file which file object holds.
* newlines: Returns `\r`, `\n`, `\r\n`, None or a tuple containing all the newline types seen.

### Open a Text File

```py
f = open("a.txt", 'a+') 
print(f.closed)
print(f.encoding)
print(f.mode)
print(f.newlines)
print(f.name)
```
### Output
    False

    cp1252

    a+ 

    None 

    a.txt 

### close text file
`close()` Used to close an open file. After using this method,an opened
file will be closed and a closed file cannot be read or written any more.

```py
f = open("a.txt", 'a+')
print(f.closed)
print("Name of the file is", f.name)
f.close()
print(f.closed)

```

### Output 
    False

    Name of the file is a.txt

    True


### Read and Write Text Files

#### The write() Method
It writes the contents to the file in the form of string. It
does not return value. Due to buffering, the string may not
actually show up in the file until the flush() or close()
method is called.

#### The read() Method
It reads the entire file and returns it contents in the form of
a string. Reads at most size bytes or less if end of file
occurs.if size not mentioned then read the entire file
contents.

#### Program
```py
f = open("a.txt", 'w')

line1 = 'Welcome to python.mykvs.in'
f.write(line1)

line2="\nRegularly visit python.mykvs.in"
f.write(line2)

f.close()

f = open("a.txt", 'r')
text = f.read()

print(text)
f.close() 
```

#### Output
    Welcome to python.mykvs.in
    Regularly visit python.mykvs.in

### Read Text Files

#### Readline([Size]) 
Read no of characters from file if size is mentioned till eof (End Of File).read line till new line character.returns empty string on EOF.

```py
f = open("a.txt", 'w')

line1 = 'Welcome to python.mykvs.in'
f.write(line1)

line2="\nRegularly visit python.mykvs.in"
f.write(line2)

f.close()

f = open("a.txt", 'r')

text = f.readline()
print(text)

text = f.readline()
print(text)
```

#### Output 
    Welcome to python.mykvs.in
    Regularly visit python.mykvs.in
    
#### readlines([size])
Read no of lines from file if size is mentioned or all
contents if size is not mentioned.

```py
f = open("a.txt", 'w')

line1 = 'Welcome to python.mykvs.in'
f.write(line1)

line2="\nRegularly visit python.mykvs.in"
f.write(line2)

f.close()

f = open("a.txt", 'r')

text = f.readlines(1)
print(text)

f.close()
```
#### Output
    ['Welcome to python.mykvs.in\n']


### Iterating over lines in a file
```py
f = open("a.txt", 'w')

line1 = 'Welcome to python.mykvs.in'
f.write(line1)

line2="\nRegularly visit python.mykvs.in"
f.write(line2)

f.close()

f = open("a.txt", 'r')

for text in f.readlines():
    print(text)
    
f.close() 
```

#### Word Processing

```py
f = open("a.txt", 'w')

line1 = 'Welcome to python.mykvs.in'
f.write(line1)

line2="\nRegularly visit python.mykvs.in"
f.write(line2)

f.close()

f = open("a.txt", 'r')

for text in f.readlines():
    for word in text.split( ):
        print(word)
        
f.close()
```

#### Output
    Welcome
    to
    python.mykvs.in
    Regularly
    visit
    python.mykvs.in
    
### Getting & Resetting the Files Position
The `tell()` method of python tells us the current position within the file, where as The seek(offset[from]) method changes the current file position. If from is `0`, the beginning of the file to seek. If it is set to `1`, the current position is used . If it is set to `2` then the end of the file would be taken as seek
position. The **offset** argument indicates the number of bytes to be moved.

```py
f = open("a.txt", 'w')

line = 'Welcome to python.mykvs.in\nRegularly visit python.mykvs.in'
f.write(line)

f.close()

f = open("a.txt", 'rb+')

print(f.tell())
print(f.read(7))# read seven characters

print(f.tell())
print(f.read())

print(f.tell())
f.seek(9,0) # moves to 9 position from begining

print(f.read(5))
f.seek(4, 1) # moves to 4 position from current location

print(f.read(5))

f.seek(-5, 2) # Go to the 5th byte before the end
print(f.read(5))

f.close()
```

### Output
    0
    b'Welcome'
    7
    b' to
    python.mykvs.in\r\nRe
    gularly visit
    python.mykvs.in'
    59
    b'o pyt'
    b'mykvs'
    b'vs.in'


## Modify a Text File
There is no way to insert into the middle of a file without re-writing
it. We can append to a file or overwrite part of it using seek but if
we want to add text at the beginning or the middle, we'll have to
rewrite it.

It is an operating system task, not a Python task. It is the same in all
languages.

What we usually do for modification is read from the file, make the
modifications and write it out to a new file called temp.txt or
something like that. This is better than reading the whole file into
memory because the file may be too large for that. Once the
temporary file is completed, rename it the same as the original file.
This is a good, safe way to do it because if the file write crashes or
aborts for any reason in between, we still have our untouched
original file.

### Replace string in the same File
```py
fin = open("dummy.txt", "rt")

data = fin.read()
data = data.replace('my', 'your')

fin.close()

fin = open("dummy.txt", "wt")

fin.write(data)

fin.close()
```

#### What have we done here?
Open file `dummy.txt` in read text mode `rt`.
``fin.read()`` reads whole text in `dummy.txt` to the variable data.
`data.replace()` replaces all the occurrences of my with your in the whole text.
`fin.close()` closes the input file `dummy.txt`.
In the last three lines, we are opening dummy.txt in write text wt mode and writing the
data to `dummy.txt` in `replace` mode. Finally closing the file `dummy.txt`.

> Note :- above program is suitable for file with small size.


### Replace string using temporary file 
```py
import os

f=open("d:\\a.txt","r")
g=open("d:\\c.txt","w")

for text in f.readlines():
    text=text.replace('my','your')
    g.write(text)
    
f.close()
g.close()

os.remove("d:\\a.txt")
os.rename("d:\\c.txt","d:\\a.txt")

print("file contents modified")
```

> **Note -** above program is suitable for large file.Here line by line is being read from `a.txt` file
> in text string and text string been replaced `my` with `your` through `replace()`
> method. Each text is written in `c.txt` file then close both files, remove old file `a.txt` through
> remove method of `os module` and rename `c.txt(temporary file)` file with `a.txt` file.After
> execution of above program all occurances of `my` will be replaced with `your`. For testing
> of above program create `a.txt` file in D: drive with some substring as `my`.Run above
> program and check changes

## Append content to a Text file

```py
f = open("a.txt", 'w')

line = 'Welcome to python.mykvs.in\nRegularly visit python.mykvs.in'
f.write(line)

f.close()

f = open("a.txt", 'a+')

f.write("\nthanks")
f.close()

f = open("a.txt", 'r')

text = f.read()
print(text)

f.close() 
```

### Output 
    Welcome to python.mykvs.in
    Regularly visit python.mykvs.in
    thanks


### Standard Input, Output, And error Streams In Python
Most programs make output to "standard out",input from "standard in", and error messages go to standard error. standard output is to
monitor and standard input is from keyboard.

```py
a = sys.stdin.readline()
sys.stdout.write(a)

a = sys.stdin.read(5)  # entered 10 characters.a contains 5 characters.

#The remaining characters are waiting to be read.

sys.stdout.write(a)

b = sys.stdin.read(5)

sys.stdout.write(b)
sys.stderr.write("\ncustom error message")
```

### Write and read a Binary file

```py
binary_file=open("D:\\binary_file.dat",mode="wb+")

text="Hello 123"
encoded=text.encode("utf-8")

binary_file.write(encoded)
binary_file.seek(0)
binary_data=binary_file.read()

print("binary:",binary_data)
text=binary_data.decode("utf-8")

print("Decoded data:",text)
```
> **Note :-** Opening and closing of binary file is same as text file opening and closing. While
> opening any binary file we have to specify `b` in file opening mode.
> In above program `binary_file.dat` is opened in `wb+` mode so that after writing, reading
> operation can be done on binary file. String variable text hold text to be `encoded` before
> writing with the help of encode method(). `utf-8` is encoding scheme.after writing text ,we
> again set reading pointer at beginning with the help of `seek()` method.then read the text
> from file and `decode` it with the help of `decode()` method then display the text.

### Binary file Operation using pickle module

The problem with the approach of previous slide comes from the
fact that it is not very easy to use when we want to write several
objects into the binary file. For instance, consider what we would
have to do if we wished to write string, integer and perhaps even
the contents of a list or dictionary into the file. How would we read
the contents of this file later? This is not a trivial task, especially if
some of the objects can have variable lengths.
Fortunately, Python has a module which does this work for us and
is extremely easy to use. This module is called pickle; it provides us
with the ability to serialize and deserialize objects, i.e., to convert
objects into bitstreams which can be stored into files and later be
used to reconstruct the original objects.

#### pickle.dump()
function is used to store the object data to the file. It
takes 3 arguments. First argument is the object that we want to
store. The second argument is the file object we get by opening the
desired file in `write-binary (wb)` mode. And the third argument is
the key-value argument. This argument defines the protocol. There
are two type of protocol – 

`pickle.HIGHEST_PROTOCOL` and `pickle.DEFAULT_PROTOCOL`.

#### Pickle.load() 
function is used to retrieve pickled data.The steps are
quite simple. We have to use `pickle.load()` function to do that. The
primary argument of pickle load function is the file object that you
get by opening the file in `read-binary (rb)` mode.

### Binary file R/W Operation using pickle module

In this program we open `a.bin` file in
binary mode using `wb` specification
and create and store value in 4
different data objects i.e.
int, string, list, dict. Write these into
binary file using `pickle.dump()`
method then close this file and open
the same for reading operation. We
read the content using `load method()`
and display the value read from file.
To use dump and load we have to
`import pickle` module first of all.

```py
import pickle

output_file = open("d:\\a.bin", "wb")

# Different values
myint = 42
mystring = "Python.mykvs.in!"
mylist = ["python", "sql", "mysql"]
mydict = { "name": "ABC", "job": "XYZ" }


pickle.dump(myint, output_file)
pickle.dump(mystring, output_file)
pickle.dump(mylist, output_file)
pickle.dump(mydict, output_file)

output_file.close()

input_file = open("d:\\a.bin", "rb")

myint = pickle.load(input_file)
mystring = pickle.load(input_file)
mylist = pickle.load(input_file)
mydict = pickle.load(input_file)

print("myint = %s" % myint)
print("mystring = %s" % mystring)
print("mylist = %s" % mylist)
print("mydict = %s" % mydict)

input_file.close()
```

### Iteration over Binary file

```py
import pickle

output_file = open("d:\\a.bin", "wb")

myint = 42
mystring = "Python.mykvs.in!"
mylist = ["python", "sql", "mysql"]
mydict = { "name": "ABC", "job": "XYZ" }

pickle.dump(myint, output_file)
pickle.dump(mystring, output_file)
pickle.dump(mylist, output_file)
pickle.dump(mydict, output_file)

output_file.close()

with open("d:\\a.bin", "rb") as f:
    while True:
        try:
            r=pickle.load(f)
            print(r)
            print("Next data")
            
        except EOFError:
            break
f.close()
```

### Insert/append record in a Binary file

```py
rollno = int(input('Enter roll number:'))
name = input('Enter Name:')
marks = int(input('Enter Marks'))

#Creating the dictionary
rec = {'Rollno':rollno,'Name':name,'Marks':marks}  # Here we are creating dictionary rec to dump it in student.dat file

#Writing the Dictionary
f = open('d:/student.dat','ab')
pickle.dump(rec,f)

f.close()
```

### Read records from a Binary file
```py
f = open('d:/student.dat','rb')

while True:
    try:
        rec = pickle.load(f)
        print('Roll Num:',rec['Rollno'])
        print('Name:',rec['Name'])
        print('Marks:',rec['Marks'])
        
    except EOFError:
        break
        
f.close()
```

> Here we will iterate using infinite while loop and exit on end of file is reached.at each iteration a dictionary data is read into rec and then values are being displayed

### Search record in a Binary file

```py
f = open('d:/student.dat','rb')

flag = False

r = int(input(“Enter rollno to be searched”))

while True:
    try:
        rec = pickle.load(f)
        if rec['Rollno'] == r:
            print('Roll Num:',rec['Rollno'])
            print('Name:',rec['Name'])
            print('Marks:',rec['Marks'])
            flag = True
            
    except EOFError:
        break
        
if flag == False:
    print('No Records found')
    
f.close()
```

> Here value of r to be searched will be compared with rollno value of file in each iteration/next record and if matches then relevant data will be shown and flag will be set to True otherwise it will remain False and `No Record Found message will be displayed`

### Update record of a Binary file

```py
f = open('d:/student.dat','rb')

reclst = []

r = int(input(“enter roll no to be updated”))
m = int(input(“enter correct marks”))

while True:
    try:
        rec = pickle.load(f)
        reclst.append(rec)
        
    except EOFError:
        break
        
f.close()

for i in range (len(reclst)):
    if reclst[i]['Rollno']==r:
        reclst[i]['Marks'] = m
        
f = open('d:/student.dat','wb')

for x in reclst:
    pickle.dump(x,f)
    
f.close()
```

> Here we are reading all records from binary file and storing those in reclst list then update relevant roll no/marks data in reclst list and create/replace student.dat file with all data of reclst. If large data are in student.dat file then It’s alternative way can be using temporary file creation with
corrected data then using os module for remove and rename method (just similar to modification of text file)

### Delete record of a Binary file

```py
f = open('d:/student.dat','rb')

reclst = []

r = int(input(“enter roll no to be deleted”))

while True:
    try:
        rec = pickle.load(f)
        reclst.append(rec)
    except EOFError:
        break
        
f.close()

f = open('d:/student.dat','wb')

for x in reclst:
    if x['Rollno']==r:
        continue
    pickle.dump(x,f)
    
f.close() 
```

> Here we are reading all records from
> binary file and storing those in reclst
> list then write all records except
> matching roll no(with the help of
> continue statement) in student.dat
> file.Due to wb mode old data will be
> removed.
> If large data are in student.dat file
> then It’s alternative way can be
> using temporary file creation with
> corrected data then using os module
> for remove and rename method
> (just similar to deletion from text
> file)

#### Python Program For Interactive Binary Data Handling

```py
import os
import pickle


#Accepting data for Dictionary
def insertRec():
    rollno = int(input('Enter roll number:'))
    name = input('Enter Name:')
    marks = int(input('Enter Marks'))

    #Creating the dictionary
    rec = {'Rollno':rollno,'Name':name,'Marks':marks}

    #Writing the Dictionary
    f = open('d:/student.dat','ab')
    pickle.dump(rec,f)
    f.close()

#Reading the records
def readRec():
    f = open('d:/student.dat','rb')
    while True:
        try:
            rec = pickle.load(f)
            print('Roll Num:',rec['Rollno'])
            print('Name:',rec['Name'])
            print('Marks:',rec['Marks'])
        except EOFError:
            break
    f.close()

#Searching a record based on Rollno
def searchRollNo(r):
    f = open('d:/student.dat','rb')
    flag = False
    while True:
        try:
            rec = pickle.load(f)
            if rec['Rollno'] == r:
                print('Roll Num:',rec['Rollno'])
                print('Name:',rec['Name'])
                print('Marks:',rec['Marks'])
                flag = True
        except EOFError:
            break
    if flag == False:
        print('No Records found')
    f.close()
    
    
#Marks Modification for a RollNo
def updateMarks(r,m):
    f = open('d:/student.dat','rb')
    reclst = []
    while True:
        try:
            rec = pickle.load(f)
            reclst.append(rec)
        except EOFError:
            break
    f.close()
    for i in range (len(reclst)):
        if reclst[i]['Rollno']==r:
            reclst[i]['Marks'] = m
    f = open('d:/student.dat','wb')
    for x in reclst:
        pickle.dump(x,f)
    f.close()            

#Deleting a record based on Rollno
def deleteRec(r):
    f = open('d:/student.dat','rb')
    reclst = []
    while True:
        try:
            rec = pickle.load(f)
            reclst.append(rec)
        except EOFError:
            break
    f.close()
    f = open('d:/student.dat','wb')
    for x in reclst:
        if x['Rollno']==r:
            continue
        pickle.dump(x,f)
    f.close()  
    
while 1==1:
    print('Type 1 to insert rec.')
    print('Type 2 to display rec.')
    print('Type 3 to Search RollNo.')
    print('Type 4 to update marks.')
    print('Type 5 to delete a Record.')
    print('Enter your choice 0 to exit')
    
    choice = int(input('Enter you choice:'))
    
    if choice==0:
        break
    elif choice == 1:
        insertRec()
        
    elif choice == 2:
        readRec()
        
    elif choice == 3:
        r = int(input('Enter a rollno to search:'))
        searchRollNo(r)
        
    elif choice == 4:
        r = int(input('Enter a rollno:'))
        m = int(input('Enter new Marks:'))
        updateMarks(r,m)
        
    elif choice == 5:
        r = int(input('Enter a rollno:'))
        deleteRec(r)
    
    else:
        print("Select a correct option")
        
```

## CSV Files
CSV (Comma Separated Values) is a file format for data storage which looks like a
text file. The information is organized with one record on each line and each field
is separated by comma.

### CSV File Characteristics
* One line for each record
* Comma separated fields
* Space-characters adjacent to commas are ignored
* Fields with in-built commas are separated by double quote characters.

### When use CSV?
* When data has a strict tabular structure
* To transfer large database between programs
* To import and export data to office applications, Qedoc modules
* To store, manage and modify shopping cart catalogue

### CSV Advantages
* CSV is faster to handle
* CSV is smaller in size
* CSV is easy to generate
* CSV is human readable and easy to edit manually
* CSV is simple to implement and parse
* CSV is processed by almost all existing applications

### CSV Disadvantages
* No standard way to represent binary data
* There is no distinction between text and numeric values
* Poor support of special characters and control characters
* CSV allows to move most basic data only. Complex configurations cannot be imported and exported this way
* Problems with importing CSV into SQL (no distinction between NULL and quotes)

### Write / Read CSV FILE

Writing and reading operation from
text file is very easy. First of all we have
to import csv module for file
operation/method call.
For writing, we open file in `w` writing
mode using `open()` method which
create newFile like object.
Through `csv.writer()` method, we
create writer object to call `writerow()`
method to write objects.
Similarly for reading, we open the file
in `r` mode and create newFile like
object,further we create newfilereader
object using `csv.reader()` method to
read each row of the file.
Three file opening modes are there
`w`,`r`,`a`. `a` for `append`
After file operation close, opened file
using `close()` method.

```py
import csv

#csv file writing code
with open('d:\\a.csv','w') as newFile:
    newFileWriter = csv.writer(newFile)
    
    newFileWriter.writerow(['user_id','beneficiary'])
    newFileWriter.writerow([1,'xyz'])
    newFileWriter.writerow([2,'pqr'])
    
    newFile.close()
    
#csv file reading code
with open('d:\\a.csv','r') as newFile:
    newFileReader = csv.reader(newFile)
    
    for row in newFileReader:
        print (row)
        
    newFile.close()
```
