---
layout: post
title: "Introduction to Programming in Python"
categories: programming, python, py
permalink: /programming/python
---
Python is a high-level, interpreted programming language that was first released in 1991 by Guido van Rossum. It is a general-purpose language that is designed to be easy to use, with a focus on readability and simplicity. Python is often used for web development, data analysis, artificial intelligence, scientific computing, and other types of software development.

One of the key features of Python is its ease of use. Python's syntax is designed to be simple and intuitive, making it accessible to both beginner and experienced programmers. Python is also an interpreted language, meaning that it does not require compilation, which makes it easy to write and test code quickly.

Another important feature of Python is its support for object-oriented programming. Python allows users to create classes and objects, and to define methods on those objects. This makes it a powerful tool for building complex software systems.

Python also includes a large and growing library of built-in modules and packages. These modules provide a wide range of functionality, from working with strings, arrays, and dictionaries to working with databases, web frameworks, and machine learning tools. Python's open-source ecosystem is one of its biggest strengths, as it allows developers to easily access and integrate with a wide range of third-party libraries and tools.

One of the most popular web development frameworks built in Python is Django. Django is a full-stack web framework that provides a set of conventions and tools for building web applications quickly and easily. With its focus on developer productivity, Django has become a popular choice for startups, small businesses, and large enterprises.

Python's popularity has also been driven by its use in data analysis and scientific computing. With packages like NumPy, Pandas, and Matplotlib, Python has become a leading language for data analysis and visualization. In recent years, Python has also become a popular language for artificial intelligence and machine learning, with packages like TensorFlow, PyTorch, and Scikit-learn providing powerful tools for building machine learning models.

Most modern programming languages have a set up similar building blocks, for example 
1. Receiving input from the user and Showing output to the user
2. Ability to store values in variables (usually of different kinds such as integers, floating points or character)
3. A string of characters where you can store names, addresses, or any other kind of text
4. Some advance data types such as arrays which can store a series of regular variables (such as a series of integers)
5. Ability to loop your code in the sense that you want to receive 10 names from a user, you will write the code for that 10 times, but just once and tell the computer to loop through it 10 times
6. Ability to execute statements of code conditionally, for example if marks are more than 40 then the student passes else fails
7. Put your code in functions
8. Advanced data types that are formed through a combination of one or more types of basic data types such as structures or classes
9. Read file from a disk and save file to a disk
10. Ability to comment your code so you can understand it when you revisit it some time later

Lets dive right in and see how we can do these things in Python. 

#### 0. How to install Ruby on your desktop?
Before we can begin to write a program in Python, we need to install [Anaconda](https://www.anaconda.com/products/individual). This will install the Anaconda data science environment and Spyder IDE for coding in Python. Once done, go ahead and open Spyder and try out the following code to see if everything is in order.  

```python
myString = "Hello, World!"
print (myString)
```

#### 1. Receiving input from the user and Showing output to the user
There are several ways in which we can show output to the user. Let's look at some ways of showing output:
```python
name = input('please enter your name') # receiving character input
print("hello ", name, ",how are you?") # showing character output

age = input('please enter your age') # receiving numeric input
print('so you are', age, 'years old.')
```

#### 2. Ability to store values in variables (usually of different kinds such as integers, floating points or character)
Python is dynamically typed - don’t need to type out the variable's data type before using it. This can sometimes cause unexpected problems if for example a user enters a character where you expect a number. To avoid this kind of problems type() can be used. Alternatively, you can "define the variable" by assigning it an initial value (like age=20).

Basic data types: In Python we have several types of objects, lets take a look at the important ones:
```python
# Boolean / Logical
v = TRUE 
print(type(v)) # type funciton can be used to see the data type of the variable

# Numeric
v = 23.5
print(type(v))

# Integer
v = 2L
print(type(v))

# Complex
v = 2+5i
print(type(v))

# Character
v = "TRUE"
print(type(v))

# Some common number functions:
hex(1) # hexadecimal representation of numbers
bin(1) # binary representation of numbers
2**3 # 2^3, 2 to the power 3
pow(2,3) # 2**3
pow(2,3,4) # 2**3 % 4
abs(-2.33)
round(3.14)
round(3.14159,2) # only till 2 decimal places
import math
sq_rt = math.sqrt(variable) # returns the square root of the variable
```
Advanced data types: Much of Python's power comes from the fact that it lets us access some advanced variable trypes other than the basic ones shown earlier. Lets take a look at some of the advanced variable types:
```python
# Lists - A list can contain many different types of elements inside it such as character, numeric, etc. and even another list inside it.
# Create a list through enumeration.
a=[] # with this we initialize a list element
a=range(1,10) # with this we insert a range of values from 1-10 in the list
print(list(a)) # to show the list as a list, we need to tell the print function that we are passing it a list
# Output: [1, 2, 3, 4, 5, 6, 7, 8, 9] # 10 is excluded because upper bound is excluded in python
# we can have mixed data types in a list
b=[1,2,3,'vivek',True,4,5]
print(list(b))
# index of list start with 0, 1, 2 ..
# so vivek is present at index 3
print(b[3])
# slicing - [start:stop:step]
a[1:6:2] # starts from 1 and goes up until 6 and selects every second element
# reversing a list
L[::-1] # this would take a lot more effort to do in C++!

# tuples - immutable list, cant be changed
t = (1,2,3) # use () instead of []

# dict - d = {'key':'value', ..} is an unordered mutable key:value pairs {"name":"frankie","age":33}
# Dictionary is quite useful in matrix indexing
m=np.array([[1,2,3],[4,5,6],[7,8,9]])
col_names={'age':0, 'weight':1, 'height':2}
row_names={'aa':0, 'cc':1, 'bb':2}
# now we can get weight of ale using actual indexes or dict indexes
m[1,1] # 5
m[row_names['cc'],col_names['weight']] # 5

# set - s=set('a','b','c',..) - unordered collection of unique objects
# It looks like a dictionary {"a","b"} when python shows output, but it is not because it doesn’t have key:value pairs
set([1,1,2,3]) # output: {1,2,3} , List can be passed to set()
set("Mississippi") # output: {'M', 'i', 'p', 's'} , Even strings can be passed to set

# Matrices - A matrix is a two-dimensional rectangular data set. It can be created using .array() function.
# Create a matrix
import numpy as np # we need to import the numpy libabry which provides tools for numerical computing. 
m=np.array([[1,2,3],[4,5,6],[7,8,9]])
print(type(m))

# Arrays - while matrices are confined to two dimensions, arrays can be of any number of dimensions. 
# Create an array.
import numpy as np # we need to import the numpy libabry which provides tools for numerical computing. 
a=np.array([1,2,3]) # this is a 1 dimentional array
print(type(a))
# Convert a list to an array
a=[1,2,3,4]
a=np.array(a) # array([1, 2, 3, 4])

# DataFrame - this is an advanced object that can be used by installing the pandas library. If you are familiar with R, this is similar to data.frame. If you are familiar with excel, you can think of a dataframe as a table with rows and column where rows and colums can potentially have names/labels. You can access data within the dataframe using row/column number (indexing starts from 0) or their labels. 
import pandas as pd
# From dict
pd.DataFrame({'col_1': [3, 2, 1, 0], 'col_2': ['a', 'b', 'c', 'd']})
# from list
pd.DataFrame(['orange', 'mango', 'grapes', 'apple'], index=['a', 'b', 'c', 'd'], columns =['Fruits'])
# from list of lists
pd.DataFrame([['orange','tomato'],['mango','potato'],['grapes','onion'],['apple','chilly']], index=['a', 'b', 'c', 'd'], columns =['Fruits', 'Vegetables'])
# from multiple lists
pd.DataFrame(
        list(zip(['orange', 'mango', 'grapes', 'apple'],
                ['tomato', 'potato', 'onion', 'chilly']))
        , index=['a', 'b', 'c', 'd']
        , columns =['Fruits', 'Vegetables'])
```

#### 3. A string of characters where you can store names, addresses, or any other kind of text
Any value written within a pair of single quote or double quotes in Python is treated as a string. 

##### Key idea here is to learn how to manipulate string variables
There are a few common operations that we will focus on:
a. Concatenate strings
```python
# Concatenate strings
str1 + str2 + " " + str3
```
b. Counting number of characters in a string
```python
# Counting number of characters in a string
str1 = "vivek"
len(str1)
```
c. Changing the case - toupper() & tolower() functions
```python
str1.upper() # convert string to upper case (.lower() for lower case)
str1.isupper(), str1.islower() # check if a string or a character is upper or lower
```
d. Splitting a string
```python
s.split('e') # returns list of strings before and after e. if there are multiple e's, then split happens for all instances of e
```
e. Palindrome of a string
```python
str1 = "vivek"
str1[::-1]
```

#### 4. Some advance data types such as lists which can store a series of regular variables (such as a series of integers)
Lists are a series of variables stored together in one variable. Lists can be one-dimentional or multi-dimentional. A list is created using the list() function. It takes variables (even other lists) as input. List is different from string because elements can be mutated/changed. 

```python
# Defining
L=[0,0,0] # [0, 0, 0]
L1=[0]*3 #shorthand way of defining a list with repeated elements

# Supports indexing and slicing
L1=['one', 'two', 'three']
L1[0] # 'one'
L1[1:2] # ['two'], upper bound is excluded
L1[1:3] # ['two', 'three']

# Indexing nested lists
L1 = ['one', 'two', ['three', 'four'], 'five']
L1[2][0] # 'three'

# Elements can be added
L1.append('six')

# Elements can be removed
L1.pop() # last element gets popped, we can save it in a variable also

# Sort
L1.sort() # sorts the list in-place, the actual list gets sorted
sorted(L1) #returns the sorted version of L3 list

# Reverse
L1=['c','a','b']
L1.reverse() # reverses the list in-place, the actual list gets reversed

# Multi dimentional list indexing
L1=[[1,2,3],[4,5,6],[7,8,9]]
L1[0][:] # returns first row
```

#### 5. Ability to loop your code in the sense that you want to receive 10 names from a user, you will write the code for that 10 times, but just once and tell the computer to loop through it 10 times
Python has several looping options such as 'for' and 'while'. There are also options of nesting (single, double, triple, ..) loops. 
a. The While loop executes the same code again and again until a stop condition is met:
```python
# Syntax
while test:
    code statements
else:
    final code statements

# Example
x = 0
while x < 10:
    print('x is currently: ',x)
    print(' x is still less than 10, adding 1 to x')
    x+=1
```
b. The for loop: acts as an iterator in Python; it goes through items that are in a sequence or any other iterable item. Objects that we've learned about that we can iterate over include strings, lists, tuples, and even built-in iterables for dictionaries, such as keys or values.
```python
# Syntax
for item in object:
    statements to do stuff

# Example
list1 = [1,2,3,4,5,6,7,8,9,10]
for num in list1:
    print(num)
```
Python also provides the break, continue and pass statements that allow us to alter the loops further. Following is their use:
  break: Breaks out of the current closest enclosing loop.
  continue: Goes to the top of the closest enclosing loop.
  pass: Does nothing at all.
```python
# Thinking about break and continue statements, the general format of the while loop looks like this:
while test: 
    code statement
    if test: 
        break
    if test: 
        continue 
else:
```
break and continue statements can appear anywhere inside the loop’s body, but we will usually put them further nested in conjunction with an if statement to perform an action based on some condition.

#### 6. Ability to execute statements of code conditionally, for example if marks are more than 40 then the student passes else fails
Python provides if.., if..else.., and if..else..if.. statements to apply conditional logic. Lets take a look at them:
a. The basic syntax for creating an if statement is:
```python
if False:
    print('It was not true!')
```
b. The basic syntax for creating an if...else statement is: 
```python
x = False
if x:
    print('x was True!')
else:
    print('I will be printed in any case where x is not true')
```
c. The basic syntax for creating an if...else if...else statement is: 
```python
loc = 'Bank'
if loc == 'Auto Shop':
    print('Welcome to the Auto Shop!')
elif loc == 'Bank':
    print('Welcome to the bank!')
else:
    print('Where are you?')
```

#### 7. Put your code in functions
Functions allows us to create a block of code that can be executed many times without needing to it write it again. 
```python
# Syntax
def name_of_function(argument_name='default value'): #snake casing for name, all lower case alphabets with underscores
    '''
    what funciton does
    '''
    print ('hello',argument_name)
    print (f'hello {argument_name}') #both print do the same thing

# Example
def add_function(a=0,b=0):
    return a+b
```
We can call the function in the following two ways:
```python
# option 1
add_function(2,3)    
# option 2
c=add_function(3,4)
```
\*args and \*\*kwargs stand for arguments and keyword arguments and allow us to extend the funcitonality of functions. 
\*args lets a function take an arbitrary number of arguments. All arguments are received as a tuple, example - (a,b,c,..). args can be renamed to something else, what really matters is \*. 
```python
def myfunc(*args):
    return args
'''
myfunc(1,2,3,4,5,6,7,8,9)
Out[30]: (1, 2, 3, 4, 5, 6, 7, 8, 9)
'''
```
\*\*kwargs lets the funciton take an arbitrary number of keyword arguments. All arguments are received as a dictionary of key,value pairs. kwargs can be renamed to something else, what really matters is \*\*. 
```python
def myfunc(**kwargs):
    print(kwargs)
'''
myfunc(name='vivek', age=34, height=186)
{'name': 'vivek', 'age': 34, 'height': 186}
'''
```

#### 8. Advanced data types that are formed through a combinaiton of one or more types of basic data types such as structures or classes
Python allows user to create classes. These can be a combination of variables and functions that operate on those variables. Lets take a look at how we can define and use them. 
```python
# Define a class
class Person:
    "This is a person class"
    age = 10

    def greet(self):
        print('Hello')

# Using class
print(Person.age) # Output: 10
print(Person.greet) # Output: <function Person.greet>
print(Person.__doc__) # Output: 'This is my second class'

# Creating an object of the class and using that
vivek = Person() # create a new object of Person class
print(vivek.greet) # Output: <bound method Person.greet of <__main__.Person object>>
vivek.greet() # Calling object's greet() method; Output: Hello
```

#### 9. Read file from a disk and save file to a disk
Lets see how to read and write a csv file in an organized way. CSV is the most common file type you will be using for data science, however python can read several other file types and data directly from websites as well.  
```python
import pandas

# read a csv using the pandas package
df = pandas.read_csv('student_data.csv')
print(df)

# write data to a csv using pandas package
df.to_csv('student_data_copy.csv')
```

#### 10. Ability to comment your code so you can understand it when you revisit it some time later
We can tell Python that a line of code is a comment by starting it with a #. 
```python
# this is a comment
```
We can tell that a multi-line block of text is a comment by enclosing it in triple inverted single quotes. 
```python
'''
this
is
a
comment
block
'''
```

Overall, Python is a versatile and powerful programming language that is well-suited for a wide range of programming tasks. With its emphasis on simplicity, object-oriented design, and a large and growing ecosystem of third-party libraries and tools, Python is a valuable tool for both beginner and experienced programmers. Whether building web applications, analyzing data, or working on artificial intelligence projects, Python provides a fast, flexible, and enjoyable development experience.

To close I will emphasize the importance of practicing in learning anything new. Persistence and trying out different combinations of these building blocks for solving easier problems first and more complex ones later on is the only way to become fluent.

Comments welcome!

{% include disqus_comments.html %}
