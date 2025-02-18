---
title: "Introduction to Programming in Ruby"
date: "2019-03-02"
tags:
    - programming
    - coding
    - ruby
thumbnail: "/assets/img/placeholder.jpg"
---
# Quick Introduction to Ruby
Ruby is a high-level, interpreted programming language that was created in the mid-1990s by Yukihiro "Matz" Matsumoto. It is a general-purpose language that is designed to be easy to use and read, with syntax that is similar to natural language. Ruby is often used for web development, as well as for building command-line utilities, desktop applications, and other types of software.

One of the key features of Ruby is its emphasis on programmer productivity and ease of use. Ruby's syntax is designed to be intuitive and easy to read, making it accessible to both beginner and experienced programmers. Ruby also includes a number of built-in features and libraries that make it easy to accomplish common programming tasks, such as working with strings, arrays, and hashes.

Another important feature of Ruby is its object-oriented programming model. Everything in Ruby is an object, and methods can be defined on objects to add functionality. Ruby also includes support for inheritance, encapsulation, and polymorphism, which makes it a powerful tool for building complex software systems.

Ruby is also known for its extensive library of open-source gems, which are pre-built packages of code that can be easily integrated into Ruby projects. These gems provide a wide range of functionality, from database access to web development frameworks, and can save developers a significant amount of time and effort in building software.

One of the most popular web development frameworks built in Ruby is Ruby on Rails. Rails is a full-stack web framework that provides a set of conventions and tools for building web applications quickly and easily. With its focus on developer productivity, Rails has become a popular choice for startups and small businesses, as well as for larger enterprises.

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

Lets dive right in and see how we can do these things in Ruby. 

## 0. How to install Ruby on your desktop?
Before we can begin writing programs in Ruby, we need to set up our ruby environment. 
1. You can install Ruby from here [ruby-lang.org](https://www.ruby-lang.org/en/downloads/). 
2. Additionally, you need to install an IDE to write and execute Ruby code. My personal favorite is [code.visualstudio.com](https://code.visualstudio.com/Download). 
3. Lastly, you will also need to install the following extensions within VSCode: Ruby (Peng Lv) and Code Runner (Jun Han). 

Now, lets write a simple program that print out hello world for the user to see
```ruby
print 'Hello World !!!'
```

## 1. Receiving input from the user and Showing output to the user
There are several ways in which we can show output to the user. Let's look at some ways of showing output:
```ruby
#Method 1:
print 'Hello World !!!'

#Method 2:
p 'Hello World !!!'

#Method 3:
puts 'Hello World !!!'

#Method 4: Showing data stored in variables to user
my_name = "Vivek"
puts "Hello #{my_name}"

#Method 5: Showing multiple variables using same puts statement
aString = "I'm a string!" 
aBoolean = true 
aNumber = 42
puts "string: #{aString} \nboolean: #{aBoolean} \nnumber: #{aNumber}"
```

## 2. Ability to store values in variables (usually of different kinds such as integers, floating points or character)
There are three main types of variable:
1. Strings (a collection of symbols inside speech marks)
2. Booleans (true or false)
3. Numbers (numeric values)

Following are some examples:
```ruby
aString = "I'm a string!" 
aBoolean = true 
aNumber = 42
puts "string: #{aString} \nboolean: #{aBoolean} \nnumber: #{aNumber}"
```

Performing basic math on numeric variables. There are 6 types of basic operations: addition, subtraction, multiplication, division, modulo and exponent. 
```ruby
a = 5
b = 2
puts "sum: #{a+b}\
    \ndifference: #{a-b}
    \nmultiplication: #{a*b}
    \ndivision: #{a/b}
    \nmodulo: #{a%b}
    \nexponent: #{a**b}"
```

## 3. A string of characters where you can store names, addresses, or any other kind of text
You can use single quotes or double quotes for strings - either one is acceptable.
```ruby
myFirstString = 'I am a string!' #single quotes
mySecondString = "Me too!" #double quotes
```
There are a few common operations that we will focus on:
```ruby
"Hi!".length #is 3
"Hi!".reverse #is !iH
"Hi!".upcase #is HI!
"Hi!".downcase #is hi!
# You can also use many methods at once. They are solved from left to right.
"Hi!".downcase.reverse #is !ih
# If you want to check if one string contains another string, you can use .include?.
"Happy Birthday!".include?("Happy")
```

## 4. Some advance data types such as arrays which can store a series of regular variables (such as a series of integers)
Arrays allow you to group multiple values together in a list. Each value in an array is referred to as an "element".
a. Defining an array:
```ruby
myArray = []  # an empty array
myOtherArray = [1, 2, 3]  # an array with three elements
```
b. Accessing array elements:
```ruby
# In order to add to or change elements in an array, you can refer to an element by number.
myOtherArray[3] = 4
```

Ruby has another advanced data type called Hash, which is similar to a python dictionary. Just like arrays, hashes allow you to store multiple values together. However, while arrays store values with a numerical index, hashes store information using key-value pairs. Each piece of information in the hash has a unique label, and you can use that label to access the value.
a. To create a hash, use Hash.new, or myHash={}. For example:
```ruby
myHash=Hash.new()
myHash["Key"]="value"
myHash["Key2"]="value2"
# or
myHash={
    "Key" => "value",
    "Key2" => "value2"
}
```
b. To access elements of a hash:
```ruby
puts myHash["Key"] # puts value
```

Instead of using a string as a key, you can also use a symbol, like this:
a. To create a hash, use Hash.new, or myHash={}. For example:
```ruby
myHash=Hash.new()
myHash[:Key]="value"
myHash[:Key2]="value2"
# or
myHash={
    Key: "value",
    Key2: "value2",
}
```
b. To access elements of a hash:
```ruby
puts myHash[:Key] # puts "value"
```


## 5. Ability to loop your code in the sense that you want to receive 10 names from a user, you will write the code for that 10 times, but just once and tell the computer to loop through it 10 times
Ruby has several looping options (For, While, and Until). There are options of nesting (single, double, triple, ..) loops as well. 
a. For loop executes code once for each element in expression. Following example shows how a for loop works:
```ruby
# Syntax
for variable [, variable ...] in expression [do]
   code
end

# Example
for i in 0..5
    puts "Value of local variable is #{i}"
end
```
b. While loop executes code while conditional is true. A while loop's conditional is separated from code by the reserved word do, a newline, backslash \, or a semicolon ;. Following example shows how a for loop works:
```ruby
# Syntax
while conditional [do]
    code
end

# Example 
a=1
b=5
while a<=b
    puts "run #{a}" 
    a=a+1 
end

# Ruby while modifier - Executes code while conditional is true.
code while condition
# or
begin # If a while modifier follows a begin statement with no rescue or ensure clauses, code is executed once before conditional is evaluated.
    code 
end while conditional
```
c. Until loop executes code while conditional is false. An until statement's conditional is separated from code by the reserved word do, a newline, or a semicolon. Following example shows how a for loop works:
```ruby
# Syntax
until conditional [do]
    code
end  

# Example
$i = 0
$num = 5
until $i > $num  do
   puts("Inside the loop i = #$i" )
   $i +=1;
end

# Ruby until modifier - Executes code while conditional is false.
code until conditional
# or 
begin # If an until modifier follows a begin statement with no rescue or ensure clauses, code is executed once before conditional is evaluated.
    code
end until conditional
```
d. Ruby also offers following keywords that can modify the behavior of the above loops:
```ruby
# break - Terminates the most internal loop. Terminates a method with an associated block if called within the block (with the method returning nil).
# next - Jumps to the next iteration of the most internal loop. Terminates execution of a block if called within a block (with yield or call returning nil).
# redo - Restarts this iteration of the most internal loop, without checking loop condition. Restarts yield or call if called within a block.
# retry - If retry appears in rescue clause of begin expression, restart from the beginning of the begin body.
# retry - If retry appears in the iterator, the block, or the body of the for expression, restarts the invocation of the iterator call. Arguments to the iterator is re-evaluated.
```

## 6. Ability to execute statements of code conditionally, for example if marks are more than 40 then the student passes else fails
Conditionals are used to add branching logic to your programs; they allow you to include complex behaviour that only occurs under specific conditions.
a. If - if condition is an expression that can be checked for truth. If the expression evaluates to true, then the code within the block is executed.
```ruby
if condition
    something to be done
end

# Ruby if modifier - executes code if the conditional is true.
code if condition
```
Following is an actual example of an if statement with both an elsif and an else.
```ruby
booleanOne = true
randomCode = "Hi!"
if booleanOne
  puts "I will be printed!"
elsif randomCode.length>=1
  puts "Even though the above code is true, I won't be executed because the earlier if statement was true!"
else
  puts "I won't be printed because the if statement was executed!"
end
```
b. If Else - You can combine if with the keyword else. This lets you execute one block of code if the condition is true, and a different block if it is false. The else block will only be executed if the if block doesn't run, so they will never both be executed.
```ruby
if condition
    something to be done
else
    something to be done if the condition evaluates to false
end
```
c. Elseif - When you want more than two options, you can use elsif. This allows you to add more conditions to be checked. Still only one of the code blocks will be run, because the statement only executes the code in the first applicable block; Once a condition has been satisfied, the whole statement ends. Here is if/elsif/else statement syntax:
```ruby
if condition
  something to be done
elsif different condition
  something else to be done
else
  another different thing to be done
end
```
d. Unless - Executes code if conditional is false. If the conditional is true, code specified in the else clause is executed.
```ruby
unless condition
    # thing to be done if the condition is false
else
    # else is optional
    # thing to be done if the condition is true
end

# Ruby unless modifier - Executes code if conditional is false.
code unless conditional
```
e. Case - this is basically same as a if-elseif-else statement, but with more clear syntax.
```ruby
# case statement syntax
case expr0
when expr1, expr2
   stmt1
when expr3, expr4
   stmt2
else
   stmt3
end
# is basically similar to the following −
if expr1 === expr0 || expr2 === expr0
   stmt1
elsif expr3 === expr0 || expr4 === expr0
   stmt2
else
   stmt3
end
```
Example of case statement
```ruby
$age =  5
case $age
when 0 .. 2
   puts "i will not be printed"
when 3 .. 6
   puts "i will be printed"
when 7 .. 12
   puts "i will not be printed"
when 13 .. 18
   puts "youth"
else
   puts "i will not be printed"
end
```

## 7. Put your code in functions
a. In Ruby we call functions methods. Methods are reuseable sections of code that perform specific tasks in our program. Using methods means that we can write simpler, more easily readable code. 
```ruby
# syntax
def methodname
    # method code here
end
```
b. Methods can also be defined to accept and process any parameters that are passed to them:
```ruby
# Methods With Parameters
def laugh(number)
    puts "haha " * number
end
```
c. We can call methods using the name of the method and specify the parameters within paranthesis or without them:
```ruby
# Using method - calling method as follows prints "haha" 5 times on the screen
laugh(5)
# You can also call laugh without paranthesis
laugh 5
```
d. We can set default values for the parameters, which will be used if method is called without passing the required parameters
```ruby
def method_name (var1 = value1, var2 = value2)
    expr..
end
```
e. We can also return values. return statement in ruby is used to return one or more values from a Ruby Method.
```ruby
return
# or
return 12
# or
return 1,2,3
```
f. We can also define methods with variable number of parameters, like so:
```ruby
Variable Number of Parameters
def sample (*test)
    puts "The number of parameters is #{test.length}"
    for i in 0...test.length
       puts "The parameters are #{test[i]}"
    end
end
sample "Zara", "6", "F"
sample "Mac", "36", "M", "MCA"
```

## 8. Advanced data types that are formed through a combinaiton of one or more types of basic data types such as structures or classes
Ruby allows user to create classes. These can be a combination of variables and functions that operate on those variables. Lets take a look at how we can define and use them. 
```ruby
# Define a class
class employee
    @@no_of_customers = 0
    def initialize(id, name, addr)
       @cust_id = id
       @cust_name = name
       @cust_addr = addr
    end
end

# Creating an object of the class and using that
cust1 = employee.new("1", "Vivek", "Somewhere on the, Internet")
```

## 9. Read file from a disk and save file to a disk
Lets see how to read and parse csv in an organized way. CSV is the most common file type you will be using for data science, however ruby can read several other file types as well.  
```ruby
require 'csv'

# read a csv 
CSV.read("file.csv")

# parse a string of text which is in csv format
CSV.parse("1,penny\n2,nickel\n3,dime")
```

## 10. Ability to comment your code so you can understand it when you revisit it some time later
a. We can tell ruby that a line of code is a comment by starting it with #. 
```ruby
#this is a comment
```
b. We can also specify a comment block, like so:
```ruby
=begin
There are three main types of variable:
1. Strings (a collection of symbols inside speech marks)
2. Booleans (true or false)
3. Numbers (numeric values)
=end
```

Overall, Ruby is a powerful and flexible programming language that is well-suited for a wide range of programming tasks. With its focus on ease of use, object-oriented design, and extensive library of gems, Ruby is a valuable tool for both beginner and experienced programmers. Whether building web applications, desktop utilities, or other types of software, Ruby provides a fast, flexible, and enjoyable development experience.

To close I will emphasize the importance of practicing in learning anything new. Persistence and trying out different combinations of these building blocks for solving easier problems first and more complex ones later on is the only way to become fluent.

Comments welcome!