---
Title: "202505311030"
Topic: CLang Learning Curve
tags:
  - programming/clang
  - type/note
  - type/sketchnote
aliases: []
template_type: Note
template_version: "1.35"
Created At: Saturday, May 31st 2025, 10:30:17 am
Modified At: Sunday, June 1st 2025, 8:56:15 pm
created: 2025-05-31T10:30
updated: 2025-06-29T16:24
---
<!--  See "Template Help" below for using properties -->
*Table of Contents*
- [[#II. Function Arguments|II. Function Arguments]]
- [[#III. C++ Programming Default Arguments (Param)|III. C++ Programming Default Arguments (Param)]]
	- [[#III. C++ Programming Default Arguments (Param)#IV. C++ Function Overloading|IV. C++ Function Overloading]]
	- [[#III. C++ Programming Default Arguments (Param)#V. C++ Inline Functions|V. C++ Inline Functions]]
	- [[#III. C++ Programming Default Arguments (Param)#VI. C++ Function Recursion|VI. C++ Function Recursion]]
	- [[#III. C++ Programming Default Arguments (Param)#Advantages of C++ Recursion|Advantages of C++ Recursion]]
	- [[#III. C++ Programming Default Arguments (Param)#Disadvantages of C++ Recursion|Disadvantages of C++ Recursion]]


# 202505311030
> [!Summary]
> **Covered Material:**
> - C++ Functions
> - C++ Programming Default Arguments
> - C++ Function Overloading
> - C++ Function Overriding
> - C++ Inline Functions
> - C++ Recursion
> - C++ Recursive Functions

# I. C++ Functions

**Table of Contents**
- [[#C++ Functions]]
	- [[#Function Arguments|Function Arguments]]
	- [[#C++ Programming Default Arguments (Param)|C++ Programming Default Arguments (Param)]]

----

**Why use them?**
- **Organized Code:** Keeps your code neat and tidy.
- **Reusability:** You write the code once, and you can use it many times in different parts of your program. If you need 5 walls for your castle, you don't build 5 separate designs; you use the same wall design 5 times.
- **Easier Debugging:** If something goes wrong, you know which "part" (function) to check.


**When to use:**
- Anytime you have a task that you repeat multiple times.
- When a specific part of your code performs a single, well-defined action.
- To make your `main` function (the starting point of your program) cleaner and easier to read.

**How to use:**
1. **Declare/Define:** Tell C++ about your function (what it's called, what it takes in, what it gives back).
    - `returnType functionName(parameterType parameterName, ...)`
2. **Call:** Use the function by its name, providing any necessary information (arguments).
    - `functionName(arguments);`

A `function` is a code block that performs a specific task.
- Dividing a complex problem into smaller chunks makes a program easy to understand and reusable
- **Two Types**: Standard Library Functions (STD), User-Defined Functions (UDF)

*User Defined Functions*
Allows users to define their own personalized functions. A User-Defined function groups code to perform a specific task and that group of code is given an ID. When a function is invoked from any part of the program, it executes all of its default programming. 

> [!Syntax] Syntax: 
> return-type function_name ( Parameter List ) { ... }

- **Return Type** − A function may return a value. The **return_type** is the data type of the value the function returns. Some functions perform the desired operations without returning a value. In this case, the return_type is the keyword **void**.
- **Function Name** − This is the actual name of the function. The function name and the parameter list together constitute the function signature.
- **Parameters** − A parameter is like a placeholder. When a function is invoked, you pass a value to the parameter. This value is referred to as actual parameter or argument. The parameter list refers to the type, order, and number of the parameters of a function. Parameters are optional; that is, a function may contain no parameters.
- **Function Body** − The function body contains a collection of statements that define what the function does.

**Function Declaration**: Tells the compiler about a function name and how to call the function. The actual body is defined separately.

> [!Syntax] 🔖 Syntax: 
> return_type function_name (Parameter List); 

----
## II. Function Arguments

if a function uses a parameter list, whenever the function is called or declared, set parameters must be set. This being as such:
```cpp
#include <iostream>
using namespace std;

// declaring a function
void greet() {
    cout << "Hello there!";
}

int main() {

    // calling the function
    greet();

    return 0;
}
```
- This function does not have any arguments, so calling the function does not need arguments

*Function With Parameters*
```cpp
// program to print a text

#include <iostream>
using namespace std;

// display a number
void displayNum(int n1, float n2) {
    cout << "The int number is " << n1;
    cout << "The double number is " << n2;
}

int main() {
     
     int num1 = 5;
     double num2 = 5.5;

    // calling the function
    displayNum(num1, num2);

    return 0;
}
```

*Diagram:*
![[Screenshot 2025-05-31 at 10.42.12 AM.jpg]]

**Return Statements:**
a `return` statement is used to return a value from a function. The return statement is commonly a 0 if the return type is an int, a string if its a string type and so on. This return statement can also be the result of parameters added toghether:
```cpp
int add (int a, int b) {
return (a + b)
}
```
- The return statement declaring an operation must first be stored into a variable. This stores the result of the return statement. 
- The variable can then be printed out using the `STD::COUT` statement

![[Screenshot 2025-05-31 at 10.50.28 AM.jpg]]
- In the program above, the add function is used to add two intergers together.
- We first pass two values to the add function and then store the returned value into the variable `sum`.
- Finally, We print the stored return value into the screen.

**Function Prototype:**
The code of the function should be before the function call. However when you want to setup a function after the function call, *function prototypes* work for these cases.
```cpp
// function prototype
void add(int, int);

int main() {
    // calling the function before declaration.
    add(5, 3);
    return 0;
}

// function definition
void add(int a, int b) {
    cout << (a + b);
}
```

> [!Syntax] Syntax: 
returnType functionName(dataType1, dataType2, ...);

*Example 2 - Function Prototype*
```cpp
// using function definition after main() function
// function prototype is declared before main()

#include <iostream>

using namespace std;

// function prototype
int add(int, int);

int main() {
    int sum;

    // calling the function and storing
    // the returned value in sum
    sum = add(100, 78);

    cout << "100 + 78 = " << sum << endl;

    return 0;
}

// function definition
int add(int a, int b) {
    return (a + b);
}
// 100 + 78 = 178
```
- Function is defined after a function call

*Benefits of Using User-Defined Functions*
- Functions make the code reusable. We can declare them once and use them multiple times.
- Functions make the program easier as each small task is divided into a function.
- Functions increase readability.

----
## III. C++ Programming Default Arguments (Param)
**Why use them?**
- **Flexibility:** Allows you to call a function with fewer arguments, making it more convenient.
- **Cleaner Code:** Avoids having to create multiple "overloaded" functions (which we'll discuss next) for slightly different scenarios.

**When to use:**
- When a function parameter often has a common or standard value.
- When you want to make a function easier to use by allowing some arguments to be optional.

**How to use:**
- Assign the default value directly in the function declaration or definition: `void myFunction(int x, std::string message = "Default");
- Default arguments must be placed at the _end_ of the parameter list. You can't have a non-default argument after a default one.`


```cpp
#include <iostream>

// The 'message' parameter has a default value of "Success!"
void displayStatus(std::string status = "Success!") {
    std==cout << "Status: " << status << std==endl;
}

int main() {
    displayStatus();             // Uses the default argument: "Success!"
    displayStatus("Error!");     // Overrides the default with "Error!"
    displayStatus("Warning!");   // Overrides the default with "Warning!"
    return 0;
}
```


- If a function with default arguments is called without passing arguments, then the default parameters are used.
- If arguments are passed while calling the function, the default arguments are ignored.

*Argument Cases - Image*
![[Screenshot 2025-05-31 at 1.15.37 PM.jpg]]

1. When `temp()` is called, both the default parameters are used by the function.
2. When `temp(6)` is called, the first argument becomes `6`while the default value is used for the second parameter.
3. When `temp(6, -2.3)` is called, both the default parameters are overridden, resulting in `i = 6` and `f = -2.3`.
4. When `temp(3.4)` is passed, the function behaves in an undesired way because the second argument cannot be passed without passing the first argument.

*Example 1 - Default Arguments*
```cpp
#include <iostream>
using namespace std;

// defining the default arguments
void display(char = '*', int = 3);
// OR
void display(char c = '*', int count = 3) {
    for(int i = 1; i <= count; ++i) {
        cout << c;
    }
    cout << endl;
}

int main() {
    int count = 5;

    cout << "No argument passed: ";
    // *, 3 will be parameters
    display(); 
    
    cout << "First argument passed: ";
     // #, 3 will be parameters
    display('#'); 
    
    cout << "Both arguments passed: ";
    // $, 5 will be parameters
    display('$', count); 

    return 0;
}

void display(char c, int count) {
    for(int i = 1; i <= count; ++i)
    {
        cout << c;
    }
    cout << endl;
}
/* 
No argument passed: ***
First argument passed: ###
Both arguments passed: $$$$$
*/
```

----
### IV. C++ Function Overloading
**Why use it?**
- **Clarity:** Use the same intuitive name for actions that are conceptually similar but operate on different data.
- **Convenience:** No need to invent new names for similar functions (e.g., `printInt`, `printDouble`, `printString`).

**When to use:**
- When you have functions that perform the same general operation but need to handle different data types or different numbers of inputs.

**How to use:**
- Create multiple functions with the exact same name, but ensure their parameter lists are different (either by type, number, or order of parameters). The return type alone is not enough to overload.

```cpp
#include <iostream>
#include <string>

// Function to print an integer
void print(int num) {
    std==cout << "Printing integer: " << num << std==endl;
}

// Function to print a double
void print(double num) {
    std==cout << "Printing double: " << num << std==endl;
}

// Function to print a string
void print(std::string text) {
    std==cout << "Printing string: " << text << std==endl;
}

int main() {
    print(10);          // Calls the print(int) function
    print(3.14);        // Calls the print(double) function
    print("Hello!");    // Calls the print(std::string) function
    return 0;
}
```


Two functions can have the same name if the number and/or type of arguments passed is different. These functions having the same name but different arguments are known as overloaded functions, Example:
```cpp
// same name different arguments
int test() { }
int test(int a) { }
float test(double a) { }
int test(int a, double b) { }
```
- All these four functions are overloaded
- The return types of all these 4 functions are not the same. Overloaded functions may or may not have different return types but they must have different arguments:
```cpp
// Error code
int test(int a) { }
double test(int b){ }
```
- <font color="#c0504d">Error:</font> Both functions have the same name, the same type, and the same number of functions


*Example 1: Overloading using different types of parameters*
![[Screenshot 2025-05-31 at 1.26.16 PM.jpg]]

**Code**:
```cpp
// Example in C++
#include <iostream>
#include <string>

// Overloaded function 1: Takes an integer
void display(int num) {
    std==cout << "Displaying integer: " << num << std==endl;
}

// Overloaded function 2: Takes a string
void display(const std::string& text) {
    std==cout << "Displaying string: " << text << std==endl;
}

// Overloaded function 3: Takes a double and a character
void display(double val, char unit) {
    std==cout << "Displaying value: " << val << " " << unit << std==endl;
}

int main() {
    // Call 1: Matches display(int)
    display(100);

    // Call 2: Matches display(const std::string&)
    display("Hello World");

    // Call 3: Matches display(double, char)
    display(3.14, 'm');

    return 0;
}
```
**Explanation of the Calls:**
- **`display(100);`**: The compiler sees a single integer argument. It looks for an overloaded `display` function that accepts one integer, and it finds `void display(int num)`.
- **`display("Hello World");`**: The compiler sees a single string literal argument. It looks for an overloaded `display` function that accepts one string (or a compatible type like `const char*` which can be implicitly converted to `std==string`), and it finds `void display(const std==string& text)`.
- **`display(3.14, 'm');`**: The compiler sees two arguments: a `double` and a `char`. It looks for an overloaded `display` function that accepts these two types in that order, and it finds `void display(double val, char unit)`.


*Example 2: Overloading Using Different Number of Parameters*
![[Screenshot 2025-05-31 at 1.27.19 PM.jpg]]
**Code:**
```cpp
#include <iostream>
using namespace std;

// function with 2 parameters
void display(int var1, double var2) {
    cout << "Integer number: " << var1;
    cout << " and double number: " << var2 << endl;
}

// function with double type single parameter
void display(double var) {
    cout << "Double number: " << var << endl;
}

// function with int type single parameter
void display(int var) {
    cout << "Integer number: " << var << endl;
}

int main() {

    int a = 5;
    double b = 5.5;

    // call function with int type parameter
    display(a);

    // call function with double type parameter
    display(b);

    // call function with 2 parameters
    display(a, b);

    return 0;
}
/* 
Integer number: 5
Float number: 5.5
Integer number: 5 and double number: 5.5
*/
```
- The `display()` function is called three times with different arguments
- Depending on the number and type of arguments passed, the corresponding `display()` function is called
- The return type of all these functions is the same but that need to be the case for function overloading.

----
### V. C++ Inline Functions
inline C++ is a hint to the compiler. When you mark a function as `inline`, you're suggesting that the compiler should try to replace the function call with the actual code of the function at compile time. This can sometimes make your program faster by avoiding the overhead of a function call.

**Think of it like this:**
- **Regular function call:** The program jumps to a different place in memory to execute the function, then jumps back.
- **Inline function (if the compiler agrees):** The function's code is directly inserted where it's called, like copy-pasting the code.

**Why use them?**
- **Potential Performance Boost:** For very small, frequently called functions, it can reduce the overhead of function calls.

**When to use:**
- For **very small** functions (typically one or two lines of code).
- For functions that are called **very frequently**.

**How to use:**
- Add the `inline` keyword before the function's return type in its definition.

**Tips:**
- `inline` is just a _hint_ to the compiler. The compiler might ignore it if it thinks inlining won't be beneficial (e.g., for large functions).
- Don't use `inline` for large functions, as it can lead to "code bloat" (your program becoming larger) and actually slow things down.
- Modern compilers are often very smart about inlining, so sometimes you don't even need to use the `inline`keyword explicitly.


```cpp
#include <iostream>

// This function is marked as inline
inline int add(int a, int b) {
    return a + b;
}

int main() {
    int result = add(5, 3); // The compiler might replace this with 'int result = 5 + 3;'
    std==cout << "Result: " << result << std==endl;

    result = add(10, 20);
    std==cout << "Result: " << result << std==endl;
    return 0;
}
```


> [!Syntax]  Syntax: 
> inline returnType function_name(parameters) {...}

*Example 1 - Inline Function*
```cpp
#include <iostream>
using namespace std;

inline void displayNum(int num) {
    cout << num << endl;
}

int main() {
    // first function call
    displayNum(5);

    // second function call
    displayNum(8);

    // third function call
    displayNum(666);

    return 0;
}
// 5 8 666
```

*Example Diagram:*
![[Screenshot 2025-05-31 at 2.03.05 PM.jpg]]

Inline Function Creation and Execution 
- Created displayNum() function with single integer parameter.
- Called function three times in main() function with different arguments.
- Compiler copies function code to call location.

---
### VI. C++ Function Recursion
A **recursive function** is a function that calls itself, either directly or indirectly. It solves a problem by breaking it down into smaller, similar sub-problems until it reaches a basic case that it knows how to solve directly.

**Why use them?**
- **Elegant Solutions:** Some problems (like navigating trees, calculating factorials, or Fibonacci sequences) have very elegant and concise solutions using recursion.
- **Mimics Problem Structure:** For problems that naturally have a self-similar structure.

**When to use:**
- When a problem can be broken down into smaller instances of the same problem.
- For algorithms that naturally lend themselves to recursive definitions (e.g., tree traversals, sorting algorithms like quicksort/mergesort).

**How to use:**
1. **Base Case:** Define one or more conditions where the function stops calling itself and returns a direct result. This is crucial to prevent infinite recursion!
2. **Recursive Step:** The function calls itself with a modified input that moves closer to the base case.

**Tips:**
- **Always have a base case!** Otherwise, your program will crash due to a "stack overflow" (running out of memory for function calls).
- Recursion can sometimes be less efficient than an iterative (loop-based) solution due to the overhead of function calls.
- For every recursive solution, there's usually an iterative equivalent. Choose the one that is clearer and more efficient for your specific problem.

```cpp
#include <iostream>

// This function calculates the factorial of a number
int factorial(int n) {
    // Base case: This is when the recursion stops
    if (n == 0 || n == 1) {
        return 1;
    }
    // Recursive step: The function calls itself with a smaller problem
    else {
        return n * factorial(n - 1);
    }
}

int main() {
    int num = 5;
    std==cout << "Factorial of " << num << " is: " << factorial(num) << std==endl; // Output: 120

    num = 0;
    std==cout << "Factorial of " << num << " is: " << factorial(num) << std==endl; // Output: 1

    num = 3;
    std==cout << "Factorial of " << num << " is: " << factorial(num) << std==endl; // Output: 6
    return 0;
}
```
**How it works (for `factorial(3)`):**
1. `factorial(3)` calls `3 * factorial(2)`
2. `factorial(2)` calls `2 * factorial(1)`
3. `factorial(1)` returns `1` (base case)
4. `factorial(2)` gets `1` and returns `2 * 1 = 2`
5. `factorial(3)` gets `2` and returns `3 * 2 = 6`

> [!Syntax]  Syntax: 
> void recurse() {==recurse();==}

*How Recursion Works:*
![[Screenshot 2025-05-31 at 2.05.51 PM.jpg]]
**Recursive Function***: A function that repeats itself


*Example 1 - Factorial of a Number using Recursion*
```cpp
// Factorial of n = 1*2*3*...*n

#include <iostream>
using namespace std;

int factorial(int);

int main() {
    int n, result;

    cout << "Enter a non-negative number: ";
    cin >> n;

    result = factorial(n);
    cout << "Factorial of " << n << " = " << result;
    return 0;
}

int factorial(int n) {
    if (n > 1) {
        return n * factorial(n - 1);
    } else {
        return 1;
    }
}
```

*Example Diagram*:
![[Screenshot 2025-05-31 at 2.07.48 PM.jpg]]
Factorial() Function Overview 
- Calls itself. 
- Decreases n value by 1. 
- Returns output when n is less than 1.

### Advantages of C++ Recursion
- It makes our code shorter and cleaner.
- Recursion is required in problems concerning data structures and advanced algorithms, such as Graph and Tree Traversal.

### Disadvantages of C++ Recursion
- It takes a lot of stack space compared to an iterative program.
- It uses more processor time.
- It can be more difficult to debug compared to an equivalent iterative program.

----
 
























---
# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on:: [[C++ References & CheatSheets]]

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see:: [[C++ Basics|CBasics]]

**Target**
<!-- Link to project note or externaly published content. -->
- used_in::[[C++ Basics|CBasics]]
