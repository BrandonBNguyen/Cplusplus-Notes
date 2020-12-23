# C++ Notes
Notes and programs created while learning C++. These were notes were created following the content and examples from [learncpp.com](https://www.learncpp.com/). 

## Table of Contents
1. [C++ Basics](#c-basics)
   1. [Compiling and Running Code](#compiling-and-running-code)
   2. [Instantiating and Assigning Variables](#instantiating-and-assigning-variables)
   3. [Output and Input with the Console](#output-and-input-with-the-console)
   4. [Literals, Operators, and Expressions](#literals-operators-and-expressions)
1. [Functions and Files](#functions-and-files)

## C++ Basics

### Compiling and Running Code
After installing Microsoft Visual Studio, I started by compiling and running *HelloWorld.cpp*, which simply outputs "Hello World" to the console.

*HelloWorld.cpp*
```cpp
// HelloWorld.cpp : This file contains the 'main' function. Program execution begins and ends there.
//

#include "pch.h"
#include <iostream>

int main()
{
    std::cout << "Hello World!\n";
}

// Run program: Ctrl + F5 or Debug > Start Without Debugging menu
// Debug program: F5 or Debug > Start Debugging menu

// Tips for Getting Started: 
//   1. Use the Solution Explorer window to add/manage files
//   2. Use the Team Explorer window to connect to source control
//   3. Use the Output window to see build output and other messages
//   4. Use the Error List window to view errors
//   5. Go to Project > Add New Item to create new code files, or Project > Add Existing Item to add existing code files 
//      to the project
//   6. In the future, to open this project again, go to File > Open > Project and select the .sln file
```
To compile code, use the hotkey `Ctrl + B`.

To run code (using debugger), use the hotkey `Ctrl + F5`.

### Instantiating and Assigning Variables
To create a variable, we need to define it starting by defining its type followed by the identifier for that variable, such as in the example below.
```cpp
int x; // Defines a variable named 'x' which we expect to hold an integer value.
```
To assign a variable a value, use the assignment operator (`=`) in a statement known as a **copy assignment**. To do this, after a variable has already been initialized, start with the variable identifier, followed by the assignment operator, followed by the value you wish to assign to the variable.
```cpp
int x; // Defines a variable named 'x' which we expect to hold an integer value.
x = 5; // Assign the value of 5 to the variable, x.
```
Initializing a variable and assigning it a value can be done in a single statement by using **copy initialization**. To do this, start with the variable type, followed by the variable's identifier, followed by the assignment operator, and lastly, followed by the value you wish to assign to that variable.
```cpp
int x = 5; // Defines a variable named 'x' which holds an integer value of 5.
```
Another common way of initializing and assigning a value to a variable is known as **direct initialization**. This is done by specifying the variable type, followed by the variable identifier, followed by parentheses containing the value you wish to assign to the variable.
```cpp
int x( 5 ); // Defines a variable named 'x' which holds an integer value of 5.
```
Since parenthesis-based direct initialization can't be used for all types of initialization, another common method for initialization and assignment is **list initialization**. This is very similar to to direct initialization only it uses curly braces instead of parentheses. Some additional features of list initialization to mention are that if no value is specified, **value initialization** will initialize the variable to some default value (usually 0 or empty). Additionally, if a value is used to initialize that would require conversion, before being valid, the statement will result in an error (which can be useful if you are expecting a value of the type specified for that variable).
```cpp
int width{ 5 };    // Direct list initialization, creating a variable named 'width' and setting its value to 5.
int width = { 5 }; // Copy list initialization, creating a variable named 'width' and setting its value to 5.

int width{}; // Value initialization (defaults to 0).

int width{ 4.5 }; // Will result in an error because you're attempting to set width (for which we expect an integer) to 4.5
                  // (which is a decimal and would require the type to be double).
```
Some best practices to follow are to favor direct list initialization whenever possible and to initialize your variables upon creation (preferably to perform instantiation and initialization in the same statement).

#### Note on Uninitialized Variables and Undefined Behaviour
A variable that is uninitialized is a variable that has not been given a value. Recall that when a variable is initialized, it is given a value at definition (the statement which defined the variable). Another way for a variable to acquire a value is by assignment in which it is given a value in some statement that occurs after definition. If a variable is declared without being given a value via initialization or assignment, it is considered **uninitialized**. Using an uninitialized variable can lead to **undefined behaviour**, because when a variable is declared but not initialized, your code will just use whatever value is already located at the location in memory used for that variable. This can lead to your program producing different results every run, producing incorrect results consistently, your program behaving inconsistently, your program crashing unexpectedly, and more. It's best to avoid this entirely by sticking to the best practice of always initializing your variables.

### Output and Input with the Console
Note that in order to receive keyboard input from the console and to output data to the console, we'll need to use the input/output library from the C++ standard library. To do so, be sure to include it by having `#include <iostream>` at the top of your code.

The variable `std::cout` (where *cout* means character output) is used to send data to the console to be printed as text. Use the insertion operator (`<<`) to send text to the console to be printed.
```cpp
#include <iostream>
// Include the standard input/output library to be able to output text to the console.

int main()
{
  std::cout << "Hello world!"; // Send the text "Hello world!" to the console to be printed.
  return 0; // Return 0 to indicate that main() has run successfully.
}
```
The value of variables can also be printed to the console using `std::cout`.
```cpp
int main()
{
  int x = 5;
  std::cout << x; // Will output '5' to the console.
  return 0;
}
```
The insertion operator can be used multiple times in a chain to combine multiple strings or combine strings and values of variables.
```cpp
int main()
{
  int x = 5;
  std::cout << "x =" << x; // Will output 'x = 5' to the console.
  return 0;
}
```
The `\n` character in a string will cause the console to print whatever comes after on a new line.
```cpp
int main()
{
    std::cout << "Hello World\n" << "My name is Brandon.";
    /* 
    *  Output:
    *  Hello World
    *  My name is Brandon.
    */ 
}
```
The variable `std::cin` is used to receive keyboard input from the console. The extraction operator (`>>`) is used to read the keyboard input from this variable and store it in another variable.
```cpp
int main()
{
  std::string user{ }; // Use direct list initialization to initialize the variable user containing an empty string.
  std::cout << "Hello, what is your name: "; // Output to the console prompting the user to type their name.
  std::cin >> user; // Initialize the name that the user typed to the variable named user.
  std::cout << "Hi, " << user << " my name is Jarvis."; // Print introduction addressing the user by name.
}
```
### Literals, Operators, and Expressions
**Literals** are fixed values that are inserted directly into the source code.
```cpp
std::cout << "Hello World!"  // "Hello World!" is a literal
int x{ 5 }                   // 5 is a literal
```
An **operator** is a symbol that denotes a specific operation to be performed. **Operands** are the input values upon which the operation is performed. *Unary*, *binary*, and *ternary* operators act on one, two, and three operands, respectively.
```cpp
x = -5  // The operator- is unary, acting only on 5 to make it -5.
y = 3 + 4 // The operator+ is binary, taking the left operand of 3 and 
          // the right operand of 4 and summing the two to produce 7.
```
Mathematical operators follow the same order of order of operations as they do in mathematics: parenthesis, exponents, multiplication/division, addition/subtraction.

**Expressions** are combinations of literals, variables, and explicit function calls that can be evaluated to a single result. You can use expressions wherever C++ expects a single value.
```cpp
int z{ (2 * 3) + 4 }; // (2 * 3) + 4 is the expression that evaluates 
                      // to 10 before being used as the value to 
                      // initialize z.
```
## Functions and Files

### Defining Functions
**Functions** are reusable sequences of statements designed to do a particular job.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU3MzY4NDE2MCwtMTM0MTAyMDYyOV19
-->