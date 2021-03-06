# C++ Notes
Notes and programs created while learning C++. These were notes were created following the content and examples from [learncpp.com](https://www.learncpp.com/) and C++ Crash Course: A Fast-Paced Introductino by Josh Lospinoso. 

## Table of Contents
1. [C++ Basics](#c-basics)
   1. [Compiling and Running Code](#compiling-and-running-code)
   2. [Instantiating and Assigning Variables](#instantiating-and-assigning-variables)
   3. [Output and Input with the Console](#output-and-input-with-the-console)
   4. [Literals, Operators, and Expressions](#literals-operators-and-expressions)
2. [Functions](#functions)
	1. [Defining Functions](#defining-functions)
	2. [Return Values](#return-values)
	3. [Parameters and Arguments](#parameters-and-arguments)
	4. [Local Scope](#local-scope)
	5. [Using Functions Effectively](#using-functions-effectively)
3. [Formatting](#formatting)
	1. [Whitespace and Basic Formatting](#whitespace-and-basic-formatting)
	2. [Forward Declarations and Definitions](#forward-declarations-and-definitions)
	3. [Separating a Program Across Multiple Files](#separating-a-program-across-multiple-files)
	4. [Naming Collisions and Namespaces](#naming-collisions-and-namespaces)
	5. [Preprocessor and Directives](#preprocessor-and-directives)
	6. [Header Files](#header-files)
4. [Data Types](#data-types)
	1. [Integer Types](#integer-types)
	2. [Floating-Point Types](#floating-point-types)
	3. [Character Types](#character-types)
	4. [Boolean Types](#boolean-types)
	5. [The `size_t` type](#the-size_t-type)
	6. [Arrays](#arrays)
	7. [Strings](#strings)
	8. [Enumerations](#enumerations)
	9. [Classes](#classes)
		1. [Plain-Old-Data (POD) Classes](#plain-old-data-pod-classes)
		2. [Unions](#unions)
		3. [Fully-Featured Classes](#fully-featured-classes)
			1. [Access Control](#access-control)
			2. [Constructors](#constructors)
			3. [Destructors](#destructors)
			4. [Copy Constructors](#copy-constructors)
			5. [Copy Assignment Operators](#copy-assignment-operators)
			6. [Default Copy](#default-copy)
			7. [Delete Copy](#delete-copy)
			8. [Move Constructors and Move Assignment Operators](#move-constructors-and-move-assignment-operators)
5. [Control Flow](#control-flow)
	1. [If Statements](#if-statements)
	2. [Switch Statements](#switch-statements)
	3. [For Loops](#for-loops)
	4. [Try-Catch Blocks](#try-catch-blocks)
		1. [Exceptions](#exceptions)
		2. [`noexcept`](#noexcept)
6. [Reference Types](#reference-types)
	1. [Pointers](#pointers)
	2. [References](#references)
	3. [`this` Pointers](#this-pointers)
	4. [`const`](#const)
	5. [`auto` Type Deduction](#auto-type-deduction)
7. [Object Life Cycle](#object-life-cycle)
	1. [Automatic Storage](#automatic-storage)
	2. [Static Storage](#static-storage)
	3. [Dynamic Storage](#dynamic-storage)
8. [Runtime Polymorphism](#runtime-polymorphism)
	1. [Virtual Methods](#virtual-methods)
	2. [Pure-Virtual Classes](#pure-virtual-classes)
		1. [Virtual Destructors](#virtual-destructors)
	3. [Implementing Interfaces](#implementing-interfaces)

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
    std::string user{ };  // Use direct list initialization to initialize the variable user
                          // containing an empty string.
    std::cout << "Hello, what is your name: ";  // Output to the console prompting the user to
                                                // type their name.
    std::cin >> user;  // Initialize the name that the user typed to the variable named user.
    std::cout << "Hi, " << user << " my name is Jarvis.";  // Print introduction addressing
                                                           // the user by name.
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
## Functions

### Defining Functions
**Functions** are reusable sequences of statements designed to do a particular job. When executing statements inside a function, the program may encounter a **function call**, which tells the CPU to interrupt the current function, execute another function, and then return. The function initiating the function call is referred to as the **caller** and the function being initiated is referred to as the **callee**.

The syntax of a function is as follows, starting with the return-type, followed by the function identifier, followed by parentheses, and followed by brackets containing the code, known as the **function body**, that will be run when that function is called.

#### Function Format
```
return-type identifier()
{
	// code to be executed
}
```
Note that functions cannot be defined within other functions, unlike in Python.
```cpp
#include <iostream>

int  main()
{
	int  foo()  // Illegal: this function is nested inside function main()
	{
		std::cout  <<  "foo!\n";
		return  0;
	}

	foo();  // function call to foo()
	return  0;
}
```

### Return Values
When defining a function, we have to define the **return-type**. Once that is defined, we know what type of value to expect when a function is executed. Therefore, in the function body, we expect a **return statement** followed by a value of the same type as the function's return-type.
```cpp
int foo()
{
	return 2;
}

double bar()
{
	return 0.2;
}
```
Wherever we see a function call, we can treat it as an expression with the same type as the function's return-type.
```cpp
int main()
{
	std::cout << "foo() returns " << foo();  // foo() can be treated as an expression that
	return 0;                                // evaluates to an integer.
}
```
```
foo() returns 2
```
The return-type **void** is used when a function doesn't need to return a value. 

Note that failing to return a value in a function for which we expect a non-void return value will lead to undefined behavior. Therefore, it's best practice to always explicitly return a value for non-void return-type functions.

Notice that `main()` is a function with an integer return-type. The integer returned from `main()` is called the **status code**, and is used to indicate whether or not the program ran successfully. Non-zero status codes generally indicate a failure of some sort.

The C++ standard library defines the meaning of 3 status codes: `0`, `EXIT_SUCCESS`, and `EXIT_FAILURE`. To use them, be sure to include `<cstdlib>` in your code. `EXIT_SUCCESSS` is used to indicate that the program terminated successfully and `EXIT_FAILURE` is used to indicate that the program did not execute successfully.
```cpp
#include <cstdlib> // for EXIT_SUCCESS and EXIT_FAILURE

int  main()
{
	return  EXIT_SUCCESS;
}
```
Once a function executes a return statement, the called function will stop and the code will continue from the callee function.
```cpp
#include <iostream>

int foo()
{
    return 2;
    std::cout << "last line of foo()";	// This line will not be executed because it is after
}                                       // the execution of the return statement.

int main()
{
    std::cout << "foo() returns " << foo();
}
```
A good guideline to follow when determining whether a segment of code should be converted into a function is to **DRY**, which stands for **don't repeat yourself**. If you find yourself reusing the same segment of code, it can probably be turned into a function for simplicity.

### Parameters and Arguments
**Function parameters** are variables used in a function that are initialized with a value provided by the caller of the function and are specified in the parentheses of the function definition. You can specify multiple 
```cpp
int multiplier(int x, int y)	// The function has two parameters: x and y
{                               // both of which the function expects to be 
    return x * y;               // integers.
}
```
An **argument** is the value passed from the caller into the function when the function call is made.
```cpp
int main()
{
    // 2 and 3 are the arguments of the function call of multiplier().
    std::cout << "foo() returns " << doubler(2, 3);  
}
```
Note that function arguments may not always be evaluated left to right. If several parameters consist of function outputs, ensure that the order in which they are called doesn't matter. If it does matter, run the functions separately and define their outputs as variables in the correct order before passing them in as arguments.
```cpp
func(a(), b()); // a() or b() may be called first.
```
```cpp
a_var = a();	
b_var = b();
func(a(), b());	//a() will be called before b().
```

### Local Scope
Function parameters and variables defined within a function body are called **local variables**.  The **lifetime** of local variables is from the variable's point of instantiation to the end of the function execution. A variable is considered **in scope** if the identifier can be accessed and is considered **out of scope** if it cannot be accessed.
```cpp
int main()
{
	// Neither x nor y are in scope at this line.
	int x = 3;	// x is in scope from this line until the end brace of main().
	x = 2 * x;	// y is not in the scope.

	int y = 2;	// y is in scope from this line until the end brace of main().
	y = 2 * y;	// x is also in the scope here.
}	// x and y leave the scope at this line.
```
Another thing to consider when determining a variable's scope is **functional separation**. When a function is called from another function, the called function will only work with variables within its local scope. That means the called function can share the same identifiers as those present in the caller function and there will be no issues, because when statements are being executed in the called function, they will only reference variables local to that called function.
```cpp
int double_and_add(int x, int y)
{
	x = 2 * x;		// Although x is an identifier in main, this reassignment won't change
	y = 2 * y;		// the value of x from main. Same for y.
	return x + y;
}

int main()
{
	int x = 3;
	int y = 4;
	int z = double_and_add(x, y);
	std::cout << "x: " << x << "\n";
	std::cout << "y: " << y << "\n";
	std::cout << "z: " << z << "\n";
}
```
```
x: 3
y: 4
z: 14
```
As a best practice, local variables should be defined as close to their first use as possible.
```cpp
int  main()
{
	std::cout  <<  "Enter an integer: ";
	int  x{};  // x defined here
	std::cin  >>  x;  // and used here

	std::cout  <<  "Enter another integer: ";
	int  y{};  // y defined here
	std::cin  >>  y;  // and used here

	int  sum{  x  +  y  };  // sum defined here
	std::cout  <<  "The sum is: "  <<  sum  <<  '\n';  // and used here
	
	return  0;
}
```

### Using Functions Effectively
The general guidelines for determining when to refactor a set of code into a function and establishing the structure of the function is as follows.

 - Statements that reappear multiple times within your code should be made into a function (DRY: don't repeat yourself). 
 - Code that has a well defined input and output are good candidates to be turned into a function, especially if the code is complex.
 - A function should generally perform one, and only one, task.
 - When a function becomes too long, it could be advantageous to split that function into multiple, smaller sub-functions.
 
 The advantages to separating your code into functions in accordance with the above guidelines is as follows.
 
 - Organization: Separating code into functions makes it more readable, less complex, and more manageable.
 - Reusability: Functions can be reused in your code, reducing copy/paste errors and duplicate code.
 - Testing: By reducing code redundancy, there is less code to test. By testing and ensuring that a function works, we can be confident that it will perform properly at every instance that it is called.
 - Extensibility: Functions can be extended to handle cases that we didn't initially account for by modifying just the function body.
 - Abstraction: You only need to know a function's name, its inputs, its outputs, and where it's located to use the function effectively, lowering the amount of knowledge by other people to effectively use a function.

## Formatting

### Whitespace and Basic Formatting
Characters used for formatting purposes are known as **whitespace**. This mostly consists of spaces, tabs, and newlines. C++ is a whitespace-independent language, meaning the compiler ignores the whitespace when compiling code (except for those within text literals). As a result, the following functions, despite being formatted differently, all perform the same action.
```cpp
int  add(int  x,  int  y)  {  return  x  +  y;  }
```
```cpp
int  add(int  x,  int  y)  {
return  x  +  y;  }
```
```cpp
int  add(int  x,  int  y)
{  return  x  +  y;  }
```
```cpp
int  add(int  x,  int  y)
{
return  x  +  y;
}
```
Within text literals, newlines are not allowed.
```cpp
std::cout << "Hello
World!"; //not allowed
```
Text literals separated by nothing but whitespace will be concatenated.
```cpp
std::cout << "Hello "
"World!"; // "Hello " and "World!" will be concatenated to "Hello World!"
```
```
Hello World!
```
Because C++ is a whitespace-independent language, convention generally dictates following styles that produce the most readable code and provide the most consistency.

Using tabs or spaces comes down to personal preference, although it would probably be best to set an IDE to produce a certain number of spaces upon pressing tab to ensure that comments and code are still readable when viewed by different text editors.

There are two generally accepted styles for function braces. The Google C++ style guide recommends having the open curly brace in the same line as the statement defining the function. This reduces vertical whitespace and allows you to fit more code on the screen.
```cpp
int main() {         // Google C++ style guide has open curly brace in the same
    do_something();  // line as function header.
}
```
The alternative is to have the open brace on its own line. This makes the code more readable and makes it easier to catch brace mismatch errors.
```cpp
int main()
{                    // Open curly brace on its own line.
    do_something();
}
```
Each statement within a curly brace should be on its own line that is one indentation level below that containing the curly brace.
```cpp
int main()
{
    do_something();  // This statement is one indentation beyond that of the
}                    // curly braces.
```
Lines should not be longer than 80 characters. If a line is longer, split the line, in a reasonable place, into multiple lines. Common conventions include having the following line at one indentation level beyond that of the initial line or aligning the following line with some similar/reasonable code in the preceding line.
```cpp
int main()
{
    std::cout << "What the fuck did you just fucking say about me, you little" 
        "bitch? I'll have you know I graduated top of my class.";
        // Having the continuing line at one indentation beyond the initial.
}
```
```cpp
int main()
{
    std::cout << "What the fuck did you just fucking say about me, you little" 
                 "bitch? I'll have you know I graduated top of my class.";
                 // Aligning the continuing line with the beginning of the text
                 // from the preceding line.
}
```
If splitting a line at a place containing an operator, the operator should start at the beginning of the following line.
```cpp
    std::cout << 3 * 4 * 5
                 + 5 * 6 * 7
                 + 8 * 9 * 10;
```
When defining multiple variables or commenting on multiple lines, whitespace can be used to align the assignment operator or the beginning of the comments to make things more readable.
```cpp
alpha = 1  // Defining a constant, alpha
d_theta_dt = 4  // Defining the derivative of theta.
```
This is more readable:
```cpp
alpha      = 1  // Defining a constant, alpha
d_theta_dt = 4  // Defining the derivative of theta.
```
It can be helpful to separate blocks of code with whitespace to promote readability.
```cpp
// cout lives in the iostream library
std::cout  <<  "Hello world!\n";
// these comments make the code hard to read
std::cout  <<  "It is very nice to meet you!\n";
// especially when all bunched together
std::cout  <<  "Yeah!\n";
```
This is more readable:
```cpp
// cout lives in the iostream library
std::cout  <<  "Hello world!\n";

// these comments make the code hard to read
std::cout  <<  "It is very nice to meet you!\n";

// especially when all bunched together
std::cout  <<  "Yeah!\n";
```

### Forward Declarations and Definitions
Consider the following code.
```cpp
#include <iostream>

int  main()
{
    std::cout  <<  "The sum of 3 and 4 is: "  <<  add(3,  4)  <<  '\n';
    return  0;
}

int  add(int  x,  int  y)
{
    return  x  +  y;
}
```
If you attempt to compile this code, it will result in the following error.
```
error C3861: 'add': identifier not found
```
This is because the code starts with `main()` and encounters the first statement where a call to the function `add()`. The issue is that `add()` has not been defined yet, because the code started with `main()` and add isn't defined until after `main()`. One simple fix to this is to simply move the function definition for `add()` before the function definition for `main()`.
```cpp
#include <iostream>

int  add(int  x,  int  y)
{
    return  x  +  y;
}  // Since add() is defined before main(), our code will compile and run.

int  main()
{
    std::cout  <<  "The sum of 3 and 4 is: "  <<  add(3,  4)  <<  '\n';
    return  0;
}
```
Another solution is to use a **forward declaration**, which is used to declare a function, object, variable, etc. before it is defined. The forward declaration for a function is called a **function prototype** and consists of the function header followed by a semicolon. This is especially useful if we have several functions that rely on one another.
```cpp
#include <iostream>

int  add(int  x,  int  y); // This function prototype is the forward
                           // declaration for our function, add().
int  main()
{
    std::cout  <<  "The sum of 3 and 4 is: "  <<  add(3,  4)  <<  '\n';
    return  0;  // When this is ran, add() will have already been declared
}               // and is defined in the lines below.

int  add(int  x,  int  y)
{
    return  x  +  y;
}
```
Note that a function with the same identifier and different number/type of parameters is treated as an entirely different function. The following example has two functions with the identifier `add`, but will compile and execute without error because one function definition has two integer parameters and the other has three integer parameters.
```cpp
#include <iostream>

int add(int x, int y);
int add(int x, int y, int z);

int  main()
{
    std::cout << "The sum of 3 and 4 is: " << add(3, 4) << '\n';
    std::cout << "The sum of 3, 4, and 5 is: " << add(3, 4, 5) << '\n';
    return  0;
}

int  add(int  x, int  y)
{
    return  x + y;
}

int  add(int  x, int  y, int z)
{
    return  x + y + z;
}
```
```
The sum of 3 and 4 is: 7
The sum of 3, 4, and 5 is: 12
```

Note the **one definition rule**:

 1. Within a given file, a function, object, type, or template can only have one definition.
 2. Within a given program (which can span over multiple files), an object or normal function can have only one definition.
 3. Types, templates, inline functions, and variables are allowed to have identical definitions in multiple files. 

### Separating a Program Across Multiple Files
For organization and reusability, it may be a good idea to split your codes into multiple files. Consider the following example. 
```cpp
#include <iostream>

int  add(int  x,  int  y)
{
    return  x  +  y;
}  // Since add() is defined before main(), our code will compile and run.

int  main()
{
    std::cout  <<  "The sum of 3 and 4 is: "  <<  add(3,  4)  <<  '\n';
    return  0;
}
```
Let's say we want to move `add()` into another file entitled *add.cpp*. Start by right clicking on the project on the right side of the Visual Studio IDE, >> Add >> New Item. Create a new .cpp file and move the function into that file. In your main file, use a forward declaration to ensure that your program knows to look for and define the `add()` function. 

**add.cpp**
```cpp
int  add(int  x, int  y)
{
    return  x + y;
}
```
**main.cpp**
```cpp
#include <iostream>

int add(int x, int y);

int  main()
{
    std::cout << "The sum of 3 and 4 is: " << add(3, 4) << '\n';
    return  0;
}
```
Compiling and running will produce the following, expected, output.
```
The sum of 3 and 4 is: 7
```

### Naming Collisions and Namespaces

#### Naming Collision
A **naming collision** is a type of error that occurs when two identical identifiers are introduced into the same program such that the compiler is unable to differentiate the two.

Consider the following two files that exist in the same directory:

**a.cpp**
```cpp
#include <iostream>

void  myFcn(int  x)
{
    std::cout  <<  x;
}
```

**main.cpp**
```cpp
#include <iostream>

void  myFcn(int  x)
{
    std::cout  <<  2  *  x;
}

int  main()
{
    return  0;
}
```
The compiler will be able to compile both *a.cpp* and *main.cpp* just fine but when the linker attempts to execute, it'll find conflicting definitions for `myFcn()` and result in an error.

Naming collisions are often introduced in separate files of a program or in the same file often when using `#include` and resulting in there being multiple definitions of a function or global variable.

#### Namespace
A **namespace** is a region that allows you to declare names inside for the purpose of disambiguation. This ensures that any identifier declared inside the namespace won't be mistaken for another identical name outside the scope of the namespace.

Any name defined outside of a function, class, and namespace is considered part of the **global namespace**. In the above example, both `main()` and `myFcn()` existed inside the global namespace, however because of conflicting definitions within that namespace, we received an error.

`std` in `std::cout` and `std::cin` is the name of the namespace used for the C++ standard library. This ensures that the identifiers of new code doesn't conflict with the existing identifiers for those in the C++ standard library and result in an error.

Consider that in `std::cout` and `std::cin`, when we want to access the `cout` and `cin` operators, we started with the name of the namespace, followed by the **scope resolution operator** (`::`), followed by the names of the variable or functions within that namespace. In this way, we explicitly tell the program to access this specific variable in this specific namespace.

An alternative (although less preferred) method of accessing variables within a namespace is by using a *using directive* statement. This allows access to all the names within that namespace without having to explicitly specify the namespace every time, effectively importing all names in that namespace into the global namespace. However, this practice defeats the purpose of using namespaces in the first place, and is not preferred.

```cpp
#include <iostream>

using  namespace  std;  // this is a using directive telling the compiler to check the std
                        // namespace when resolving identifiers with no prefix

int  main()
{
    cout  <<  "Hello world!";  // cout has no prefix, so the compiler will check to see
    // if cout is defined locally or in namespace std
    return  0;
}
```

### Preprocessor and Directives
Prior to compilation, your code is run through a process called **translation**, which involves a **preprocessor**, which can be thought of as a program that manipulates the text in each code file. **Preprocessor directives** are instructions that start with the `#` symbol and end with a newline. These instructions tell the preprocessor to perform some text manipulation on the code. Note that directives have their own syntax and do not follow C++ syntax.

#### Include
The `#include` directive replaces that line with the contents of the included file. The included contents are then preprocessed and the rest of your file are preprocessed and compiled.

```cpp
#include <iostream>  // Preprocessed contents of file entitled `iostream` are placed here. 

int  main()
{
    std::cout  <<  "Hello, world!";
    return  0;
}
```

#### Macro Defines
The `#define` directive can be used to create a **macro**, which is a rule that defines how input text is converted into replacement output text.

Object-like macros are created by starting with `#define`, followed by the macro identifier, and potentially followed by substitution text. By convention, the macro identifier is typically typed in all caps.
```cpp
#define identifier                    // Without substitution text
#define identifier substitution_text  // With substitution text
```

##### Object-Like Macros with Substitution Text
When the preprocessor encounters a directive with substitution text, it directly replaces future occurrences of the macro identifier with the substitution text.
```cpp
#include <iostream>

#define MY_NAME "Brandon"  // Object-like macro with substitution text. Wherever MY_NAME is
                           // is present in the code after this line, it will be replaced with 
int main()                 // "Brandon".
{
    std::cout << "My name is " << MY_NAME;
    return 0;
}
```
After preprocessing:
```cpp
// Preprocessed contents of iostream...

int main()
{
    std::cout << "My name is " << "Brandon";  // MY_NAME is detected and the text is replaced
    return 0;                                 // with "Brandon".
}
```

##### Object-Like Macros without Substitution Text
Object-like macros such as the one below are defined without any substitution text and can be used for things such as conditional compilation. They are not used for text substitution like those with text following the identifier.

#### Conditional Compilation
Conditional compilation determines whether specific segments of code will be compiled or not. Using the directives `#ifdef`, `#ifndef`, and `#endif`, you can specify code blocks that will only be compiled if a certain macro is defined. By convention, the directives for the conditional blocks within a function are written at the same indentation level as the function header.
```cpp
#include <iostream>

#define PRINT_AARON  // PRINT_AARON is now defined such that all code within conditional
                     // directive blocks seeing if PRINT_AARON is defined will run.
int main()
{
#ifdef PRINT_BRANDON  // Since PRINT_BRANDON is not defined, we do not expect this to run.
    std::cout << "My name is Brandon.";
#endif

#ifdef PRINT_AARON  // Since PRINT_AARON is defined, we do expect this to run.
    std::cout << "My name is Aaron.";
#endif
    
    return 0;
}
```
After preprocessing:
```cpp
/ Preprocessed contents of iostream...

int main()
{
    std::cout << "My name is Aaron.";
    return 0;
}
```
Console output:
```
My name is Aaron.
```
The directive, `#ifdef 0`, will evaluate to False and run without code contained within that conditional block. This has the same effect as commenting out the code within the conditional block.
```cpp
int main()
{
#ifdef 0
    std::cout << "This will not print."  // This line will not print.
#endif
    
    return 0;
}
```

#### Scope of Directives
Directives are only within that file so when defining a macro, it will only exist for a code within the same file as that macro. Additionally, they do not need to be called to take effect like an ordinary variable or function definition as the preprocessor doesn't understand C++ syntax. 

Also note that directives only apply to the code in the lines following the directive.
```cpp
#include <iostream>

#define PRINT_AARON  // PRINT_AARON is now defined such that all code within conditional
                     // directive blocks seeing if PRINT_AARON is defined will run.
int main()
{
#ifdef PRINT_BRANDON  // Since PRINT_BRANDON is not defined, we do not expect this to run.
    std::cout << "My name is Brandon.";
#endif

#ifdef PRINT_AARON  // Since PRINT_AARON is defined, we do expect this to run.
    std::cout << "My name is Aaron.";
#endif

#define PRINT_BRANDON  // PRINT_BRANDON is now defined such that all code within conditional  
                       // directive blocks seeing if PRINT_BRANDON is defined will run.

#ifdef PRINT_BRANDON  // Since PRINT_BRANDON is now defined, so we do expect this to run.
    std::cout << "My name is Brandon.";
#endif

    return 0;
}
```

### Header Files

Header files are used to propagate declarations to code files and usually end with a .h extension.

#### Using Header Files

Consider the example below that prints `Hello, World!` to the console.

```cpp
#include <iostream>

int main()
{
	std::cout << "Hello, world!";
	return 0;
}
```

`std::cout` is able to be used because it has been forward declared in the `iostream` header file after `#include <iostream>`. 

#### Writing Header Files

Header files typically only contain function and variable declarations and not their definitions. This is done to ensure that the *one definition rule* isn't violated. For example, a header file containing a function definition could result in a collision with the function declaration in a .cpp file somewhere.

Header files contain two parts:

 1. A header guard
 2. The forward declaration for all identifiers

Header files are usually paired with a code file and provide the forward declarations for that corresponding code file. It's best practice to name the header file the same name as its paired code file (e.g. `add.h` would contain the forward declarations for `add.cpp`).

Consider the following example from [3.3](#separating-a-program-across-multiple-files) consisting of a main code file, `main.cpp`, and another file, `add.cpp`, where `main.cpp` uses a function declared in `add.cpp`. 

**add.cpp**
```cpp
int  add(int  x, int  y)
{
    return  x + y;
}
```
**main.cpp**
```cpp
#include <iostream>

int add(int x, int y);

int  main()
{
    std::cout << "The sum of 3 and 4 is: " << add(3, 4) << '\n';
    return  0;
}
```

Consider that for this example, instead of including the forward declaration for `add()` in `main.cpp`, we want to use a header file to forward declare `add()`. We would create a header file named `add.h` (since we're forward declaring a function defined in `add.cpp`) and simply include the forward declaration in there instead of in `main.cpp`. In `main.cpp`, we would need to include that header file using `#include` followed by the header file name in quotations (`#include "add.h"`) in this case.

**add.h**
```cpp
int add(int x, int y);
```
**add.cpp**
```cpp
int  add(int  x, int  y)
{
    return  x + y;
}
```
**main.cpp**
```cpp
#include <iostream>
#include "add.h"

int  main()
{
    std::cout << "The sum of 3 and 4 is: " << add(3, 4) << '\n';
    return  0;
}
```

It's good practice to write a header file for a source file even if the functions in that source file are not being used immediately to promote forward compatibility.

`#include`'s that specify a header file with angled brackets (`<>`) instead of double quotations (`""`) will search for header files in a specified `include directories`, which are configured as part of a project or IDE's settings. Those specified with double quotations will search for header files in the current directory or specified search directory (specified by the IDE project settings) first before searching the `include directories`.

Although header files can also include other header files (known as transitive includes) this is not best practice as these includes become implicit rather than explicit when your header file is included somewhere.

Best practice for order of `#include` statements is first user-defined headers, followed by 3rd party headers, followed by standard library headers. Each section should be sorted alphabetically.

#### Header Guards

## Data Types

### Integer Types

Integer types are used to store whole numbers. There are four main integer types: `short`, `int`, `long` and `long long`. These each can either be `signed`, meaning positive integers, negative integers and zero can be stored, or `unsigned`, meaning only non-negative integers can be stored. The difference between these data types is the amount of memory required and the range of values they can store. The greater the range of values, the greater the memory required. The range of each type, `signed` and `unsigned` is listed in the table below.

| Type | Range |
|--|--|
| `signed short` | -32,768 to 32,767 |
| `unsigned short` | 0 to 65,535 |
| `signed int` | -2,147,483,648 to 2,147,483,647 |
| `unsigned int` | 0 to 4,294,967,295 |
| `signed long` | -2,147,483,648 to 2,147,483,647 |
| `unsigned long` | 0 to 4,294,967,295 |
| `signed long long` | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| `unsigned long long` | 0 to 18,446,744,073,709,551,615 |

### Floating-Point Types

Floating-point types are used to store numbers that contain decimal or fractional components. There are three floating-point types: `float`, `double`, and `long double`. `float` has 4 bytes of precision while `double` and `long double` have 8 bytes of precision. The higher the precision, the more accurate the numerical representation but the more memory required. For general use, `double` is usually sufficient.

Floating-points variables can be initialized using scientific notation.

```cpp
double avogadros_number = 6.0221409e23;
```

### Character Types

Character types are used to store a single character. There are four types: `char`, `char16_t`, `char32_t`, and `wchar_t`. `char` can either be `signed` or `unsigned`. 

 - `char`: The default type. Used for 1 byte character sets such as ASCII.
 - `char16_t`: Used for 2-byte character sets such as UTF-16.
 - `char32_t`: Used for 4-byte character sets such as UTF-32.

A character literal is declared by enclosing the specific character within a set of single quotations ('). 

```cpp
char favorite_letter = 'e';
```

### Boolean Types

Booleans use the `bool` type and simply store `true` or `false`. They are usually the result of some sort of comparison expression. 

```cpp
bool name_is_brandon = true;
```

#### Comparison Operators

Common operators that are used to compare the values of different variables are listed below.

| Operation| Operator |
|--|--|
| Equality | `==` |
| Inequality | `!=` |
| Greater Than| `>` |
| Less Than| `<` |
| Greater Than or Equal To| `>=` |
| Less Than or Equal To| `<=` |

```cpp
printf("69 >= 429 evaluates to: %d", 69 >= 420); // Evaluates to false
```

#### Logical Operators

Common operators used to evaluate Boolean logic on `bool` types are listed below.

| Operation | Operator |
|--|--|
| NOT | `!` |
| AND | `&&` |
| OR | `||` |

```cpp
bool i_am_lactose = true;
bool food_has_lactose = true;
bool i_can_eat_food = food_has_lactose && !i_am_lactose;

printf("I can eat the food?: %d", i_can_eat_food); // Evaluates to false 
```

### The `size_t` Type

The `size_t` type is used to encode the size of objects. The maximum value it can represent is such that it's sufficient to represent the maximum size of all objects. It is commonly used as the type of the iterator variable when iterating through arrays.

### Arrays

Arrays are used to store multiple elements of the same type. They are initialized in the same way you declare an ordinary variable of some type except following the identifier are brackets containing the number of elements in the array. **Note that in doing it this way, each element in the array is uninitialized.**

```cpp
int my_numbers[100]; // Creates an array that can store 100 int values.
```

Another way to initialize an array is by equating it to a  comma, separated list of values contained within a curly braces and neglecting the number inside the brackets.

```cpp
int my_numbers[] = {1, 3, 2, 5, 1};
```

A specific element in an array is accessed by its index (starting at 0). Use the identifier, followed by brackets containing the index of the value in the array you wish to access.

```cpp
int value = my_numbers[1]; // Retrieves the second value of my_numbers
printf("The value is %d", value); // Will print out `The value is 3`
```

Using brace initialization, you can create an array and initialize all its elements to 0. To do this, declare an array with the number of elements within the brackets and follow it with a set of empty braces. If you use a set of braces containing values, it'll initialize the first few elements of the array to those and all remaining, undefined elements in the array to 0.

```cpp
int zeros[100]{}; // Creates a 100-element array where all elements are 0.
int mostly_zeros[100]{ 1, 2, 3 }; // Creates a 100-element array where the first
                                  // three elements are defined and the rest are
                                  // 0.
```

A note that arrays created must have a known size beforehand at compile time (in other words you can't use a non-constant variable to define the size of an array). To create arrays of custom sizes determined at runtime, see the section on [dynamic arrays](#dynamic-arrays).

### Strings

Strings can be thought of as an array of characters. To declare a string literal, enclose the text you wish to convert into a string within a set of double quotations (").

```cpp
char navy_seal_copy_pasta[] = "I'll have you know I graduated top of my class in the Navy Seals.";
```
When declaring especially long strings, it is okay to separate them by only whitespace. This can be especially useful for separating strings into multiple lines.

```cpp
char expression[] = "Roses are red, "
     "I forget how this goes, "
     "I think there's something "
     "up your nose.";
```

Strings can also be declared by equating a char pointer to the string. See the section on pointers for more information.

```cpp
char* name = "Brandon";
```

### Enumerations

Enumerations are a type of user-defined type that you can set to a set of predefined values, which is great for modeling categorical concepts. The categories for an enumeration are declared by `enum class` followed by the name for the user-defined type followed by curly brackets containing a comma, separated list of categories that a variable of that type can be set to.

```cpp
enum class Language {
	English,
	Spanish,
	Vietnamese,
	Cantonese,
	Mandarin
};
```

To assign an enumeration variable to a value, start with the type, followed by the variable identifier, followed by an assignment operator, followed by the category from within the namespace of the type using the `::`.

```cpp
Language my_language = Language::English;
```

This can be especially useful when using if statements with an  equality operator or switch statements.

### Classes

*Classes* are user-defined types that contain data and functions.

#### Plain-Old-Data (POD) Classes

*Plain-old-data (POD) classes* are a simple type of class that only stores data. They can store data of different types and can be used to represent something. They are defined by the keyword `struct` followed by the identifier for the class, followed by a set of curly braces initializing the *members*, which are the different elements of data stored by the class.

```cpp
#include <string>
#include <iostream>

struct School {
	std::string name;
	std::string country;
	int student_population;
	double latitude;
	double longitude;
	bool public_institution;
}; // Note that the definition must be proceeded by a semicolon.
```

Members are accessed by using the dot operator (`.`).

```cpp
int main() {
	School UCSD;
	UCSD.name = "University of California, San Diego";
	UCSD.country = "US";
	UCSD.student_population = 35'821;
	UCSD.latitude = 32.8328;
	UCSD.longitude = -117.2713;
	UCSD.public_institution = true;

	std::cout << "Name: \t\t" << UCSD.name << "\n";
	std::cout << "Country: \t" << UCSD.country << "\n";
	std::cout << "Students: \t" << UCSD.student_population << "\n";
	std::cout << "Coordinate: \t" << UCSD.latitude << ", " << UCSD.longitude 
	<< "\n";
	std::cout << "Public: \t" << UCSD.public_institution << "\n";

	return 0;
}
```

```
Name:           University of California, San Diego
Country:        US
Students:       35821
Coordinate:     32.8328, -117.271
Public:         1
```

##### Braced Initialization

A POD can be initialized using braces containing the data to be stored in its members. If there is nothing between the braces, all members will be initialized to 0. If there are, it will be assigned to the members in the order in which they are defined within the POD. Any members with unassigned values will be zeroed.

```cpp
struct Restaurant{
	std::string restauraunt_name;
	int number_of_reviews
	double average_rating; 
};

int main {
	Restaurant placeA{}; // All fields will be zeroed
	Restaurant placeB{ "McDonalds", 9203, 4.67 }; // All fields defined
	Restaurant placeB{ "ChickFilA", 651 }; // Name and number of reviews defined
	                                       // but average rating is zeroed.
	
	return 0;
}
```

##### Structured Binding Declaration

PODs can be used to establish a return type consisting of multiple members. This way, a function can be used to return multiple variables instead of one. The syntax for unpacking multiple variables from a function call is the keyword `auto` followed by brackets containing a comma separated list of the variables to which you would like to unpack to. **Note that in VS Studio, you have to be using C++17 to do this.**

```cpp
struct ReturnValue {
    // Establish return type containing multiple members.
    int number;
    bool true_or_false;
};

ReturnValue some_function() {
    // Implicitly return the return type with specified members.
    return { 3, true };
}

int main()
{
    // Unpack using auto followed by brackets containing
    // variables to unpack to.
    auto [my_number, my_truth] = some_function();
}
```

#### Unions

The *union* is a special type of class that can be used when a particular variable can be interpreted in several different types.  It is defined similar to POD's but using the keyword `union`.

```cpp
#include <iostream>

union Grade {
	char letter_grade;
	int score;
	double percentage;
}
```

To assign a variable of the specified union type, write out the type, followed by the identifier followed by a semicolon to declare it. To specify which format to store the information as, use the dot operator on the newly created variable followed by the member of the format that you want to save the information and assign it. The same can be done for accessing the information. 

Note that it's possible to access a union type variable data using the wrong type, leading to unexpected output. For this reason, using this class type to store and access information is not recommended unless absolutely required.

```cpp
int main() {
	Grade my_letter_grade;
	my_letter_grade.letter_grade = 'A';
	Grade my_score;
	my_score.score = 94;
	Grade my_percentage;
	my_percentage.percentage = 0.94;

	std::cout << "Letter Grade:  " << my_letter_grade.letter_grade << "\n";
	std::cout << "       Score:  " << my_score.score << "\n";
	std::cout << "  Percentage:  " << my_percentage.percentage << "\n\n";

	// This will interpret incorrectly because the type with which the grade
	// was saved is not the same as the type with which it is being accessed.
	std::cout << "Incorrect Interpretation:" << my_percentage.letter_grade 
	<< "\n";

	return 0;
}
```

```
Letter Grade:  A
       Score:  94
  Percentage:  0.94

Incorrect Interpretation:¶
```

#### Fully-Featured Classes

Fully-featured classes, in addition to storing information in members, have *methods*, which are functions that can access, manipulate, and return information from members within the class. They are declared in the same way that ordinary functions outside of classes are. They already have access to members.

Consider the following example which models a jar in which you can put in and remove individual jelly beans.

```cpp
struct JellyBeanJar {
	int jelly_beans = 0;

	bool add_bean() {
		if (jelly_beans < 0) return false;
		jelly_beans += 1;
		return true;
	}

	bool remove_bean() {
		if (jelly_beans <= 0) return false;
		jelly_beans -= 1;
		return true;
	}
};
```

Running the following represents starting with an empty jar, checking the count, adding a bean, and checking the count.

```cpp
int main() {
	JellyBeanJar jar;

	std::cout << "Start with an empty jar.\n";
	std::cout << "Bean Count: " << jar.jelly_beans << "\n";
	std::cout << "Add a bean.\n";
	jar.add_bean();
	std::cout << "Bean Count: " << jar.jelly_beans << "\n";

	return 0;
}
```

```
Start with an empty jar.
Bean Count: 0
Add a bean.
Bean Count: 1
```

##### Access Control

The problem with the above class is that anyone can just access the `jelly_beans` member and modify it to an invalid value.

```cpp
jar.jelly_beans = -3;
```

Access control allows you to specify whether certain members or methods are accessible from outside the class. When using a `struct` to specify private members and methods, use `private:` and define members and methods after to  make those private.

```cpp
struct JellyBeanJar {
	bool add_bean() {
		if (jelly_beans < 0) return false;
		jelly_beans += 1;
		return true;
	}

	bool remove_bean() {
		if (jelly_beans <= 0) return false;
		jelly_beans -= 1;
		return true;
	}

	int count() {
		return jelly_beans;
	}
	
	private:
		// The number of jelly beans is not directly accessible because
		// jelly_beans is declared in this private section. All the methods
		// defined above are outside of this section and are considered public.
		int jelly_beans = 0;
};
```

By default, members and methods in `struct` are public unless specified after `private:`. Instead of using `struct`, you can also use `class`, which is identical in function except members and methods are private by default unless specified after `public:`.

```cpp
class JellyBeanJar {
	// By default, jelly_beans is private.
	int jelly_beans = 0;

	public:
		// These functions declared in the public section are accessible from
		// outside the class.
		bool add_bean() {
			if (jelly_beans < 0) return false;
			jelly_beans += 1;
			return true;
		}

		bool remove_bean() {
			if (jelly_beans <= 0) return false;
			jelly_beans -= 1;
			return true;
		}

		int count() {
			return jelly_beans;
		}
};
```

##### Constructors

Constructors are used to create an instance of a class with members specified from a set of inputs. This can be useful in employing logic to verify inputs and specify members based on those inputs.

Constructors are specified within a class definition by the class identifier, followed by a set of parentheses with specified inputs, followed by curly braces containing statements to assign class members.

```cpp
struct JellyBeanJar {
	// If no inputs are specified, the inital jelly bean count is 0.
	JellyBeanJar() {
		jelly_beans = 0;
	}

	// If an input is specified, make sure it is a valid number before
	// assigning the initial jelly bean count. If it is invalid, default
	// the number of jelly beans to 0.
	JellyBeanJar(int initial_count) {
		if (initial_count >= 0) jelly_beans = initial_count;
		else jelly_beans = 0;
	}

	bool add_bean() {
		if (jelly_beans < 0) return false;
		jelly_beans += 1;
		return true;
	}

	bool remove_bean() {
		if (jelly_beans <= 0) return false;
		jelly_beans -= 1;
		return true;
	}

	int count() {
		return jelly_beans;
	}

	private:
		int jelly_beans;
};
```

```cpp
int main() {
	JellyBeanJar jar1; // By default, initializes to 0 jelly beans.
	JellyBeanJar jar2{ 4 };

	std::cout << "Initial Jar Counts\n";
	std::cout << "Jar1: " << jar1.count() << "\t" 
			  << "Jar2: " << jar2.count() << "\n";
	std::cout << "Add a bean to each.\n";
	jar1.add_bean();
	jar2.add_bean();
	std::cout << "Jar1: " << jar1.count() << "\t"
		      << "Jar2: " << jar2.count() << "\n";

	return 0;
}
```

```
Initial Jar Counts
Jar1: 0 Jar2: 4
Add a bean to each.
Jar1: 1 Jar2: 5
```

##### Destructors

Destructors are functions that execute before the instance is destroyed. To define a destructor, specify a function in the class with the same name as the class except with a tilde (`~`) before and with a set of empty parentheses (no arguments).

```cpp
struct SomeClass {
	--snip--

	~SomeClass() {
		// Statements to be executed before the destruction of an instance of
		// this class.
		statements;
	}

	--snip--
};
```

Note on members of a class: Members are constructed before the class instance's constructor is called and they are destructed after the class instance's destructor is called.

##### Copy Constructors

Copying an instance of a class will simply copy, by value, the members of one class into the other. This is not great practice, particularly when working with classes which have pointer members, as the resulting copy and original will actually point to the same variable, where modifications to one will lead to changes in the other. The solution around this is to implement a *copy constructor*. This is simply an ordinary constructor that takes its own class as an argument (by reference and usually `const` to ensure no modifications of the original are made during the process) and creates a new copy with members which are same by value.

```cpp
struct MyString {
    MyString() {
        name = nullptr;
    }

    MyString(const char name[]) {
        change_name(name);
    }

    // Here is the copy constructor
    MyString(const MyString& other) {
        std::strncpy(name, other.name, strlen(other.name));
    }

    void change_name(const char name[]) {
        std::strncpy(this->name, name, strlen(name));
        this->name[strlen(name)] = 0;
    }

    char* name = new char[1];
};

int main()
{
    MyString string_1{ "Hello World!" };
    MyString string_2{ "Goodbye World!" };
    MyString string_3{ string_1 };
    // string_1 name is "Hello World!" and string_3 name is "Hello World!" but
    // they do not point to the same location in memory.
    string_3.change_name("Disney World!");
    // string_3 name is changed, but this does not change that of string_1

    std::cout << "string_1: " << string_1.name << std::endl;
    std::cout << "string_2: " << string_2.name << std::endl;
    std::cout << "string_3: " << string_3.name << std::endl;
}
```

```
string_1: Hello World!
string_2: Goodbye World!
string_3: Disney World!
```

Commenting out the copy constructor from the above example yields the following result. `name` of `string_1` and `string_3` refer to the same location in memory, so modifying one changes the other, which is not the behavior that we want.

```cpp
string_1: Disney World!
string_2: Goodbye World!
string_3: Disney World!
```

##### Copy Assignment Operators

Copy assignment operators allow us to overwrite an existing instance with the contents of another using the copy operator (`=`). The syntax for this is to specify a constructor with the class's type followed by an `&` (to indicate you are returning a reference to this instance) followed by `operator=`. Within the arguments, take a `const` reference to the instance being copied.

Within the copy constructors, it is generally good practice to check if the instance being passed as an argument is actually itself. See the example below for details.

```cpp
struct MyString {
    MyString() {
        name = nullptr;
    }

    MyString(const char name[]) {
        assign_name(name);
    }

    MyString(const MyString& other) {
        std::strncpy(name, other.name, strlen(other.name));
    }

    // Here is the copy assignment constructor
    MyString& operator=(const MyString& other) {
        // Checks if other is actually this instance. If so,
        // return this instance.
        if (this == &other) return *this;
        change_name(other.get_name());
        return *this;
    }

    void change_name(const char name[]) {
        delete[] this->name;
        assign_name(name);
    }

    char* get_name() const {
        return name;
    }

private:

    char* name;

    void assign_name(const char name[]) {
        this->name = new char[strlen(name) + 1];
        std::strncpy(this->name, name, strlen(name));
        this->name[strlen(name)] = 0;
    }
};

int main()
{
    MyString string_1{ "Hello World!" };
    MyString string_2{ "Goodbye World!" };
    MyString string_3{ "Disney World!" };

    // The string from string_1 is copied over to string_3, but
    // they are independent. Modifications to string_3 are independent
    // of that on string_1.
    string_3 = string_1;
    // If they were not independent, we would expect the statement
    // below to also change string_1.
    string_3.change_name("Jurassic World!");

    std::cout << "string_1: " << string_1.get_name() << std::endl;
    std::cout << "string_2: " << string_2.get_name() << std::endl;
    std::cout << "string_3: " << string_3.get_name() << std::endl;
}
```

```
string_1: Hello World!
string_2: Goodbye World!
string_3: Jurassic World!
```

##### Default Copy

By default, when copying one instance to an other, the members are copied over using either copy construction or copy assignment (depending on  if the instances involved were copied via construction or assignment). It is good practice to be explicit about how your class can be copied, either by specifying copy constructors and copy assignment constructors or by using `default`, which specifies that copying via the default method is acceptable.

```cpp
struct SomeClass {
	SomeClass(const SomeClass&) = default;
	SomeClass& operator=(const SomeClass&) = default;
	...
}
```

##### Delete Copy

To specify that an instance of a class cannot and should not be copied, use the `delete` in place of `default` when specifying copy constructors.

```cpp
struct SomeClass {
	SomeClass(const SomeClass&) = delete;
	SomeClass& operator=(const SomeClass&) = delete;
	...
}
```

##### Move Constructors and Move Assignment Operators

Copying can be quite wasteful. Say we encounter a situation where we want to transfer ownership of resources from one object to another. By copying, while one object does acquire the data from the other object, the other object continues to exist, despite no longer being needed. What moving does is transfer the data from the one object to the other before setting the moved from object in a *moved-from* state. The only two things which can be done with an object in a *moved-from* state are to reassign them or destruct them (freeing up resources).

###### `rvalues` and `lvalues`

`rvalues` can be thought of as literals or initialized objects that have not been assigned. The reasoning behind the name is that they typically (although not always) reside on the right side of a copy assignment statement.

`lvalues` can be thought of as objects that have been assigned an identifier and are now variables. They typically reside on the left side of a copy assignment statement.

```cpp
struct SomeObject {
    int some_value;
};

int main()
{
    int x = 3; // x is an lvalue, 3 is an rvalue.
    SomeObject object_A{ 5 }; // object_A is an lvalue, 5 is an rvalue.
    SomeObject object_B = SomeObject{ 4 }; // object_B is an lvalue,
                                           // SomeObject{ 4 } is an rvalue.
}
```

###### `std::move` Function

The `std::move()` function, which can be used after including the `<utility>` header, is used to convert an `lvalue` object to an `rvalue`. This is important because within functions and move constructors, you can specify that that an input be an `rvalue` object. 

###### Move Constructors

To specify a **move constructor**, follow the argument data type with `&&` (versus a `const` reference like in copy and copy assignment constructors, although the return type should still be a reference). Additionally, include `noexcept` after argument list (because compilers cannot use exception-throwing move constructors). Within the move constructor, the values of the members of the input should be copied over before the input members are set to null.

```cpp
	// Move constructor
    MyString(MyString&& other) noexcept {
        this->name = other.name;
        other.name = nullptr;
    }
```

###### Move Assignment Operator

A similar syntax can be followed for the move assignment operator as the copy assignment constructor. Note the self check at the beginning just as in the copy assignment constructor and also note the `noexcept` after the arguments.

```cpp
	// Move assignment constructor
    MyString& operator=(MyString&& other) noexcept {
        // Checks if other is actually this instance. If so,
        // return this instance.
        if (this == &other) return *this;
        this->name = other.name;
        other.name = nullptr;
        return *this;
    }
```

###### Moving an Object

To move an object after specifying the move constructors, use the `std::move()` function to convert the object to be moved into an `rvalue` before inputting that as an argument for initializing or copying to move to another object. This should result in the move constructor or the move assignment constructor being called instead of the copy constructor or copy assignment constructor.

```cpp
int main()
{
    MyString string_1{ "Hello World!" };
    MyString string_2{ "Goodbye World!" };
    
    std::cout << "Initial Values:\n";
    std::cout << "string_1: " << string_1.get_name() << std::endl;
    std::cout << "string_2: " << string_2.get_name() << std::endl;

    // Move from string_1 into string_2. Then delete string_1.
    string_2 = std::move(string_1);
    delete &string_1;

    std::cout << "Final Values:\n";
    std::cout << "string_1: No longer valid. Error occurs if you attempt to retrieve.";
    std::cout << "string_2: " << string_2.get_name() << std::endl;
}
```

```
Initial Values:
string_1: Hello World!
string_2: Goodbye World!
Final Values:
string_1: No longer valid. Error occurs if you attempt to retrieve.
string_2: Hello World!
```

## Control Flow

### If Statements

There are two general ways to write if statements depending on the number of statements to be executed for a given condition. If there is only one statement to be executed, the following format can be used. 

```cpp
if (condition) statement;
```

If multiple statements are to be executed for a given condition, the statements to be executed are contained within a set of curly braces.

```cpp
if (condition) {
	statement_1;
	statement_2;
	statement_3;
}
```

`else if` and `else` statements can be used to evaluate and execute code based on alternate conditions.

```cpp
if (condition_1) statement_1;
else if (condition_2) statement_2;
else statement_3;

if (condition_1) {
	statement_1A;
	statement_1B;
} else if (condition_2) {
	statement_2A;
	statement_2B;
} else {
	statement_3A;
	statement_3B;
}
```

### Switch Statements

Switch statements are used to evaluate if a condition matches a specific case and executes code depending on the case. The format for a `switch` block is shown below.

```cpp
switch (condition) {
	case (case_a): {
	// This code executes if condition == case_a is true.
	statements_a;
	} break;
	case (case_b): {
	// This code executes if condition == case_b is true.
	statements_b;
	} break;
	case (case_c): {
	// This code executes if condition == case_c is true.
	statements_c;
	} break;
	default: {
	// This code executes if condition does not match any of the above specified
	// cases.
	statements_default;
	} break;
}
```

### For Loops

A `for` loop can be used to iterate over every item in a list. The format for a `for` loop is as follows.

```cpp
for (init-statement; conditional; iteration-statement) {
	statements;
}
```

The `init-statement` is a statement that is executed before the start of the loop. This is usually used to initialize the iterator variable (such as one used to access the elements in a list). **Note: If accessing elements in an array, `size_t` should be the type of the iterator variable as `int` may not be able to store large enough values to iterate over a large list.**

The `conditional` is an expression that evaluates before each iteration. If it evaluates to `true`, then the iteration is executed and the loop continues. Otherwise, the loop is terminated.

The `iteration-statement` is executed at the end of each iteration and is typically used to increment the iterator variable.

#### Range-Based For Loop

The *range-based for loop* is a way to iterate over all the elements in a list without having to deal with an iterator variable. The format is as follows.

```cpp
for (element_type element_name : array_name) {
	statements;
}
```

It operates in a similar manner to for loops in Python where the loop will iterate through each element in `array_name` using `element_name` to modify or access the value of each element. `element_type` is simply the type of the elements in the array.

### Try-Catch Blocks

Try-catch blocks are segments of code used to check for errors that occur and handle them appropriately based on the type of error.

Try-catch blocks are made by using the keyword `try` followed by an enclosed code block, followed by any number of `catch` cases followed by enclosed code blocks. Notice that when working with exceptions, we are passing them into the catch blocks by reference (hence the `&` after the variable type `std::runtime_error` or `std::logic_error`). A catch case enclosed with `...` will handle any exception (or any throwable object) not specified by other catch cases.

```cpp
try {
	//--some code--
} catch (const std::runtime_error& e) {
	//--error handling case 1--
} catch (const std::logic_error& e) {
	//--error handling case 2--
} catch (...) {
	//--error handling case 3--
	// If the exception doesn't match either a runtime_error or logic_error,
	// then handle the exception (or whatever it is) here.
}
```

To throw an object (typically an error. This is analogous to `raise` in Python), use the keyword `throw` followed by the object to be thrown. When throwing exceptions, you can initialize them with a string argument detailing exactly what went wrong. When catching errors, you can call their `what()` function, which returns that string description detailing the nature of the error.

```cpp
#include <stdexcept>
#include <iostream>

void some_function(int input) {
	if (input < 0) throw std::logic_error{ "Input to some_function cannot be" 
	"negative" }; // Exceptions can be initialized 
	return;
}

int main() {
	try {
		some_function(-1);
		std::cout << "Success! We passed -1 into some_function()";
	}
	catch (std::logic_error& err) {
		std::cout << "Error: " << err.what();
	}
}
```

#### Exceptions

*Exceptions* are used to communicate an error condition. All exceptions are a subclass of class `std::exception` class. The two main types of exceptions within that are `std::runtime_error` exceptions and `std::logic_error` exceptions. To use the standard library exceptions, include the `<stdexcept>` header.

`logic_error` exceptions are usually caused when a logical precondition of a class or function is not satisfied. `logic_error` has several subclasses, which are listed below along with their use cases.

 - `domain_error`: Error related to valid input range. For example, this could be thrown when a function receives a negative number when its domain includes all non-negative numbers.
 - `invalid_argument`: This is a general exception raised when a function receives an unexpected argument.
 - `length_error`:  This exception is used when some action would violate a maximum size constraint.
 - `out_of_range`: This exception is used to report that some value is not in some expected range, such as when referencing some index of an array (or other data structure) that does not exist.

`runtime_error` exceptions report error conditions outside the program's scope.

 - `system_error`: This exception reports that the operating system encountered an error. This can be particular useful to catch as details about the nature of the error can be accessed using the `.code()` method. To use this exception, include the `<system_error>` header.
 - `overflow_error`: Arithmetic overflow.
 - `underflow_error`: Arithmetic underflow.

#### `noexcept`


The keyword `noexcept` can be specified after a functions argument list before the function's body. This allows for some optimization but it means you better be sure that it is impossible for the an exception to be thrown within the function.

#### Throwing in Destructors

Not even once.

## Reference Types

### Pointers

**Pointers** are variables that store the memory address of other variables. 

Pointers are declared by appending an asterisk (`*`) to a data type following with the identifier for the pointer. The pointer should point to the memory address storing a variable of the specified data type.

```cpp
int* here_is_my_number; // we expect here_is_my_number to point to a memory
                        // address containing an int variable.
```

#### Address-Of-Operator

To get a variable's memory address location to store in a pointer, prepend the variable identifier with the *address-of-operator* (`&`).

```cpp
std::string my_house{ "Welcome to my humble abode" };
std::string* my_address = &my_house; // Pointer to the variable, my_house.
```

#### Dereferencing Operator

To access a variable from its pointer, prepend a pointer with a *dereferencing operator* (`*`).

```cpp
#include <iostream>

int main()
{
    std::string my_house{ "Welcome to my humble abode" }; // Initialize my_house
    std::string* my_address = &my_house; // Get the address of my_house
    cout << my_house << "\n";
    cout << "My Address: " << my_address << "\n";
    
    my_house = { "I am now home" }; // Change the message of my_house
    cout << *my_address; // Access my_house via its pointer. This is
	                     // functionally the same as using my_house instead.

    return 0;
}
```

```
Welcome to my humble abode
My Address: 0x7ffef9569910
I am now home
```

#### Member-Of-Pointer Operator

The *member-of-pointer operator* (`->`) is used to simultaneously access an object through its pointer and then access a member of that object.

```cpp
int main()
{
	JellyBeanJar my_jar;
	JellyBeanJar* my_jars_location = &my_jar;
	// my_jar's functions are accessible directly through its pointer using the
	// member-of-operator (->).
	my_jars_location->add_bean();
    std::cout << "My jar has " << my_jars_location->count() << " beans!";
}
```

#### Arrays and Pointers

Creating a pointer to an array is equivalent to creating a pointer to the first value of an array. The identifier for an array without brackets (`[]`) can be treated as a pointer to the array's first value.

```cpp
int main()
{
	int my_numbers[]{ 5, 4, 3, 2, 1 };
	int* my_numbers_location = my_numbers;

	//my_numbers_location should point to the first value in my_numbers.
	std::cout << "First value in my_numbers: " << *my_numbers_location;
}
```

```
First value in my_numbers: 5
```

Adding and subtracting to the pointer allows us to access the elements ahead or behind of the current value. This is called *pointer arithmetic*.

```cpp
int main()
{
	int my_numbers[]{ 5, 4, 3, 2, 1 };
	int* my_numbers_location = my_numbers;
	int* my_second_number = my_numbers + 1;

	//my_second_number should point to the second value in my_numbers.
	std::cout << "Second value: " << *my_second_number;
}
```

```
Second value: 4
```

Using bracket notation to access a value and pointer notation are functionally equivalent.

```cpp
int main()
{
	int my_numbers[]{ 5, 4, 3, 2, 1 };

	// From accessing the third value by bracket notation.
	std::cout << "    my_numbers[2]: " << my_numbers[2] << std::endl;
	// From accessing the pointer to the third value and dereferencing.
	std::cout << "*(my_numbers + 2): " << *(my_numbers + 2) << std::endl;
}
```

```
    my_numbers[2]: 3
*(my_numbers + 2): 3
```

`nullptr` is a literal for a pointer in which the pointer does not point to any address. Pointers have an implicit conversion to `bool` where a `nullptr` evaluates to `false` and everything else evaluates to `true`.

```cpp
int main()
{
	int* points_somewhere = nullptr;

	if (points_somewhere) std::cout << "I have direction!";
	else std::cout << "I have no direction :(";
}
```

```
I have no direction :(
```

### References

#### Passing Arguments by Value vs by Reference

When passing an object into a function by value, the value is essentially copied over and stored as a variable local to the function. This means that any attempts to modify the value using the function will only occur to the local variable and not the variable used as an argument.

```cpp
void add_and_print(int value) {
	value += 1;
	std::cout << "value is " << value << std::endl;
}

int main()
{
	int my_lucky_number = 3;
	// Pass my_lucky_number into add_and_print. The value of my_lucky_number is
	// copied and value is assigned that value. Any changes to value are not 
	// received by my_lucky_number.
	add_and_print(my_lucky_number);

	// We can see that my_lucky_number remains unchanged.
	std::cout << "my_lucky_number is " << my_lucky_number << std::endl;
}
```

```
value is 4
my_lucky_number is 3
```

To get around this, if we do want to modify the variable we are passing into the function, we can use pointers. Instead of passing the variable itself, we will pass a pointer to the variable. Within the function, we can dereference the pointer, allowing us to work directly with the variable.

```cpp
void add_and_print(int* value) {
	*value += 1;
	std::cout << "value is " << *value << std::endl;
}

int main()
{
	int my_lucky_number = 3;
	// Pass the pointer for my_lucky_number into add_and_print. The function  
	// then dereferences the pointer and is able to work directly with 
	// my_lucky_number.
	add_and_print(&my_lucky_number);

	// We can see that my_lucky_number accepts the change.
	std::cout << "my_lucky_number is " << my_lucky_number << std::endl;
}
```

```
value is 4
my_lucky_number is 4
```

It can be quite cumbersome to use the dereference operator or member-of-operator on the pointer for every statement involving the variable. Instead, we can use a **reference**.  This is done by appending an ampersand (`&`) to the parameter type in the function definition. That way, when we pass a variable as an argument to a function, we can work directly with that variable within the function as if it were a local variable, eliminating the need to use the dereferencing operator within the function.

```cpp
void add_and_print(int& value) {
	value += 1;
	std::cout << "value is " << value << std::endl;
}

int main()
{
	int my_lucky_number = 3;
	// By passing the variable by reference, add_and_print can work directly to
	// modify my_lucky_numbers. Within add_and_print, it is as if we are working
	// with a normal, local variable.
	add_and_print(my_lucky_number);

	// We can see that my_lucky_number accepts the change.
	std::cout << "my_lucky_number is " << my_lucky_number << std::endl;
}
```

```
value is 4
my_lucky_number is 4
```

#### Use Cases

Pointers and references are largely interchangeable, however, references cannot be assigned to null easily or be reseated, meaning changed such that it references another variable instead of the one originally set.

### `this` Pointers

The `this` pointer is used within a class to distinguish the current object when accessing a member. This can be used to make explicit the instance of an object you are referring to (which can be especially useful when an object is interacting with other objects of the same type). 

```cpp
struct DoublyLinkedListObject {
	DoublyLinkedListObject* right_object{}; // Pointer to object on right.
	DoublyLinkedListObject* left_object{}; // Pointer to object on left.
	char* name;

	DoublyLinkedListObject(char* name) {
		this->name = name;
	}

	void add_right(DoublyLinkedListObject* new_object) {
		// Link up this object's right_object to the new_object if it exists.
		if (this->right_object) {
			this->right_object->left_object = new_object;
			new_object->right_object = this->right_object;
		}

		// Link up this object to new_object
		new_object->left_object = this;
		this->right_object = new_object;
	}

	void add_left(DoublyLinkedListObject* new_object) {
		// Link up this object's left_object to the new_object if it exists.
		if (this->left_object) {
			this->left_object->right_object = new_object;
			new_object->left_object = this->left_object;
		}

		// Link up this object to new_object
		new_object->right_object = this;
		this->left_object = new_object;
	}
};
```

### `const`

The keyword `const`, short for "constant", is used to specify that a particular variable cannot be modified.

#### Constant Methods

Using `const` in a method ensures that the execution of the method will not permit any change to the state of the object from which it is called. You can think of it as a read-only method.

To make a method `const`, specify include the keyword after the arguments list but before the method body.


Recall the `JellyBeanJar` class. The `count()` method, which reads and returns the number of jelly beans present in the jar would be a good method to make read-only.
```cpp
struct JellyBeanJar {
	// If no inputs are specified, the inital jelly bean count is 0.
	JellyBeanJar() {
		jelly_beans = 0;
	}

	// If an input is specified, make sure it is a valid number before
	// assigning the initial jelly bean count. If it is invalid, default
	// the number of jelly beans to 0.
	JellyBeanJar(int initial_count) {
		if (initial_count >= 0) jelly_beans = initial_count;
		else jelly_beans = 0;
	}

	bool add_bean() {
		if (jelly_beans < 0) return false;
		jelly_beans += 1;
		return true;
	}

	bool remove_bean() {
		if (jelly_beans <= 0) return false;
		jelly_beans -= 1;
		return true;
	}

	int count() const {
		return jelly_beans;
	}

private:
	int jelly_beans;
};
```

#### Constant Arguments

The keyword `const` placed before the data type and identifier for arguments to a function will ensure that that variable remains unmodified throughout the execution of that function. Note that when an object is passed as `const` into a function, the object can only call `const` methods within that function.

```cpp
int some_function(const JellyBeanJar& jar) {
	// Won't compile because jar is const but add_bean() is not const.
	jar.add_bean();
	return jar.count();
}
```

#### Constant  Member Variables

Constant variables can't be modified after initialization. To use `const` for variables within a class initialized to values specified at construction, we need to use a *member initializer list*. To create a member initializer list, put a colon (`:`) after the arguments list for the constructor followed by a comma separated list containing the name of the member to be assigned followed by curly braces containing the argument assigned to the member.

```cpp
struct Student {
	Student(char* preferred_name, const int id_number, int current_age)
		: name{ preferred_name }, id{ id_number }, age{ current_age } {
		// This is where you could place logic to verify input parameters.
	} // the student's id is a constant as we don't expect this to change with
	  // time.

	char* name;
	const int id;
	int age;
};
```

### `auto` Type Deduction

`auto` can be used to automatically infer the type of a variable based on context. 

```cpp
auto number{ 2 };       // number is an int.
auto name{ "Alfred" };  // name is a char[6].
```

Modifiers such as `&`, `*`, and `const`, when paired with auto, are used to specify if we should expect a variable to be a reference or pointer and whether it should be constant.

```cpp
auto year { 2021 };             // int
auto& year_ref = year;          // int& (reference)
const auto& year_cref = year;   // const int& (constant reference)
auto* year_ptr = &year;         // int* (pointer)
const auto* year_cptr = &year;  // const int* (constant pointer)
```

The main function of `auto` is to save time during code refactoring such that changing the type of some variable doesn't require you to change data types everywhere in your code.

## Object Life Cycle

Object's have a life cycle starting from when they are declared (memory is allocated to store the object) and ending when their destructors are called (followed by the object's storage being deallocated). 

### Automatic Storage

An *automatic object* is allocated memory at the beginning of an enclosing code block (`{}`) and deallocated at the end of the enclosing code block.

```cpp
int main()
{
    {
        // enclosed_number is only in scope within this enclosed code block.
        int enclosed_number = 3;
    } // by the end, enclosed_number has been deallocated.

    // This won't compile because it's attempting to access a variable that
    // no longer exists.
    std::cout << "Enclosed Number: " << enclosed_number;
}
```

```cpp
int main()
{
    for (int i = 0; i < 5; i++) {
        // i exists only within the for loop.
        std::cout << i << std::endl;
    } // i is deallocated by the time the for loop is completed.

    // This won't compile because i no longer exists.
    std::cout << "Last iterator was " << i;
}
```

This is the reason why ordinary variables in functions only exists within the scope of the function.

### Static Storage

For a *static object*, the object is allocated when the program starts and is deallocated when the program ends. Because of this, they can be accessed from any function within the translation unit (consisting of the contents of the source file and all its headers). 

Static objects are declared at the same level functions are declared (global scope). You declare one by prepending the variable type with the keyword `static`. 

```cpp
static int bean_count = 0; // bean_count is static and should be accessible
                           // throughout the duration of the program.

void add_beans(int new_beans){
    for (int bean = 0; bean < new_beans; bean++) {
        // bean_count can be accessed because it is static.
        bean_count++;
        std::cout << "Added " << bean + 1
            << " beans. I now have " << bean_count << " beans.";
        std::cout << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    // for every function call, bean_count is accessed and modified
    // despite not passing a reference to bean_count.
    add_beans(3);
    add_beans(4);
}
```
```
Added 1 beans. I now have 1 beans.
Added 2 beans. I now have 2 beans.
Added 3 beans. I now have 3 beans.

Added 1 beans. I now have 4 beans.
Added 2 beans. I now have 5 beans.
Added 3 beans. I now have 6 beans.
Added 4 beans. I now have 7 beans.
```

If a variable needs to be accessed from another translation unit (from another source file) the keyword `extern` would be used in place of `static`. Otherwise, they are functionally identical.

#### Local Static Variables

Static variables declared within a function are only accessible within the context of that function, however, they continue to exists between function calls until they are deallocated at the end of the program. They are allocated at the first function call involving that static variable.

```cpp
void add_beans(int new_beans){
    // bean_count will initialize on the first function call. This statement
    // is ignored for subsequent function calls and bean_count won't be reset
    // to 0 every time add_beans() is called.
    static int bean_count = 0;

    for (int bean = 0; bean < new_beans; bean++) {
        bean_count++;
        std::cout << "Added " << bean + 1
            << " beans. I now have " << bean_count << " beans.";
        std::cout << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    add_beans(3);
    add_beans(4);

    // This won't compile because bean_count despite being static and existing
    // between function calls is local to add_beans and can only be accessed
    // within that function.
    std::cout << "In total, I now have " << bean_count << "beans!";
}
```

#### Static Members

Static members are not associated with a particular instance of a class but instead with all instances of the class.

Static variables declared in a class definition must be initialized outside at the global scope. Static members are accessed using the scope resolution operator (`::`).

Static methods can only work with the static variables and other static methods of the class.

```cpp
struct Planet {
    // This static variable is declared here but must be initialized outside the
    // class definition.
    static double gravitational_constant;
    int population;

    // Constructors
    Planet(int population) {
        if (population >= 0) {
            this->population = population;
        }
        else {
            this->population = 0;
        }
    }

    Planet() {
        this->population = 0;
    }

    // This ordinary method is able to work with non-static members of the class.
    bool change_population(int change_in_population) {
        auto new_population = this->population + change_in_population;
        if (new_population >= 0) {
            this->population = new_population;
            return true;
        }
        else {
            return false;
        }
    }

    // This static method can only work with static members of the class.
    static void change_gravitaitonal_constant(double new_gravitational_constant) {
        gravitational_constant = new_gravitational_constant;
    }
};

// The static variable gravitational_constant is initialized here at the global scale.
// The scope resolution operator (::) is used to access and modify the static member.
double Planet::gravitational_constant = 6.67430e-11;

int main()
{
    Planet Earth{ 2 };
    // Reproduce
    Earth.change_population(1);

    // Casually change the laws of the universe. The static method of the Planet class
    // must be accessed by using the scope resolution operator (::).
    Planet::change_gravitaitonal_constant(6.67430e-10);
}
```

#### `thread_local`

`thread_local` is used to specify that a static variable is local to  a specific thread. This is mainly to make code *thread-safe*, because multiple threads accessing the same mutable global variable is a common source of issues when multithreading.

```cpp
void add_beans(int new_beans){
	// If running this function on multiple threads, each thread will acquire
	// its own copy of bean_count.
    thread_local static int bean_count = 0;

    for (int bean = 0; bean < new_beans; bean++) {
        bean_count++;
        std::cout << "Added " << bean + 1
            << " beans. I now have " << bean_count << " beans.";
        std::cout << std::endl;
    }
    std::cout << std::endl;
}
```

### Dynamic Storage

*Dynamic objects* are objects that you have manual control over when their lives begin and end.

To create a dynamic object, use the keyword `new` followed by the variable type, optionally followed by a curly brace with initialization arguments. This will return a pointer to the object which you can store to access the variable. 

To destroy a dynamic object, use the keyword `delete` followed by the pointer pointing to the dynamic object.

```cpp
int main()
{
	int* secret_number = new int{ 12345124 };
	std::cout << "The secret number is " << *(secret_number);
	delete secret_number;

	// Results in an error because the dynamic object has already been destroyed.
	std::cout << "I recovered the secret numgber: " << *(secret_number);
}
```

```
The secret number is 12345124
C:\Users\Brand\source\repos\object lifecycle\Debug\object lifecycle.exe (process 20728) exited with code -1073741819.
```

#### Dynamic Arrays

Creating a dynamic array is very similar to creating a dynamic object. Simply insert brackets following the object type specifying the number of elements.

```cpp
	int n = 8;
	// You can specify the length of a dynamic array using a variable.
	int* secret_numbers = new int[n] {};
```
When deleting a dynamic array, be sure to include brackets `[]` after the keyword `delete`.

```cpp
	// delete should include brackets when deleting dynamic arrays.
	delete[] secret_numbers;
```

#### Memory Leaks

It's important to delete dynamic variables sometime after creating them before the end of your program. Failure to do so could result in memory leaks where memory is not released, even after the conclusion of your program.

## Runtime Polymorphism

**Interfaces** can be thought of as contracts between classes that implement the interfaces and *consumers*, or classes that use the class implementing the interface. The consumers know what members are accessible of classes that implement the interfaces. Classes that implement the interface know what members must be implemented.

### Virtual Methods

Virtual methods are methods that are able to be overwritten by derived classes. A virtual method is declared by adding the keyword `virtual` to a method's definition.

To overwrite the method in a derived class, use the keyword `override` after the function identifier and parentheses but before the function body.

```cpp
struct ParentClass {
    virtual void say() {
        std::cout << "This function is in the ParentClass." << std::endl;
    }

    void gene() {
        std::cout << "This is present in both parent and child." << std::endl;
    }
};

struct ChildClass : ParentClass {
    void say() override {
        std::cout << "This function is from the ChildClass overriding the ParentClass" 
        "function." << std::endl;
    }
};

int main()
{
    ParentClass parent;
    ChildClass child;

    std::cout << "ParentClass Function Results:\nsay(): ";
    parent.say();
    std::cout << "gene(): ";
    parent.gene();

    std::cout << std::endl;

    std::cout << "ChildClass Function Results:\nsay(): ";
    child.say();
    std::cout << "gene(): ";
    child.gene();
}
```

```
ParentClass Function Results:
say(): This function is in the ParentClass.
gene(): This is present in both parent and child.

ChildClass Function Results:
say(): This function is from the ChildClass overriding the ParentClass function.
gene(): This is present in both parent and child.
```

### Pure-Virtual Classes

A *pure-virtual method* specified such that it must be override in its derived classes. They are established by omitting a function body and appending the method header with `= 0;`.

A *pure-virtual class* is a class that consists of only pure-virtual methods. These are the bases of interfaces as they make clear what members should be implemented for classes implementing the interface and what members should be used by consumers.

```cpp
// BasePerson is a pure-virtual class and serves as an interface.
struct BasePerson {
    virtual void say_the_thing() = 0;
};

// These are the classes that implement the interface.
struct Unggoy : BasePerson {
    void say_the_thing() override {
        std::cout << "I see  bad guy!" << std::endl;
    }
};

struct Sangheili : BasePerson {
    void say_the_thing() override {
        std::cout << "WORT, WORT, WORT!" << std::endl;
    }
};

struct Jiralhanae : BasePerson {
    void say_the_thing() override {
        std::cout << "I will sniff you out, Demon!" << std::endl;
    }
};

// This is the consumer.
struct CharactersList {
    void add_character(BasePerson& character) {
        auto new_characters_list = new BasePerson*[number_of_characters + 1];
        for (size_t i = 0; i < number_of_characters; i++) {
            // Copy over existing characters into new character list.
            new_characters_list[i] = characters[i];
        }
        // Add address of new character into new character list.
        new_characters_list[number_of_characters] = &character;
        if (characters) delete characters; // Delete old character list if it exists.
        characters = new_characters_list;
        number_of_characters++;
    }

    void everyone_say_the_thing() {
        for (size_t i = 0; i < number_of_characters; i++) {
            characters[i]->say_the_thing();
        }
    }

private:
    BasePerson** characters{ nullptr };
    size_t number_of_characters{ 0 };
};

int main()
{
    Unggoy grunt;
    Sangheili elite;
    Jiralhanae brute;

    CharactersList Halo;

    Halo.add_character(grunt);
    Halo.add_character(elite);
    Halo.add_character(brute);
    Halo.everyone_say_the_thing();
}
```

```
I see  bad guy!
WORT, WORT, WORT!
I will sniff you out, Demon!
```

#### Virtual Destructors

If dynamically implementing classes implementing an interface, it's a good idea to specify a default destructor in the interface to prevent from leaking resources. 


```cpp
BaseClass {
	virtual ~BaseClass() = default;
};
```

### Implementing Interfaces

When implementing a class where a field is an instance of a class using the interface, there are two ways to *inject* the member: **constructor injection** or **property injection**.

In constructor injection, the member is initialized as a reference to the class implementing the interface. Remember that references cannot be reseated. If you need the class being implemented to be reseated, use property injection instead.

```cpp
struct MyCharacter {
    MyCharacter(BasePerson& character) : my_character{ character } {}
private:
    BasePerson& my_character;
};
```

In property injection, the member is initialized as a pointer to the class implementing the interface. A setter function can be used to reseat the member.

```cpp
struct MyCharacter {
	MyCharacter(BasePerson* character_ptr) : my_character_ptr{ character_ptr } {}
	void set_character(BasePerson* new_character_ptr) {
		my_character_ptr = new_character_ptr;
	}
private:
	BasePerson* my_character_ptr;
}
```
