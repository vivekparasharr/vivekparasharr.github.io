---
title: "Introduction to Programming in Julia"
date: "2019-04-06"
tags:
    - programming
    - coding
    - julia
thumbnail: "/assets/img/placeholder.jpg"
---
# Quick Introduction to Julia
Julia is a high-level, high-performance programming language that was created in 2012 by a team of computer scientists led by Jeff Bezanson, Stefan Karpinski, and Viral Shah. Julia was designed to address the limitations of traditional scientific computing languages, such as MATLAB, Python, and R, while still retaining their ease of use and flexibility.

One of the key features of Julia is its performance. Julia is designed to be fast, with execution speeds comparable to those of compiled languages such as C and Fortran. This is achieved through a combination of just-in-time (JIT) compilation, which compiles code on the fly as it is executed, and type inference, which allows Julia to determine the data types of variables at runtime.

Another important feature of Julia is its support for multiple dispatch. Multiple dispatch allows Julia to select the appropriate method to use based on the types of the arguments being passed to a function. This makes Julia a flexible and expressive language that can be easily extended and customized to fit a wide range of programming tasks.

Julia also includes a number of built-in data structures and libraries that make it easy to work with arrays, matrices, and other scientific computing tools. These include tools for linear algebra, statistics, optimization, and machine learning, as well as support for distributed computing and parallelism.

In addition to its scientific computing features, Julia also includes support for general-purpose programming tasks, such as web development, database access, and file I/O. Julia's growing package ecosystem provides a wide range of libraries and tools for these tasks, making it a versatile language that can be used for a variety of programming tasks.

One of the key benefits of Julia is its community. Julia has a rapidly growing community of developers and users who are actively contributing to the language and its ecosystem. This community has created a large number of high-quality packages, as well as a number of online resources and forums for learning and discussing the language.

# Most modern programming languages have a set up similar building blocks, for example 
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

Lets dive right in and see how we can do these things in Julia. 

## 0. How to install Julia on your desktop?
Before we can begin to write a program in Julia, we need to install [Julia](https://julialang.org/downloads/). Next you can install [VSCode](https://code.visualstudio.com/Download). Now launch VSCode and install the Julia (by julialang) extension. Now you can create a new test.jl file and add the following code and see if runs.  

```julia
4+2; # If you don't want to see the result of the expression printed, use a semicolon at the end of the expression
ans; # the value of the last expression you typed on the REPL, it's stored within the variable ans
```

Before we dive in, chaining functions is possible in Julia, like so:
```julia
1:10 |> collect
```

## 1. Receiving input from the user and Showing output to the user
There are several ways in which we can show output to the user. Let's look at some ways of showing output:
```julia
# receiving input from user
name = readline(stdin) 

# showing output to user
println("you name is ", name) 
```

## 2. Ability to store values in variables (usually of different kinds such as integers, floating points or character)
Names of variables are in lower case. Word separation can be indicated by underscores. 
Julia has several types of variables broadly classified into Concrete and abstract types. The types that can have subtypes (e.g. Any, Number) are called abstract types. The types that can have instances are called concrete types. These types cannot have any subtypes.

Concrete types can be further divided into primitive (or basic), and complex (or composite). Let's take a deeper look:
```julia
# Primitive types
## the basic integer and float types (signed and unsigned): Int8, UInt8, Int16, UInt16, Int32, UInt32, Int64, UInt64, Int128, UInt128, Float16, Float32, and Float64
a = 10 

## more advanced numeric types: BigFloat, BigInt
a = BigInt(2)^200 

## Boolean and character types: Bool and Char
selected = true

## Text string types: String
name = "vivek"

# Composite type
## Rational, used to represent fractions. It is composed of two pieces, a numerator and a denominator, both integers (of type Int)
666//444 # To make rational numbers, use two slashes (//)
```

Some advanced data types include dictionary and sets. Sets are similar to arrays with the difference that they dont allow element duplication. 
```julia
dict = Dict("a" => 1, "b" => 2, "c" => 3)
dict = Dict{String,Integer}("a"=>1, "b" => 2) # If you know the types of the keys and values in advance, you can specify them after the Dict keyword, in curly braces
# looking things up
dict["a"]
values(dict) # to retrieve all values
keys(dict) # to retrieve all keys
# these can be useful for iterating
for k in keys(dict)
for (key, value) in dict

merge(d1, d2) # merge() function which can merge two dictionaries
findmin(d1) # find the minimum value in a dictionary, and return the value, and its key
filter((k, v) -> k == 1, d1)

# sort dict - you can use the SortedDict data type from the DataStructures.jl package
Pkg.add("DataStructures")
import DataStructures
dict = DataStructures.SortedDict("b" => 2, "c" => 3, "d" => 4, "e" => 5, "f" => 6)

# Sets - A set is a collection of elements, just like an array or dictionary, with no duplicated elements. 
colors = Set{String}(["red","green","blue","yellow"])
push!(colors, "black")  # You can use push!() to add elements to a set

union(colors, rainbow) # The union of two sets is the set of everything that is in one or the other sets
intersect(colors, rainbow) # The intersection of two sets is the set that contains every element that belongs to both sets
setdiff(colors, rainbow) # The difference between two sets is the set of elements that are in the first set, but not in the second
```
We will discuss abstract data types in section 8 below. 

## 3. A string of characters where you can store names, addresses, or any other kind of text
Any value written within a pair of double quotes in Julia is treated as a string. 
```julia
"this is a string"

# double quotes and dollar signs need to be preceded (escaped) with a backslash
"""this is "a" string with double quotes""" # triple double quotes can be used to store strings with double quotes in them
```

Julia also allows the user to indicate special strings. 
```julia
# special strings
r" " indicates a regular expression
v" " indicates a version string
b" " indicates a byte literal
raw" " indicates a raw string that doesn't do interpolation
```

Key idea here is to learn how to manipulate string variables. There are a few common operations that we will focus on:
a. Concatenate strings
```julia
# Concatenate strings
join(split(s, r"a|e|i|o|u", false), "aiou") # You can join the elements of a split string in array form using join()
```
b. Counting number of characters in a string
```julia
# Counting number of characters in a string
length(str) # to find the length of a string
lastindex(str) # to find index of last char of string
```
c. Changing the case - toupper() & tolower() functions
```julia
uppercase(s)
```
d. Splitting a string
```julia
split("You know my methods, Watson.") # by default splits on space
split("You know my methods, Watson.", 'W') # splits on the char W
# If you want to split a string into separate single-character strings, use the empty string ("") 

split("You know my methods, Watson.", r"a|e|i|o|u", false) # splits string on the char that matches any of the vowels
# false makes sure that empty strings are not returned
```
e. String interpolation
```julia
# string interpolation - use the results of Julia expressions inside strings.
x = 42
"The value of x is $(x)." # "The value of x is 42."
```
f. Iterate over a string
```julia
for char in s  # iterate through a string
    print(char, "_")
end
```
g. Get index of all characters in a string
```julia
for i in eachindex(str)
    @show su[i]
end
```
h. Converting between numbers and strings
```julia
a = BigInt(2)^200 
a=string(a) # convert number to string
parse(BigInt, a) # convert strings to numbers
```
i. Finding and replacing things inside strings
```julia
s = "My dear Frodo";
in('M', s) # true
occursin("Fro", s) # true
findfirst("My", s) # 1:2
replace(s, "Frodo" => "Frodo Baggins")
```
There are a lot of other functions as well:
```julia
length(str) - - length of string
sizeof(str) - length/size
startswith(strA, strB) - does strA start with strB?
endswith(strA, strB) - does strA end with strB?
occursin(strA, strB) - does strA occur in strB?
all(isletter, str) - is str entirely letters?
all(isnumeric, str) - is str entirely number characters?
isascii(str) - is str ASCII?
all(iscntrl, str) - is str entirely control characters?
all(isdigit, str) - is str 0-9?
all(ispunct, str) - does str consist of punctuation?
all(isspace, str) - is str whitespace characters?
all(isuppercase, str) - is str uppercase?
all(islowercase, str) - is str entirely lowercase?
all(isxdigit, str) - is str entirely hexadecimal digits?
uppercase(str) - return a copy of str converted to uppercase
lowercase(str) - return a copy of str converted to lowercase
titlecase(str) - return copy of str with the first character of each word converted to uppercase
uppercasefirst(str) - return copy of str with first character converted to uppercase
lowercasefirst(str) - return copy of str with first character converted to lowercase
chop(str) - return a copy with the last character removed
chomp(str) - return a copy with the last character removed only if it's a newline
```

## 4. Some advance data types such as arrays which can store a series of regular variables (such as a series of integers)
Arrays can be one-dimentional or multi-dimentional. An array is created using the square brackets, Array constructor or several other methods. Arrays support a lot of functionality within Julia so I have covered it in more detail in [this](vivekparasharr.github.io) array specific article. For now lets check out the key functionality. 

```julia
# Defining
# Creating arrays by initializing
arr_Int64 = [1, 2, 3, 4, 5]

# Creating empty arrays
b = Int64[]

# Creating 2-d arrays
arr_2d = [1 2 3 4] # If you leave out the commas when defining an array, you can create 2D arrays quickly. Here's a single row, multi-column array: 
arr_2d = [1 2 3 4 ; 5 6 7 8] # you can add another row using ;

# Creating arrays using range objects
a = 1:10 # creates a range variable with 10 elements from 1 to 10
collect(a) # collect displays a range variable 
[a...] # instead of collect, you could use the ellipsis (...) operator (three periods) after the last element
range(1, length=12, stop=100) # Julia calculates the missing pieces for you by combining the values for the keywords step(), length(), and stop()

# Using comprehensions and generators to create arrays
[n^2 for n in 1:5] # a 1-d array
[r * c for r in 1:5, c in 1:5] # a 2-d array

# Reshape an array to create a multi-dimentional array
reshape([1, 2, 3, 4, 5, 6, 7, 8], 2, 4) # create a simple array and then change its shape

# Supports indexing and slicing
# 1-d
a[5] # 5th element
a[end] # last element
a[end-1] # second last element
# 2-d
a = [[1, 2] [3,4]]
a[2,2] # element at row-2 x col-2
a[:,2] # all elements of col-2
getindex(a, 2,2) # same as a[2,2]

# Elements can be added
a = Array[[1, 2], [3,4]]
push!(a, [5,6]) # The push!() function pushes another item onto the back of an array
pushfirst!(a, 0) # To add an item at the front
splice() # To insert an element into an array at a given index
splice!(a, 4:5, 4:6) # insert, at position 4:5, the range of numbers 4:6
L = ['a','b','f']; splice!(L, 3:2, ['c','d','e']) # insert c, d, e between b and f

# Elements can be removed
splice!(a,5); # If you don't supply a replacement, you can also use splice!() can remove elements and move the rest of them along
pop!(a) # To remove the last item
popfirst!(a)

# Elementwise and vectorized operations
a / 100 # every element of the new array is the original divided by 100. These operations operate elementwise

n1 = 1:6;
n2 = 2:7;
n1 .* n2; # if two arrays are to be multiplied then we just add a . before the mathematical operator to signify elementwise
# the first element of the result is what you get by multiplying the first elements of the two arrays, and so on

# How function works on individual variables
f(a, b) = a * b
a=10;b=20;print(f(a,b))

# How function can be applied elementwise to arrays
n1 = 1:6;
n2 = 2:7;
print(f.(n1, n2))
```

## 5. Ability to loop your code in the sense that you want to receive 10 names from a user, you will write the code for that 10 times, but just once and tell the computer to loop through it 10 times
Julia has several looping options such as 'for' and 'while'. There are also options of nesting (single, double, triple, ..) loops. 
a. The While loop executes the same code again and again until a stop condition is met:
```julia
# while end - iterative conditional evaluation
x=0
while x < 4
    println(x)
    global x += 1
end
```
b. The for loop: acts as an iterator in Julia; it goes through items that are in a sequence or any other iterable item. Objects that we've learned about that we can iterate over include strings, lists, tuples, and even built-in iterables for dictionaries, such as keys or values.
```julia
# for end - iterative evaluation
# use the global keyword to define a variable that outlasts the loop
for i in 1:10
    z = i
    println("z is $z")
end

# Some sample for loop statements for different data types
for color in ["red", "green", "blue"] # an array
for letter in "julia" # a string
for element in (1, 2, 4, 8, 16, 32) # a tuple
for i in Dict("A"=>1, "B"=>2) # a dictionary
for i in Set(["a", "e", "a", "e", "i", "o", "i", "o", "u"])
```
Julia also provides the break and continue statements that allow us to alter the loops further. Following is their use:
  break: Breaks out of the current closest enclosing loop.
  continue: Goes to the top of the closest enclosing loop.
```julia
# Example with break statement
x=0
while true
    println(x)
    x += 1
    x >= 4 && break # breaks out of the loop
end
```
break and continue statements can appear anywhere inside the loop’s body, but we will usually put them further nested in conjunction with an if statement to perform an action based on some condition.

Following are some other options for looping options:
```julia
# list comprehensions
[i^2 for i in 1:10]
[(r,c) for r in 1:5, c in 1:2] # two iterators in a comprehension

# Generator expressions - generator expressions can be used to produce values from iterating a variable
sum(x^2 for x in 1:10)

# Enumerating arrays
m = rand(0:9, 3, 3)
[i for i in enumerate(m)]

# Zipping arrays
for i in zip(0:10, 100:110, 200:210)
    println(i)
end

# Iterable objects
ro = 0:2:100
[i for i in ro]
```

## 6. Ability to execute statements of code conditionally, for example if marks are more than 40 then the student passes else fails
Julia provides several options to apply conditional logic. Lets take a look at them:
a. ternary and compound expressions:
```julia
x = 1
x > 3 ? "yes" : "no"
```
b. Boolean switching expressions: 
```julia
isodd(1000003) && @warn("That's odd!")
isodd(1000004) || @warn("That's odd!")
```
c. if elseif else end - conditional evaluation: 
```julia
name = "Julia"
if name == "Julia"
   println("I like Julia")
elseif name == "Python"
   println("I like Python.")
   println("But I prefer Julia.")
else
   println("I don't know what I like")
end
```
c. Error handling using try.. catch. This allows the code to still keep executing even if an error occurs, which would usually halt the program. 
```julia
# try catch error throw exception handling
try
    <statement-that-might-cause-an-error>;
catch e # error gets caught if it happens
    println("caught an error: $e") # show the error if you want to
end
println("but we can continue with execution...")

# Example 1 - error doesnt occur
try
    a=10 # no error 
catch e
    print(e)
end

# Example 2 - error occurs
try
    la-la-la # undefined variable error
catch e
    print(e)
end
```

## 7. Put your code in functions
Functions allows us to create a block of code that can be executed many times without needing to it write it again. 
Julia has something called a single expression function. These are usually defined in one line like so:
```julia 
# Single expression functions
f(x) = x * x
g(x, y) = sqrt(x^2 + y^2)
```

Functions with multiple expressions are also supported and can be defined using the function keyword: 
```julia
# Syntax
# Functions with multiple expressions
function say_hello(name) 
    println("hello ", name)
end
say_hello("vivek")
```

Additionally, functions can be programmed to retun a single or multiple value using the return keyword. 
```julia
# define function which returns a value
function add_numbers(a,b)
    return a+b
end
# call the function
add_numbers(2,3)

# define function which returns multiple values
function add_multiply_numbers(a, b=10) # we can supply default values as well
    return(a+b, a*b)
end
# call the function
add_multiply_numbers(2,3)
add_multiply_numbers(2)
```
args... lets a function take an arbitrary number of arguments. A for loop can be used to iterate over these arguments.  
```julia
function show_args(args...)
    for arg in args
        println(arg," ")
    end
end
show_args(10,20,25,35,50)
```
Julia also supports anonymous functions, with no name. 
```julia
map((x,y,z) -> x + y + z, [1,2,3], [4, 5, 6], [7, 8, 9])
```

Map and reduce can also be used to apply functions to arrays. 
Map - If you already have a function and an array, you can call the function for each element of the array by using map()
```julia
a=1:10;
map(sin, a) # map() returns a new array but if you call map!() , you modify the contents of the original array
```
The map() function collects the results of some function working on each and every element of an iterable object, such as an array of numbers. 
```julia
map(+, 1:10)
```
The reduce() function does a similar job, but after every element has been seen and processed by the function, only one is left. The function should take two arguments and return one.
```julia
reduce(+, 1:10)
```

## 8. Advanced data types that are formed through a combinaiton of one or more types of basic data types such as structures or classes
Julia allows user to create user defined variables using abstract type (which are abstract) or mutable struct (which are concrete). Lets take a look at both. 
Abstract type
```julia
abstract type MyAbstractType end # By default, the type you create is a direct subtype of Any
abstract type MyAbstractType2 <: Number end # the new abstract type is a subtype of Number
```
Concrete type using mutable struct
```julia
# define the data type
mutable struct student <: Any
   name
   age::Int
end

# initialize a variable of that data type
x=student("vivek", 30)

# use the variable
x.name
x.age
```

## 9. Read file from a disk and save file to a disk
Lets see how to read in an organized way. 
```julia
f = open("sherlock-holmes.txt") # To read text from a file, first obtain a file handle: 
close(f) # When you've finished with the file, you should close the connection
```

If you use the following technique then you dont need to close. The open file is automatically closed when this block finishes.
```julia
open("sherlock-holmes.txt") do file
    # do stuff with the open file
end
```

## 10. Ability to comment your code so you can understand it when you revisit it some time later
We can tell Julia that a line of code is a comment by starting it with a #. 
```julia
# this is a comment
```

Overall, Julia is a powerful and flexible programming language that is well-suited for scientific computing and other high-performance tasks. With its emphasis on performance, multiple dispatch, and a growing ecosystem of packages and tools, Julia is a valuable tool for researchers, data scientists, and other professionals who need a fast, flexible, and expressive language for their work.

To close I will emphasize the importance of practicing in learning anything new. Persistence and trying out different combinations of these building blocks for solving easier problems first and more complex ones later on is the only way to become fluent.

Comments welcome!