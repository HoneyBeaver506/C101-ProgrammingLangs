---
Title: "202505281842"
Topic: CLang Learning Curve
tags:
  - programming/clang
  - type/note
  - type/sketchnote
aliases:
  - CBasics
updated: 2025-06-03T09:53
created: 2025-03-04T21:39
template_type: Note
template_version: "1.35"
Created At: Wednesday, May 28th 2025, 6:42:33 pm
Modified At: Tuesday, June 3rd 2025, 9:53:36 am
---

*Table of Contents*
- [[#Keywords|Keywords]]
- [[#C++ Identifiers|C++ Identifiers]]
- [[#Variables|Variables]]
- [[#Constants|Constants]]
	- [[#Constants#CONST EXPRESSION|CONST EXPRESSION]]
- [[#Literals|Literals]]
	- [[#Literals#C++ Modified Data Types List|C++ Modified Data Types List]]
- [[#Type Modifiers|Type Modifiers]]

# 202505281842 - C++ Basics
> [!Summary]
> **Topics to Cover:**
> - Comments
> - Variables, Literals & Constants
> - Data Types
> - Basic Input / Output
> - Basic Operators

# C++ Comments
Comments are hints that are added to the code to make it easier to read and understand. They also work to temporarily disable a line of code.
- `//` single line comments
- `/**/` Multi-Lined Comments


# C++ Keywords and Identifiers

## Keywords
Keywords are predefined words that have special meanings in the compiler. For example `int` is a keyword meaning Integer. This holds a special meaning because it is a data type used by c++.

| `alignas`    | `decltype`     | `namespace`        | `struct`       |
| ------------ | -------------- | ------------------ | -------------- |
| `alignof`    | `default`      | `new`              | `switch`       |
| `and`        | `delete`       | `noexcept`         | `template`     |
| `and_eq`     | `do`           | `not`              | `this`         |
| `asm`        | `double`       | `not_eq`           | `thread_local` |
| `auto`       | `dynamic_cast` | `nullptr`          | `throw`        |
| `bitand`     | `else`         | `operator`         | `true`         |
| `bitor`      | `enum`         | `or`               | `try`          |
| `bool`       | `explicit`     | `or_eq`            | `typedef`      |
| `break`      | `export`       | `private`          | `typeid`       |
| `case`       | `extern`       | `protected`        | `typename`     |
| `catch`      | `false`        | `public`           | `union`        |
| `char`       | `float`        | `register`         | `unsigned`     |
| `char16_t`   | `for`          | `reinterpret_cast` | `using`        |
| `char32_t`   | `friend`       | `return`           | `virtual`      |
| `class`      | `goto`         | `short`            | `void`         |
| `compl`      | `if`           | `signed`           | `volatile`     |
| `const`      | `inline`       | `sizeof`           | `wchar_t`      |
| `constexpr`  | `int`          | `static`           | `while`        |
| `const_cast` | `long`         | `static_assert`    | `xor`          |
| `continue`   | `mutable`      | `static_cast`      | `xor_eq`       |
## C++ Identifiers
Identifiers are special names given to variables, data types, classes, etc. 
```cpp
int money; // int (keyword) money (identifier)
double AccountBalance;
```

*Rules for naming identifiers
- Identifiers can be composed of letters, digits, and the underscore character.
- It has no limit on name length.
- It must begin with either a letter or an underscore.
- It is case-sensitive.
- We cannot use keywords as identifiers

**Naming Cases:**
- Camel Case: Start the name with a small letter. If the name has multiple words, capitalize the rest.
- Snake case: Using underscore to separate the name into two pieces. Commonly used in python EX:`last_name`
- Kebab Case: Same as snake case but instead of using an underscore, we use a hyphen. EX: `last-name`
- Pascal Case: Names with this case have their starting letters capitalied. EX: `LastName`


# C++ Variables, Literals & Constants
## Variables
Variables are basically storage areas, where a value is stored. A unique ID is given to identify and call the variable name
```cpp
int age = 14; // int (keyword) age (id) = (assignment Operator) 14; (Value)
age = 17; // Changes the value of "age" to 17
```
- Variables, functions and so much more have to end with a `;`
- Variables can be changed simply by calling the variable identifier and assigning it a new value

*Rules for naming a variable*
1. A variable name can only have alphabets, numbers, and the underscore `_`.
2. A variable name cannot begin with a number.
3. It is a preferred practice to begin variable names with a lowercase character. For example, name is preferable to Name.
4. A variable name cannot be a [keyword](https://www.programiz.com/cpp-programming/keywords-identifiers). For example, `int` is a keyword that is used to denote integers.
5. A variable name can start with an underscore. However, it's not considered a good practice.

**Scope of C++ Variables**
The scope of a variable refers to the region of a program where that variable can be accessed. In C++, there are two types of scopes:
- **Local Scope:** These are the variables that are declared within a function or block having local scope. Thus, they can only be accessed from within that function or block.
- **Global Scope:** Those variables that are declared outside all functions have global scope. Hence, they can be accessed from any part of the program.
- **Static Variables:** Static variables in C++ have a limited scope for the function where they are initialised and retain their value even after function execution is completed.
## Constants
Constants are basically variables with unchangeable/mutable values. This means that their value cannot be changed or it will produce an error.
```cpp
const int light_speed =  299792458;
// const (keyword) int (data type) light_speed (id) = 2997924..; (value)
light_speed = 2500;
// Output: ERROR! light_speed is a constant.
```
- A constant can be created with the `#define` keyword as well


*Const References*
We can also make references using the `const` keyword. There are different types of such references with different behaviors. These are

|Reference Type|Description|
|---|---|
|Constant reference to a constant variable|Both the variable and the reference are constant.|
|Constant reference to a non-constant variable|The variable is non-constant but the reference is constant.|
```cpp
//Const Reference to a Const Variable
#include <iostream>
using namespace std;

int main() {

    // initialize a constant PI  
    const double PI = 3.14;
  
    // create a read-only reference to PI
    const double &PI_REF = PI;
  
    cout << "PI: " << PI;
    cout << "\nPI_REF: " << PI_REF;
  
    return 0;
}
```
- Ampersand (&) is used in code to reference another variable


*Consts and Pointers*
Like with references, we can also make different types of pointers using the `const` keyword. These are:

|Pointer Type|Description|
|---|---|
|Pointers to a Const|The pointer is a non-constant but the value being pointed to is a constant.|
|Const Pointer|The pointer is a constant but the value being pointed is a non-constant.|
|Const Pointer to a Const|Both the pointer and the value being pointed are constant.|
**Pointers to a Const**
A pointer to a constant is a pointer variable that points to a constant variable.
- Allows to change the address the pinter is pointing to, & does not allow the change of the value stored inside the constant var
```cpp
#include <iostream>
using namespace std;

int main() {

    // initialize a constant TOTAL_MONTHS  
    const int TOTAL_MONTHS = 12;
 
    // MONTHS_PTR is a pointer to an int const
    const int *MONTHS_PTR = &TOTAL_MONTHS;
  
    cout << "TOTAL_MONTHS: " << TOTAL_MONTHS << endl;
    cout << "*MONTHS_PTR: " << *MONTHS_PTR << endl;

    // create another int constant
    const int HALF_MONTHS = 6;

    // MONTHS_PTR now points to HALF_MONTHS
    MONTHS_PTR = &HALF_MONTHS;

    cout << endl;
  
    cout << "HALF_MONTHS: " << HALF_MONTHS << endl;
    cout << "*MONTHS_PTR: " << *MONTHS_PTR;

    return 0;
}
/* Output
TOTAL_MONTHS: 12
*MONTHS_PTR: 12

HALF_MONTHS: 6
*MONTHS_PTR: 6
*/
```

**Const Pointer**
A pointer in which we can change the value pointed by the pointer but not the variable it points to.

```cpp
#include <iostream>
using namespace std;

int main() {
    
    string country1 = "Nepal";
    string country2 = "USA";
  
    cout << "Initially, country1: " << country1 << endl;
  
    // PTR1 is a const pointer to country1
    string *const PTR1 = &country1;
  
    // change the value of country1 using PTR1
    *PTR1 = country2;
  
    cout << "Finally, country1: " << country1;
  
    return 0;
}
/* output:
Initially, country1: Nepal
Finally, country1: USA
*/
```

**Const Pointer to Const**
A pointer through which we can neither change the variable it points to nor its value.
```cpp
#include <iostream>
using namespace std;

int main() {
    
    // create a const variable
    const string COUNTRY1 = "Nepal";
    
    // create a const pointer to const
    const string *const PTR = &COUNTRY1;

    cout << *PTR;
  
    return 0;
}
// Output: Nepal
```

### CONST EXPRESSION
`constexpr` are values that cannot be changed but be evaluated at compile time.

```cpp
// declare a function as constexpr
constexpr int add_numbers(int a, int b) {...}

// declare a variable as constexpr
constexpr int sum = add_numbers(660, 6);
```

**Const Member Functions**
Ensure that the data members of an object are not changed. Syntax:
> [!Example]+ 🔖 Syntax
> return_type function_name() const {
> }

*Properties of a const member function*:
- We cannot change the values of the member variables inside a const member function.
- We can only call const member functions from a **constant object**.
```cpp
#include <iostream>
using namespace  std;

class Rectangle {
private:
    int breadth, length;

public:
    Rectangle(int length, int breadth){
        this->breadth = breadth;
        this->length = length;
    }

     // constant member function
    int get_area() const {
        return length * breadth;
    }

    // non-constant member function
    int get_perimeter() {
        return 2 * (length + breadth);
    }
};

int main() {

    // create a const Rectangle object
    const Rectangle RECT = Rectangle(7, 6);

    // call the const member function
    cout << "Area: " << RECT.get_area() << endl;

    return 0;
}
```

## Literals
Data used to represent fixed value/data types.
*Types of Literals*:
1. <font color="#c0504d">Integer</font>: A numeric literal associated with numeric numbers without any fractional or exponent part to them.
	1. Decimal (Base 10): 0, -9, 22, etc
	2. Octal (Base 8): 021, 227, 033, etc
	3. Hexadecimal (Base 16): 0x7f, 0x2a, 0x521, etc
2. <font color="#c0504d">Floating Point Literals</font>: Covers numerical numbers that cover factorial and exponent forms.
	1. -2.0
	2. 0.0000234
	3. -0.22E-5

> **note** E-5 = 10-5

1. <font color="#c0504d">Characters</font>: Created by enclosing single characters into single quotation marks. EX: 'A', 'C', '{'
2. <font color="#c0504d">String Literals</font> Created by enclosing a sequence of characters in double-quotation marks.
*EXAMPLES:*

| "good"             | String Constant                       |
| ------------------ | ------------------------------------- |
| ""                 | null string constant                  |
| " "                | String Constant with six white spaces |
| "Earth is Round\n" | "Prints string with a new line"       |

- **Primitive (Fundamental) Data Types:**
    These are the basic data types that are built into the C++ language.
    - `int`: Used to store whole numbers (integers) without decimal points, for example: 10, -5, 0.
    - `float`: Used to store single-precision floating-point numbers (numbers with decimal points), for example: 3.14, -2.5, 0.0.
    - `double`: Used to store double-precision floating-point numbers, which can hold more decimal places than `float`.
    - `char`: Used to store single characters, such as letters, numbers, or symbols, for example: 'a', '5', '$'.
    -  `w_char` - Represents wide characters. It is used to represent characters that require more memory to represent them than a single `char`.
        - `wchar_t test = L'ם'  // storing Hebrew character;`
    - `bool`: Used to store boolean values, which can be either `true` or `false`.
    - `void`: Represents the absence of a type. It is often used as the return type of functions that do not return a value.

| **Primary Data Types** | **Derived Data Types** | **User-Defined Data Types** |
| ---------------------- | ---------------------- | --------------------------- |
| int                    | Arrays                 | Structures (struct)         |
| char                   | Pointers               | Unions (union)              |
| bool                   | References             | Enumerations (enum)         |
| float                  | Functions              | Classes (class)             |
| double                 |                        |                             |
| void                   |                        |                             |

### C++ Modified Data Types List

|Data Type|Size (in Bytes)|Meaning|
|---|---|---|
|`signed int`|4|used for integers (equivalent to `int`)|
|`unsigned int`|4|can only store positive integers|
|`short`|2|used for small integers (range **-32768 to 32767**)|
|`unsigned short`|2|used for small positive integers (range **0 to 65,535**)|
|`long`|at least 4|used for large integers (equivalent to `long int`)|
|`unsigned long`|4 or 8|used for large positive integers or 0 (equivalent to `unsigned` `long int`)|
|`long long`|8|used for very large integers (equivalent to `long long int`).|
|`unsigned long long`|8|used for very large positive integers or 0 (equivalent to `unsigned long long int`)|
|`long double`|8, 12, or 16|used for large floating-point numbers|
|`signed char`|1|used for characters (guaranteed range **-127 to 127**)|
|`unsigned char`|1|used for characters (range **0 to 255**)|

----
# C++ Input Output
To input or output data, C++ needs the ==iostream== header included at the start of the file. This headers allows for outputting and inputting data with its keywords: `cin` and `cout`.

> [!Example] 🔖 COUT 
> (standard library) std::cout (stream-output) << (output operator) "text to Print"

```cpp
//Output to terminal
std::cout << "This is a C++ Program"
// Output:: This is a C++ Program

#include <iostream>
using namespace std;

int main() {
    int num1 = 70;
    double num2 = 256.783;
    char ch = 'A';

    cout << num1 << endl;    // print integer
    cout << num2 << endl;    // print double
    cout << "character: " << ch << endl;    // print char
    return 0;
}
```
- The `std::endl;` operator is used to insert a new line into the output
- the `<<` can be used more then once inside of a cout statement to print different things in a single statement.

> [!Example] 🔖 CIN Syntax
> (standard library) std::cin (Stream-input) >> (Input Operator) variable_name;
> Basically means that we are taking the input of a keyboard and inputing it into a variable.

*To create an input*
1. Create a variable in which to store the input. `int num;`
2. Create a label with the `cout` operator. (e.g., "Enter an Interger?")
3.  Take the input with the `cin` operator and store it into the `num` variable. (`cin >> num;)

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    int a;
    cout << "Enter an integer: ";
    cin >> num;   // Taking input
    cin >> a >> num; // Taking multiple inputs
    cout << "The number is: " << num;
    return 0;
}
/* output:
Enter an integer: 70
The number is: 70
*/
```


## Type Modifiers
| Data Type            | Size (in Bytes) | Meaning                                                                                      |
| -------------------- | --------------- | -------------------------------------------------------------------------------------------- |
| `signed int`         | 4               | Used for integers (equivalent to `int`). Range: **-2,147,483,648** to **2,147,483,647**.     |
| `unsigned int`       | 4               | Can only store non-negative integers. Range: **0** to **4,294,967,295**.                     |
| `short`              | 2               | Used for small integers.  <br>Range: **-32768** to **32767**                                 |
| `long`               | at least 4      | Used for large integers.  <br>Equivalent to `long int`.                                      |
| `unsigned long`      | 4               | Used for large positive integers or **0**.  <br>Equivalent to `unsigned long int`.           |
| `long long`          | 8               | Used for very large integers.  <br>Equivalent to `long long int`.                            |
| `unsigned long long` | 8               | Used for very large positive integers or **0**.  <br>Equivalent to `unsigned long long int`. |
| `long double`        | 8               | Used for large floating-point numbers.                                                       |
| `signed char`        | 1               | Used for characters.  <br>Guaranteed range **-127** to **127**.                              |
| `unsigned char`      | 1               | Used for characters.  <br>Range **0** to **255**.                                            |


# C++ Operators
| **Operator Type**              | **Operators**                              | **Description**                                                                                |
| ------------------------------ | ------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| Arithmetic Operators           | +, -, *, /, %                              | Perform basic arithmetic operations (addition, subtraction, multiplication, division, modulus) |
| Relational Operators           | ==, !=, >, <, >=, <=                       | Compare two values and return a boolean result (true or false)                                 |
| Logical Operators              | &&, \|, !                                  | Perform logical operations (AND, OR, NOT)                                                      |
| Bitwise Operators              | &, \|, ^, ~,<<, >>                         | Perform operations on bits and bit patterns                                                    |
| Assignment Operators           | =, +=, -=, *=, /=, %=, <<=, >>=, &=, ^=, ` | Assign values to variables and modify them                                                     |
| Increment/Decrement Operators  | ++, —                                      | Increase or decrease the value of a variable by one                                            |
| Conditional (Ternary) Operator | ? :                                        | Return one of two values depending on a condition                                              |
| Comma Operator                 | ,                                          | Separate two or more expressions                                                               |
| Member Access Operators        | . , ->                                     | Access members of a class or structure                                                         |
| Pointer Operators              | *, &                                       | Operate on pointer variables                                                                   |
| Type Cast Operator             | (type)                                     | Convert a variable from one type to another                                                    |
| sizeof Operator                | sizeof                                     | Return the size of a data type or variable                                                     |
| Other Operators                | ::, .*, ->*, new, delete                   | Miscellaneous operators for various purposes                                                   |
Assignment Operators:
|"=="|Is Equal To|`3 == 5` gives us **false**|
|`!=`|Not Equal To|`3 != 5` gives us **true**|
|`>`|Greater Than|`3 > 5` gives us **false**|
|`<`|Less Than|`3 < 5` gives us **true**|
|`>=`|Greater Than or Equal To|`3 >= 5` give us **false**|
|`<=`|Less Than or Equal To|`3 <= 5` gives us **true**|


# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on:: Self Made

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see::  [[C++ Cheat Sheet & Quick Reference.pdf]]
- see::[[C++ Variables]] -> More in depth information

