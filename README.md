# C++ Notes
Notes and programs created while learning C++. These were notes were created following the content and examples from [learncpp.com](https://www.learncpp.com/). 

## Table of Contents
1. [Compiling and Running Code](https://github.com/BrandonBNguyen/Cplusplus-Notes/blob/main/README.md#compiling-and-running-code)
2. Instantiating and Assigning Variables
3. Output and Input with the Console

## Compiling and Running Code
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
