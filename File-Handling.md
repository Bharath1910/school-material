<h1 align="center"> File Handling </h1>

# Index


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
`` False ``

`` cp1252 ``

`` a+ ``

`` None ``

`` a.txt ``

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
`False`

`Name of the file is a.txt`

`True`


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
