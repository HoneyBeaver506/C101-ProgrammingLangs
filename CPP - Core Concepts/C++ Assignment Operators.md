---
Title: Assignment Operators
Topic: CLang Learning Curve
tags:
  - programming/clang
  - theme/Assignment
  - type/note
Created At: Monday, May 19th 2025, 4:47:38 pm
Modified At: Sunday, June 1st 2025, 8:58:19 pm
created: 2025-05-19T16:47
updated: 2025-06-29T16:24
---

---
*Table of Contents*
- [[#I. Increment & Decrement Operator|I. Increment & Decrement Operator]]
- [[#II. Assignment Operators|II. Assignment Operators]]
- [[#Arithmetic Operatores|Arithmetic Operatores]]
- [[#IV. Logical Operators|IV. Logical Operators]]
- [[#Special Operators|Special Operators]]





**Common Operators**:
- Increment - Decrement
- Arithmetic
- Logical
- Comparison
- Member Access

## I. Increment & Decrement Operator

| Operators | Meaning        | Standard English                                                                                                                                                    |
| :-------- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **++a**   | Pre-increment  | First, increase the value of 'a' by one, and then use the _new_ value of 'a' in the current operation.                                                              |
| **--a**   | Pre-decrement  | First, decrease the value of 'a' by one, and then use the _new_ value of 'a' in the current operation.                                                              |
| **a++**   | Post-increment | First, use the _current_ value of 'a' in the current operation, and then increase the value of 'a' by one. The increment happens _after_ the current value is used. |
| **a--**   | Post-decrement | First, use the _current_ value of 'a' in the current operation, and then decrease the value of 'a' by one. The decrement happens _after_ the current value is used. |


## II. Assignment Operators
Know as a compound assignment operator, which combines the mathematical operator with the assignment operator into a single step.


| Operators | Meaning                        | Standard English                                                                                                                                                                                                                                                                                                                                       | Equivalent to |
| --------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------- |
| a += b    | Addition Assignment            | “Takes the current value of a, add the value of b to it and store it back into a”                                                                                                                                                                                                                                                                      | a = a +b      |
| a = b     | Simple Assignment              | “"Assigns a value of b to the variable a”                                                                                                                                                                                                                                                                                                              | int a = b;    |
| a -= b    | Subtraction Assignment         | “Takes the current value of a, subtracts the value of b to it and store it back into a”                                                                                                                                                                                                                                                                | a = a - b     |
| a *= b    | Multiplication Assignmnt       | “Takes the current value of a, multiplies the value of b to it and store it back into a”                                                                                                                                                                                                                                                               | a = a  * b    |
| a ≠ b     | Division Assignment            | “Takes the current value of a, divides the value of b to it and store it back into a”                                                                                                                                                                                                                                                                  | a = a  / b    |
| a %= b    | Remainder Assignment           | ”Calculates the remainder of `A` divided by `B` and then assigns it to `A`”                                                                                                                                                                                                                                                                            | a = a  & b    |
| a &= b    | Bitwise AND Assignment         | “Performs a bitwise AND operation and assigns it back to A”                                                                                                                                                                                                                                                                                            | a = a & b     |
| a \|= b   | Bitwise or Assignment          | “Performs a bitwise OR operation and assigns it back to A”                                                                                                                                                                                                                                                                                             | a = a \| b    |
| a ^= b    | Bitwise XOR Assignment         | “Performs a bitwise XOR operation and assigns it back to A”                                                                                                                                                                                                                                                                                            | a = a ^ b     |
| a <≤ b    | Bitwise left Shift Assignment  | “It performs a left bit shift operation on the binary representation of `A` by `B` positions. This effectively multiplies `A` by 2 raised to the power of `B` (assuming no overflow). The result is assigned back to `A`.”                                                                                                                             | a = a << b    |
| a >≥ b    | Bitwise right shift assignment | “It performs a right bit shift operation on the binary representation of `A` by `B` positions. This effectively divides `A` by 2 raised to the power of `B`. The behavior for signed integers can be either arithmetic (sign-extending) or logical (zero-filling), depending on the compiler and the type of `A`. The result is assigned back to `A`.” | a = a >> b    |

```cpp
// a %= b
int a = 17;
int b = 5;
a %= b; // a becomes 17 % 5, which is 2
std::cout << a; // Output: 2

// a &= b
int a = 10;  // Binary: 00001010
int b = 12;  // Binary: 00001100
a &= b;      // Binary: 00001010 & 00001100 = 00001000 (decimal 8)
std::cout << a; // Output: 8

// a |= b
int a = 10;  // Binary: 00001010
int b = 12;  // Binary: 00001100
a |= b;      // Binary: 00001010 | 00001100 = 00001110 (decimal 14)
std::cout << a; // Output: 14

// a ^= b
int a = 10;  // Binary: 00001010
int b = 12;  // Binary: 00001100
a ^= b;      // Binary: 00001010 ^ 00001100 = 00000110 (decimal 6)
std::cout << a; // Output: 6

// a <<= b
int a = 5;   // Binary: 00000101
int b = 2;
a <<= b;     // Binary: 00000101 shifted left by 2 becomes 00010100 (decimal 20)
std::cout << a; // Output: 20

// a >>= b
int a = 20;  // Binary: 00010100
int b = 2;
a >>= b;     // Binary: 00010100 shifted right by 2 becomes 00000101 (decimal 5)
std::cout << a; // Output: 5

```


## Arithmetic Operatores

| Operator   | Meaning                    | Standard English                                                                                                                                                                                   |
| :--------- | :------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **+a**     | Unary plus                 | The value of 'a' (it usually doesn't change the value, but ensures it's treated as positive if not explicitly negative).                                                                           |
| **-a**     | Unary minus                | The negation of 'a' (changes the sign of 'a').                                                                                                                                                     |
| **a + b**  | Addition                   | The sum of 'a' and 'b'.                                                                                                                                                                            |
| **a - b**  | Subtraction                | The result of subtracting 'b' from 'a'.                                                                                                                                                            |
| **a * b**  | Multiplication             | The product of 'a' and 'b'.                                                                                                                                                                        |
| **a / b**  | Division                   | The quotient when 'a' is divided by 'b'.                                                                                                                                                           |
| **a % b**  | Modulo (remainder)         | The remainder after 'a' is divided by 'b'.                                                                                                                                                         |
| **-a**     | Unary minus (repeated)     | The negation of 'a' (changes the sign of 'a').                                                                                                                                                     |
| **a & b**  | Bitwise AND                | Performs a bit-by-bit AND operation between 'a' and 'b'. The result has a 1 in each bit position where both 'a' and 'b' have a 1.                                                                  |
| **a \|b**  | Bitwise OR                 |                                                                                                                                                                                                    |
| **a ^ b**  | Bitwise XOR (exclusive OR) | Performs a bit-by-bit XOR operation between 'a' and 'b'. The result has a 1 in each bit position where 'a' and 'b' have different bits (one is 0 and the other is 1).                              |
| **a << b** | Left bit shift             | Shifts the bits of 'a' to the left by 'b' positions. This effectively multiplies 'a' by 2 to the power of 'b' (assuming no overflow).                                                              |
| **a >> b** | Right bit shift            | Shifts the bits of 'a' to the right by 'b' positions. This effectively divides 'a' by 2 to the power of 'b'. The behavior for signed numbers depends on the type of shift (arithmetic or logical). |

## IV. Logical Operators

| Operator    | Meaning     | Standard English                                                                                                                        |
| :---------- | :---------- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| **!a**      | Logical NOT | This operator is true if 'a' is false, and false if 'a' is true. It inverts the boolean value of 'a'.                                   |
| **a && b**  | Logical AND | This operator is true if and only if both 'a' is true _and_ 'b' is true. If either 'a' or 'b' (or both) are false, the result is false. |
| **a \|\|b** | Disjunction | "'a' or 'b'", "'a' is true or 'b' is true (or both)".                                                                                   |



## Special Operators
[static_cast](https://en.cppreference.com/w/cpp/language/static_cast "cpp/language/static cast") converts one type to another related type  
[dynamic_cast](https://en.cppreference.com/w/cpp/language/dynamic_cast "cpp/language/dynamic cast") converts within inheritance hierarchies  
[const_cast](https://en.cppreference.com/w/cpp/language/const_cast "cpp/language/const cast") adds or removes [cv](https://en.cppreference.com/w/cpp/language/cv "cpp/language/cv")-qualifiers  
[reinterpret_cast](https://en.cppreference.com/w/cpp/language/reinterpret_cast "cpp/language/reinterpret cast") converts type to unrelated type  
[C-style cast](https://en.cppreference.com/w/cpp/language/explicit_cast "cpp/language/explicit cast") converts one type to another by a mix of static_cast, const_cast, and reinterpret_cast  
[new](https://en.cppreference.com/w/cpp/language/new "cpp/language/new") creates objects with dynamic storage duration  
[delete](https://en.cppreference.com/w/cpp/language/delete "cpp/language/delete") destructs objects previously created by the new expression and releases obtained memory area  
[sizeof](https://en.cppreference.com/w/cpp/language/sizeof "cpp/language/sizeof") queries the size of a type  
[sizeof...](https://en.cppreference.com/w/cpp/language/sizeof... "cpp/language/sizeof...") queries the size of a [pack](https://en.cppreference.com/w/cpp/language/pack "cpp/language/pack") (since C++11)  
[typeid](https://en.cppreference.com/w/cpp/language/typeid "cpp/language/typeid") queries the type information of a type  
[noexcept](https://en.cppreference.com/w/cpp/language/noexcept "cpp/language/noexcept") checks if an expression can throw an exception (since C++11)  
[alignof](https://en.cppreference.com/w/cpp/language/alignof "cpp/language/alignof") queries alignment requirements of a type (since C++11)








# Back Matter

**Source**
<!-- Always keep a link to the source- --> 
- based_on:: [[C++ Conditionals]]

**References**
<!-- Links to pages not referenced in the content. see: [[related note]] because <reason> -->
- see==CPPReference==[Assignment operators - cppreference.com](https://en.cppreference.com/w/cpp/language/operator_assignment)
- see==CPPReference==[Move assignment operator - cppreference.com](https://en.cppreference.com/w/cpp/language/move_assignment)

**Terms**
<!-- Links to definition pages. -->
- Assignment Operators
- Simple Assignment
- Subtraction
- Multiplication
- Division
- Remainder
- Bitwise AND
- bitwise OR
- bitwise XOR
- Bitwise left shift
- Bitwise Right Shift

**Target**
<!-- Link to project note or externaly published content. -->
- used_in::

---
**Tasks**
<!-- What remains to be done with this note? --> 
- 

**Questions**
<!-- What remains for you to consider? --> 
- question::
