---
layout: post
title:  "[Building Blocks] of C++"
date:   2020-08-15 16:00:00 -0300
categories: building blocks, c++, cpp, learn programming
---
#### C++ is between 10 and 100 times faster than Python when doing any serious number crunching.

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

Lets dive right in and see how we can do these things in C++. 

Before we can begin to write a program in C++, we need to install [Dev-C++](https://www.bloodshed.net/). Once done, go ahead and open the IDE and try out the following code to see if everything is in order.  

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello World!";
    return 0;
}
```

As you noticed, unlike languages such as Python, R or Ruby, it takes more than a few statements just to display basic text to the user in C++. In the next section we will try to dismantle this code and understand the various components. Lets however cover a few important points:
* In C++ we need to end each line of code with a semi-colon ;
* The scope of statements is defined using curly brackets {}, unlike Python where the scope is defined through indentation
* All statements need to be within a function. Here we have included the statements in the main() function which is the first function that is executed during a compiler call. All other functions will be called from within this funciton. 

#### 1. Receiving input from the user and Showing output to the user
Following program shows output to the user. The include statement is used to call the iostream header file which is same as a python library. This header file provides information on basic programming routines including input and output constructs. The next is int main() which says that the main function will return an integer after execution. Within the main function we use cout<< to show the text to the user. The text is enclosed in double quotes "text". endl after the text tells the compiler to insert a new line in the output window. Finally we return 0 as the main function is supposed to return an integer. 0 signifies that everything was in order during the execution of the function. 
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "This is some text." << endl;
    return 0;
}
```
We can modify this program to accept input form the user. The cin>> statement allows us to receive input. The variable in which we store the received input needs to be defined beforehand. 
```cpp
#include <iostream>
using namespace std;

int main() {
    int age_ = 0;
    cout << "What is your age?";
    cin>>age_;
    cout << "So your age is: " << age_;
    return 0;
}
```

#### 2. Ability to store values in variables (usually of different kinds such as integers, floating points or character)
C++ is not dynamically typed - you need to type out the variable's name and data type before using it. 

Basic data types: In C++ we have several types of variables, lets take a look at the important ones:
```cpp
// Integer
int numberCats=5; 
long int numberCats=5; //long int can be used for storing large values

// Floating point numbers. These are numbers with significant digits after the decimal
float pi=3.1415926535; //pi=22/7

// Double
double dValue=3.1415926535; //for more significant digits we need to use other variable type than float
long double ldValue=3.1415926535;

// Boolean
bool bval=true; //boolean type is true or false; c++ uses 1 for true and 0 for false when outputting

// Character
char cval=55, cval2='7'; //takes exactly 1 byte of computer memory, char represents single characters from the ascii character set, 55 is the ascii code for 7, this is not the number 7 but the character 7

// String
string myname;
```

#### 3. A string of characters where you can store names, addresses, or any other kind of text
A string in C++ can be defined using the string keyword. It can be assigned usign the input from user or it can be assigned by providing text within double quotes "text". 
```cpp
string yourName;
cout << "\n\nwhat is your name? ";
cin >> yourName;
cout <<"\nnice to meet you "<<yourName<<endl<<endl;
```

#### 4. Some advance data types such as arrays which can store a series of regular variables (such as a series of integers)
Arrays are a series of variables stored together in one variable. Arrays can be one-dimentional or multi-dimentional. 
One-dimentional arrays:
```cpp
// Defining
int ar[3];

// Initializing the array
ar[0]=10;
ar[1]=20;
ar[2]=30;

// Supports indexing
cout<<ar[0]; // this will output the value stored at index 0, which is 10
```
Multi-dimentional arrays:
```cpp
// Defining
int mar[3][2] //multi-dim array

// Initializing the array
mar[3][2]={
    {34,188},
    {29,165},
    {29,160}
};

// Supports indexing
cout<<ar[0][0]; // this will output the value stored at row index 0 x column index 0, which is 34
```
Loops can be used to iterate over one-dimentional or multi-dimentional arrays. We will take a closer look at this in the next section. 

#### 5. Ability to loop your code in the sense that you want to receive 10 names from a user, you will write the code for that 10 times, but just once and tell the computer to loop through it 10 times
C++ has several looping options such as 'for', 'while' and 'do while'. There are also options of nesting (single, double, triple, ..) loops. 
a. The for loop
```cpp
// Syntax
for (i=0;i<10;i++){
    statements to do stuff
}

// iterate over elements of one-dimentional array
// practice - create an array with a table of 12
int t12[10];
for (int i=0;i<10;i++){
    t12[i]=12*(i+1);
}

// iterate over elements of two-dimentional array (concept of nesting - we will enclose a for loop within another for loop)
int mar[3][2]={
    {34,188},
    {29,165},
    {29,160}
}; //multi-dim array
cout<<"\nthis is a multi dimentional array: ";
for (int i=0;i<3;i++){ //3 rows in the array
    cout<<"\nrow "<<i+1<<":  ";
    for (int j=0;j<2;j++){ //2 columns in the array
        cout<<"col "<<j+1<<": "<<mar[i][j]<<", ";
    }
}
```
b. The While loop executes the same code again and again until a stop condition is met:
```cpp
// Syntax
int i=0;
while (i<10){
    code statements;
    i+=1;
}

// Example
int i=1;
cout<<"\n\nwhile loop - first 10 natural numbers"<<endl;
while (i<=10){
    cout<<i<<", ";
    i+=1; //same as i=i+1 or i+=1
}
```
c. The Do-While loop executes the same code again and again until a stop condition is met. The difference from while loop is that in do-while loop atleast the content of the loop is executed once before checking the condition. 
```cpp
// Syntax
int i=0;
do{
    code statements;
    i+=1;
}while (i<10)

// Example
//for example if you want the user to enter the password again and again until they enter the correct password
cout<<"\n\ndo-while loop\n";
i=1;
string pass="pass", pass2;
do{
    if(i!=1){
        cout<<"\naccess denied, try again";
    }
    cout<<"\nenter your password?";
    cin>>pass2;
    i=0;
}while(pass2 != pass);
cout<<"\npassword accepted\n\n";
```
C++ also provides the break and continue statements that allow us to alter the loops further. Following is their use:
  break jumps immidiately out of the loop. mostly used in while loops but can also be used in for loops
```cpp
// break statement example
cout<<"\nbreak statement\n";
for(int f=1;f<11;f++){
    if(f==5){
        break; //we break out of the loop when f==5, and dont execute the loop for f>=5
    }
    cout<<f<<", ";
}
```
  continue is similar to break, but just breaks out of the current iteration, but still continues running the next iterations
```cpp
// continue statement example
cout<<"\nbreak statement\n";
for(int f=1;f<11;f++){
    if(f==5){
        continue;
    }
    cout<<f<<", "; //this statement not executed for f==5
}
```

#### 6. Ability to execute statements of code conditionally, for example if marks are more than 40 then the student passes else fails
C++ provides if.., if..else.., and switch statements to apply conditional logic. Lets take a look at them:
a. The basic syntax for creating an if statement is:
```cpp
/////////// IF STATEMENT ////////////
string pass="password",pass2;
cout<<"\n\n--if statement capability--\n";
cout<<"\nenter password:";
cin>>pass2;
if (pass==pass2){
    cout<<"\npassword matches! you can enter!!";
} else{
    cout<<"\npassword doesnt match! begone!!";
}
```
b. The basic syntax for creating an if...else statement is: 
```cpp
/////////// IF-ELSE STATEMENT ////////////
int menuChoice=5;
cout<<"\n\n--if-else statement capability--\n";
cout<<"\n1.\tadd record";
cout<<"\n2.\tdelete record";
cout<<"\n3.\texit";
cout<<"\nwhat do you want to do?";
cin>>menuChoice;
if (menuChoice==1){
    cout<<"\nlets add some records!!";
} else if (menuChoice==2){
    cout<<"\nlets delete some records!!";
} else{
    cout<<"\nexiting! good-bye!!";
}
```
c. The basic syntax for creating a switch statement is: 
```cpp
/////////// SWITCH STATEMENT ////////////
int menuChoice2=5;
cout<<"\n\n--switch statement capability--\n";
cout<<"\n1.\tadd record";
cout<<"\n2.\tdelete record";
cout<<"\n3.\texit";
cout<<"\nwhat do you want to do?";
cin>>menuChoice2;
switch(menuChoice2){
case 1:
    cout<<"\nlets add some records!!";
    break;
case 2:
    cout<<"\nlets delete some records!!";
    break;
case 3:
    cout<<"\nexiting! good-bye!!";
    break;
default:
    cout<<"\n!!!!error!!!!";
}
```

#### 7. Put your code in functions
Functions allows us to create a block of code that can be executed many times without needing to it write it again. 
```cpp
// Following is an example case where we define a function that shows a menu to the user
int sub_menu(int choice) {
    switch(choice){
        case 1:
            cout<<"\nLets add a new record";
            break;
        case 2:
            cout<<"\nLets view an existing record";
            break;
        case 3:
            cout<<"\nLets delete an existing record";
            break;
        default:
            cout<<"\nExiting! Goodbye!!";
    }
    return 0;
}
```
We can call the function by its name:
```cpp
// lets say we are writing the main() and we want to call the funciton
// lines-of-code
sub_menu()
// lines-of-code
```

#### 8. Advanced data types that are formed through a combinaiton of one or more types of basic data types such as structures or classes
C++ allows user to create classes. These can be a combination of variables and functions that operate on those variables. Lets take a look at how we can define and use them. 
```cpp
// Create a Car class with some attributes
class Car {
  public:
    string brand;   
    string model;
    int year;
};

// Create an object of Car
Car carObj1;
carObj1.brand = "Mahindra";
carObj1.model = "Scorpio";
carObj1.year = 2020;

// Using the object
cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";
```

#### 9. Read file from a disk and save file to a disk
Lets see how to read and write a text file in an organized way. We use the fstream header file for importing the functions necessary to read/write files. 
```cpp
#include <fstream>

// read a text file
string line;
ifstream myfile ("file.txt");
if (myfile.is_open())
{
  while ( getline (myfile,line) )
  {
    cout << line << '\n';
  }
  myfile.close();
}
else cout << "Unable to open file"; 

// write a text file
ofstream myfile ("file.txt");
if (myfile.is_open())
{
  myfile << "This is a line.\n";
  myfile << "This is another line.\n";
  myfile.close();
}
else cout << "Unable to open file";
```

#### 10. Ability to comment your code so you can understand it when you revisit it some time later
We can tell C++ that a line of code is a comment as follows. 
```cpp
// this is a comment
```
We can tell that a multi-line block of text as follows. 
```cpp
/*
this
is
a
comment
block
*/
```

To close I will emphasize the importance of practicing in learning anything new. Persistence and trying out different combinations of these building blocks for solving easier problems first and more complex ones later on is the only way to become fluent.

Comments welcome!

{% include disqus.html %}
