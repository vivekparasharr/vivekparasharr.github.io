---
title: "Introduction to Programming in R"
date: "2019-07-06"
tags:
    - programming
    - coding
    - r
    - r-programming
    - r-studio
thumbnail: "/assets/img/placeholder.jpg"
---
# Quick Introduction
R is a programming language and environment for statistical computing and graphics. It was created in the early 1990s by Ross Ihaka and Robert Gentleman at the University of Auckland, New Zealand. R is now widely used in academia, industry, and government for data analysis, statistical modeling, and data visualization.

One of the key features of R is its wide range of statistical and graphical techniques. R provides a vast array of statistical and graphical methods, including linear and nonlinear modeling, classical statistical tests, time-series analysis, classification, clustering, and graphical techniques for data visualization. R is also highly extensible and has an active community of users and developers who create and contribute packages that enhance the capabilities of the language.

R is an open-source language, which means that the code is available for free and can be modified and redistributed. This has led to the development of a large and active community of R users and developers. The R community provides a wealth of resources, including documentation, tutorials, and help forums, making it easy for users to get started with the language and to find solutions to their problems.

One of the advantages of R is its integration with other programming languages and data sources. R can read data from a wide range of sources, including text files, spreadsheets, databases, and web services. R can also interact with other programming languages, such as Python, Java, and C++, allowing users to take advantage of the strengths of different languages and libraries.

Another advantage of R is its versatility. R can be used for a wide range of tasks, from data analysis and visualization to machine learning and artificial intelligence. R can also be used in a variety of settings, from research and academia to industry and government.

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

Lets dive right in and see how we can do these things in R. 

Before we can begin to write a program in R, we need to install [R](https://cran.r-project.org/mirrors.html) and [R studio](https://rstudio.com/products/rstudio/download/).  

```r
myString <- "Hello, World!"
print (myString)
```

## 1. Receiving input from the user and Showing output to the user
There are several ways in which we can show output to the user. Let's look at some ways of showing output:
```r
var.1 = c(0,1,2,3)
'Method 1: values of the variables can be printed using print()
print(var.1)
# Output: 0 1 2 3

'Method 2: cat() function combines multiple items into a continuous print output
cat ("var.1 is ", var.1 ,"\n")
# Output: var.1 is  0 1 2 3
```

## 2. Ability to store values in variables (usually of different kinds such as integers, floating points or character)
Basic data types: In R we call variables as objects. There are several types of objects, lets take a look at the important ones:
```r
# Logical
v <- TRUE 
print(class(v)) # class funciton can be used to see the data type of the variable

# Numeric
v <- 23.5
print(class(v))

# Integer
v <- 2L
print(class(v))

# Complex
v <- 2+5i
print(class(v))

# Character
v <- "TRUE"
print(class(v))

# Raw
v <- charToRaw("Hello")
print(class(v))
```
Advanced data types: Much of R's power comes from the fact that R lets us access some advanced objects other than the basic ones shown earlier. Lets take a look at some of the advanced variables:
```r
# Vectors - When you want to create vector with more than one element, you should use c() function which means to combine the elements into a vector.
# Create a vector.
apple <- c('red','green',"yellow")
print(apple)
# Get the class of the vector.
print(class(apple))

# Lists - A list is an R-object which can contain many different types of elements inside it like vectors, functions and even another list inside it.
# Create a list.
list1 <- list(c(2,5,3),21.3,sin)
# Print the list.
print(list1)

# Matrices - A matrix is a two-dimensional rectangular data set. It can be created using a vector input to the matrix function.
# Create a matrix.
M = matrix( c('a','a','b','c','b','a'), nrow = 2, ncol = 3, byrow = TRUE)
print(M)

# Arrays - While matrices are confined to two dimensions, arrays can be of any number of dimensions. The array function takes a dim attribute which creates the required number of dimension. In the below example we create an array with two elements which are 3x3 matrices each.
# Create an array.
a <- array(c('green','yellow'),dim = c(3,3,2))
print(a)

# Factors - Factors are the r-objects which are created using a vector. It stores the vector along with the distinct values of the elements in the vector as labels. The labels are always character irrespective of whether it is numeric or character or Boolean etc. in the input vector. They are useful in statistical modeling. Factors are created using the factor() function. The nlevels functions gives the count of levels.
# Create a vector.
apple_colors <- c('green','green','yellow','red','red','red','green')
# Create a factor object.
factor_apple <- factor(apple_colors)
# Print the factor.
print(factor_apple)
print(nlevels(factor_apple))

# Data frames are tabular data objects. Unlike a matrix in data frame each column can contain different modes of data. The first column can be numeric while the second column can be character and third column can be logical. It is a list of vectors of equal length. Data Frames are created using the data.frame() function.
# Create the data frame.
BMI <-  data.frame(
   gender = c("Male", "Male","Female"), 
   height = c(152, 171.5, 165), 
   weight = c(81,93, 78),
   Age = c(42,38,26)
)
print(BMI)
```

## 3. A string of characters where you can store names, addresses, or any other kind of text
Any value written within a pair of single quote or double quotes in R is treated as a string. 

Key idea here is to learn how to manipulate string variables. There are a few common operations that we will focus on:
a. Concatenate strings
```r
# Concatenate strings
paste(str1, str2, str3, ... , sep = " ", collapse = NULL)
```
b. Counting number of characters in a string
```r
# Counting number of characters in a string - nchar() function
nchar(test_str)
```
c. Changing the case - toupper() & tolower() functions
```r
str = 'apPlE'
toupper(str) # APPLE
tolower(str) # apple
```
d. Extracting parts of a string - substring() function
```r
# Syntax
substring(x,first,last)
# Example - Extract characters from 5th to 7th position.
result <- substring("Extract", 5, 7)
print(result)
```
e. Formatting - Numbers and strings can be formatted to a specific style using format() function.
```r
# Syntax
format(x, digits, nsmall, scientific, width, justify = c("left", "right", "centre", "none")) 
# Example
# Total number of digits displayed. Last digit rounded off.
result <- format(23.123456789, digits = 9)
print(result)
# Display numbers in scientific notation.
result <- format(c(6, 13.14521), scientific = TRUE)
print(result)
# The minimum number of digits to the right of the decimal point.
result <- format(23.47, nsmall = 5)
print(result)
# Format treats everything as a string.
result <- format(6)
print(result)
# Numbers are padded with blank in the beginning for width.
result <- format(13.7, width = 6)
print(result)
# Left justify strings.
result <- format("Hello", width = 8, justify = "l")
print(result)
# Justfy string with center.
result <- format("Hello", width = 8, justify = "c")
print(result)
```

## 4. Some advance data types such as arrays which can store a series of regular variables (such as a series of integers)
Arrays are a series of similar type of data stored together in one variable. Arrays can be one-dimentional or multi-dimentional. An array is created using the array() function. It takes vectors as input and uses the values in the dim parameter to create an array. 

For example − If we create an array of dimension (2, 3, 4) then it creates 4 rectangular matrices each with 2 rows and 3 columns.
```r
# dim=c(rows, columns, matrices)
array2 = array(1:12, dim=c(2, 3, 2))
# Naming Columns and Rows
column.names <- c("COL1","COL2","COL3")
row.names <- c("ROW1","ROW2")
matrix.names <- c("Matrix1","Matrix2")
array2 = array(1:12, dim=c(2, 3, 2), dimnames = list(row.names, column.names, matrix.names))
```
Lets see how we can access array elements:
```r
# dim=c(rows, columns, matrices)
print(array2[2,,2]) # Print the second row of the second matrix of the array.
print(array2[1,3,1]) # Print the element in the 1st row and 3rd column of the 1st matrix.
print(array2[,,2]) # Print the 2nd Matrix.
```
Since the returned values here are matrices, we can perform matrix operations on them

Calculations Across Array Elements (we can use user defined functions as well)
- apply()
- lapply()
- sapply()
- tapply()
```r
# apply(X, MARGIN, FUN) - apply to r or c or both - input to this funciton is a df - output is a vector, list or array
m1 <- matrix(C<-(1:10),nrow=5, ncol=2)
apply(m1, 2, sum)
# lapply(X, FUN) - apply to all elements - input to this function is list, vector or df - output is a list
# sapply(X, FUN) - apply to all elements - input to this function is list, vector or df - output is a vector or a matrix
movies <- c("BRAVEHEART","BATMAN","VERTIGO","GANDHI")
lapply(movies, tolower)
sapply(movies, tolower)
# tapply(X, INDEX, FUN = NULL) - apply to each factor variable in a vector - input to this function is a vector - output it an array
data(iris)
tapply(iris$Sepal.Width, iris$Species, median)
```

## 5. Ability to loop your code in the sense that you want to receive 10 names from a user, you will write the code for that 10 times, but just once and tell the computer to loop through it 10 times
R has several looping options (repeat, while and for). There are also options of nesting (single, double, triple, ..) loops. 
a. The Repeat loop executes the same code again and again until a stop condition is met:
```r
# Syntax
repeat { 
   commands 
   if(condition) {
      break
   }
}

# Example
v <- c("Hello","loop")
cnt <- 2
repeat {
   print(v)
   cnt <- cnt+1   
   if(cnt > 5) {
      break
   }
}
```
b. The While loop executes the same code again and again until a stop condition is met:
```r
# Syntax
while (test_expression) {
   statement
}

# Example
v <- c("Hello","while loop")
cnt <- 2
while (cnt < 7) {
   print(v)
   cnt = cnt + 1
}
```
c. The for loop:
```r
# Syntax
for (value in vector) {
   statements
}

# Example
v <- LETTERS[1:4]
for ( i in v) {
   print(i)
}
```
R also provides the break and next statements that allow us to alter the loops further. Following is their use:
- When the break statement is encountered inside a loop, the loop is immediately terminated and program control resumes at the next statement following the loop.
- On encountering next, the R parser skips further evaluation and starts next iteration of the loop.

## 6. Ability to execute statements of code conditionally, for example if marks are more than 40 then the student passes else fails
R provides if.., if..else.., if..else..if.., and switch options to apply conditional logic. Lets take a look at them:
a. The basic syntax for creating an if statement in R is:
```r
# Syntax
if (test_expression) {
statement
}

# Example
x <- 5
if(x > 0){
print("Positive number")
}
```
b. The basic syntax for creating an if...else statement in R is: 
```r
if (test_expression) {
statement1
} else {
statement2
}

# Example
x <- -5
if(x > 0){
print("Non-negative number")
} else {
print("Negative number")
}
```
c. The basic syntax for creating an if...else if...else statement in R is: 
```r
if (test_expression1) {
statement1
} else if (test_expression2) {
statement2
} else if (test_expression3) {
statement3
} else {
statement4
}

# Example
x <- 0
if (x < 0) {
print("Negative number")
} else if (x > 0) {
print("Positive number")
} else
print("Zero")
```
d. A switch statement allows a variable to be tested for equality against a list of values. Each value is called a case, and the variable being switched on is checked for each case.
```r
x <- switch(
   2,
   "first",
   "second",
   "third",
   "fourth"
)
print(x)
```

## 7. Put your code in functions
In R a user defined function is created by using the keyword function. 
```r
# Syntax
function_name <- function(arg_1, arg_2, ...) {
   Function body 
}
# Example
# Create a function to print squares of numbers in sequence.
new.function <- function(a) {
   for(i in 1:a) {
      b <- i^2
      print(b)
   }
}
```
We can call the function new.function supplying 6 as an argument.
```r
new.function(6)
```
We can also create functions to which we can pass arguments. These functions can also be defined to use default values for those arguments in case user does not provide a value. Lets see how this is done:
```r
new.function <- function(a = 3, b = 6) {
   result <- a * b
   print(result)
}
```
Now we can call this with or without passing any values:
```r
# Call the function without giving any argument.
new.function()
# Call the function with giving new values of the argument.
new.function(9,5)
```

## 8. Advanced data types that are formed through a combinaiton of one or more types of basic data types such as structures or classes
Class is the blueprint that helps to create an object and contains its member variable along with the attributes. R lets you create two types of classes, S3 and S4. 
S3 Classes: These let you overload the functions.
S4 Classes: These let you limit the data as it is quite difficult to debug the program

We will cover s4 classes here. S4 class is defined by the setClass() method. 
```r
# Defining a class
setClass("emp_info", slots=list(name="character", age="numeric", contact="character"))
emp1 <- new("emp_info",name="vivek", age=30, contact="somehwere on the internet")

# Access elements of a class
emp1@name
```

## 9. Read file from a disk and save file to a disk
Lets see how to read and write csv in an organized way. CSV is the most common file type you will be using for data science, however R can read several other file types as well.  
```r
# read a csv file
data <- read.csv('file.csv')

# write a csv file
write.csv(df, 'file.csv', row.names = FALSE)
```

## 10. Ability to comment your code so you can understand it when you revisit it some time later
We can tell R that a line of code is a comment by starting it with a #. 
```r
# this is a comment
```
In summary, R is a powerful and versatile programming language that is widely used for statistical computing and graphics. Its extensive range of statistical and graphical techniques, its open-source nature, and its active community of users and developers make it a valuable tool for data analysis and modeling. Whether you are a researcher, data analyst, or developer, R provides a wide range of tools and resources for working with data and creating meaningful insights.

To close I will emphasize the importance of practicing in learning anything new. Persistence and trying out different combinations of these building blocks for solving easier problems first and more complex ones later on is the only way to become fluent.

Comments welcome!