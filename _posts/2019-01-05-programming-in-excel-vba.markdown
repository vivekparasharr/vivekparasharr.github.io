---
layout: post
title: "Programming in Microsoft Excel VBA"
categories: programming, microsoft, excel, vba
---
Excel VBA, or Visual Basic for Applications, is a programming language that can be used to automate tasks and enhance functionality in Microsoft Excel. VBA is a powerful tool that allows users to write custom macros and functions to automate repetitive tasks, perform complex calculations, and create custom solutions.

VBA is a type of Visual Basic, which is an object-oriented programming language developed by Microsoft. VBA is integrated directly into Excel, making it easy to access and use. VBA code is stored in modules, which can be accessed through the Visual Basic Editor in Excel. In the Editor, users can write, edit, and run VBA code, as well as debug their code to identify and fix any errors.

One of the key advantages of VBA is that it allows users to automate repetitive tasks that would otherwise be time-consuming to perform manually. For example, users can write a VBA macro to format data, generate reports, or update data in bulk. VBA can also be used to perform complex calculations, create custom user interfaces, and interact with other applications.

To get started with VBA, users should have a basic understanding of programming concepts and syntax. The VBA language is based on Visual Basic, so many programming concepts, such as variables, loops, and conditional statements, are similar to other programming languages. Excel also provides many built-in functions and objects that can be used in VBA code, making it easy to access and manipulate data in a spreadsheet.

#### Most modern programming languages have a set up similar building blocks, for example 
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

Lets dive right in and see how we can do these things in VBA. 

#### 0. Enable VBA in your Excel file
Before we can begin to write a program in VBA, also known as a macro, we need to enable the developer tab. You can do this by going to the File > Options > Customise ribbon. Once the developer tab is available, go there and choose the leftmost option which says Visual Basic. Now you will see a panel in the left where you can double clock on the sheet name you are working on. This will open a empty code window. Here write the following code and save the file as a macro enabled workbook (extension will be .xlsb). 

```vb
Sub simple_hello()
Range("A2").Value = "Hello World!"
End Sub
```

Close the file, then opn it back again and chose the option (if shown) to enable macros. Now go to the Developer tab again and this time select the second option called Macros. Here you should see the macro that you just created. Select it and hit run! 

#### 1. Receiving input from the user and Showing output to the user
There are several ways in which a macro can show output to the user. Let's look at some ways of showing output:
```vb
'Method 1:
Range("A2").Value = "Hello"

'Method 2:
Worksheets("Sheet1").Range("B2").Value = "Hello"

'Method 3:
Worksheets(1).Range("C2").Value = "Hello"

'Method 4:
MsgBox "I added Hello in cell A2, B2 and C2"

'Method 5:
MsgBox "Hello " & Range("C5").Value & vbNewLine & "So you are " & Range("C6") & " years old!"
```

#### 2. Ability to store values in variables (usually of different kinds such as integers, floating points or character)
VBA allows 4 key types of variables: Integer, String, Double and Boolean
Integer is good for soring most numeric values, String is for character input and Boolean is for a 0/1 or yes/no type of data. Here are some examples:
```vb
'Integer:
Dim x As Integer
x = 6
Range("A1").Value = x

'String:
Dim book As String
book = "bible"
Range("A1").Value = book

'Double:
Dim x As Double
x = 5.5
MsgBox "value is " & x

'Boolean:
Dim continue As Boolean
continue = True
If continue = True Then MsgBox "Boolean variables are cool"
```

#### 3. A string of characters where you can store names, addresses, or any other kind of text
Key idea here is to learn how to manipulate string variables. There are a few common operations that we will focus on:
a. Joining strings
```vb
'Join Strings
Dim text1 As String, text2 As String
text1 = "Hi"
text2 = "Tim"
MsgBox text1 & " " & text2
```
b. Left/right or middle functions - To extract the leftmost/rightmost or middle characters from a string. 
```vb
Dim text As String
text = "example text"
MsgBox Left(text, 4)

'Just as left, we can also extract a substing from the right or middle
MsgBox Right("example text", 2)
MsgBox Mid("example text", 9, 2)
```
c. To get the length of a string, use Len.
```vb
MsgBox Len("example text")
```
d. To find the position of a substring in a string, use Instr.
```vb
MsgBox InStr("example text", "am")
```

#### 4. Some advance data types such as arrays which can store a series of regular variables (such as a series of integers)
Array's are a series of similar type of data stored together in one variable. Arrays can be one-dimentional or multi-dimentional. 
a. Following example shows how a one dimentional array works:
```vb
Dim Films(1 To 5) As String
Films(1) = "Lord of the Rings"
Films(2) = "Speed"
Films(3) = "Star Wars"
Films(4) = "The Godfather"
Films(5) = "Pulp Fiction"
MsgBox Films(4)
```
b. Following example shows how a two dimentional array works:
```vb
Dim Films(1 To 5, 1 To 2) As String
Dim i As Integer, j As Integer
For i = 1 To 5
    For j = 1 To 2
        Films(i, j) = Cells(i, j).Value
    Next j
Next i
MsgBox Films(4, 2)
```

#### 5. Ability to loop your code in the sense that you want to receive 10 names from a user, you will write the code for that 10 times, but just once and tell the computer to loop through it 10 times
VBA has several looping options (for, do-while, do-until). There are options of nesting (single, double, triple, ..) loops. 
a. Following example shows how a simple/single for loop works:
```vb
Dim i As Integer
For i = 1 To 6
    Cells(i, 1).Value = 100
Next i
```
b. Following example shows how a double for loop works:
```vb
Dim i As Integer, j As Integer
For i = 1 To 6
    For j = 1 To 2
        Cells(i, j).Value = 100
    Next j
Next i
```
c. Following example shows how a triple for loop works:
```vb
Dim c As Integer, i As Integer, j As Integer
For c = 1 To 3
    For i = 1 To 6
        For j = 1 To 2
            Worksheets(c).Cells(i, j).Value = 100
        Next j
    Next i
Next c
```
VBA also has a do-while loop. Following example shows how it works:
```vb
Dim i As Integer
i = 1
Do While i < 6
    Cells(i, 1).Value = 20
    i = i + 1
Loop
```
VBA also has a do-until loop. Following example shows how it works:
```vb
Dim i As Integer
i = 1
Do Until i > 6
    Cells(i, 1).Value = 20
    i = i + 1
Loop
```

#### 6. Ability to execute statements of code conditionally, for example if marks are more than 40 then the student passes else fails
a. If Then Statement - VBA has the option of an if statement, which executes a piece of code only if a specified condition is met. 
```vb
Dim score As Integer, result As String
score = Range("A1").Value

If score >= 60 Then result = "pass"
Range("B1").Value = result

Dim score As Integer, result As String
score = Range("A1").Value
```
b. If Else Statement - VBA has the option of an if-else statement, which executes a piece of code only if a specified condition is met, if not then it executes another piece of code. 
```vb
If score >= 60 Then
    result = "pass"
Else
    result = "fail"
End If

Range("B1").Value = result
```
c. If Else Statement - VBA has the option of an if-else statement, which executes a piece of code only if a specified condition is met, if not then it executes another piece of code. 
```vb
'Select Case
'First, declare two variables. One variable of type Integer named score and one variable of type String named result
Dim score As Integer, result As String
'We initialize the variable score with the value of cell A1
score = Range("A1").Value
'Add the Select Case structure
Select Case score
    Case Is >= 80
        result = "very good"
    Case Is >= 70
        result = "good"
    Case Is >= 60
        result = "sufficient"
    Case Else
        result = "insufficient"
End Select
'Write the value of the variable result to cell B1
Range("B1").Value = result
```

#### 7. Put your code in functions
VBA allows us to specify a function or a sub. The difference between the two is that funciton allows us to return a variable whereas a sub does not. 

a. Function - If you want Excel VBA to perform a task that returns a result, you can use a function. Place a function into a module (In the Visual Basic Editor, click Insert, Module). For example, the function with name Area.
```vb
'Explanation: This function has two arguments (of type Double) and a return type (the part after As also of type Double). You can use the name of the function (Area) in your code to indicate which result you want to return (here x * y).
Function Area(x As Double, y As Double) As Double
Area = x * y
End Function

'Explanation: The function returns a value so you have to 'catch' this value in your code. You can use another variable (z) for this. Next, you can add another value to this variable (if you want). Finally, display the value using a MsgBox.
Dim z As Double
z = Area(3, 5) + 2
MsgBox z
```
b. Sub - If you want Excel VBA to perform some actions, you can use a sub. 
```vb
Place a sub into a module (In the Visual Basic Editor, click Insert, Module). For example, the sub with name Area.
Sub Area(x As Double, y As Double)
MsgBox x * y
End Sub
'Explanation: This sub has two arguments (of type Double). It does not have a return type! You can refer to this sub (call the sub) from somewhere else in your code by simply using the name of the sub and giving a value for each argument.
'Call it using Area 3, 5
```

#### 8. Advanced data types that are formed through a combinaiton of one or more types of basic data types such as structures or classes
VBA Class allows us to create our own Object function in which we can add any kind of features, details of the command line, type of function. When we create Class in VBA, they act like totally an independent object function but they all are connected together. Detailed example of how to do this is out of the scope of this article. 

#### 9. Out of scope of this article. 

#### 10. Ability to comment your code so you can understand it when you revisit it some time later
We can tell VBA that a line of code is a comment by starting it with an single inverted comma. 
```vb
'this is a comment
```

Overall, Excel VBA is a powerful tool that can help users automate tasks, improve productivity, and enhance the functionality of Microsoft Excel. With its flexibility and ease of use, VBA is a valuable tool for users of all skill levels, from beginners to advanced programmers.

To close I will emphasize the importance of practicing in learning anything new. Persistence and trying out different combinations of these building blocks for solving easier problems first and more complex ones later on is the only way to become fluent.

Comments welcome!

{% include disqus_comments.html %}
