# C++ Notes
Notes and programs created while learning C++. These were notes were created following the content and examples from [learncpp.com](https://www.learncpp.com/). 

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
5. [Control Flow](#control-flow)
	5. [If Statements](#if-statements)
	6. [For Loops](#for-loops)

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

Arrays are used to store multiple elements of the same type. They are initialized in the same way you declare an ordinary variable of some type except following the identifier are brackets containing the number of elements in the array.

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

### Strings

Strings can be thought of as an array of characters. To declare a string literal, enclose the text you wish to convert into a string within a set of double quotations (").

```cpp
navy_seal
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
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEzMzg4ODQwNCwxMzY2OTkzNTAwLDE5ND
ExODg1MjYsLTkwNDc1ODYzMiwtMTI3MzYyNzUwNyw4MjY5MjIy
MTYsLTE4NTcyNjAxNzYsODk3NjEyMywtMjA4MjI1NDc1OSwyNj
I4MTc1MzAsMTk1NDc4MDY1MF19
-->